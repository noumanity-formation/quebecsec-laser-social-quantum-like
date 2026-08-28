# Spécification technique — simulateur `solaser`

**Document de conception** — état : proposé, 2026-08-28.
Répond à ANL-006. À lire avec `01-exigences.md` et `02-architecture.md`.

Unités : `ħ = 1`, temps en **jours**, tous les taux en **jour⁻¹**.
Campagne : 39 jours, du 27 août au 5 octobre 2026.

---

## 1. Dimensions et notations

| Symbole | Valeur | Sens |
|---|---|---|
| `J` | 11 | champs (ANL-001) |
| `P` | 5 | partis : CAQ, PQ, PLQ, QS, PCQ |
| `C` | 6 | contextes (enjeux) |
| `d_j` | 10 | dimension d'un champ : `C² ⊗ C^P` |
| `T` | 39 | durée de la campagne, en jours |
| `Δt` | 0,01 | pas de temps, en jours (≈ 15 min) |
| `n_pas` | 3 900 | nombre de pas |

**Contextes retenus** (FND-022) : `c₀` économie et coût de la vie ;
`c₁` identité, langue et laïcité ; `c₂` santé et services publics ;
`c₃` environnement et énergie ; `c₄` souveraineté et rapport au Canada ;
`c₅` intégrité et gouvernance.

**Ordonnancement des amplitudes.** L'état d'un champ est un vecteur de dix
amplitudes, `ψ_j[m·P + p]` avec `m ∈ {0,1}` (0 = `|g⟩`, 1 = `|e⟩`) et
`p ∈ 0..P`. Les indices `0..5` forment le bloc `|g⟩`, les indices `5..10` le
bloc `|e⟩`. **Tout le code dépend de cette convention ; elle doit être
documentée à l'endroit où elle est définie.**

---

## 2. Construction des observables de contexte

### 2.1 Depuis les positions des partis

Pour chaque contexte `c`, la configuration fournit un vecteur réel
`x_c ∈ R^P` : la position de chaque parti sur cet enjeu, dérivée de la matrice
d'ANL-003 et de FND-022.

**Correspondance proposée** de la notation qualitative d'ANL-003 vers un réel :

| Notation | Valeur |
|---|---|
| `++` | +2 |
| `+` | +1 |
| `0` | 0 |
| `−` | −1 |
| `−−` | −2 |
| `≠` | traité à part — voir §2.3 |

**Cette correspondance est une décision de modélisation non triviale, et elle
est portée à l'attention de l'humain dans PLN-001.** Elle transforme un
jugement qualitatif en nombre, et tout ce qui suit en dépend.

### 2.2 L'observable

On pose l'observable du contexte `c` comme une matrice symétrique réelle
`P × P` :

> `Q_c = x_c x_cᵀ / ‖x_c‖² + β_c · S_c`

où le premier terme est un projecteur de rang 1 sur la direction des positions,
et `S_c` une matrice symétrique de structure (par défaut nulle) permettant
d'enrichir le spectre lorsqu'un enjeu comporte plus de deux positions pures.
`β_c` est configurable, nul par défaut.

`U_c` est la matrice des vecteurs propres de `Q_c`, `D_c` le vecteur de ses
valeurs propres. La diagonalisation se fait **une fois**, au chargement.

**Vérifications obligatoires au chargement** : `Q_c` symétrique à `1e-12`,
`U_c` unitaire à `1e-12`, `U_c D_c U_cᵀ = Q_c` à `1e-10`.

### 2.3 Les contestations de nomos

ANL-003 note `≠` les propositions qui contestent la règle du champ plutôt que
d'y jouer. **Elles ne sont pas une position sur un enjeu** et ne peuvent donc
pas entrer dans `x_c`. Traitement retenu : elles alimentent le terme `H_pref`
(§4.4) via une composante distincte, et non l'observable de contexte.
*Décision assumée, et discutable : elle revient à dire qu'une contestation de
règle agit sur la préférence sans changer la base de mesure. L'alternative —
qu'une contestation de nomos change `U_c` lui-même — est plus fidèle à ANL-004
mais n'a pas de formulation simple. Reportée hors version 1.*

### 2.4 Les commutateurs

> `κ_{c,c'} = ‖[Q_c, Q_{c'}]‖_F / (‖Q_c‖_F · ‖Q_{c'}‖_F)`

Norme de Frobenius, normalisée pour être sans dimension et comparable entre
paires. **`κ = 0` : contextes compatibles. `κ` grand : contextes incompatibles.**

C'est la sortie de `solaser commut`, et c'est le premier résultat vérifiable du
dépôt : elle confirme ou réfute la famille commutante et l'incompatibilité
irréductible posées en ANL-004 §6 et reprises en ANL-005 §8.

---

## 3. Paramètres par champ

Configuration `config/champs.toml`, une entrée par champ, valeurs de départ
issues d'ANL-006 §4.5 — **toutes marquées `E` sauf `M_j`, marquée `D`**.

```toml
[[champ]]
nom          = "journalistique"
m_eff        = { value = 1_590_000, provenance = "D", source = "ANL-004 §4" }
omega        = { value = 2.0,   provenance = "E", source = "ANL-006 §4.5 — cadence de reprise" }
omega_drive  = { value = 2.0,   provenance = "E", source = "scénario" }
rabi_max     = { value = 1.5,   provenance = "E", source = "ANL-006 §4.5 — atteignabilité" }
gamma_down   = { value = 0.10,  provenance = "E", source = "ANL-006 §4.5 — démobilisation" }
gamma_phi    = { value = 1.5,   provenance = "E", source = "ANL-006 §4.5 — déphasage" }
k_moyen      = { value = 40.0,  provenance = "E", source = "ANL-001 — densité interne" }
tau_base     = { value = 0.66,  provenance = "V", source = "participation 2022 : 66,05 %" }
rwa          = true
```

**Bornes de validation** : `omega > 0` ; `rabi_max ≥ 0` ; `gamma_down ≥ 0` ;
`gamma_phi ≥ 0` ; `0 ≤ tau_base ≤ 1` ; `m_eff > 0`.

**Contrainte globale vérifiée au chargement** :
`Σ_j m_eff = 6 400 000 ± 1 %` — l'électorat inscrit vérifié (FND-020).
Échec explicite sinon.

**Avertissement RWA** : si `rwa = true` et `rabi_max ≳ omega`, le validateur
émet un avertissement nommant le champ. *ANL-006 identifie le bureaucratique
(`Ω=0,4`, `ω=0,07`) et l'académique (`Ω=0,3`, `ω=0,03`) comme les cas où
l'approximation séculaire n'est pas justifiée.*

---

## 4. L'hamiltonien

> `H(t) = H₀ + H_ctx(t) + H_pump(t) + H_pref(t) + H_int`

**Note par rapport à ANL-006.** L'analyse en énonçait quatre termes. La
spécification en ajoute un cinquième, `H_pref`, parce qu'un terme de contexte
diagonal dans sa propre base ne fait qu'ajouter des phases : il produit de
l'interférence dans la base des partis, mais **aucune dérive nette** vers un
parti. `H_pref` porte l'offre différenciée des partis aux champs — c'est-à-dire
le pompage multi-couleur d'ANL-005 dans sa dimension *préférentielle*, là où
`H_pump` en porte la dimension *mobilisatrice*. **Cet ajout est une décision de
la spécification, pas un contenu d'ANL-006, et il doit être signalé comme
tel.**

### 4.1 `H₀` — énergie propre (enjeu existentiel)

> `H₀ = Σ_j (ω_j / 2) σ_j^z ⊗ I_P`

Application : multiplier le bloc `|g⟩` par `e^{+i ω_j Δt/2}` et le bloc `|e⟩`
par `e^{−i ω_j Δt/2}`. Coût : 10 multiplications complexes par champ.

### 4.2 `H_ctx` — les contextes

> `H_ctx(t) = Σ_c λ_c(t) · I_2 ⊗ Q_c`

`λ_c(t)` est la **saillance du contexte au jour `t`** : la seule fonction du
modèle qui soit observable en pratique, par la part du contexte dans la
couverture médiatique quotidienne. Fournie par le scénario, en escalier ou
interpolée.

**Application — la rotation de contexte, cœur du schéma :**

```
pour chaque bloc b ∈ {|g⟩, |e⟩} :          # deux tranches de 5 amplitudes
    φ ← U_cᵀ · ψ[b]                        # produit 5×5
    pour k ∈ 0..P :
        φ[k] ← φ[k] · exp(−i · λ_c(t) · D_c[k] · Δt)
    ψ[b] ← U_c · φ                         # produit 5×5
```

Coût : 4 produits 5×5 par champ et par contexte. Avec `J=11`, `C=6` :
264 produits 5×5 par pas — négligeable.

### 4.3 `H_pump` — pompage multi-couleur

**Forme complète :**

> `H_pump(t) = Σ_j Ω_j(t) · cos(ω_j^d t + φ_j) · (σ_j^+ + σ_j^-) ⊗ I_P`

**Forme séculaire (RWA), utilisable si `Ω_j ≪ ω_j` :**

> `H_pump^RWA(t) = Σ_j (Ω_j(t)/2) · (σ_j^+ e^{−i Δ_j t} + h.c.) ⊗ I_P`,
> avec `Δ_j = ω_j^d − ω_j`

Application : rotation `2 × 2` sur chaque paire d'amplitudes
`(ψ[p], ψ[P+p])`, `p ∈ 0..P`. L'exponentielle d'une matrice `2×2` hermitienne
se calcule en forme close — pas de diagonalisation numérique.

`φ_j` est la **phase de la couleur `j`** : c'est le calendrier relatif des
pompages. Des phases verrouillées produisent l'analogue d'un blocage de modes —
une impulsion brève plutôt qu'une émission continue. **C'est le paramètre
qu'ANL-005 désigne comme critique et que ce programme rend calculable.**

**Condition de résonance implémentée** : le couplage effectif décroît en
`Ω_j² / (Ω_j² + Δ_j²)`. Le programme expose ce facteur en diagnostic, afin que
l'on voie quand un champ est hors résonance.

### 4.4 `H_pref` — l'offre différenciée aux champs

> `H_pref(t) = Σ_j |e_j⟩⟨e_j| ⊗ A_j(t)`,
> `A_j(t) = κ_j(t) · ( |v_j⟩⟨u| + |u⟩⟨v_j| )`

où `|u⟩ = (1,…,1)/√P` est l'état uniforme et `|v_j⟩ ∝ Σ_p a_{jp} |p⟩` le
vecteur d'offre du champ `j`, construit depuis la matrice d'ANL-003 par la
correspondance de §2.1. `A_j` est hermitienne par construction.

**Le terme n'agit que sur le bloc `|e⟩`** : un champ non mobilisé ne se laisse
pas déplacer en préférence. C'est la traduction directe de la thèse d'ANL-004
selon laquelle le message ne crée pas la charge mais la libère.

### 4.5 `H_int` — couplage inter-champ

> `H_int = Σ_{j<k} J_{jk} σ_j^z σ_k^z + Σ_{j<k} g_{jk} (σ_j^+ σ_k^- + h.c.)`

`J_{jk}` est construit depuis la matrice de recoupement d'ANL-001, normalisée :

> `J_{jk} = J₀ · s_{jk} · O_{jk} / min(M_j, M_k)`

où `O_{jk}` est l'effectif du recoupement et `s_{jk} ∈ {+1, −1}` le signe de
l'alignement. **`s = −1` pour `{syndical, bureaucratique}` contre
`{économique}`** — c'est l'incompatibilité irréductible d'ANL-004 encodée dans
le hamiltonien.

En mode champ moyen, `σ_k^z` est remplacé par sa moyenne `⟨σ_k^z⟩`, ce qui rend
le terme diagonal et son application triviale. En mode cluster, il est exact
sur les champs du cluster.

`g_{jk}` produit la **compétition de modes** identifiée en ANL-005 §9.1.

---

## 5. Dissipation

Opérateurs de saut, par champ :

> `L_j^↓ = √γ_j · σ_j^- ⊗ I_P`  (relaxation : démobilisation)
> `L_j^φ = √(Γ_j/2) · σ_j^z ⊗ I_P`  (déphasage : perte de cohérence)

**Algorithme MCWF, par pas :**

1. Propager avec `H_eff = H(t) − (i/2) Σ_k L_k† L_k` (non hermitien).
2. Calculer `δp = 1 − ‖ψ‖²`.
3. Tirer `r ~ U(0,1)`. Si `r > δp` : renormaliser, continuer.
4. Sinon : choisir `k` avec probabilité `‖L_k ψ‖² / Σ ‖L_m ψ‖²`, appliquer
   `ψ ← L_k ψ / ‖L_k ψ‖`.

**Contrainte** : `δp ≪ 1` à chaque pas, sinon le pas est trop grand. Le
programme vérifie `δp < 0,01` et avertit sinon.

`Γ_j` est la **température sociale** de FND-021, ici dotée d'une définition
opératoire : le taux auquel un champ perd la cohérence de son cadrage.

---

## 6. Mesure du vote

### 6.1 Question de l'urne

Si le scénario déclare une question de l'urne effective `a`, l'observable
mesuré est `V^{(a)} = U_a† V U_a`. En pratique, on applique `U_a†` à l'état
avant projection. **C'est le modèle en une ligne : on projette toujours dans la
base des partis, mais l'état a été tourné par la question de l'urne.**

### 6.2 Préférence conditionnelle

> `P(p | j) = |ψ_j[p]|² + |ψ_j[P+p]|²`

sommée sur les deux blocs après normalisation — la préférence existe que le
champ soit mobilisé ou non ; c'est la participation qui décide s'il vote.

### 6.3 Participation

> `τ_j(T) = τ_j⁰ + (1 − τ_j⁰) · (1 + ⟨σ_j^z⟩_T) / 2`

avec `⟨σ_j^z⟩ = Σ_p (|ψ_j[P+p]|² − |ψ_j[p]|²)`, borné à `[−1, +1]`.

### 6.4 Agrégation

> `V_p = Σ_j M_j · τ_j(T) · P(p | j)`,  puis parts `V_p / Σ_q V_q`

**Vérification obligatoire** : `Σ_j M_j` égale l'électorat déclaré à 1 % près.

### 6.5 Ce qui n'est pas fait

La conversion en sièges exige les résultats de 2022 transposés sur la carte à
127 circonscriptions. **Hors périmètre de la version 1** ; le programme produit
des parts de vote agrégées.

---

## 7. Diagnostics

Exportés à cadence configurable :

| Diagnostic | Formule | Ce qu'il sert |
|---|---|---|
| Norme | `‖Ψ‖` | contrôle numérique (ENF-2.1) |
| Inversion | `⟨σ_j^z⟩` | seuil de lasing atteint ou non |
| **Cohérence intra-champ** | `2·\|Σ_p ψ_j[p]* ψ_j[P+p]\|` | **signature de détection d'ANL-005 §10** |
| Facteur de résonance | `Ω_j²/(Ω_j²+Δ_j²)` | champ en résonance ou non |
| Énergie | `⟨H(t)⟩` | contrôle de la dynamique |
| Sauts | compteur par champ | intensité de la dissipation |

**La cohérence intra-champ est le diagnostic le plus important du programme** :
c'est elle qui distingue un lasing multi-couleur — cohérence qui monte à
l'intérieur de chaque champ sans convergence entre champs — d'une campagne
large ordinaire.

---

## 8. Banc de comparaison classique

Sous-commande `solaser sim --model ising`.

> `H(s₁…s_N) = −J Σ_{ij} A_{ij} s_i s_j − Σ_i h_i s_i`

Paramètres : température `T` (volatilité sociale), champs de campagne `h⁺`,
`h⁻`, proportion `p`. Valeurs de départ issues de la calibration publiée :
`T* = 0,922`, seuil critique ≈ 1,83 M$ (Korbel, Dahdoul et Thurner, mars 2026).

Simulation par Metropolis ou Glauber sur le même graphe de champs. Métriques de
comparaison identiques : parts de vote, participation, et — pour ce que le
modèle classique peut en dire — polarisation.

**Critère de décision** : à nombre de paramètres comparable et hors
échantillon, si le modèle quantum-like ne fait pas mieux, il n'apporte rien, et
le rapport doit le dire.

---

## 9. Format de sortie

CSV (ou Parquet), une ligne par jeu de paramètres et par trajectoire agrégée,
avec un en-tête de métadonnées :

```
# solaser vX.Y.Z
# config_sha256 = …
# seed = …
# date = 2026-…
# provenance: omega_journalistique=E, m_eff_journalistique=D, tau_base=V, …
jeu,traj,part_caq,part_pq,part_plq,part_qs,part_pcq,tau_moyen,
coherence_max_journalistique,…,n_sauts,norme_finale
```

Le **rapport de provenance** est produit séparément par `--provenance-report` :
la liste complète des paramètres, leur valeur, leur marque et leur source.
