---
type: fondation
id: FND-014
titre: "Théorie du contrôle optimal"
version: 0.1.0
status: actif
date: 2026-08-27
---

# FND-014 - Théorie du contrôle optimal

- **Objectif** : établir ce que coûte un contrôle et comment on calcule le
  moins coûteux, y compris pour des systèmes quantiques et des réseaux. Pour
  qui : quiconque doit évaluer la **faisabilité** d'une opération sur un
  système social — c'est-à-dire répondre à la question « combien faudrait-il
  d'énergie, appliquée où, pendant combien de temps ? » plutôt qu'à la
  question « est-ce possible en principe ? », qui n'apprend rien.

## Note de rigueur

Cette fondation repose sur des **résultats mathématiques démontrés** et sur
des **résultats numériques publiés dans des revues de premier plan**. C'est,
avec FND-013, le corpus le plus solide du dépôt.

**Vérifié en ligne le 2026-08-27** :
- Gang Yan, Jie Ren, Ying-Cheng Lai, Choy-Heng Lai, Baowen Li, « Controlling
  complex networks: How much energy is needed? », *Physical Review Letters*,
  vol. 108, article 218703, 2012 (arXiv:1204.2401) — lois d'échelle pour les
  bornes inférieure et supérieure de l'énergie de contrôle ;
- Gang Yan, Georgios Tsekenis, Baruch Barzel, Jean-Jacques Slotine, Yang-Yu
  Liu, Albert-László Barabási, « Spectrum of controlling and observing complex
  networks », *Nature Physics*, vol. 11, p. 779-786, 2015 (arXiv:1503.01160) —
  **résultat central de cette fondation** : si tous les nœuds sont pilotés
  directement, l'énergie maximale croît de façon sous-linéaire avec la taille
  du système ; si le contrôle passe par un **seul** nœud, l'énergie devient
  prohibitive dans certaines directions, croissant **exponentiellement** avec
  la taille ; entre les deux, l'énergie maximale décroît exponentiellement à
  mesure qu'on ajoute des nœuds pilotes ;
- l'existence d'une littérature dédiée au coût énergétique du contrôle des
  **réseaux sociaux**, incluant l'effet des agents inflexibles et des
  comportements de conformité ;
- la chronologie et la nature des méthodes de contrôle optimal quantique
  (GRAPE, 2005 ; CRAB, 2011, raffiné en dCRAB en 2015 ; méthode de Krotov) et
  l'existence de la revue de S. J. Glaser et al., *European Physical Journal
  D*, vol. 69, n° 12, 2015.

**Non vérifié dans cette session** : Pontryagin, Bellman, Kalman,
Bertsekas, Sutton et Barto, Rabitz, Judson et Rabitz, Khaneja et al. — corpus
de manuel, donné de mémoire.

**Avertissement d'usage.** Comme en FND-013, le transfert au social est une
analogie. Mais **un résultat d'impossibilité ou de coût se transfère mieux
qu'une recette** : si le contrôle par peu de nœuds coûte une énergie
exponentielle dans un réseau bien décrit, il n'y a aucune raison de croire
qu'il coûterait moins dans un réseau mal décrit.

Vitesse de vieillissement : **très lente** pour la théorie ; **moyenne** pour
le contrôle des réseaux et le contrôle quantique.

## Cadrage

**Dans le périmètre.** Le calcul des variations et ses deux héritiers — le
principe du maximum et la programmation dynamique ; le régulateur quadratique
linéaire et le filtrage optimal ; la commande prédictive ; le contrôle optimal
stochastique et son lien avec l'apprentissage par renforcement ; le contrôle
optimal quantique, y compris des systèmes ouverts ; le coût énergétique du
contrôle des réseaux.

**Hors périmètre.** Les fondements du contrôle (stabilité, rétroaction,
commandabilité), traités en FND-013. L'optimisation numérique générale.

**Définitions de travail.**

- *Fonctionnelle de coût* : ce qu'on cherche à minimiser — typiquement une
  intégrale combinant l'écart à l'objectif et l'effort de commande. **Le
  choix de cette fonctionnelle est le choix politique déguisé en choix
  technique** ; tout le reste n'est que calcul.
- *Énergie de contrôle* : intégrale du carré de la commande. C'est la mesure
  standard du coût d'une intervention, et la grandeur dont on démontre les
  lois d'échelle.
- *Horizon* : durée sur laquelle on optimise. Fini ou infini, fixe ou
  glissant.
- *État adjoint / co-état* : variable duale du principe du maximum, qui porte
  le « prix marginal » de l'état à chaque instant.
- *Bang-bang* : commande optimale saturée en permanence à l'une de ses
  bornes, typique quand le coût est linéaire en la commande. **Traduction
  sociale : dans certains régimes, l'action optimale est tout ou rien, jamais
  dosée.**

## Corps

### 1. La théorie, sa portée, ses résultats et ses usages

**1.1 Les deux voies royales.**

*Le principe du maximum de Pontryagin* (Pontryagin, Boltyanskii, Gamkrelidze
et Mishchenko, années 1950-1962). Condition **nécessaire** d'optimalité : le
long d'une trajectoire optimale, la commande maximise à chaque instant un
hamiltonien construit à partir de l'état et d'un état adjoint. C'est
l'extension du calcul des variations aux commandes contraintes, et c'est ce
qui produit les solutions **bang-bang** lorsque la commande entre linéairement.

*La programmation dynamique de Bellman* (1957). Principe d'optimalité : toute
sous-trajectoire d'une trajectoire optimale est elle-même optimale. Conduit à
l'équation de Hamilton-Jacobi-Bellman, dont la solution — la fonction de
valeur — donne la commande optimale **en boucle fermée**, pour tout état. Prix
à payer : la **malédiction de la dimension**, l'équation devenant insoluble
dès que l'état a plus de quelques composantes.

*Les deux voies se répondent* : Pontryagin donne une trajectoire (boucle
ouverte, calcul léger), Bellman donne une politique (boucle fermée, calcul
lourd). Pour un système social, où l'état est de très grande dimension et mal
observé, seule la première est calculable — ce qui signifie qu'une stratégie
d'attaque planifiée serait, formellement, une commande **en boucle ouverte**,
donc dépourvue de toute robustesse aux écarts de modèle. C'est une remarque
propre à ce dépôt, et elle est lourde de conséquences pour l'évaluation de
faisabilité.

**1.2 Le cas linéaire-quadratique, et son piège.**

*LQR* : dynamique linéaire, coût quadratique ; la commande optimale est un
retour d'état linéaire dont le gain se calcule par une équation de Riccati.
Résultat d'une élégance rare, et la brique de base de l'ingénierie.
*Filtre de Kalman* (1960) : estimateur optimal de l'état sous bruits gaussiens.
*LQG* et **principe de séparation** : on conçoit indépendamment l'estimateur
et le régulateur, et on les combine sans perte d'optimalité.
**Le piège** : le résultat de Doyle (1978, voir FND-013) — le LQG n'offre
aucune garantie de marge de robustesse. L'optimalité selon un critère et la
robustesse aux erreurs de modèle sont deux choses différentes, et la première
n'implique pas la seconde.

**1.3 Commande prédictive.**

À chaque pas de temps : résoudre un problème de contrôle optimal sur un
horizon glissant, appliquer uniquement la première commande, mesurer,
recommencer. C'est la méthode dominante dans l'industrie, parce qu'elle gère
naturellement les contraintes et parce que la ré-optimisation permanente
compense les erreurs de modèle. **C'est aussi la structure la plus plausible
pour un mécanisme de contrôle social défendable** : horizon court,
réoptimisation continue, contraintes explicites — plutôt qu'un plan optimal
calculé une fois.

**1.4 Stochastique et apprentissage.**

*Contrôle optimal stochastique* : la fonctionnelle de coût devient une
espérance ; l'équation HJB acquiert un terme du second ordre. Cadre de la
finance mathématique (Merton) et du filtrage non linéaire.
*Apprentissage par renforcement* : programmation dynamique approchée quand le
modèle est inconnu, exploré par essais. Bertsekas d'un côté, Sutton et Barto
de l'autre, ont établi que **contrôle optimal et apprentissage par
renforcement sont la même théorie sous deux vocabulaires**. Conséquence pour
ce projet : un attaquant qui n'a pas de modèle de la société mais qui peut
essayer, mesurer et recommencer fait de l'apprentissage par renforcement — et
c'est vraisemblablement la description la plus réaliste d'une opération
d'influence réelle, qui teste des messages et retient ce qui fonctionne.
Cette lecture a un corollaire défensif immédiat : **priver l'attaquant de son
signal de récompense — les métriques d'engagement — dégrade sa boucle
d'apprentissage plus sûrement que de bloquer ses messages.**

**1.5 Le contrôle optimal quantique — le pont direct avec FND-007.**

Objectif : trouver le champ de commande, typiquement une impulsion laser
mise en forme, qui amène un système quantique d'un état initial à un état
cible, en maximisant une fidélité sous contrainte de puissance et de durée.

*Méthodes.* **GRAPE** (montée de gradient sur des impulsions découpées en
créneaux, 2005) rend le domaine accessible ; **Krotov** garantit sous
conditions une convergence monotone ; **CRAB** (2011), puis **dCRAB** (2015),
optimise dans une base tronquée aléatoire, ce qui convient aux systèmes où
seul un simulateur est disponible. La revue de Glaser et al. (2015) fait le
point sur l'ensemble.

*Contrôle en boucle fermée sur l'expérience* : dès les années 1990, la
combinaison d'un façonneur d'impulsions et d'un algorithme d'apprentissage a
permis d'optimiser des rendements de réaction **sans modèle** du système,
l'expérience elle-même servant de fonction objectif (approche de Judson et
Rabitz). Le parallèle avec le point 1.4 est exact.

*Systèmes ouverts.* Lorsque le système est couplé à un environnement, la
dynamique suit une équation maîtresse de type Lindblad (GKSL), et le contrôle
doit composer avec la **décohérence**. Deux résultats structurants : il existe
des sous-espaces sans décohérence qu'il vaut mieux exploiter que combattre ;
et il existe des **limites de vitesse quantiques** — un temps minimal
incompressible pour aller d'un état à un autre, quelle que soit l'énergie
disponible.
**C'est le pont direct avec FND-007**, où Khrennikov (2023) couple le laser
social à une équation maîtresse quantique. Si le formalisme est pris au
sérieux, alors le contrôle optimal d'un système quantique ouvert est
exactement la boîte à outils qui s'applique — et elle vient avec ses
impossibilités : décohérence irréductible, limite de vitesse, coût croissant
avec la fidélité exigée.

**1.6 Le coût énergétique du contrôle des réseaux — la section décisive.**

C'est le résultat le plus important de cette fondation pour l'évaluation de
faisabilité du projet.

*Yan, Ren, Lai, Lai et Li* (*PRL*, 2012, vérifié) établissent et valident des
lois d'échelle pour les bornes inférieure et supérieure de l'énergie
nécessaire au contrôle d'un réseau complexe.

*Yan, Tsekenis, Barzel, Slotine, Liu et Barabási* (*Nature Physics*, 2015,
vérifié) précisent le tableau, et le résultat est net :
- si **tous** les nœuds sont pilotés directement, l'énergie maximale croît de
  façon **sous-linéaire** avec la taille du système — le contrôle est
  énergétiquement réalisable ;
- si le contrôle passe par un **seul** nœud, l'énergie devient
  **prohibitive** dans certaines directions de l'espace d'état, croissant
  **exponentiellement** avec la taille du système ;
- entre les deux, l'énergie maximale **décroît exponentiellement** à mesure
  qu'on ajoute des nœuds pilotes.

*Conséquence directe, et elle est sévère pour toute thèse d'attaque à faible
coût.* La commandabilité structurelle de FND-013 disait qu'un grand réseau est
presque toujours commandable en droit. Ce résultat-ci dit que **cette
commandabilité de droit se paie une énergie exponentielle si l'on entre par
peu de points**. Un attaquant disposant de quelques points d'entrée peut, en
principe, amener le système n'importe où ; en pratique, il ne peut l'amener
que dans les rares directions énergétiquement accessibles. **La question
opérationnelle n'est donc pas « peut-on contrôler la société », mais « quelles
sont les quelques directions bon marché », et cette question-là est
répondable.** C'est, à mon sens, la meilleure formulation disponible du
problème que ce dépôt s'est donné.

*Il existe en outre une littérature dédiée au coût énergétique du contrôle des
réseaux sociaux*, incluant l'effet des agents inflexibles (*zealots*) et des
comportements de conformité — deux notions qui recoupent exactement les
inflexibles de Galam (FND-008) et la conformité d'Asch (FND-009). **Cette
littérature est le point de jonction le plus direct entre tout le corpus de ce
dépôt, et elle n'a pas encore été dépouillée.**

### 2. Évolution de la discipline, intervenants et contributions

**Le calcul des variations (1696-1900).** Problème de la brachistochrone
(Jean Bernoulli, 1696) ; *Euler* et *Lagrange* établissent l'équation qui
porte leurs noms ; *Hamilton* et *Jacobi* donnent la formulation qui
resurgira dans l'équation HJB. *Weierstrass* : conditions nécessaires fortes.

**La naissance du contrôle optimal (1950-1965).** Contexte : guidage de
missiles et course à l'espace, des deux côtés du rideau de fer.
*Lev Pontryagin* et son équipe (Boltyanskii, Gamkrelidze, Mishchenko)
formulent le principe du maximum — **contribution majeure : traiter les
contraintes sur la commande, ce que le calcul des variations classique ne
savait pas faire**. *Richard Bellman* invente la programmation dynamique et
nomme la malédiction de la dimension. *Rudolf Kalman* fournit le LQR, le
filtre optimal et le principe de séparation. **En une quinzaine d'années, la
discipline acquiert la totalité de son socle.**

**Extensions (1965-1990).** *Robert Merton* : contrôle optimal stochastique
en finance. *Wendell Fleming* et *Raymond Rishel* : formalisation
mathématique. *Arthur Bryson* et *Yu-Chi Ho* (*Applied Optimal Control*,
1969) : le manuel qui diffuse la théorie dans l'ingénierie. *John Doyle*
(1978) : la douche froide sur la robustesse du LQG. Naissance de la commande
prédictive dans l'industrie pétrochimique.

**Contrôle quantique (1985-2015).** *Herschel Rabitz* : programme de contrôle
cohérent des réactions chimiques. *David Tannor* et *Stuart Rice* : contrôle
par interférence de chemins. *Judson et Rabitz* (1992) : contrôle en boucle
fermée sur l'expérience, par algorithme d'apprentissage, **sans modèle**.
*Khaneja, Reiss, Kehlet, Schulte-Herbrüggen, Glaser* (2005) : GRAPE, qui rend
la méthode utilisable en résonance magnétique puis en information quantique.
*Krotov*, puis *CRAB* (2011) et *dCRAB* (2015). *Glaser et al.* (2015) : revue
de synthèse et feuille de route européenne. **Contribution collective** :
faire du contrôle optimal l'outil standard de la manipulation quantique, avec
ses bornes propres (limites de vitesse, décohérence).

**Contrôle des réseaux et apprentissage (2011-2026).** *Liu, Slotine,
Barabási* (2011) posent la commandabilité (FND-013) ; *Yan et al.* (2012,
2015) posent le coût, et **c'est le coût qui tranche**. *Bertsekas*,
*Sutton et Barto* : unification du contrôle optimal et de l'apprentissage par
renforcement. Depuis 2018 : contrôle piloté par les données, apprentissage
avec garanties, et une littérature spécifique sur le coût énergétique du
contrôle des réseaux sociaux.

**Ce sur quoi la discipline ne s'entend pas.**
- Les méthodes d'apprentissage peuvent-elles offrir des garanties comparables
  à celles du contrôle classique ?
- Les lois d'échelle énergétiques établies sur des dynamiques linéaires
  valent-elles pour des dynamiques sociales fortement non linéaires ? **C'est
  la question qui décide de la transposabilité du résultat central de cette
  fondation, et elle est ouverte.**
- Comment choisir une fonctionnelle de coût quand l'objectif est social ?
  Question normative que la théorie n'aborde pas.

### 3. Questions de recherche principales, et qui d'autre s'en occupe

**Q1 — Quel est le coût minimal d'un contrôle donné ?**
*Autres disciplines* : physique statistique et thermodynamique (coût
énergétique du traitement de l'information, principe de Landauer) ; théorie de
l'information ; économie (coût d'opportunité).

**Q2 — Comment contrôler sans modèle ?**
*Autres disciplines* : apprentissage automatique ; statistique
expérimentale (plans d'expérience séquentiels) ; contrôle quantique en boucle
fermée sur l'expérience ; **marketing et croissance produit**, qui font
exactement cela à grande échelle depuis vingt ans.

**Q3 — Où placer les entrées pour minimiser l'énergie ?**
*Autres disciplines* : science des réseaux ; optimisation combinatoire ;
biologie des systèmes ; **maximisation d'influence en informatique**
(FND-003), qui est le même problème posé par l'autre bout.

**Q4 — Comment contrôler un système ouvert et bruité ?**
*Autres disciplines* : physique des systèmes quantiques ouverts ; filtrage
stochastique ; ingénierie de la fiabilité ; **et FND-007**, dont le modèle de
2023 repose sur une équation maîtresse de ce type.

**Q5 — Quelles sont les limites de vitesse d'un contrôle ?**
*Autres disciplines* : physique fondamentale (limites de vitesse quantiques) ;
théorie de l'information ; thermodynamique hors équilibre. **Question directe
pour ce projet : existe-t-il un temps minimal incompressible pour retourner
une opinion collective, quelle que soit l'énergie investie ?** Aucune réponse
n'existe, et poser la question serait déjà une contribution.

**Q6 — Comment choisir la fonctionnelle de coût ?**
*Autres disciplines* : philosophie morale ; théorie du choix social
(FND-005) ; économie du bien-être ; droit. **La théorie du contrôle est
muette ici, et c'est exactement là que se loge la décision politique.**

## Synthèse

Six résultats à retenir.

1. **Le contrôle par peu de points d'entrée coûte une énergie exponentielle**
   (Yan et al., 2015). Piloter tous les nœuds coûte une énergie sous-linéaire
   en la taille ; piloter par un seul nœud rend certaines directions
   énergétiquement prohibitives, avec une croissance exponentielle. Ajouter
   des nœuds pilotes fait décroître ce coût exponentiellement. **C'est le
   résultat quantitatif le plus important de tout le dépôt pour évaluer la
   faisabilité d'une attaque.**
2. **La bonne question n'est pas la possibilité mais la direction.** Puisque
   presque tout grand réseau est commandable en droit (FND-013) mais coûteux
   en fait, la question opérationnelle devient : *quelles sont les rares
   directions énergétiquement bon marché ?* Cette question est formulable et
   calculable, et elle donne au projet un objet de simulation précis.
3. **Bellman est incalculable, Pontryagin est fragile.** Sur un système
   social, seule la voie en boucle ouverte est calculable, et elle n'offre
   aucune robustesse aux écarts de modèle. Une stratégie planifiée d'avance
   est structurellement fragile ; seule une stratégie réoptimisée en continu
   ne l'est pas.
4. **Un attaquant sans modèle fait de l'apprentissage par renforcement.**
   C'est la description la plus réaliste d'une opération d'influence :
   essayer, mesurer, retenir. Corollaire défensif inhabituel et fort :
   **couper le signal de récompense — les métriques d'engagement publiques —
   dégrade la boucle d'apprentissage de l'attaquant plus efficacement que de
   bloquer ses messages.**
5. **Le contrôle optimal quantique ouvert est la boîte à outils cohérente
   avec FND-007** — et elle vient avec ses impossibilités : décohérence
   irréductible, limites de vitesse, coût croissant avec la fidélité exigée.
   Si l'on prend au sérieux le formalisme du laser social, il faut en prendre
   au sérieux les bornes.
6. **La fonctionnelle de coût est le choix politique.** Tout le reste est du
   calcul. Une présentation qui ne dit pas ce qu'elle minimise, et pour qui,
   cache sa thèse dans ses équations.

## Limites

- **Les lois d'échelle énergétiques sont établies sur des dynamiques
  linéaires.** Leur transposition à une dynamique sociale non linéaire, à
  seuils et à rétroactions, n'est **pas** établie. C'est la limite la plus
  sérieuse de cette fondation, et elle porte précisément sur son résultat
  central. Elle doit être énoncée dans tout livrable qui s'appuie dessus.
- **L'unité d'énergie n'a pas de traduction sociale.** L'intégrale du carré de
  la commande se mesure en unités du modèle ; personne ne sait la convertir en
  budget, en heures de travail ou en portée publicitaire. Sans cette
  conversion, le résultat reste **qualitatif** : il ordonne des stratégies, il
  ne chiffre pas une campagne.
- **Le corpus classique n'a pas été re-vérifié.** Pontryagin, Bellman, Kalman,
  Bryson et Ho, Rabitz, Bertsekas : références de manuel données de mémoire.
- **La littérature sur le coût énergétique du contrôle des réseaux sociaux
  n'a pas été dépouillée**, alors qu'elle est le point de jonction le plus
  direct entre les fondations du dépôt — elle traite explicitement des agents
  inflexibles et de la conformité. C'est la première lecture à faire pour la
  suite.
- **Rien sur l'observation.** Toute cette théorie suppose que l'on sait où en
  est le système. FND-007 n'offre aucun instrument de mesure de l'énergie
  sociale. Tant que ce verrou n'est pas levé, le contrôle optimal d'un laser
  social reste un exercice formel — ce qui n'est pas rien, mais qui doit être
  dit.

## Sources

**Vérifiées en ligne le 2026-08-27.**
- Gang Yan, Jie Ren, Ying-Cheng Lai, Choy-Heng Lai, Baowen Li, « Controlling
  complex networks: How much energy is needed? », *Physical Review Letters*,
  vol. 108, art. 218703, 2012 ; arXiv:1204.2401.
  https://arxiv.org/abs/1204.2401
- Gang Yan, Georgios Tsekenis, Baruch Barzel, Jean-Jacques Slotine, Yang-Yu
  Liu, Albert-László Barabási, « Spectrum of controlling and observing complex
  networks », *Nature Physics*, vol. 11, p. 779-786, 2015 ; arXiv:1503.01160.
  **Résultat central : coût exponentiel du contrôle par peu de nœuds.**
  https://www.nature.com/articles/nphys3422
- « Energy-Aware Controllability of Complex Networks », *Annual Review of
  Control, Robotics, and Autonomous Systems*. Synthèse du sous-domaine.
  https://www.annualreviews.org/content/journals/10.1146/annurev-control-042920-014957
- « How zealots affect the energy cost for controlling complex social
  networks », arXiv:2107.11744 ; « Energy cost study for controlling complex
  social networks with conformity behavior », arXiv:2101.03828. **Point de
  jonction direct avec FND-008 (inflexibles) et FND-009 (conformité) ; non
  dépouillés.**
- S. J. Glaser et al., *European Physical Journal D*, vol. 69, n° 12, 2015 :
  revue de référence sur le contrôle optimal quantique. Chronologie vérifiée
  des méthodes : GRAPE (2005), CRAB (2011), dCRAB (2015), Krotov.

**Non vérifiées dans cette session — corpus classique.**
- Lev Pontryagin, Vladimir Boltyanskii, Revaz Gamkrelidze, Evgenii
  Mishchenko, *The Mathematical Theory of Optimal Processes*, 1962.
  **Principe du maximum.**
- Richard Bellman, *Dynamic Programming*, Princeton UP, 1957. **Principe
  d'optimalité, équation HJB, malédiction de la dimension.**
- Rudolf Kalman, travaux de 1960 : LQR, filtre optimal, principe de
  séparation.
- Arthur Bryson et Yu-Chi Ho, *Applied Optimal Control*, 1969. Manuel de
  diffusion.
- Wendell Fleming et Raymond Rishel, *Deterministic and Stochastic Optimal
  Control*, 1975.
- Dimitri Bertsekas, *Dynamic Programming and Optimal Control* ; Richard
  Sutton et Andrew Barto, *Reinforcement Learning: An Introduction*.
  **Unification contrôle optimal / apprentissage par renforcement.**
- Herschel Rabitz, programme de contrôle cohérent ; Richard Judson et Herschel
  Rabitz, contrôle en boucle fermée sur l'expérience, *Physical Review
  Letters*, 1992.
- Navin Khaneja, Timo Reiss, Cindie Kehlet, Thomas Schulte-Herbrüggen, Steffen
  Glaser, méthode GRAPE, *Journal of Magnetic Resonance*, 2005.
- John Doyle, « Guaranteed margins for LQG regulators: none », 1978
  (voir FND-013).

**Relations.** Référence FND-013 (fondements du contrôle), FND-007 (laser
social et équation maîtresse), FND-008 (inflexibles, réseaux), FND-003
(maximisation d'influence) ; fournit le cadre de l'évaluation de faisabilité
et le paramétrage du script de simulation attendu par la session.
