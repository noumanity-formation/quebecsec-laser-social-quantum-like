---
type: analyse
id: ANL-006
titre: "Modélisation numérique quantum-like du scrutin par champs"
version: 0.1.0
status: actif
date: 2026-08-28
---

# ANL-006 - Modélisation numérique quantum-like du scrutin par champs

> Un modèle implémentable : 110 amplitudes en champ moyen, un hamiltonien à
> quatre termes, une propagation par découpage de Trotter où chaque contexte
> s'applique après rotation dans sa propre base, un pompage multi-couleur
> résonant par champ, et une mesure du vote par règle de Born pondérée par la
> mobilisation. Le modèle rend enfin les commutateurs d'ANL-004 calculables —
> et il a désormais un concurrent classique calibré à battre.

## Question posée

Quatre questions, posées par la session.

1. Que contient la littérature de sociophysique et de modélisation
   quantum-like qui ressemble à ce que nous voulons faire, ou dont nous
   pouvons nous inspirer ?
2. Quel modèle numérique — fonction d'onde, hamiltonien, observable — simule
   un scrutin en fonction des champs, et avec quels paramètres pour chaque
   terme et chaque champ ?
3. Comment organiser une propagation à temps court décomposable en un produit
   de propagateurs par contexte, et comment appliquer un propagateur
   uniquement sur la composante correspondante de la fonction d'onde ?
4. Comment mesure-t-on le vote ?

## Méthode

### Ce qui a été examiné

- Une recherche de littérature menée le 2026-08-28, en deux volets :
  modélisation quantum-like du vote, et sociophysique électorale.
- **ANL-004** (formalisme : question de l'urne comme base de mesure, enjeux
  existentiels, masses effectives), **ANL-005** (mécanisme multi-couleur),
  **ANL-001** (champs, recoupements), **ANL-003** (matrice partis × champs).
- **FND-021** pour les équations du laser social, **FND-020** et **FND-022**
  pour les données de conjoncture.

### Convention

**[V]** vérifié, **[D]** dérivé, **[E]** estimé. **Aucun paramètre de ce
modèle n'est mesuré.** Les valeurs proposées en section 4 sont des points de
départ pour une analyse de sensibilité, et rien d'autre. On travaille en
unités réduites : `ħ = 1`, temps en **jours**, tous les taux en **jour⁻¹**.
La campagne dure **39 jours** [V].

## Constats

### 1. Ce que la littérature offre — volet quantum-like

**Le précédent direct existe, et il est ancien de plus de dix ans.**

- **Polina Khrennikova**, « Quantum like modelling of the non-separability of
  voters' preferences in the U.S. political system », arXiv:1405.1029, mai
  2014 [V]. Objet : le *ticket splitting* — voter pour des partis différents à
  la présidentielle et au Congrès. L'article montre que ce comportement
  **viole la théorie classique des probabilités**, identifie une
  « interférence hyperbolique », reconstruit les vecteurs d'état des électeurs
  à partir de probabilités de transition et teste une règle de Born
  généralisée, dans un espace de Hilbert sur les nombres hypercomplexes.
  **C'est le précédent exact de la thèse de non-séparabilité d'ANL-004**, et
  il est empirique.
- **« An Application of the Theory of Open Quantum Systems to Model the
  Dynamics of Party Governance in the US Political System »**, *International
  Journal of Theoretical Physics*, 2013 [V, auteurs non vérifiés] : l'équation
  de **GKSL** appliquée à la décision électorale, l'état mental de l'électeur
  étant une superposition des choix possibles. **Précédent direct du terme de
  dissipation que ce modèle ajoute.**
- **François Dubois**, « On quantum models for opinion and voting intention
  polls », arXiv:2411.13593, novembre 2024 [V]. Propose un **opérateur densité
  relatif à la famille des candidats**, et surtout une **méthode numérique
  pour le déterminer à partir de sondages d'opinion**, par un algorithme
  fondé sur le théorème de Perron-Frobenius. Appliqué à la présidentielle
  française de 2012. **C'est la réponse à la question de l'initialisation :
  d'où vient l'état initial.**
- Également repérés, non dépouillés : « Quantum voting and violation of
  Arrow's Impossibility Theorem » (arXiv:1501.00458) ; « Quantum voting and
  its physical interpretation » (arXiv:1912.05356) ; « A quantum approach for
  determining a state of the opinion » (arXiv:2411.10041).

### 2. Ce que la littérature offre — volet sociophysique, et le concurrent à battre

**Le concurrent classique existe, il est récent, et il est calibré sur données
réelles.**

- **Jan Korbel, Remah Dahdoul, Stefan Thurner** (Complexity Science Hub
  Vienna ; Medical University Vienna ; Santa Fe Institute), « Empirical
  validation of the polarization transition in a double-random field model of
  elections », arXiv:2510.00612, mars 2026 [V].
  Modèle : Ising à champ aléatoire, `H(s₁…s_N) = −J Σ_ij A_ij s_i s_j − Σ_i h_i s_i`,
  où `A` porte les interactions sociales et `h_i` est tiré d'une distribution
  **bimodale** représentant les deux campagnes.
  Paramètres : température `T` (volatilité sociale), intensités de campagne
  `h⁺`, `h⁻`, et proportion `p` d'électeurs suivant la première campagne.
  Résultat : **transition de polarisation** au-delà d'un seuil critique de
  dépenses, avec **hystérésis** liée à l'avantage du sortant.
  **Validation : 6 357 courses à la Chambre des représentants américaine,
  1980-2020 ; seuil critique estimé à ≈ 1,83 million de dollars ; température
  optimale T* = 0,922 ; amélioration prédictive statistiquement significative
  à p < 0,0001.**

**C'est le modèle à battre.** FND-007 et FND-021 posaient la comparaison avec
un concurrent classique comme obligatoire ; elle a maintenant une cible
précise, récente et calibrée. **Si le modèle quantum-like ne fait pas mieux
hors échantillon, à nombre de paramètres comparable, il n'apporte rien.**

Autres travaux repérés et utiles :
- **Modèle de Hegselmann-Krause modifié pour électeurs et partis en
  interaction**, arXiv:2410.13378, *Physica A* 2025 : système multipartite,
  agents et partis évoluant dans un même espace d'opinion.
- **Modèles d'Ising couplés et choix discrets interdépendants sous influence
  sociale**, arXiv:1104.4887 : **le couplage entre plusieurs choix
  simultanés** — c'est l'analogue classique des contextes intriqués d'ANL-004.
- **Extension de Potts** aux systèmes multipartites, mentionnée comme voie
  d'extension au-delà du binaire.
- « Sociophysics models inspired by the Ising model », *EPJ B* 2025
  (arXiv:2506.23837) : revue récente.
- « Modelling Surveys Effects in Political Competitions », arXiv:1711.02765 :
  les sondages comme rétroaction sur le système — directement pertinent, vu la
  place des sondages dans la campagne de 2026.

### 3. L'architecture du modèle

**3.1 Les dimensions.** `J = 11` champs (ANL-001), `P = 5` partis (CAQ, PQ,
PLQ, QS, PCQ), `C = 6` contextes retenus : économie et coût de la vie ;
identité, langue et laïcité ; santé et services publics ; environnement et
énergie ; souveraineté et rapport au Canada ; intégrité et gouvernance
(FND-022).

**3.2 La fonction d'onde.** Chaque champ `j` porte
`ψ_j ∈ C² ⊗ C^P`, soit **10 amplitudes complexes** :
- le facteur `C²` est le **qubit de mobilisation** : `|g_j⟩` fondamental
  (passif), `|e_j⟩` excité (mobilisé) — l'atome social de FND-021 ;
- le facteur `C^P` est le **registre de préférence** sur les partis.

**Modèle A — champ moyen, séparable.**
`Ψ = ⊗_j ψ_j`, soit **11 × 10 = 110 amplitudes complexes**. Les couplages
inter-champs sont traités en champ moyen. Coût dérisoire, exécution en
millisecondes, adapté à l'analyse de sensibilité massive.

**Modèle B — cluster intriqué.**
La forme produit tue l'intrication, qui est le cœur d'ANL-004. On conserve
donc l'intrication **là où ANL-001 dit qu'elle est forte** : le triplet
`{syndical, bureaucratique, économique}`, qui porte le recoupement de
≈ 930 000 personnes [D] et l'incompatibilité irréductible. Ce cluster vit dans
`(C² ⊗ C⁵)^{⊗3}`, soit **1 000 amplitudes** — entièrement traitable, y compris
en matrice densité (10⁶ éléments). Les huit autres champs restent en champ
moyen.

**C'est la matrice de recoupement d'ANL-001 qui dicte où l'intrication doit
être conservée.** C'est le principe de troncature du modèle, et il est
justifié plutôt qu'arbitraire.

**3.3 Les bases et les rotations de contexte.**
- **Base du vote** `B_V = {|p⟩}`, `p = 1…P`.
- Pour chaque contexte `c`, une **base propre** `B_c`, reliée à `B_V` par une
  unitaire `U_c` : `|c,k⟩ = U_c |k⟩`.
- La **non-commutativité** est portée par le fait que `U_c† U_{c'}` n'est ni
  l'identité ni une permutation.

**Construction concrète de `U_c` — et c'est ce qui rend ANL-004 calculable.**
Soit `X_c ∈ R^{P}` le vecteur des positions des partis sur le contexte `c`,
lu dans la matrice partis × champs d'ANL-003 et dans FND-022. On construit
l'observable
`Q_c = Σ_{p,q} x_{c,p} x_{c,q} |p⟩⟨q| / ‖X_c‖²` — un projecteur de rang 1
enrichi, ou plus généralement une matrice symétrique réelle dont les
composantes encodent les positions relatives — puis on prend `U_c` comme
matrice de ses vecteurs propres.

**Conséquence directe** : `[Q_c, Q_{c'}]` devient **numériquement évaluable**.
ANL-004 signalait en limite qu'aucun commutateur n'avait été calculé, faute
d'opérateurs explicites. **Ce modèle lève cette limite** : la famille
commutante et l'incompatibilité irréductible cessent d'être des jugements et
deviennent un calcul — `‖[Q_c, Q_{c'}]‖` mesure le degré d'incompatibilité.
**C'est le premier résultat vérifiable que le dépôt puisse produire.**

### 4. L'hamiltonien, terme par terme, avec paramètres

> `H(t) = H_0 + H_ctx(t) + H_pump(t) + H_int`
> et une dissipation non hamiltonienne traitée en section 6.

**4.1 `H_0` — l'énergie propre des champs (l'enjeu existentiel).**

> `H_0 = Σ_j (ω_j / 2) σ_j^z`

`ω_j` est l'écart de niveaux du champ `j`, c'est-à-dire son **enjeu
existentiel** (ANL-004). Interprétation opératoire retenue : **`ω_j` est la
fréquence caractéristique de reprise interne du champ** — la cadence à
laquelle sa boucle d'écho tourne. C'est la lecture qui rend la condition de
résonance sociale de FND-021 (`2L_s = m_s λ_s`) estimable : **un message dont
le rythme ne s'accorde pas à la cadence du champ ne s'y amplifie pas.**

**4.2 `H_ctx` — les enjeux comme observables.**

> `H_ctx(t) = Σ_c λ_c(t) Q_c`,  avec `Q_c = U_c D_c U_c†`, `D_c` diagonale

`λ_c(t)` est la **saillance du contexte `c` au jour `t`** — c'est l'agenda de
la campagne, et c'est la seule fonction du modèle qui soit observable en
pratique : elle se mesure par la part du contexte `c` dans la couverture
médiatique quotidienne. `D_c` porte la valence des positions pures.

**4.3 `H_pump` — le pompage multi-couleur.**

> `H_pump(t) = Σ_j Ω_j(t) cos(ω_j^d t + φ_j) (σ_j^+ + σ_j^-)`

et, sous approximation séculaire (RWA), la forme utilisable :

> `H_pump^RWA(t) = Σ_j (Ω_j(t)/2) (σ_j^+ e^{-i Δ_j t} + h.c.)`,  `Δ_j = ω_j^d − ω_j`

- `Ω_j` : **fréquence de Rabi sociale**, l'intensité du pompage adressé au
  champ `j` — proportionnelle à l'atteignabilité médiatique du champ.
- `ω_j^d` : **la fréquence de la couleur adressée au champ `j`**, c'est-à-dire
  le rythme de la question de l'urne qui lui est destinée.
- `Δ_j` : le **désaccord**. **Condition de résonance : `|Δ_j| ≲ Ω_j`.** Si
  `|Δ_j| ≫ Ω_j`, le champ ne couple pas — c'est exactement la condition
  d'accord d'énergie de FND-021 (`E ≪ ΔE` ou `E ≫ ΔE` ⟹ probabilité ≈ 0),
  ici sous forme calculable.
- `φ_j` : la **phase** — le calendrier relatif des couleurs. Si les `φ_j` sont
  verrouillées, on obtient l'analogue d'un **blocage de modes** : une
  impulsion brève et intense plutôt qu'une émission continue. **C'est le
  paramètre que ANL-005 désignait comme critique et que le modèle disponible
  ne savait pas calculer.** Ici, il est explicite.

**4.4 `H_int` — le couplage inter-champ (l'intrication).**

> `H_int = Σ_{j<k} J_{jk} σ_j^z σ_k^z + Σ_{j<k} g_{jk} (σ_j^+ σ_k^- + h.c.)`

- `J_{jk}` : couplage de type Ising, **construit à partir de la matrice de
  recoupement d'ANL-001**, normalisé par les masses effectives. Signe positif
  quand les champs sont alignés, **négatif quand ils sont antagonistes** — le
  couple `{syndical, bureaucratique}` contre `{économique}` porte le `J` le
  plus négatif du système (ANL-004, ANL-005).
- `g_{jk}` : terme d'échange, qui transfère la mobilisation d'un champ à
  l'autre. C'est lui qui produit la **compétition de modes** identifiée en
  ANL-005 comme premier point de rupture.

**4.5 Paramètres proposés, par champ.** Tous **[E]**, tous en jour⁻¹, tous à
soumettre à l'analyse de sensibilité.

| Champ | `M_j` (ANL-004) | `ω_j` cadence | `Ω_j^max` pompage | `γ_j` démobilisation | `Γ_j` déphasage | `⟨k⟩_j` densité interne |
|---|---|---|---|---|---|---|
| Numérique | 1 290 000 | 10 | 2,0 | 0,20 | 8,0 | élevée |
| Journalistique | 1 590 000 | 2,0 | 1,5 | 0,10 | 1,5 | élevée |
| Politique | 100 000 | 1,0 | 1,0 | 0,05 | 0,7 | élevée |
| Religieux | 920 000 | 0,14 | 0,3 | 0,02 | 0,10 | moyenne |
| Syndical | 370 000 | 0,15 | 0,6 | 0,03 | 0,10 | **très élevée** |
| Associatif | 300 000 | 0,15 | 0,4 | 0,03 | 0,12 | moyenne |
| Culturel | 550 000 | 0,10 | 0,5 | 0,03 | 0,10 | moyenne |
| Économique | 200 000 | 0,20 | 0,7 | 0,04 | 0,15 | élevée |
| Bureaucratique | 410 000 | 0,07 | 0,4 | 0,02 | 0,06 | élevée |
| Académique | 650 000 | 0,03 | 0,3 | 0,02 | 0,03 | **très élevée** |
| Juridique | 20 000 | 0,01 | 0,05 | 0,01 | 0,01 | élevée |

**Rationnel des colonnes.** `ω_j` : cadence de reprise interne — le champ
numérique tourne en heures, le juridique en trimestres. `Ω_j^max` :
atteignabilité médiatique. `γ_j` : la mobilisation retombe en semaines.
`Γ_j` : l'attention se perd d'autant plus vite que le champ est rapide.
`⟨k⟩_j` : densité du réseau interne, qui commande le seuil
`σ_seuil,j = κ_j Γ_j /(g_j² ⟨k⟩_j)` (FND-021, ANL-004) — **les champs
syndical et académique, structurellement organisés, ont les seuils les plus
bas**, malgré des masses modestes.

### 5. La propagation à temps court et la rotation de contexte

**5.1 Le découpage.** Sur un pas `Δt`, découpage symétrique de Strang :

> `U(Δt) ≈ e^{−i H_0 Δt/2} · e^{−i H_int Δt/2} · [∏_c U_c† e^{−i λ_c D_c Δt} U_c] · e^{−i H_pump Δt} · e^{−i H_int Δt/2} · e^{−i H_0 Δt/2}`

Erreur locale `O(Δt³)`, globale `O(Δt²)`. Le découpage simple (Trotter au
premier ordre) donne `O(Δt)` global et suffit pour l'exploration.

**5.2 La rotation de contexte — la réponse explicite à la question posée.**

Pour appliquer le propagateur du contexte `c` **uniquement sur la composante
correspondante** de la fonction d'onde, on procède en trois temps :

1. **Rotation** : `φ = U_c† ψ` — on exprime l'état dans la base propre du
   contexte `c`, celle de ses positions pures.
2. **Propagation diagonale** : `φ_k ← e^{−i λ_c ε_{c,k} Δt} φ_k` — composante
   par composante, coût linéaire. **C'est ici, et seulement ici, que le
   contexte `c` agit.**
3. **Rotation inverse** : `ψ = U_c φ` — retour dans la base du vote.

**C'est exactement la méthode de découpage d'opérateur de la dynamique
quantique** : on applique le terme cinétique dans l'espace des impulsions et
le terme potentiel dans l'espace des positions, avec une transformée de
Fourier entre les deux. **Ici, `U_c` remplace la transformée de Fourier.**
Toute personne ayant fait de la propagation de paquet d'ondes reconnaîtra le
schéma, ce qui est un avantage de présentation.

Coût : deux produits matrice-vecteur de taille `P = 5` par champ, par
contexte, par pas. Avec `J = 11` et `C = 6`, cela fait 132 produits 5×5 par
pas — négligeable.

**5.3 Le pas de temps.** Il faut `Δt ≪ 1/max(ω_j, Ω_j, λ_c)`. Avec
`ω_max ≈ 10` jour⁻¹, on prend **`Δt = 0,01 jour`, soit environ 15 minutes**.
Sur 39 jours : **3 900 pas**. Une trajectoire complète coûte quelques
millisecondes ; une analyse de sensibilité de 10⁶ trajectoires reste à portée
d'un ordinateur portable.

### 6. La dissipation — ce que FND-021 n'a pas

FND-021 établit que le modèle de Khrennikov **n'a aucun terme de
dissipation** : ni décohérence, ni saturation, ni relaxation formalisées.
C'est la lacune qui bloque toute conception d'un contrôle (FND-013). On la
comble par une équation maîtresse de Lindblad, dans la lignée du précédent
GKSL relevé au constat 1 :

> `dρ/dt = −i[H(t), ρ] + Σ_j ( D[L_j^↓]ρ + D[L_j^φ]ρ )`

avec `L_j^↓ = √γ_j · σ_j^-` (**relaxation** : démobilisation, retour à l'état
fondamental) et `L_j^φ = √(Γ_j/2) · σ_j^z` (**déphasage** : perte de
cohérence, l'attention se disperse sans que la mobilisation retombe).

`Γ_j` est la **température sociale** de FND-021, enfin dotée d'une définition
opératoire : c'est le taux auquel un champ perd la cohérence de son cadrage.

**Mise en œuvre recommandée : la méthode Monte-Carlo de fonction d'onde**
(trajectoires quantiques). Elle conserve le formalisme de **fonction d'onde**
demandé par la session, traite la dissipation par sauts stochastiques, et est
massivement parallélisable. La matrice densité complète reste possible ici —
110² ou 1 000² éléments — mais la méthode par trajectoires est plus lisible et
donne directement la variance.

**Conséquence attendue, et testable :** un système à gain et à pertes
présente des **oscillations de relaxation** — un dépassement puis une décrue
avant le régime permanent. Sur 39 jours, cela signifie qu'**une vague pompée
trop tôt retombe avant le scrutin**. ANL-005 désignait le calendrier comme le
paramètre critique ; **ce terme de dissipation est ce qui permet enfin de le
calculer.**

### 7. La mesure du vote

**7.1 L'observable.** Le vote est un observable `V = Σ_p v_p Π_p`, où
`Π_p = |p⟩⟨p|` projette sur le parti `p` dans la base `B_V`. La mesure est
**projective et irréversible** — c'est ce qui distingue le scrutin d'un
sondage.

**7.2 Le rôle de la question de l'urne.** Suivant ANL-004, la question de
l'urne effective `a` détermine la base dans laquelle l'état est présenté à la
mesure. L'observable effectivement mesuré est

> `V^{(a)} = U_a† V U_a`

**Le modèle tient en une phrase : on projette toujours dans la base des
partis, mais l'état qu'on projette a été tourné par la question de l'urne.**

**7.3 La participation.** Un champ à l'état fondamental ne vote pas. On pose

> `τ_j(T) = τ_j^0 + (1 − τ_j^0) · (1 + ⟨σ_j^z⟩_T) / 2`

où `τ_j^0` est la participation de base du champ. Calage global : la
participation provinciale était de **66,05 % en 2022** [V].

**7.4 L'agrégation.** Pour chaque champ, la règle de Born donne
`P(p | j) = |⟨p | ψ_j^{pref}(T)⟩|²`, et l'on agrège par les **masses
effectives** d'ANL-004, qui somment exactement à 6,4 M [V] :

> `V_p = Σ_j M_j · τ_j(T) · P(p | j)`

**7.5 Ce qui manque pour aller aux sièges.** La conversion voix → sièges exige
les résultats par circonscription transposés sur la **nouvelle carte à
127 circonscriptions** [V]. **Ces données existent chez Élections Québec et
n'ont toujours pas été dépouillées** — c'est la lacune signalée depuis la
tâche 4, et c'est elle qui sépare une simulation d'opinion d'une simulation
d'élection.

**7.6 L'initialisation.** L'état initial `ψ_j(0)` se construit à partir des
sondages, selon la méthode de Dubois (constat 1) : détermination d'un
opérateur densité à partir des intentions de vote. Point de départ vérifié
pour 2026 : PQ 30 %, CAQ 23 %, PLQ 23 %, PCQ 16 %, QS 7 % (Léger, 21-24 août)
[V], avec ventilation régionale disponible [V].

### 8. Le protocole de validation

Sans ce protocole, le modèle est un exercice de style. Quatre étapes, par
ordre de coût croissant :

1. **Calculer les commutateurs** `‖[Q_c, Q_{c'}]‖` à partir des positions des
   partis (constat 3.3). Coût : nul. **Vérifie ou réfute la structure de
   compatibilité posée en ANL-004 et ANL-005.**
2. **Tester la contrainte d'ordre des questions** sur données de sondage
   québécoises (ANL-004, constat 8). Contrainte sans paramètre libre : si elle
   est violée, le noyau du modèle est faux.
3. **Comparer au concurrent classique** de Korbel, Dahdoul et Thurner — Ising
   à champ aléatoire, calibré sur 6 357 courses, seuil à 1,83 M$, `T* = 0,922`
   [V]. **À nombre de paramètres comparable et hors échantillon.** Si le modèle
   quantum-like ne fait pas mieux, il n'apporte rien, et il faut le dire.
4. **Analyse de sensibilité comme résultat principal.** Aucun paramètre
   n'étant mesuré, le livrable n'est pas une prédiction mais une **carte des
   régimes** : quelles régions de l'espace des paramètres produisent un
   lasing multi-couleur stable, laquelle produit une compétition de modes,
   laquelle une extinction avant le scrutin.

## Réponse

**Sur la littérature.** Le précédent quantum-like du vote existe depuis 2014
(Khrennikova, non-séparabilité et *ticket splitting*), le précédent GKSL
depuis 2013, et une méthode d'initialisation depuis 2024 (Dubois, opérateur
densité déterminé à partir de sondages). Côté sociophysique, **le concurrent
à battre est identifié** : Korbel, Dahdoul et Thurner (mars 2026), modèle
d'Ising à double champ aléatoire, validé sur 6 357 courses électorales réelles
avec une amélioration prédictive à `p < 0,0001`.

**Sur le modèle.** Onze champs, cinq partis, six contextes. Chaque champ porte
`ψ_j ∈ C² ⊗ C⁵` — un qubit de mobilisation et un registre de préférence, soit
**110 amplitudes complexes en champ moyen**. L'intrication est conservée sur
le triplet `{syndical, bureaucratique, économique}`, soit 1 000 amplitudes ;
**c'est la matrice de recoupement d'ANL-001 qui dicte cette troncature.**
L'hamiltonien a quatre termes — énergie propre `H_0` (l'enjeu existentiel),
contextes `H_ctx` (les enjeux comme observables non commutants), pompage
`H_pump` (multi-couleur, résonant par champ), couplage `H_int` (l'intrication,
construite sur les recoupements) — auxquels s'ajoute une dissipation de
Lindblad, **absente du modèle de Khrennikov et ajoutée ici**. Les paramètres
sont proposés au constat 4.5, tous estimés, tous en jour⁻¹.

**Sur la propagation et la rotation de contexte.** Découpage symétrique de
Strang, erreur globale `O(Δt²)`, avec `Δt = 0,01 jour` et 3 900 pas sur la
campagne. Pour appliquer un propagateur sur la seule composante d'un contexte :
**rotation `U_c†` dans la base propre du contexte, propagation diagonale
composante par composante, rotation inverse `U_c`.** C'est la méthode de
découpage d'opérateur de la dynamique quantique, où `U_c` remplace la
transformée de Fourier.

**Sur la mesure du vote.** Mesure projective dans la base des partis, mais sur
un état préalablement tourné par la question de l'urne : `V^{(a)} = U_a† V U_a`.
La participation du champ dépend de sa mobilisation `⟨σ_j^z⟩` ; l'agrégation
se fait par les masses effectives d'ANL-004, qui somment à 6,4 M. **La
conversion en sièges reste bloquée faute des résultats transposés sur la
carte à 127 circonscriptions.**

**Le gain le plus net de cette analyse** est ailleurs : en construisant les
`Q_c` à partir des positions des partis, elle rend les **commutateurs
numériquement évaluables**. La famille commutante et l'incompatibilité
irréductible d'ANL-004 et ANL-005 cessent d'être des jugements argumentés et
deviennent un calcul. **C'est le premier résultat vérifiable que le dépôt
puisse produire, et il ne coûte rien.**

## Limites

- **Aucun paramètre n'est mesuré.** Le tableau 4.5 est un point de départ
  d'analyse de sensibilité, pas une calibration. Les `ω_j` en particulier
  reposent sur une interprétation — la cadence de reprise du champ — qui est
  plausible et non validée.
- **La construction des `Q_c` dépend d'ANL-003**, dont la notation `++` à `−−`
  est qualitative et posée. Les commutateurs seront donc calculables mais
  **hérités d'un jugement**, non d'une mesure. C'est un progrès, pas une
  preuve.
- **L'approximation séculaire (RWA) n'est pas justifiée ici.** Elle suppose
  `Ω_j ≪ ω_j`, ce qui est faux pour les champs lents fortement pompés — le
  bureaucratique et l'académique, où `Ω_j > ω_j` dans le tableau proposé.
  **Pour ces champs, il faut garder la forme complète du pompage**, sous peine
  d'un artefact.
- **Le découpage en 11 champs n'est pas validé** (limite héritée d'ANL-001),
  ni le choix des 6 contextes.
- **Le modèle ne dit rien des circonscriptions.** Sans transposition sur la
  carte à 127, il simule des intentions de vote agrégées, pas une élection.
- **La comparaison au concurrent classique n'a pas été faite**, seulement
  posée. Tant qu'elle ne l'est pas, rien n'établit que le formalisme
  quantum-like apporte quoi que ce soit — c'est la question ouverte de FND-007
  et elle reste ouverte.
- **Rien ici n'établit une efficacité.** Le modèle décrit une dynamique
  possible ; FND-011 rappelle que les effets persuasifs mesurés sont petits et
  FND-014 que le contrôle par peu de points d'entrée coûte une énergie
  exponentielle.
- **Ce qui reste à examiner** : le calcul effectif des commutateurs ; le test
  de la contrainte d'ordre sur sondages québécois ; la lecture des articles
  repérés au constat 1 et non dépouillés ; et les résultats par
  circonscription d'Élections Québec.

**Relations.** Dérive d'ANL-004 (formalisme) et d'ANL-005 (mécanisme
multi-couleur). Référence ANL-001 (champs, recoupements, troncature),
ANL-003 (positions des partis, construction des `Q_c`), FND-007 (statut du
programme), FND-013 et FND-014 (contrôle, dissipation), FND-020 (sondages,
carte à 127), FND-021 (mécanisme du laser, absence de dissipation), FND-022
(propositions). Spécifie le script de simulation numérique attendu par la
session.
