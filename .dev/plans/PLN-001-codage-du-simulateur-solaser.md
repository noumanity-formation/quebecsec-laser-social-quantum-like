---
type: plan
id: PLN-001
titre: "Codage du simulateur solaser"
version: 0.1.0
etat: propose
repond-a: ANL-006
---

# PLN-001 - Codage du simulateur solaser

> Écrire en Rust le programme de dynamique numérique spécifié par ANL-006, en
> livrant d'abord la seule chose qui soit vérifiable — les commutateurs — et en
> plaçant le banc de comparaison classique dans le programme plutôt qu'à côté.

## Le problème

Le dépôt a produit une modélisation complète — ANL-004 pour le formalisme,
ANL-005 pour le mécanisme, ANL-006 pour le modèle numérique — et **rien qui
s'exécute**. La session attend un script de simulation numérique parmi ses
livrables ; il n'existe pas.

Trois constats précis, tirés des analyses :

1. **Aucun paramètre du modèle n'est mesuré.** L'analyse de sensibilité n'est
   donc pas une précaution mais le résultat principal attendu, et elle exige un
   programme capable d'exécuter des dizaines de milliers de scénarios.
2. **Une affirmation du dépôt est calculable et n'a pas été calculée.** ANL-004
   pose une famille commutante de champs et une incompatibilité irréductible,
   et note en limite qu'aucun commutateur n'a été évalué faute d'opérateurs
   explicites. ANL-006 fournit la construction des opérateurs. **Le calcul est
   à portée et ne coûte rien.**
3. **Un concurrent classique calibré existe** — le modèle d'Ising à champ
   aléatoire de Korbel, Dahdoul et Thurner, validé sur 6 357 courses
   électorales. FND-007 et FND-021 posent la comparaison comme obligatoire.
   Sans elle, rien n'établit que le formalisme quantum-like apporte quoi que ce
   soit.

## Ce que ce plan fait, et ce qu'il ne fait pas

**Ce qu'il fait.** Il découpe l'écriture de `solaser` — espace de travail Rust
à trois caisses — en neuf chantiers vérifiables, conformément aux documents de
conception déposés dans `.dev/architecture/` : exigences, architecture,
spécification.

**Ce qu'il ne fait pas.**

- **Il ne convertit pas les voix en sièges.** Cela exige les résultats de 2022
  transposés sur la carte à 127 circonscriptions, qui n'ont pas été dépouillés.
  Le programme produit des parts de vote agrégées. *C'est la limite la plus
  lourde de la version 1, et elle est signalée depuis la tâche 4 de la session.*
- **Il n'estime aucun paramètre à partir de données.** Aucune inférence, aucun
  ajustement.
- **Il ne collecte rien.** Le programme lit des fichiers de configuration et
  écrit des tableaux. Aucune interaction avec une plateforme, aucun suivi de
  compte, aucune donnée personnelle.
- **Il ne teste pas la contrainte d'ordre des questions** sur données de
  sondage québécoises (ANL-004 §8). C'est un travail d'analyse de données, pas
  de simulation, et il relève d'un autre plan.
- **Il ne publie pas.** La décision de publier ou non le programme appartient à
  l'humain — voir les objections.

## Chantiers

### C1 — Espace de travail et configuration typée

Créer l'espace de travail Cargo à trois caisses `solaser-core`,
`solaser-config`, `solaser-cli`, avec `#![forbid(unsafe_code)]` partout.
Implémenter `Tracked<T>` portant valeur, provenance `V`/`D`/`E` et source, et
la désérialisation TOML des champs, contextes, partis et scénarios.

**Vérifiable** : `cargo test` passe ; une configuration à laquelle il manque
une marque de provenance est rejetée avec le nom du paramètre fautif ; une
configuration dont les `m_eff` ne somment pas à 6 400 000 ± 1 % est rejetée ;
`solaser --dry-run` imprime le rapport de provenance complet et s'arrête sans
calculer.

### C2 — Noyau algébrique et construction des observables

Implémenter `types`, `state`, `operators` : convention d'ordonnancement des dix
amplitudes en deux blocs de cinq, matrices de Pauli, projecteurs de parti,
construction de `Q_c` depuis les positions des partis, diagonalisation,
extraction de `U_c` et `D_c`.

**Vérifiable** : tests de propriété — `Q_c` symétrique à `1e-12`, `U_c`
unitaire à `1e-12`, `U_c D_c U_cᵀ = Q_c` à `1e-10` — passant sur cent
configurations engendrées aléatoirement ; le lift de Kronecker n'est jamais
matérialisé, vérifié par revue et par l'absence d'allocation 10×10 dans le
chemin chaud.

### C3 — `solaser commut` et la première réponse vérifiable

Implémenter le calcul de `κ_{c,c'} = ‖[Q_c,Q_{c'}]‖_F / (‖Q_c‖_F ‖Q_{c'}‖_F)`
pour toutes les paires de contextes, et l'export en table.

**Vérifiable** : la commande produit une matrice 6×6 symétrique à diagonale
nulle ; `κ = 0` exactement pour deux contextes construits volontairement
proportionnels ; **la table est confrontée à la structure de compatibilité
posée en ANL-004 §6 et ANL-005 §8, et le résultat de la confrontation est
consigné** — qu'il la confirme ou la réfute.

*Ce chantier ne dépend que de C1 et C2. Il est livré avant tout le reste,
parce que c'est le seul résultat du dépôt qui soit à la fois vérifiable et
gratuit.*

### C4 — Propagateur de Strang et rotation de contexte

Implémenter `propagate` : découpage symétrique dans l'ordre spécifié,
application de `H₀` par phases sur les deux blocs, et **rotation de contexte**
— `U_cᵀ` sur chaque bloc de cinq, phases diagonales, `U_c` retour.

**Vérifiable** : la norme est conservée à `1e-10` par pas sur 3 900 pas sans
dissipation ; un test de convergence divisant `Δt` par deux montre une erreur
divisée par quatre, pente `2,0 ± 0,1` en échelle log-log ; **avec deux
contextes commutants, l'ordre d'application ne change pas le résultat à
`1e-12` ; avec deux contextes non commutants, il le change** — ce dernier test
est la vérification directe du noyau du modèle.

### C5 — Pompage multi-couleur

Implémenter `H_pump` sous forme complète et sous approximation séculaire,
commutable **par champ** ; rotation `2×2` en forme close ; exposition du
facteur de résonance `Ω²/(Ω²+Δ²)` en diagnostic.

**Vérifiable** : sous pompage résonant (`Δ = 0`), sans contexte ni dissipation,
un champ isolé reproduit les **oscillations de Rabi** de période `2π/Ω` à
`1e-8` près ; hors résonance (`Δ ≫ Ω`), l'inversion reste sous 1 % ; le
validateur avertit lorsque `rwa = true` alors que `Ω_j ≳ ω_j`, et l'avertissement
se déclenche effectivement sur les champs bureaucratique et académique de la
configuration de référence.

### C6 — Terme d'offre et couplage inter-champ

Implémenter `H_pref` — hermitien par construction, actif sur le seul bloc
`|e⟩` — et `H_int` en champ moyen, avec construction de `J_{jk}` depuis la
matrice de recoupement d'ANL-001 et signe négatif sur l'axe
`{syndical, bureaucratique}` contre `{économique}`.

**Vérifiable** : `H_pref` et `H_int` sont hermitiens à `1e-12` ; un champ non
mobilisé (`|e⟩` d'amplitude nulle) ne voit **aucune** dérive de préférence sous
`H_pref`, à `1e-12` ; le signe négatif produit bien une anticorrélation des
inversions des deux blocs, mesurée sur une trajectoire.

### C7 — Dissipation par trajectoires quantiques

Implémenter `lindblad` : opérateurs de saut, hamiltonien effectif non
hermitien, tirage et application des sauts, générateur `ChaCha` graine.
Implémenter en parallèle le mode matrice densité en champ moyen comme oracle.

**Vérifiable** : sous déphasage pur, la cohérence décroît en `exp(−Γt)` à `2 %`
près sur un ensemble de 10⁴ trajectoires ; la moyenne d'ensemble MCWF et la
matrice densité coïncident à `1e-3` sur 10⁴ trajectoires ; `δp < 0,01` à chaque
pas, avec avertissement sinon ; deux exécutions à même graine sont identiques
bit à bit.

### C8 — Mesure, agrégation et balayage parallèle

Implémenter `measure` — question de l'urne, préférence conditionnelle,
participation, agrégation par masses effectives — et `cmd_sweep` avec grille,
latin hypercube et Sobol, parallélisé par `rayon`, graines dérivées
déterministement.

**Vérifiable** : les parts de vote somment à 1 à `1e-12` ; l'agrégation refuse
une configuration dont les `m_eff` ne somment pas à l'électorat déclaré ; un
balayage de 10⁴ jeux × 10³ trajectoires s'exécute **en moins de 15 minutes sur
16 cœurs** (ENF-3.3), mesuré par `criterion` ; deux exécutions du même balayage
à même graine produisent des fichiers identiques.

### C9 — Banc de comparaison classique

Implémenter le modèle d'Ising à champ aléatoire comme sous-commande
`solaser sim --model ising`, sur le même graphe de champs et les mêmes
métriques, avec les valeurs publiées comme point de départ (`T* = 0,922`).

**Vérifiable** : le modèle classique reproduit la **transition de
polarisation** au-delà d'un seuil de champ, visible dans un balayage en `h` ;
les deux modèles s'exécutent sur un scénario commun et produisent une table de
comparaison unique ; **le rapport consigne lequel fait mieux, et si c'est le
modèle classique, il le dit.**

## Livrables attendus

- Un espace de travail Rust `solaser/` compilant sur stable, sans `unsafe`,
  `clippy -D warnings` propre.
- Trois exécutables : `solaser commut`, `solaser sim`, `solaser sweep`.
- Quatre fichiers de configuration de référence dans `config/`, commentés
  paramètre par paramètre avec leur provenance.
- Une suite de tests comprenant : tests de propriété (hermiticité, unitarité,
  norme), tests analytiques (Rabi, décroissance exponentielle), test de
  convergence de Strang, test de commutation.
- **Une table de commutateurs 6×6**, livrée dès C3, avec sa confrontation
  écrite à ANL-004 §6.
- Une table de comparaison `solaser` contre Ising à champ aléatoire sur un
  scénario commun.
- Un rapport de provenance listant tout paramètre utilisé, sa valeur, sa marque
  et sa source.

## Comment on saura que c'est fait

Sept critères, tous vérifiables par exécution, écrits avant de commencer.

1. `cargo test --workspace` passe, et `cargo clippy --workspace -- -D warnings`
   ne produit aucun avertissement.
2. `solaser commut --config config/` produit une matrice 6×6 dont la
   confrontation à ANL-004 §6 est consignée dans un fichier de résultat.
3. Le test de convergence de Strang mesure une pente de `2,0 ± 0,1`.
4. Le test de Rabi reproduit la période analytique `2π/Ω` à `1e-8` près.
5. Le test de commutation montre une différence nulle à `1e-12` pour deux
   contextes commutants et non nulle pour deux contextes non commutants.
6. `solaser sweep` exécute 10⁴ jeux × 10³ trajectoires en moins de 15 minutes
   sur 16 cœurs, et deux exécutions à même graine produisent des fichiers
   identiques.
7. `solaser sim --model ising` et `solaser sim --model quantum` s'exécutent sur
   le même scénario et produisent une table de comparaison unique.

**Si l'un de ces sept critères ne peut pas être atteint, le plan a échoué sur ce
point et cela se dit** — un plan qui, à l'exécution, ne produit rien est un
défaut du plan.

## Objections de l'agent

Six points que je ne peux pas trancher seul.

**O-1 — La correspondance du qualitatif vers le numérique.**
La spécification §2.1 propose de traduire la notation d'ANL-003 par
`++ → +2`, `+ → +1`, `0 → 0`, `− → −1`, `−− → −2`. **Cette correspondance
détermine tous les opérateurs et donc tous les résultats**, y compris la table
de commutateurs de C3. Elle transforme un jugement qualitatif — que j'ai posé
moi-même en ANL-003, sans métrique — en nombres. L'échelle linéaire est un
choix ; une échelle non linéaire, ou une pondération par la masse du champ,
donnerait d'autres commutateurs. **À valider avant C2.**

**O-2 — Le traitement des contestations de nomos.**
ANL-003 note `≠` les propositions qui contestent la règle d'un champ. Je les
route vers `H_pref` plutôt que vers `U_c`. L'option plus fidèle à ANL-004 —
qu'une contestation de nomos **change la base de mesure elle-même** — n'a pas
de formulation simple et je l'ai reportée hors version 1. C'est peut-être le
mauvais arbitrage, puisque c'est précisément la thèse centrale d'ANL-004.

**O-3 — L'ajout d'un cinquième terme à l'hamiltonien.**
ANL-006 en énonce quatre ; la spécification en ajoute un, `H_pref`, sans lequel
aucune dérive nette de préférence n'existe. ANL-006 est un point fixe et ne
sera pas révisée. **L'écart entre l'analyse et la spécification doit être
assumé explicitement**, ou l'analyse remplacée par une autre.

**O-4 — Le mode cluster en version 1.**
Le mode champ moyen tue l'intrication, qui est le cœur d'ANL-004. Le mode
cluster la conserve pour 1 000 amplitudes — coût négligeable, mais complexité
d'implémentation réelle. Faut-il le livrer en version 1, ou accepter une
version 1 séparable qui **ne peut pas démontrer ce qu'elle prétend** ?

**O-5 — La lacune des circonscriptions.**
Sans les résultats de 2022 transposés sur la carte à 127, le programme simule
des parts de vote et non une élection. Cette lacune est signalée depuis la
tâche 4 et les données sont publiques chez Élections Québec. **Faut-il les
dépouiller avant d'écrire le programme, ou livrer une version 1 qui ne va pas
jusqu'aux sièges ?**

**O-6 — La publication.**
L'intention du dépôt prévoit un dépôt publié. Ce programme est un simulateur
d'un mécanisme d'influence visant une élection **en cours** — la campagne
québécoise a été déclenchée le 27 août 2026 pour un scrutin le 5 octobre.
Les documents d'analyse contiennent aussi une signature de détection, ce qui
leur donne une valeur défensive ; un exécutable paramétré n'a pas le même
statut qu'un texte. **Publier le code, le publier après le scrutin, ne publier
que les documents, ou ne rien publier avant relecture : c'est une décision
humaine, et je ne la prends pas.** Elle devrait être tranchée avant C1, parce
qu'elle change le choix du dépôt de destination et la licence.
