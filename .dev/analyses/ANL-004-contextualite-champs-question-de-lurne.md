---
type: analyse
id: ANL-004
titre: "Contextualité, champs et question de l'urne : une modélisation quantum-like du problème électoral québécois"
version: 0.1.0
status: actif
date: 2026-08-28
---

# ANL-004 - Contextualité, champs et question de l'urne : une modélisation quantum-like du problème électoral québécois

> La question de l'urne est un **choix de base de mesure**. Les champs
> québécois admettent une grande famille de questions compatibles autour de la
> légitimité, et **une incompatibilité irréductible** — l'État contre le
> marché — sur laquelle aucun parti ne peut laser des deux côtés à la fois.

## Question posée

Trois questions enchaînées, posées par la session.

1. Les deux conditions avancées — l'existence de **contextes intriqués** et
   celle d'**états propres** — sont-elles les bonnes conditions pour qu'un
   système social soit modélisable dans le formalisme quantum-like, et le
   système électoral québécois les satisfait-il ?
2. Quelle modélisation formelle correspond aux hypothèses posées : espace
   d'enjeux intriqué, champs bourdieusiens comme unité atomique, dynamique
   électorale comme lutte inter-champ, espérance de votes comme somme
   pondérée par champ ?
3. Quelles **questions de l'urne non contradictoires**, optimisées pour chaque
   champ québécois, cette modélisation permet-elle de formuler — et le tout en
   termes d'effet de laser social ?

## Méthode

### Ce qui a été examiné

- **FND-007** (programme quantum-like, statut) et **FND-021** (mécanisme du
  laser social, appareil formel) pour le formalisme.
- **ANL-001** pour les onze champs, leur nomos, leur capital, leur illusio,
  leurs effectifs et leurs recoupements.
- **ANL-002** pour les découpages alternatifs et leur statut de mesurabilité.
- **ANL-003** et **FND-022** pour l'offre réelle des partis en 2026.
- **FND-004** (Riker, *heresthetics* ; Zaller) et **FND-001** (luttes de
  classement) pour les équivalents classiques.

### Convention de marquage

Reprise d'ANL-001 : **[V]** vérifié, **[D]** dérivé par calcul, **[E]**
estimation. **Aucun paramètre du modèle proposé ici n'est mesuré.** Le modèle
est une **construction formelle**, pas un résultat empirique, et la section
« Limites » ne le nuance pas : elle le dit.

### Une décision de modélisation, posée d'emblée

L'hypothèse de la session fait du champ l'unité atomique du problème
électoral. ANL-001 établissait qu'un champ, au sens strict, est peuplé
d'agents spécialisés — quelques milliers — et non d'électeurs. **Cette analyse
adopte donc une définition élargie, explicitement différente de celle
d'ANL-001** : le « champ » y désigne le champ **et sa population sous
emprise**, c'est-à-dire l'ensemble des électeurs dont les dispositions de vote
sont structurées par les catégories de ce champ. Sans cette convention, les
effectifs ne sont pas ceux d'un électorat et la formule d'espérance de votes
n'a pas de sens. **Cette convention est un choix, il est révisable, et il doit
être rappelé chaque fois que les nombres de cette analyse sont cités.**

## Constats

### 1. Les deux conditions posées sont bonnes, mais l'une est mal nommée

La session pose deux conditions : des **contextes intriqués** et des **états
propres**.

**Sur les états propres : la condition est exacte et non triviale.** Un
observable n'est défini que par une base d'états propres. Pour l'enjeu
« économie », il faut décider ce que sont les **positions pures** —
celles où la réponse est certaine. Ce n'est pas un détail technique : c'est
la décision de modélisation la plus lourde, parce qu'elle fixe ce qui compte
comme une position et ce qui n'est qu'une superposition. Une bonne part de ce
que Zaller (FND-004) appelle les non-attitudes est exactement cela : des états
qui ne sont propres pour aucun observable disponible.

**Sur les « contextes intriqués » : l'intuition est juste, le nom recouvre
deux propriétés distinctes**, et les distinguer change le modèle.

- La **non-commutativité** (incompatibilité) concerne **un seul système mesuré
  de deux façons**. Deux observables ne commutent pas quand mesurer l'un
  modifie l'état pertinent pour l'autre, si bien qu'il n'existe **aucune
  distribution jointe** des deux. C'est exactement ce que décrit l'exemple
  donné : demander « quelle importance accordez-vous à l'économie ? » puis
  « quelle importance accordez-vous à l'environnement ? » ne donne pas le même
  résultat que l'ordre inverse. **C'est la propriété qui fonde la question de
  l'urne**, et c'est le seul endroit du programme quantum-like qui dispose d'un
  appui empirique fort (FND-007 : contrainte quantitative sur les effets
  d'ordre des questions, vérifiée sur un large corpus de sondages réels).
- L'**intrication** (non-séparabilité) concerne **deux sous-systèmes** dont
  l'état conjoint ne se factorise pas. C'est la propriété pertinente **entre
  champs** : si l'état du champ syndical et celui du champ économique ne se
  factorisent pas, alors aucune intervention ne peut porter sur l'un sans
  déplacer l'autre. C'est précisément la « lutte inter-champ » posée par la
  session.

**Le système décrit possède les deux**, et elles opèrent à deux niveaux
différents : la non-commutativité entre **enjeux**, l'intrication entre
**champs**. La condition posée par la session est donc satisfaite, à condition
de la dédoubler.

### 2. La question de l'urne est un choix de base de mesure

C'est le constat central de cette analyse, et il est exact au sens du
formalisme.

Un parti ne cherche pas, principalement, à déplacer l'état de l'électeur. Il
cherche à déterminer **quel observable sera mesuré** le jour du scrutin.
Puisque les observables « importance de l'économie », « importance de
l'environnement », « importance de l'identité » ne commutent pas, **la
distribution des résultats dépend de l'observable choisi**, et il n'existe pas
de distribution jointe qui les réconcilierait.

Formellement : soit `ψ` l'état de l'électorat, et `{Q_a}` la famille des
questions de l'urne possibles. Le résultat du vote est
`P(parti p | Q_a) = ‖Π_p^{(a)} ψ‖²`, où `Π_p^{(a)}` est le projecteur associé
au parti `p` dans la base propre de `Q_a`. **Changer `a` change la
distribution sans changer `ψ`.**

Trois traditions disent la même chose par trois chemins indépendants, et
cette convergence est le meilleur argument en faveur du modèle :
- **Riker** (FND-004) : l'*heresthetics*, l'art de gagner en restructurant la
  dimension du débat plutôt qu'en persuadant.
- **Bourdieu** (FND-001) : les luttes de classement portent sur la définition
  légitime du champ, non sur les positions dans le champ.
- **Zaller** (FND-004) : la réponse d'enquête est un échantillon des
  considérations rendues accessibles au moment de la question.

**Le formalisme quantum-like n'invente donc rien ici ; il donne un cadre
mathématique unique à ce que trois disciplines avaient établi séparément.**
C'est son apport réel, et il ne faut pas en revendiquer davantage.

### 3. Le modèle : espace d'état, observables, mesure

**3.1 Espace d'état.** Les champs étant l'unité atomique, l'espace d'état du
système est le produit tensoriel des espaces de champ :

> `H = H_1 ⊗ H_2 ⊗ … ⊗ H_11`

Un état `Ψ` de l'électorat québécois est un vecteur de `H`. **Il est en
général intriqué** : `Ψ ≠ ψ_1 ⊗ ψ_2 ⊗ … ⊗ ψ_11`. C'est la formalisation exacte
de l'hypothèse « aucun enjeu n'est isolé des autres ».

**3.2 Observables.** Chaque enjeu sociétal `a` est un observable hermitien
`Q_a` sur `H`, dont les états propres sont les **positions pures** sur cet
enjeu. Deux enjeux `a` et `b` sont **compatibles** si `[Q_a, Q_b] = 0`, et
**incompatibles** sinon. La compatibilité, dans le langage de la session,
c'est la **non-contradiction**.

**3.3 La mesure.** Le vote est une mesure projective : irréversible, et elle
modifie l'état. C'est ce qui distingue un scrutin d'un sondage répété — et
c'est aussi pourquoi les sondages, qui mesurent sans projeter définitivement,
**perturbent** l'état qu'ils prétendent observer. Le résultat de Bourdieu sur
l'artefact sondagier (FND-001) reçoit ici une expression formelle.

**3.4 Le pompage.** Une campagne agit de deux façons distinctes, et les
confondre est l'erreur principale :
- **Agir sur `Ψ`** — déplacer l'état : c'est la persuasion. FND-011 établit
  que son effet est petit et peu durable.
- **Agir sur `a`** — choisir l'observable : c'est la question de l'urne. Coût
  faible, effet potentiellement grand.

**Le modèle prédit donc que l'essentiel de l'effort rationnel d'une campagne
porte sur `a`, non sur `Ψ`** — et c'est ce que la littérature empirique
observe (effets persuasifs minimaux contre effets d'agenda robustes, FND-004).

### 4. L'espérance de votes, et la correction des recoupements

La session propose : espérance de votes = somme, sur les champs, de la
probabilité de vote multipliée par le nombre d'électeurs du champ, en tenant
compte des recoupements.

**La formule naïve est fausse par un facteur ~2,7.** ANL-001 établit que la
somme des emprises est de ≈ 17,3 M pour 6,4 M d'électeurs [D sur base E].
Sommer les `N_j` compte chaque électeur 2,7 fois en moyenne.

**Correction proposée.** À chaque électeur `i` on associe un vecteur de poids
`w_ij ≥ 0` sur les champs, avec `Σ_j w_ij = 1` : c'est la part de sa décision
qui se joue dans le cadre du champ `j`. On définit la **masse effective** du
champ :

> `M_j = Σ_i w_ij`, avec la propriété exacte `Σ_j M_j = 6 400 000`

et l'espérance de votes devient :

> `E[votes pour p] = Σ_j M_j(Q_a) · P(p | j, Q_a)`

**Le point décisif** : `w_ij` **n'est pas une constante**. C'est l'amplitude
de saillance du champ `j` chez l'électeur `i`, **et elle dépend de la question
de l'urne** :

> `w_ij(Q_a) = |⟨ j | ψ_i(Q_a) ⟩|²`

C'est une structure de règle de Born, et c'est ce qui articule les deux
éléments posés par la session : la question de l'urne redistribue les masses
effectives entre champs, et la somme reste invariante à 6,4 M. **Une campagne
ne crée pas d'électeurs ; elle déplace la masse d'un champ vers un autre.**

**Masses effectives de référence**, sous l'hypothèse grossière d'un poids
uniforme `w_ij = 1/n_i` (facteur 6,4/17,33 = 0,369) :

| Champ | Emprise `N_j` [E] | Masse effective `M_j` [D sur base E] |
|---|---|---|
| Journalistique | 4 300 000 | **1 590 000** |
| Numérique | 3 500 000 | **1 290 000** |
| Religieux | 2 500 000 | **920 000** |
| Académique | 1 750 000 | **650 000** |
| Culturel | 1 500 000 | **550 000** |
| Bureaucratique | 1 100 000 | **410 000** |
| Syndical | 1 000 000 | **370 000** |
| Associatif | 800 000 | **300 000** |
| Économique | 550 000 | **200 000** |
| Politique | 280 000 | **100 000** |
| Juridique | 50 000 | **20 000** |
| **Total** | 17 330 000 | **6 400 000** |

**Ces nombres ne sont pas des mesures.** Ils héritent des estimations [E]
d'ANL-001 et de l'hypothèse de poids uniforme, qui est fausse par
construction — puisque tout le modèle repose sur le fait que les poids varient
avec la question posée. Ils servent à donner l'ordre des grandeurs et à
fournir un point de départ à une analyse de sensibilité.

### 5. L'enjeu existentiel de chaque champ

Pour qu'une question de l'urne entre en résonance avec un champ, elle doit,
selon l'hypothèse de la session, toucher son **enjeu existentiel**. Cette
analyse définit l'enjeu existentiel d'un champ comme ce qui, s'il était
tranché défavorablement, **détruirait le champ lui-même** — son nomos, son
capital ou son illusio — et non simplement ses intérêts.

| Champ | Enjeu existentiel | Question de l'urne résonante |
|---|---|---|
| Politique | La légitimité de la délégation représentative | **« Qui a le mandat de parler au nom du Québec ? »** |
| Journalistique | La capacité à imposer les sujets, et la survie économique | **« Qui décide de ce dont on parle ? »** |
| Religieux | Le droit à une existence publique | **« Que peut-on porter dans l'espace public ? »** |
| Académique | L'autorité de l'expertise comme fondement de décision | **« Qui a autorité pour dire ce qui est vrai ? »** |
| Syndical | La légitimité de la représentation collective du travail | **« Qui négocie pour ceux qui travaillent ? »** |
| Bureaucratique | La croyance que l'État est l'instrument légitime de l'action collective | **« L'État est-il la solution ou le problème ? »** |
| Économique | La légitimité de la création privée de richesse | **« Qui crée la richesse ? »** |
| Juridique | Que le tribunal soit le dernier mot légitime | **« Qui a le dernier mot ? »** |
| Culturel | Qu'une culture nationale distincte mérite d'être soutenue | **« Le Québec existera-t-il culturellement ? »** |
| Associatif | Que la proximité fonde une connaissance supérieure du besoin | **« Qui sait ce dont les gens ont besoin ? »** |
| Numérique | Que la portée soit la mesure de l'importance | **« Qui a le droit d'être entendu ? »** |

**Ces formulations sont des reconstructions analytiques**, dérivées des
nomos et illusio consignés en ANL-001. Elles ne sont ni des slogans, ni des
énoncés de campagne, ni testées.

### 6. La structure de compatibilité — le résultat principal

En examinant les onze questions du constat 5, une structure apparaît.

**6.1 Une grande famille compatible : la légitimité.**

Quatre à cinq questions sont **le même observable posé dans des registres
différents** :

- « Qui a le mandat ? » (politique)
- « Qui a autorité pour dire ce qui est vrai ? » (académique)
- « Qui a le dernier mot ? » (juridique)
- « Qui sait ce dont les gens ont besoin ? » (associatif)
- « Qui décide de ce dont on parle ? » (journalistique)

Elles commutent, parce qu'un même énoncé peut y répondre favorablement
simultanément **sans contradiction** : une réponse qui déplace la légitimité
vers un pôle donné les satisfait toutes ensemble. Elles forment donc une
**famille commutante**, et il existe une base propre commune.

**Masse effective cumulée de cette famille : 1 590 000 + 650 000 + 20 000 +
300 000 + 100 000 ≈ 2 660 000 [D sur base E], soit ~42 % de l'électorat.**

*C'est le résultat le plus utile de l'analyse* : il existe une méta-question —
**« qui a la légitimité de décider pour le Québec ? »** — qui projette
favorablement sur cinq champs à la fois, et c'est mathématiquement possible
parce que ces cinq champs partagent un observable.

**6.2 Une incompatibilité irréductible : l'État contre le marché.**

Deux questions **ne commutent pas** et ne peuvent pas être satisfaites
ensemble :

- « L'État est-il la solution ou le problème ? » (bureaucratique)
- « Qui crée la richesse ? » (économique)

Toute réponse qui affirme l'une nie l'autre. Et le champ **syndical** est
**intriqué** avec le bureaucratique — ANL-001 établit un recoupement de
**≈ 930 000 personnes [D]**, 14,5 % de l'électorat, et de 350 000 à 450 000 à
l'intersection à trois champs avec l'académique. L'état conjoint
`{syndical, bureaucratique}` **ne se factorise pas**.

Il en résulte deux blocs antagonistes :
- bloc `{bureaucratique, syndical}` : masse effective ≈ **780 000** ;
- bloc `{économique}` : masse effective ≈ **200 000**.

**Aucun parti ne peut laser des deux côtés de cette incompatibilité.** C'est
ce que constate ANL-003 par une tout autre voie — l'écart maximal de l'offre
de 2026 tombe exactement sur cet axe, QS à `++/++` contre le PCQ à `−−/≠≠`.
**Deux analyses indépendantes du dépôt convergent sur la même fracture, l'une
par l'offre observée, l'autre par la structure formelle.**

**6.3 Trois champs faiblement couplés.** Religieux, culturel et numérique
commutent avec la plupart des autres et peuvent être ajoutés à une famille
sans coût de contradiction — mais le religieux est fortement intriqué avec le
juridique par la loi 21, ce qui le rend instable tant que le jugement de la
Cour suprême n'est pas rendu (FND-020).

### 7. La formulation en termes de laser social

En reprenant le mécanisme de FND-021, terme à terme :

| Élément du laser | Traduction dans ce modèle |
|---|---|
| Milieu amplificateur | Un champ et sa population sous emprise |
| Écart de niveaux `ΔE` | L'**enjeu existentiel** du champ |
| Énergie de l'infon `E` | La charge portée par la question de l'urne |
| **Condition d'accord `ΔE = E`** | **La question de l'urne résonne avec l'enjeu existentiel du champ** |
| Désaccord `Δ_j` | Distance entre le cadrage proposé et l'enjeu existentiel |
| Pompage `P(t)` | La campagne : annonces, couverture, amplification algorithmique |
| Inversion de population | Majorité du champ en état de mobilisation |
| Émission stimulée | Reprise à l'identique du cadrage à l'intérieur du champ |
| Résonateur | L'écho interne du champ : ses revues, ses réseaux, ses lieux |
| **Cohérence** | **Le champ vote comme un seul bloc** |
| Saturation | Épuisement des mobilisables du champ |

**Deux conséquences propres, non présentes chez Khrennikov.**

1. **Il y a une fréquence de pompage par champ.** La condition d'accord
   `ΔE = E` étant indexée sur l'enjeu existentiel, qui diffère d'un champ à
   l'autre, un pompage unique ne peut laser plusieurs champs que si ces champs
   **partagent un observable** — c'est-à-dire s'ils appartiennent à une famille
   commutante (constat 6.1). **La compatibilité des questions de l'urne est
   donc la condition d'un pompage multi-champs cohérent.** C'est, à ma
   connaissance, la contribution originale la plus nette de cette analyse.
2. **Le seuil de FND-021 devient un seuil par champ.** `σ_seuil = κΓ/(g²⟨k⟩)`
   s'écrit `σ_seuil,j = κ_j Γ_j /(g_j² ⟨k⟩_j)` : chaque champ a sa densité de
   réseau, sa perte d'attention et son couplage propres. **Le champ dont le
   seuil est le plus bas est celui dont le réseau interne est le plus dense** —
   ce qui, sur les onze, désigne probablement le champ syndical et le champ
   académique, structurellement organisés, plutôt que les grands champs
   d'emprise diffuse.

### 8. Ce qui rendrait ce modèle faux — et c'est testable

La contrainte quantitative sur les effets d'ordre des questions (FND-007) est
**parameter-free** et a été vérifiée sur un large corpus de sondages réels. Si
la question de l'urne est bien un choix de base de mesure, alors cette
contrainte doit être satisfaite par les paires de questions d'importance
d'enjeux dans les sondages québécois.

**C'est un test faisable, peu coûteux, et falsifiant** : il suffit de sondages
québécois posant, dans des ordres contrebalancés, deux questions d'importance
d'enjeux. Si la contrainte est violée, le modèle proposé ici est faux dans son
noyau. Si elle est satisfaite, c'est le premier appui empirique québécois du
programme.

**Aucun autre élément de cette analyse n'est actuellement testable**, faute
d'instrument pour l'énergie sociale, les masses effectives et les couplages
(ANL-002, constats 2, 3, 9 ; FND-021).

## Réponse

**Aux deux conditions.** Elles sont les bonnes, à condition de dédoubler la
première : le système exige la **non-commutativité** entre enjeux — un seul
système mesuré de deux façons — et l'**intrication** entre champs — deux
sous-systèmes non séparables. Le système électoral québécois présente les
deux. La condition d'états propres est exacte et coûteuse : décider ce qu'est
une position pure sur un enjeu est la décision de modélisation la plus lourde.

**À la modélisation.** L'espace d'état est le produit tensoriel des onze
espaces de champ, où l'état de l'électorat est en général intriqué. Chaque
enjeu est un observable ; la **question de l'urne est le choix de la base de
mesure** ; le vote est une projection irréversible. L'espérance de votes
s'écrit `E[votes p] = Σ_j M_j(Q) · P(p | j, Q)` avec des **masses effectives**
`M_j` qui somment exactement à 6,4 M — correction nécessaire, faute de quoi la
formule naïve surcompte d'un facteur ~2,7. Ces masses **dépendent de la
question posée** : une campagne ne crée pas d'électeurs, elle déplace la masse
d'un champ à l'autre.

**Aux questions de l'urne.** Le constat 5 en propose une par champ, dérivée de
son enjeu existentiel. Le constat 6 établit leur structure de compatibilité,
et c'est la réponse à la contrainte de non-contradiction :

- **Une famille commutante de cinq champs** — politique, journalistique,
  académique, juridique, associatif — partage un observable unique,
  « **qui a la légitimité de décider pour le Québec ?** », pour une masse
  effective cumulée d'environ **2 660 000 électeurs, soit ~42 %**. Un pompage
  unique peut y produire une cohérence multi-champs sans contradiction.
- **Une incompatibilité irréductible** oppose le bloc
  `{bureaucratique, syndical}` (~780 000 de masse effective, et 930 000
  personnes au recoupement) au champ `{économique}` (~200 000). **Aucune
  formulation ne satisfait les deux.** Tout parti doit choisir, et ce choix est
  le vrai clivage structurel du système québécois.
- **Trois champs faiblement couplés** — religieux, culturel, numérique —
  peuvent être ajoutés à une famille sans coût, sauf le religieux, instable
  tant que le jugement sur la loi 21 n'est pas rendu.

**En termes de laser social.** Chaque champ est un milieu amplificateur dont
l'écart de niveaux est son enjeu existentiel ; la question de l'urne est la
fréquence de pompage ; la condition d'accord `ΔE = E` devient la condition de
résonance entre question et enjeu existentiel ; le seuil `σ_seuil,j =
κ_jΓ_j/(g_j²⟨k⟩_j)` est propre à chaque champ et le plus bas là où le réseau
interne est le plus dense. **Un pompage unique ne peut laser plusieurs champs
que s'ils partagent un observable** : la compatibilité des questions de l'urne
est la condition formelle d'un lasing multi-champs cohérent. C'est la
contribution propre de cette analyse au modèle de Khrennikov.

## Limites

- **Aucun paramètre n'est mesuré.** Ni les masses effectives, ni les couplages
  `g_j`, ni les pertes `κ_j`, `Γ_j`, ni les densités `⟨k⟩_j`. Le modèle est une
  construction formelle. Il ordonne des grandeurs et rend des questions
  posables ; il ne prédit rien.
- **La convention de « champ élargi » diffère d'ANL-001** et doit être
  rappelée chaque fois que les nombres sont cités.
- **Les masses effectives héritent d'estimations [E]** et d'une hypothèse de
  poids uniforme qui contredit le modèle lui-même. Elles ne valent que comme
  point de départ d'une analyse de sensibilité.
- **Les enjeux existentiels du constat 5 sont des reconstructions
  analytiques**, dérivées d'ANL-001, non validées auprès des champs concernés.
  Un membre d'un de ces champs pourrait légitimement contester la formulation
  de son propre enjeu existentiel.
- **La structure de compatibilité du constat 6 est argumentée, non calculée.**
  Aucun commutateur n'a été évalué, faute d'opérateurs explicites. La famille
  commutante et l'incompatibilité irréductible sont des jugements, appuyés par
  la convergence avec ANL-003 mais pas démontrés.
- **Le formalisme quantum-like peut n'apporter aucun gain.** FND-007 pose la
  question et cette analyse ne la tranche pas : un modèle classique
  multi-attributs avec effets d'ordre pourrait produire les mêmes résultats.
  **Le seul point où le formalisme se distingue est la contrainte
  parameter-free sur les effets d'ordre**, et c'est pourquoi le constat 8 en
  fait le test.
- **Rien ici n'établit l'efficacité d'une intervention.** Le modèle décrit une
  structure de possibilités ; FND-011 rappelle que les effets persuasifs
  mesurés sont petits, et FND-014 que le contrôle par peu de points d'entrée
  coûte une énergie exponentielle.
- **Ce qui reste à examiner** : le test de la contrainte d'ordre sur données
  de sondage québécoises ; l'explicitation d'au moins deux observables sous
  forme d'opérateurs, pour que « commuter » cesse d'être une métaphore ; et la
  construction du modèle classique concurrent, sans lequel rien ici n'est
  évaluable.

**Relations.** Dérive d'ANL-001 (les champs), de FND-007 et FND-021 (le
formalisme et le mécanisme). Référence ANL-002 (mesurabilité), ANL-003
(convergence sur la fracture État-marché), FND-001 (luttes de classement,
artefact sondagier), FND-004 (heresthetics, Zaller), FND-011 (taille des
effets), FND-014 (coût du contrôle), FND-020 (conjoncture, loi 21).
