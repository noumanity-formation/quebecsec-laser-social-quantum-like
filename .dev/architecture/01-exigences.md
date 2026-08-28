# Exigences — simulateur `solaser`

**Document de conception** — état : proposé, 2026-08-28.
Répond à ANL-006 (modélisation numérique quantum-like du scrutin par champs).
À lire avec `02-architecture.md` et `03-specification.md`.

`solaser` est le programme de dynamique numérique qui simule le modèle
d'ANL-006 : onze champs bourdieusiens, cinq partis, six contextes, un
hamiltonien à cinq termes, une dissipation de Lindblad, et une mesure du vote
par règle de Born pondérée par la mobilisation.

---

## 1. Exigences fonctionnelles

### EF-1 — Chargement de configuration typée

Le programme lit toute sa paramétrisation depuis des fichiers de
configuration. **Aucun paramètre du modèle n'est écrit en dur dans le code.**

- EF-1.1 — Les champs, contextes, partis, et le scénario de campagne sont
  décrits dans des fichiers TOML distincts.
- EF-1.2 — **Chaque paramètre porte une marque de provenance** : `V` (vérifié),
  `D` (dérivé), `E` (estimé), conformément à la convention des analyses du
  dépôt. La marque est obligatoire ; un paramètre sans marque est une erreur de
  configuration, pas un défaut par omission.
- EF-1.3 — Le programme refuse de démarrer si une valeur est absente,
  hors bornes, ou dépourvue de provenance, et nomme le paramètre fautif.

### EF-2 — Construction des opérateurs

- EF-2.1 — Construire, pour chaque contexte `c`, l'observable `Q_c` à partir
  des positions des partis, et en extraire la base propre `U_c` par
  diagonalisation.
- EF-2.2 — Vérifier l'hermiticité de tout opérateur construit, à la tolérance
  près, et échouer explicitement sinon.
- EF-2.3 — Vérifier l'unitarité de chaque `U_c` construite.
- EF-2.4 — **Calculer et exporter les commutateurs `‖[Q_c, Q_{c'}]‖`** pour
  toutes les paires de contextes.

### EF-3 — Propagation

- EF-3.1 — Propager l'état sur un pas `Δt` par découpage symétrique de Strang,
  dans l'ordre spécifié en `03-specification.md`.
- EF-3.2 — Appliquer chaque terme de contexte **par rotation dans sa base
  propre**, propagation diagonale, rotation inverse.
- EF-3.3 — Supporter deux formes du terme de pompage — **approximation
  séculaire (RWA)** et **forme complète** — et permettre de choisir la forme
  **champ par champ**. *ANL-006 établit que la RWA n'est pas justifiée pour les
  champs lents fortement pompés ; le programme ne doit pas imposer un choix que
  l'analyse a déclaré invalide.*
- EF-3.4 — Supporter un pas de temps configurable et un ordre de découpage
  configurable (Trotter 1er ordre ou Strang 2e ordre).

### EF-4 — Dissipation

- EF-4.1 — Implémenter la relaxation `L_j^↓ = √γ_j σ_j^-` et le déphasage
  `L_j^φ = √(Γ_j/2) σ_j^z` par champ.
- EF-4.2 — Résoudre la dynamique dissipative par **Monte-Carlo de fonction
  d'onde** (trajectoires quantiques), afin de conserver le formalisme de
  fonction d'onde.
- EF-4.3 — Permettre l'exécution en matrice densité complète comme mode de
  vérification croisée, au moins en champ moyen.

### EF-5 — Modes de représentation

- EF-5.1 — **Mode champ moyen** (défaut) : état produit `Ψ = ⊗_j ψ_j`,
  110 amplitudes complexes.
- EF-5.2 — **Mode cluster intriqué** : intrication conservée sur un
  sous-ensemble de champs déclaré en configuration, les autres restant en champ
  moyen. Le cluster par défaut est `{syndical, bureaucratique, économique}`.
- EF-5.3 — Le programme refuse un cluster dont la dimension dépasse une borne
  configurable, et le dit avant d'allouer.

### EF-6 — Mesure et agrégation

- EF-6.1 — Calculer, pour chaque champ, `P(p|j) = |⟨p|ψ_j^{pref}(T)⟩|²`.
- EF-6.2 — Calculer la participation `τ_j(T)` en fonction de `⟨σ_j^z⟩_T`.
- EF-6.3 — Agréger par les masses effectives : `V_p = Σ_j M_j τ_j P(p|j)`, et
  **vérifier que `Σ_j M_j` égale l'électorat déclaré** à la tolérance près.
- EF-6.4 — Permettre de spécifier la question de l'urne effective `a`, la
  mesure portant alors sur `V^{(a)} = U_a† V U_a`.

### EF-7 — Diagnostics

Exporter à chaque pas, ou à une cadence configurable :
- norme de l'état, par champ et globale ;
- inversion `⟨σ_j^z⟩` par champ ;
- **cohérence intra-champ**, définie en `03-specification.md` — c'est la
  signature de détection d'ANL-005 ;
- énergie instantanée `⟨H(t)⟩` ;
- nombre de sauts quantiques par trajectoire.

### EF-8 — Balayage de paramètres

- EF-8.1 — Exécuter un balayage sur un espace de paramètres décrit en
  configuration, par grille, échantillonnage latin hypercube, ou séquence de
  Sobol.
- EF-8.2 — Paralléliser sur tous les cœurs disponibles.
- EF-8.3 — Produire une sortie tabulaire : une ligne par jeu de paramètres,
  avec les parts de vote, les diagnostics agrégés et **les marques de provenance
  des paramètres utilisés**.

### EF-9 — Banc de comparaison

- EF-9.1 — Implémenter le **modèle d'Ising à champ aléatoire** de Korbel,
  Dahdoul et Thurner comme modèle de référence classique.
- EF-9.2 — Exécuter les deux modèles sur le même scénario et produire une
  comparaison sur les mêmes métriques.

*ANL-006 pose cette comparaison comme la condition sans laquelle le modèle
quantum-like n'établit rien. Elle est donc une exigence fonctionnelle, pas une
extension.*

### EF-10 — Interface en ligne de commande

Trois sous-commandes au minimum :
- `solaser commut` — calcule et exporte les commutateurs (EF-2.4) ;
- `solaser sim` — exécute un scénario, une ou plusieurs trajectoires ;
- `solaser sweep` — exécute un balayage (EF-8).

---

## 2. Exigences non fonctionnelles

### ENF-1 — Reproductibilité

- ENF-1.1 — Toute exécution est **déterministe** à configuration et graine
  fixées.
- ENF-1.2 — Le générateur pseudo-aléatoire est explicitement graine et
  reproductible entre plateformes (`ChaCha`), jamais le générateur du système.
- ENF-1.3 — Chaque sortie porte en en-tête : la version du programme,
  l'empreinte de la configuration complète, la graine, et la date d'exécution.

### ENF-2 — Correction numérique

- ENF-2.1 — Hors saut quantique, la norme de l'état est conservée à
  **`1e-10`** près par pas.
- ENF-2.2 — L'erreur globale du découpage de Strang décroît en **`O(Δt²)`**,
  vérifié par un test qui divise le pas et mesure la pente.
- ENF-2.3 — Les opérateurs construits sont hermitiens à `1e-12` près ; les
  changements de base sont unitaires à `1e-12` près.
- ENF-2.4 — Les cas analytiques connus sont reproduits : **oscillations de
  Rabi** sous pompage résonant sans dissipation, et **décroissance en
  `exp(-Γt)`** de la cohérence sous déphasage pur.

### ENF-3 — Performance

Cibles sur une machine de bureau à 16 cœurs :
- ENF-3.1 — Une trajectoire en champ moyen sur 39 jours à `Δt = 0,01`
  (3 900 pas) : **< 1 ms**.
- ENF-3.2 — Un ensemble de 10³ trajectoires : **< 1 s**.
- ENF-3.3 — Un balayage de 10⁴ jeux de paramètres × 10³ trajectoires :
  **< 15 minutes**.
- ENF-3.4 — L'empreinte mémoire en mode champ moyen reste inférieure à 10 Mo
  par fil d'exécution.

### ENF-4 — Sûreté et qualité

- ENF-4.1 — `#![forbid(unsafe_code)]` sur l'ensemble des caisses.
- ENF-4.2 — Aucune panique en chemin nominal : toute erreur est une valeur de
  retour typée.
- ENF-4.3 — `clippy` sans avertissement au niveau `-D warnings`.
- ENF-4.4 — Couverture des modules numériques par des tests de propriété
  (hermiticité, unitarité, conservation de la norme) et non seulement par des
  tests d'exemple.

### ENF-5 — Traçabilité des paramètres

- ENF-5.1 — La marque de provenance `V`/`D`/`E` de chaque paramètre est
  **portée jusque dans la sortie**.
- ENF-5.2 — Le programme peut produire un **rapport de provenance** : la liste
  des paramètres utilisés, leur valeur, leur marque et leur source déclarée.

*Cette exigence est propre à ce dépôt. Le modèle repose majoritairement sur des
estimations ; un résultat qui ne dit pas de quoi il est fait serait présenté
comme une mesure alors qu'il n'en est pas une.*

### ENF-6 — Portabilité et dépendances

- ENF-6.1 — Rust stable, sans dépendance à une bibliothèque système
  (BLAS/LAPACK non requis).
- ENF-6.2 — Compile et passe ses tests sur Linux et macOS.
- ENF-6.3 — Les dépendances sont épinglées et leur nombre reste faible.

### ENF-7 — Observabilité

- ENF-7.1 — Journalisation structurée par niveaux, sans coût en chemin chaud.
- ENF-7.2 — Le mode `--dry-run` valide la configuration, imprime le rapport de
  provenance et la dimension allouée, et s'arrête sans calculer.

### ENF-8 — Documentation

- ENF-8.1 — Chaque terme de l'hamiltonien est documenté dans le code par une
  référence explicite à la section d'ANL-006 dont il provient.
- ENF-8.2 — Le fichier de configuration de référence est commenté paramètre par
  paramètre, avec sa provenance et son rationnel.

---

## 3. Hors périmètre — explicitement

- **La conversion voix → sièges.** Elle exige les résultats de 2022 transposés
  sur la carte à 127 circonscriptions, qui n'ont pas été dépouillés. Le
  programme produit des **parts de vote agrégées**, pas une élection.
- **L'estimation des paramètres à partir de données.** Aucune procédure
  d'inférence ou d'ajustement n'est prévue en version 1.
- **L'interface graphique.** Sortie tabulaire uniquement ; la visualisation est
  faite ailleurs.
- **Toute forme de collecte de données réelles**, de suivi de comptes ou
  d'interaction avec des plateformes. Le programme lit des fichiers de
  configuration et écrit des tableaux, et rien d'autre.
