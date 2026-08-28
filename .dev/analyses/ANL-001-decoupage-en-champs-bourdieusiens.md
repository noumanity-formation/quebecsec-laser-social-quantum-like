---
type: analyse
id: ANL-001
titre: "Découpage de la société québécoise en champs bourdieusiens"
version: 0.1.0
status: actif
date: 2026-08-27
---

# ANL-001 - Découpage de la société québécoise en champs bourdieusiens

> La société québécoise se décompose en onze champs, dont aucun n'est
> orthogonal aux autres : l'électeur moyen relève d'environ 2,7 champs à la
> fois, et le champ le plus exposé du système compte moins de 6 000 agents
> pour 6,4 millions d'électeurs.

## Question posée

Comment décomposer la société québécoise en champs au sens de Bourdieu ;
quels sont, pour chaque champ, son nomos, sa pratique, son habitus, son
capital, son illusio et sa doxa ; combien d'électeurs chaque champ
concerne-t-il ; et dans quelle mesure ces champs se recoupent-ils ?

## Méthode

### Une réserve conceptuelle, posée d'abord

La demande mêle **deux objets bourdieusiens distincts**, et il faut le dire
avant de compter quoi que ce soit.

Un **champ** est un espace structuré de positions où des agents *spécialisés*
luttent pour un capital spécifique. Le champ politique est occupé par les
professionnels de la politique, pas par les électeurs — c'est précisément la
thèse de Bourdieu sur la délégation et la dépossession (voir FND-001,
« La représentation politique », 1981). Les électeurs y sont des **profanes**,
exclus du jeu et constitués comme public. Compter « les électeurs d'un champ »
revient donc à compter les spectateurs d'un stade comme des joueurs.

L'outil bourdieusien qui *segmente une population entière* n'est pas le champ
mais l'**espace social** : la distribution des agents selon le **volume** et la
**structure** de leur capital.

Cette analyse ne tranche pas la demande, elle la dédouble. Elle livre :
- **niveau A** — les onze champs, chacun analysé sur les six dimensions
  demandées, avec deux décomptes distincts : les **agents** du champ (ceux qui
  y jouent) et les **électeurs sous emprise** (ceux dont les dispositions de
  vote sont structurées par ce champ, sans y jouer) ;
- **niveau B** — l'espace social des 6,4 millions d'électeurs, décomposé en
  classes de position, qui est le découpage exploitable pour une simulation ;
- **niveau C** — la quantification des recoupements.

### Ce qui a été examiné

- Les dix-neuf fondations du dépôt, en particulier FND-001 (appareil
  conceptuel), FND-016 (état des lieux chiffré) et FND-017 à FND-019
  (les trois paliers).
- Des données publiques recherchées et vérifiées en ligne le 2026-08-27,
  listées ci-dessous avec leur source.

### Convention de marquage — appliquée à chaque nombre de cette analyse

- **[V]** — chiffre **vérifié** en ligne le 2026-08-27, source nommée.
- **[D]** — chiffre **dérivé** par calcul explicite à partir d'un ou plusieurs
  chiffres [V]. Le calcul est donné.
- **[E]** — **estimation d'ordre de grandeur**, non vérifiée, produite par
  raisonnement à partir de données connexes. **Ces nombres ne sont pas des
  mesures.** Ils sont donnés en fourchette, et servent à ordonner des
  grandeurs, jamais à chiffrer un résultat.

Un lecteur qui veut contester cette analyse doit attaquer les [E] en premier :
c'est là qu'elle est faible, et c'est signalé partout.

### Ancrages vérifiés

| Grandeur | Valeur | Source |
|---|---|---|
| Personnes ayant le droit de vote au Québec (2026) | ~6 800 000 [V] | Élections Québec |
| Inscrites sur la liste électorale | ~6 400 000 [V] | Élections Québec |
| Ayants droit non inscrits | >400 000 [V] | Élections Québec |
| Emplois au Québec (moyenne 2025) | 4 645 000 [V] | Statistique Québec |
| Taux d'activité | ~65 % [V] | Statistique Québec |
| Présence syndicale (2024) | 39,8 % [V] | Ministère du Travail |
| Présence syndicale, secteur public | 84,7 % [V] | Ministère du Travail |
| Présence syndicale, secteur privé | 22,9 % [V] | Ministère du Travail |
| Salariés dans le secteur public (2022) | 26,4 % [V] | IRIS / EPA |
| Emplois en santé et assistance sociale | ~625 000, 14 % [V] | Guichet-Emplois |
| Emplois en construction | 315 700, 7,0 % [V] | Guichet-Emplois |
| Grade universitaire, 25-64 ans | 29,5 % [V] | Recensement 2021 |
| Diplôme postsecondaire, 25-64 ans | 71,2 % [V] | Recensement 2021 |
| Catholiques (2021) | 4 472 560, 53,8 % [V] | Recensement 2021 |
| Sans religion (2021) | 2 267 720, 27,3 % [V] | Recensement 2021 |
| Musulmans (2021) | 421 720, ~5 % [V] | Recensement 2021 |
| **Journalistes au Québec** | **~3 450 [V]** | Guichet-Emplois |
| Élus municipaux | >8 000, dont 6 833 conseillers [V] | Statistique Québec |
| Députés à l'Assemblée nationale | 125 [V] | FND-017 |
| Députés fédéraux du Québec | 78 [V] | FND-018 |
| Avocats au Barreau du Québec | ~31 500 [V] | Barreau du Québec |
| Participation provinciale 2022 | 66,05 % [V] | FND-017 |
| Participation municipale Montréal 2025 | 37,07 % [V] | FND-019 |
| Confiance envers les médias, francophones | 46 % [V] | Digital News Report 2026 |

### Méthode d'estimation de l'emprise

Pour chaque champ, l'**emprise** est estimée en partant d'une proportion
vérifiée lorsqu'il en existe une (syndicalisation, secteur public, scolarité,
appartenance religieuse), et en la rapportant à l'électorat de 6,4 M. Lorsque
aucune proportion vérifiée n'existe, l'estimation est marquée [E] et donnée en
fourchette large. **L'emprise n'est pas l'appartenance déclarée** : elle
désigne le fait que les dispositions de vote d'une personne soient
significativement structurées par les catégories de ce champ.

## Constats

### 1. Le décompte demandé porte sur deux objets distincts

Les champs sont peuplés d'agents spécialisés, en nombre petit — de quelques
milliers à quelques dizaines de milliers. L'électorat compte 6,4 millions de
personnes [V]. **Le rapport entre les deux est de l'ordre de 1 à 1 000.**
Ce rapport n'est pas un défaut de la question posée : c'est le résultat
principal de cette analyse, et il est établi au constat 15.

### 2. Champ politique

| Dimension | Contenu |
|---|---|
| **Nomos** | Se distinguer par la capacité à parler *au nom de*. Le principe de division est la légitimité représentative : qui peut prétendre exprimer une volonté collective. |
| **Pratique** | Occuper l'espace public, construire une coalition, gérer une machine, arbitrer entre le noyau militant et l'électorat médian, tenir la ligne. |
| **Habitus** | Disponibilité totale, tolérance à l'exposition et à l'attaque, sens du moment opportun, aptitude à parler simultanément à des publics incompatibles. Fortement lié à la trajectoire : droit, communication, milieu des affaires, syndicalisme, fonction publique. |
| **Capital** | Capital politique : notoriété, réseau, capacité d'investiture, loyautés accumulées, accès aux médias. Convertible en capital économique après sortie du champ. |
| **Illusio** | La croyance que l'accès au pouvoir d'État change le cours des choses, et que la lutte partisane en vaut le prix personnel. |
| **Doxa** | Que la représentation est le mode normal de la décision collective ; que le clivage partisan existant recouvre les divisions réelles de la société ; que gagner l'élection précède tout le reste. |

- **Agents** : 125 députés provinciaux [V] + 78 fédéraux [V] + >8 000 élus
  municipaux [V] ≈ **8 200 élus**, plus le personnel politique (cabinets,
  permanents de partis, conseillers) estimé à **3 000-5 000 [E]**.
  → **≈ 12 000 agents [D/E]**.
- **Électeurs sous emprise** (militants encartés et sympathisants actifs) :
  **200 000-350 000 [E]**.
- **Observation** : le rapport entre les 8 200 personnes détenant un mandat
  électif et les 6,4 M d'électeurs est de **1 pour 780 [D]**.

### 3. Champ journalistique et médiatique

| Dimension | Contenu |
|---|---|
| **Nomos** | Ce qui compte est ce qui est nouveau, vérifiable et intéressant *maintenant*. Le principe de division est la capacité à imposer un sujet à l'attention collective. |
| **Pratique** | Sélectionner, hiérarchiser, cadrer, interroger, publier sous contrainte de temps. Surveiller ce que publient les concurrents — la « circulation circulaire de l'information » (FND-001). |
| **Habitus** | Réactivité, scepticisme professionnel de surface, intériorisation des formats, sens de ce qui « passe », goût du scoop. |
| **Capital** | Capital de crédibilité et de signature ; accès aux sources ; capacité à faire reprendre un sujet par les autres. |
| **Illusio** | La croyance que l'information publiée compte, que le métier a une fonction démocratique, et que l'écart entre le travail bien fait et le reste est perceptible. |
| **Doxa** | Que la mise à l'agenda est neutre ; que les deux « côtés » d'un sujet existent et s'équilibrent ; que l'audience mesure l'intérêt public. |

- **Agents** : **~3 450 journalistes [V]**, plus recherchistes, animateurs et
  éditeurs estimés à **~2 000 [E]** → **≈ 5 500 agents [D/E]**.
- **Électeurs sous emprise** : les réseaux sociaux sont devenus la principale
  source d'information des Canadiens et la confiance des francophones envers
  les médias est de 46 % [V] ; on estime la part de l'électorat exposée
  régulièrement à l'information d'actualité à **60-75 %**, soit
  **3 800 000-4 800 000 [E]**.
- **Autonomie** : la plus faible de tous les champs analysés, par dépendance à
  l'audience et à la plateforme (FND-001, FND-016).
- **Observation** : rapport de **1 agent pour 1 850 électeurs [D]** — le plus
  déséquilibré du système.

### 4. Champ religieux

| Dimension | Contenu |
|---|---|
| **Nomos** | La légitimité à dire le sens ultime et à administrer le sacré. Division entre le qualifié et le profane. |
| **Pratique** | Célébrer, enseigner, accompagner, administrer des lieux et des œuvres ; au Québec, défendre une place résiduelle dans un espace public sécularisé. |
| **Habitus** | Sens de la continuité longue, rapport particulier à l'autorité et au texte, indifférence relative au cycle médiatique. |
| **Capital** | Capital de sainteté et d'autorité doctrinale ; capital d'organisation ; patrimoine immobilier considérable au Québec. |
| **Illusio** | La croyance qu'il existe un ordre de valeur non réductible au politique et à l'économique. |
| **Doxa** | Que la transmission est possible ; du côté sécularisé du champ, que la religion est affaire privée — doxa devenue majoritaire et inscrite dans la loi. |

- **Agents** : clergé et personnel religieux de toutes confessions, estimés à
  **4 000-8 000 [E]**.
- **Électeurs sous emprise** : l'appartenance déclarée est massive —
  4 472 560 catholiques et 421 720 musulmans [V] — mais la pratique est
  faible ; les pratiquants réguliers sont estimés à **5-10 % de l'électorat,
  soit 320 000-640 000 [E]**. **L'emprise doxique est en revanche beaucoup plus
  large que la pratique** : 27,3 % de la population se déclare sans religion
  [V], et c'est de la friction entre ces deux pôles que la laïcité tire sa
  puissance mobilisatrice.
- **Observation** : c'est le seul champ dont l'emprise politique passe presque
  entièrement par un **enjeu extérieur à lui** — la laïcité —, arbitré par le
  champ juridique et instrumenté par le champ politique.

### 5. Champ académique et scientifique

| Dimension | Contenu |
|---|---|
| **Nomos** | Ce qui compte est ce qui est démontré et reconnu par les pairs. Division entre le savant et le profane. |
| **Pratique** | Publier, évaluer, enseigner, obtenir des subventions, siéger. |
| **Habitus** | Prudence énonciative, tolérance à la longue durée, réflexe de qualification, aversion pour l'affirmation non sourcée. |
| **Capital** | Capital scientifique (publications, citations, prix) et capital institutionnel (postes, comités, financement). Les deux ne coïncident pas. |
| **Illusio** | La croyance que la connaissance produite compte, et que la reconnaissance par les pairs est le bon juge. |
| **Doxa** | Que la vérité se départage par la méthode ; que l'expertise fonde une autorité légitime dans le débat public. |

- **Agents** : professeurs, chercheurs et chargés de cours estimés à
  **15 000-20 000 [E]**.
- **Électeurs sous emprise** : les titulaires d'un grade universitaire
  représentent 29,5 % des 25-64 ans [V] ; rapporté à l'électorat, cela donne
  **1 600 000-1 900 000 [D]** — estimation basse car le taux est plus faible
  chez les 65 ans et plus.
- **Observation** : 71,2 % des 25-64 ans détiennent un diplôme postsecondaire
  [V], la plus forte proportion au Canada, alors que la part de diplômés
  universitaires y est plus basse qu'ailleurs. **Le Québec est une société à
  fort capital scolaire technique et à capital scolaire universitaire moyen** —
  configuration qui n'a pas d'équivalent exact dans la littérature de FND-001.

### 6. Champ syndical

| Dimension | Contenu |
|---|---|
| **Nomos** | La légitimité à parler au nom des travailleurs ; division entre l'organisé et l'inorganisé. |
| **Pratique** | Négocier, mobiliser, représenter en grief, faire pression sur l'État, occuper le débat public. |
| **Habitus** | Culture du rapport de force, méfiance envers l'employeur et l'État patronal, discipline d'organisation, mémoire des luttes. |
| **Capital** | Capital de mobilisation (nombre de membres, capacité de grève), capital de négociation, fonds. |
| **Illusio** | La croyance que le rapport de force collectif obtient ce que l'individu n'obtiendrait pas. |
| **Doxa** | Que les intérêts des salariés sont objectivement distincts de ceux de l'employeur ; que la représentation collective est légitime en soi. |

- **Agents** : permanents et élus syndicaux estimés à **6 000-10 000 [E]**.
- **Électeurs sous emprise** : présence syndicale de 39,8 % sur
  4 645 000 emplois → **≈ 1 850 000 travailleurs couverts [D]**. L'emprise au
  sens fort — vote structuré par l'appartenance syndicale — est estimée à
  **800 000-1 200 000 [E]**.
- **Observation** : le Québec a le plus fort taux de présence syndicale au
  Canada [V]. C'est la principale structure d'encadrement collectif non
  étatique de la société québécoise.

### 7. Champ bureaucratique et étatique

| Dimension | Contenu |
|---|---|
| **Nomos** | La légitimité à agir au nom de l'intérêt public sous couvert de la règle. Division entre le mandaté et le requérant. |
| **Pratique** | Appliquer, instruire, arbitrer, produire de la norme, protéger l'institution. |
| **Habitus** | Sens de la procédure, aversion au risque, culture de l'écrit, loyauté institutionnelle qui survit aux alternances. |
| **Capital** | Capital statutaire (rang, permanence), capital d'expertise administrative, maîtrise de l'information interne. |
| **Illusio** | La croyance que l'État est l'instrument légitime de l'action collective — croyance particulièrement forte au Québec depuis 1960 (FND-016). |
| **Doxa** | Que la règle également appliquée est équitable ; que la continuité administrative est un bien. |

- **Agents** : haute fonction publique et cadres estimés à **10 000-15 000 [E]**.
- **Électeurs sous emprise** : 26,4 % des salariés étaient dans le secteur
  public en 2022 [V] ; rapporté à un effectif salarié de l'ordre de 4,2 M
  (4 645 000 emplois moins les travailleurs autonomes, estimés [E]), cela donne
  **≈ 1 100 000 salariés du secteur public [D]**.
- **Observation** : la thèse de Guindon (FND-016) — la Révolution tranquille
  comme prise de pouvoir d'une nouvelle classe moyenne d'État — décrit la
  genèse de ce champ, qui est aujourd'hui le plus gros employeur collectif du
  Québec.

### 8. Champ économique et patronal

| Dimension | Contenu |
|---|---|
| **Nomos** | La performance mesurée en résultat. Division entre celui qui porte le risque et celui qui ne le porte pas. |
| **Pratique** | Investir, embaucher, négocier, faire du lobbying, siéger dans les associations sectorielles. |
| **Habitus** | Orientation vers le résultat, tolérance au risque, impatience envers la procédure, valorisation de l'autonomie. |
| **Capital** | Capital économique d'abord, capital social sectoriel ensuite, capital de réputation entrepreneuriale. |
| **Illusio** | La croyance que la création de richesse est le moteur légitime du progrès collectif. |
| **Doxa** | Que le marché arbitre correctement ; que la charge réglementaire est un coût plutôt qu'une condition. |

- **Agents** : dirigeants, cadres supérieurs et responsables d'associations
  patronales estimés à **40 000-70 000 [E]**.
- **Électeurs sous emprise** : travailleurs autonomes et propriétaires de PME
  estimés à **500 000-600 000 [E]**.
- **Observation** : ce champ est celui dont l'emprise sur le vote est la plus
  mal documentée dans les sources consultées.

### 9. Champ juridique

| Dimension | Contenu |
|---|---|
| **Nomos** | La légitimité à dire le droit. Division entre le qualifié et le justiciable. |
| **Pratique** | Plaider, conseiller, juger, rédiger, interpréter. |
| **Habitus** | Formalisme, sens de la distinction analytique, réserve publique, respect de la hiérarchie des sources. |
| **Capital** | Capital juridique (titre, jurisprudence obtenue, réputation professionnelle) et capital d'accès aux instances. |
| **Illusio** | La croyance que le droit est le lieu propre du règlement des conflits. |
| **Doxa** | Que la forme juridique est neutre quant au fond ; que le tribunal est le dernier mot légitime. |

- **Agents** : **~31 500 avocats [V]**, plus notaires (~4 000 [E]) et
  magistrature (~700 [E]) → **≈ 36 000 [D/E]**.
- **Électeurs sous emprise** : faible en direct — **moins de 50 000 [E]**.
- **Observation** : l'emprise de ce champ n'est pas démographique mais
  **arbitrale**. Le jugement attendu de la Cour suprême sur la loi 21
  (FND-015) peut, à lui seul, reconfigurer l'enjeu principal d'une campagne en
  cours. **Aucun autre champ ne dispose d'un tel effet de levier à si petit
  effectif.**

### 10. Champ artistique et culturel

| Dimension | Contenu |
|---|---|
| **Nomos** | La reconnaissance par les pairs et l'originalité de l'œuvre. Division entre la logique de la création et celle du marché. |
| **Pratique** | Créer, diffuser, obtenir du financement public, occuper la scène médiatique. |
| **Habitus** | Refus revendiqué de la logique commerciale, sens du geste public, familiarité avec l'exposition. |
| **Capital** | Capital symbolique de consécration, notoriété, capital de subvention. |
| **Illusio** | La croyance que la culture nationale est un enjeu vital et que l'œuvre vaut par elle-même. |
| **Doxa** | Que la culture québécoise doit être soutenue par l'État ; que la parole de l'artiste porte une légitimité publique particulière. |

- **Agents** : estimés à **30 000-60 000 [E]** (artistes, techniciens,
  organismes).
- **Électeurs sous emprise** : élevée et difficile à chiffrer ; le système de
  vedettariat québécois — un marché linguistique fermé de taille moyenne —
  donne à ce champ une pénétration sans équivalent dans les grandes
  démocraties. Estimation : **1 200 000-1 800 000 [E]**.
- **Observation** : c'est le champ dont le rapport
  notoriété-sur-effectif est le plus élevé après le champ journalistique.

### 11. Champ associatif et communautaire

| Dimension | Contenu |
|---|---|
| **Nomos** | La légitimité tirée du service rendu au terrain et de la proximité avec les personnes concernées. |
| **Pratique** | Intervenir, représenter, revendiquer, quêter du financement récurrent. |
| **Habitus** | Éthique du dévouement, méfiance envers la bureaucratie, culture de la précarité assumée. |
| **Capital** | Capital de légitimité de terrain, capital de réseau, ancienneté de l'organisme. |
| **Illusio** | La croyance que l'action de terrain corrige ce que l'État ne voit pas. |
| **Doxa** | Que la proximité fonde une connaissance supérieure du besoin. |

- **Agents** : estimés à **60 000-80 000 [E]**.
- **Électeurs sous emprise** : **600 000-1 000 000 [E]**.

### 12. Champ numérique et de l'attention — champ en formation

| Dimension | Contenu |
|---|---|
| **Nomos** | Ce qui compte est ce qui capte. Division entre celui qui a une audience et celui qui n'en a pas. |
| **Pratique** | Publier en continu, tester des formats, entretenir une communauté, monétiser l'attention. |
| **Habitus** | Réactivité extrême, aisance avec l'exposition de soi, lecture intuitive des métriques, absence de déontologie codifiée. |
| **Capital** | Capital d'attention : abonnés, portée, taux d'engagement. Directement mesuré, publiquement affiché, instantanément converti. |
| **Illusio** | La croyance que la portée est la mesure de l'importance. |
| **Doxa** | Que l'authenticité personnelle vaut certification ; que ce qui circule mérite de circuler. |

- **Agents** : créateurs québécois à audience significative estimés à
  **2 000-5 000 [E]**.
- **Électeurs sous emprise** : les réseaux sociaux, YouTube et Facebook en
  tête, sont devenus la principale source d'information [V] ; environ trois
  Canadiens sur quatre ignorent le blocage des médias d'information sur Meta
  [V]. Estimation : **3 000 000-4 000 000 [E]**.
- **Statut** : ce champ n'a pas d'instance de consécration propre ni de
  barrière à l'entrée. Il satisfait trois des quatre critères d'un champ —
  enjeu spécifique, capital propre, luttes de classement — mais pas le
  quatrième, l'autonomie. **Il est en formation, et il est aujourd'hui le
  principal concurrent du champ journalistique pour le même capital.**

### 13. L'espace social des électeurs — niveau B

Le découpage exploitable pour une modélisation ne suit pas les champs mais le
volume et la structure du capital. Six classes de position, estimées :

| Classe de position | Description | Effectif estimé | Part |
|---|---|---|---|
| Pôle culturel dominant | Fort capital culturel, capital économique moyen : professions intellectuelles, enseignement, santé qualifiée, culture, haute fonction publique | 900 000-1 100 000 [E] | ~15 % |
| Pôle économique dominant | Fort capital économique, capital culturel variable : dirigeants, cadres du privé, professions libérales lucratives | 350 000-500 000 [E] | ~7 % |
| Classes moyennes salariées | Capital scolaire technique (le cégep comme marqueur), emploi stable, souvent syndiqué | 1 800 000-2 200 000 [E] | ~31 % |
| Petite bourgeoisie indépendante et régionale | Propriétaires de PME, commerçants, agriculteurs, entrepreneurs hors métropole | 500 000-650 000 [E] | ~9 % |
| Classes populaires salariées | Faible capital scolaire, emploi manuel ou de service, exposition économique élevée | 1 500 000-1 800 000 [E] | ~26 % |
| Retirés du jeu | Faible capital de tous types, forte abstention structurelle | 700 000-900 000 [E] | ~12 % |

Trois axes traversent ces six classes sans s'y réduire : **l'âge**, **le
territoire** (métropole / région de Québec / autres régions, dont FND-016
montre l'effet direct sur le vote) et **la trajectoire migratoire et
linguistique**.

**Aucun de ces effectifs n'est mesuré.** Ils sont construits à partir des
proportions vérifiées de scolarité, de secteur d'emploi et de syndicalisation,
et leur somme est calée sur 6,4 M. Ils servent à ordonner des grandeurs.

### 14. Les champs ne sont pas orthogonaux — quantification

**Ils ne peuvent pas l'être.** L'homologie structurale est une thèse centrale
de Bourdieu (FND-001) : les positions se correspondent d'un champ à l'autre.
Chercher l'orthogonalité serait chercher ce que la théorie exclut.

**Recoupements les plus forts, par ordre de solidité de l'estimation :**

| Recoupement | Effectif | Base |
|---|---|---|
| **Syndical × Bureaucratique** | **≈ 930 000 [D]** | 84,7 % de présence syndicale dans le secteur public [V] × ~1 100 000 salariés publics [D] |
| Académique × Bureaucratique | quasi total pour les agents | universités et collèges publics |
| Syndical × Santé et éducation | 400 000-500 000 [E] | 625 000 emplois en santé [V], majoritairement publics et syndiqués |
| Culturel × Journalistique | fort, non chiffré | chroniqueurs, animateurs, personnalités à double appartenance |
| Numérique × Journalistique | croissant | concurrence pour le même capital d'attention |
| Économique × Politique | faible en effectif, fort en effet | financement, lobbying, mobilité entre les deux |
| Religieux × Politique | médié par la laïcité | l'enjeu, pas les personnes |
| Juridique × Bureaucratique | partiel | contentieux de l'État, magistrature |

**Le recoupement le plus massif et le mieux établi du système québécois est
donc syndical × bureaucratique**, soit environ **930 000 personnes [D]** —
**14,5 % de l'électorat [D]** — simultanément salariées de l'État et
syndiquées. Si l'on ajoute la condition « diplômé universitaire », on obtient
une intersection à trois champs — bureaucratique, syndical, académique —
estimée à **350 000-450 000 personnes [E]**, soit **5,5-7 % de l'électorat**.
C'est le bloc le plus dense et le plus identifiable de la structure sociale
québécoise.

**Indice de recoupement global.** En additionnant les emprises médianes
estimées des onze champs — journalistique 4,3 M, numérique 3,5 M, religieux
(emprise doxique) 2,5 M, académique 1,75 M, culturel 1,5 M, bureaucratique
1,1 M, syndical 1,0 M, associatif 0,8 M, économique 0,55 M, politique 0,28 M,
juridique 0,05 M — on obtient **≈ 17,3 M d'appartenances pour 6,4 M
d'électeurs [D sur base E]**, soit un indice de **≈ 2,7 champs par électeur**.

**Ce chiffre est construit sur des estimations et ne vaut que comme ordre de
grandeur.** Ce qu'il établit n'est pas sa valeur exacte mais son ordre : un
électeur québécois relève simultanément de **plusieurs** logiques de champ, et
un modèle qui lui assignerait une appartenance unique serait faux par
construction.

### 15. Le déséquilibre d'effectif est le constat principal

| Champ | Agents | Électeurs sous emprise | Rapport |
|---|---|---|---|
| Journalistique | ~5 500 | ~4 300 000 | **1 : 780** |
| Politique (élus seuls) | 8 203 | 6 400 000 | **1 : 780** |
| Numérique | ~3 500 | ~3 500 000 | **1 : 1 000** |
| Religieux | ~6 000 | ~2 500 000 | 1 : 415 |
| Académique | ~17 500 | ~1 750 000 | 1 : 100 |
| Juridique | ~36 000 | arbitral | sans objet |
| Syndical | ~8 000 | ~1 000 000 | 1 : 125 |

Trois champs — journalistique, politique et numérique — présentent un rapport
d'un agent pour environ mille électeurs. **Le champ journalistique québécois
compte environ 3 450 journalistes [V] pour 6,4 millions d'électeurs [V], et
c'est aussi celui dont FND-001 établit qu'il a la plus faible autonomie et la
plus forte tendance à la circulation circulaire de l'information.**

## Réponse

**Sur le découpage.** La société québécoise se décompose en **onze champs** :
politique, journalistique, religieux, académique, syndical, bureaucratique,
économique, juridique, artistique, associatif, et un champ numérique en
formation. Chacun a été analysé sur les six dimensions demandées (constats 2
à 12).

**Sur le décompte d'électeurs.** La demande mêle deux objets : un champ est
peuplé d'agents spécialisés, pas d'électeurs. L'analyse livre donc deux
décomptes par champ — agents et électeurs sous emprise — et un découpage
distinct de l'électorat en six classes de position (constat 13), qui est le
découpage exploitable pour une simulation. **Aucun effectif d'électeurs n'est
mesuré ; tous sont des estimations d'ordre de grandeur marquées [E] ou dérivées
[D] de proportions vérifiées.**

**Sur l'orthogonalité.** Les champs ne sont pas orthogonaux, et ne peuvent pas
l'être : l'homologie structurale est constitutive de la théorie. L'indice de
recoupement estimé est de **≈ 2,7 champs par électeur**. Le recoupement le
mieux établi est **syndical × bureaucratique, ≈ 930 000 personnes [D], soit
14,5 % de l'électorat** ; l'intersection à trois champs avec le champ
académique est estimée à 5,5-7 % de l'électorat.

**Le constat que cette analyse établit et qui n'était pas demandé** : le
rapport d'effectif entre les champs qui produisent le cadrage public et la
population qui le reçoit est de l'ordre de **1 pour 1 000**. Trois champs —
journalistique (~3 450 journalistes [V]), politique (8 203 élus [V]) et
numérique (~3 500 créateurs [E]) — totalisent moins de **15 000 personnes**
pour 6,4 millions d'électeurs. C'est la disproportion structurelle centrale du
système québécois.

## Limites

- **La quasi-totalité des effectifs de champs sont des estimations [E].**
  Seuls les journalistes, les élus, les avocats, les taux de syndicalisation,
  de secteur public, de scolarité et d'appartenance religieuse sont vérifiés.
  Les effectifs des champs académique, culturel, associatif, économique et
  numérique sont des ordres de grandeur non vérifiés, et c'est par eux qu'il
  faut attaquer cette analyse.
- **L'« emprise » n'est pas une grandeur mesurée** et n'a pas d'instrument.
  C'est une notion construite pour les besoins de cette analyse, et sa
  quantification est la partie la plus faible du travail. L'indice de 2,7
  champs par électeur en dépend entièrement.
- **Les six classes de position du constat 13 ne reposent sur aucune analyse
  géométrique des données.** La méthode bourdieusienne exigerait une analyse
  des correspondances multiples sur des données individuelles ; elle n'a pas
  été faite, et les effectifs sont posés, non calculés.
- **Rien sur les Premières Nations et les Inuit**, ni sur les communautés
  anglophones et allophones comme positions structurées. Ce sont des lacunes
  réelles du découpage, pas seulement de la documentation.
- **Le champ numérique n'est peut-être pas un champ.** Il ne satisfait pas le
  critère d'autonomie. Le traiter comme tel est une décision de cette analyse,
  contestable.
- **Aucune validation empirique du découpage.** Rien ici n'établit que ces
  onze champs sont *les* champs de la société québécoise plutôt qu'un
  découpage parmi d'autres. Un découpage concurrent, en cinq ou en vingt
  champs, ne serait pas réfuté par ce document.
- **Ce qui reste à examiner** : les données individuelles nécessaires à une
  analyse des correspondances multiples ; les effectifs réels des ordres
  professionnels et des secteurs culturel et communautaire ; et la question,
  non traitée ici, de savoir **quels champs sont les plus exposés** — qui
  relève d'une analyse distincte et non d'un découpage.

**Relations.** Dérive de FND-001 (appareil conceptuel des champs). Référence
FND-002, FND-015, FND-016, FND-017, FND-018, FND-019.
