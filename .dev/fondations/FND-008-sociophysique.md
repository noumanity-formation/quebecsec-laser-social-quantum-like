---
type: fondation
id: FND-008
titre: "Sociophysique"
version: 0.1.0
status: actif
date: 2026-08-27
---

# FND-008 - Sociophysique

- **Objectif** : établir ce que la physique statistique a produit de solide
  sur les dynamiques d'opinion, de vote et de mobilisation, et ce que ces
  modèles permettent ou ne permettent pas d'affirmer. Pour qui : quiconque
  doit écrire le script de simulation numérique du dépôt, et doit choisir un
  modèle en sachant ce qu'il vaut.

## Note de rigueur

Cette fondation s'appuie sur des **articles fondateurs** du domaine et sur
des **revues de synthèse** de référence. Le corpus est large, ancien de plus
de quarante ans, publié dans des revues de physique à comité de lecture.

**Vérifié en ligne le 2026-08-27** : l'existence et la portée de la revue
« Sociophysics: A Review of Galam Models » (Galam, *International Journal of
Modern Physics C*, arXiv:0803.1800), incluant la classification en cinq
familles de modèles ; l'existence d'un numéro spécial de la revue *Physics*
en l'honneur des soixante-dix ans de Serge Galam et de quarante ans de
sociophysique ; et la revue « Opinion dynamics: Statistical physics and
beyond » (arXiv:2507.11521, soumise le 15 juillet 2025, révisée le
20 mai 2026), signée de Michele Starnini, Fabian Baumann, Tobias Galla,
David Garcia, Gerardo Iñiguez, Márton Karsai, Jan Lorenz et Katarzyna
Sznajd-Weron. A également été vérifié l'état du débat sur la **validation
empirique des modèles à confiance bornée**, qui est faible et contesté.

**Non vérifié** : les dates et références exactes des articles fondateurs
(Galam 1982, Sznajd 2000, Deffuant 2000, Hegselmann-Krause 2002, Castellano
Fortunato Loreto 2009), donnés de mémoire à partir du corpus canonique. Ils
sont très largement cités et faciles à retrouver, mais doivent être vérifiés
avant citation publique.

Vitesse de vieillissement : **lente pour les modèles, rapide pour la
validation**. Les modèles fondateurs sont stables depuis vingt à quarante
ans ; ce qui bouge, c'est la confrontation aux données, et elle bouge dans un
sens défavorable aux modèles.

**Avertissement transversal, à porter dans tout livrable.** La sociophysique
produit beaucoup de modèles et peu de tests. La revue de 2025-2026 comme la
littérature spécialisée sur les modèles à confiance bornée constatent la même
chose : la recherche s'est concentrée sur la théorie et le développement de
modèles, avec **peu de validation empirique**, et les rares tests
longitudinaux donnent des résultats mitigés — l'influence négative explique
une part des changements d'opinion observés, la confiance bornée beaucoup
moins. Un modèle sociophysique bien calibré reste un **outil d'exploration
qualitative**, pas un instrument de prédiction.

## Cadrage

**Dans le périmètre.** Les modèles de dynamique d'opinion (modèle du votant,
Sznajd, majorité de Galam, confiance bornée), les modèles de seuil et de
cascade sur réseau, les modèles de ségrégation, les régularités statistiques
des résultats électoraux, les modèles de foule et de panique, et la question
de la validation empirique.

**Hors périmètre.** L'éconophysique (marchés financiers) sauf mention. La
théorie du laser social, traitée dans FND-007 — même si elle appartient
formellement à la même famille. Les modèles épidémiologiques classiques, sauf
en tant qu'analogues de diffusion.

**Définitions de travail.**

- *Modèle du votant* : chaque agent adopte l'opinion d'un voisin choisi au
  hasard. Le modèle le plus simple, et l'un des rares exactement soluble.
- *Modèle d'Ising* : chaque agent porte un spin ±1, aligné sur ses voisins
  avec une probabilité fonction d'une température. Matrice de presque tous les
  modèles binaires d'opinion.
- *Confiance bornée* : un agent n'est influencé que par ceux dont l'opinion
  est à une distance inférieure à un seuil. Produit consensus, polarisation ou
  fragmentation selon ce seuil.
- *Agent contrariant* (Galam) : agent qui adopte systématiquement l'opinion
  contraire à la majorité locale. Une petite fraction de tels agents suffit à
  empêcher tout consensus.
- *Agent inflexible* (Galam) : agent dont l'opinion ne change jamais. Une
  petite minorité d'inflexibles peut déterminer l'issue globale.
- *Transition de phase* : changement qualitatif brusque du comportement
  collectif à la traversée d'une valeur critique d'un paramètre.

## Corps

### 1. Les modèles, leur portée, leurs résultats et leurs usages

**1.1 Modèles binaires d'opinion.**

*Modèle du votant* (Clifford et Sudbury, 1973 ; Holley et Liggett, 1975).
Exactement soluble. Résultat : sur un réseau de dimension inférieure ou égale
à 2, le système atteint le consensus ; en dimension supérieure, il peut
coexister indéfiniment. Sert de référence nulle : tout modèle plus riche doit
justifier ce qu'il ajoute.

*Modèle de Sznajd* (Sznajd-Weron et Sznajd, 2000). Principe : « l'union fait
la force » — deux agents voisins qui s'accordent convainquent leur
entourage ; s'ils divergent, ils le désorganisent. Très étudié, notamment
pour ses applications électorales.

*Modèle de majorité de Galam*. Des agents sont réunis en petits groupes
aléatoires et adoptent la majorité locale ; l'opération est répétée. Résultat
central : **le seuil de basculement n'est pas 50 %**. Avec des groupes de
taille paire, une règle de départage introduit un biais qui peut faire
gagner une opinion initialement minoritaire ; avec des agents inflexibles, une
minorité déterminée peut renverser une majorité. Galam en tire une conclusion
politiquement lourde : dans les systèmes de décision hiérarchiques,
« démocratiques » à chaque étage, une minorité organisée peut prendre le
contrôle du sommet en partant d'une base minoritaire.
**Résultat le plus directement pertinent de toute la sociophysique pour ce
projet.**

*Contrariants et inflexibles* (Galam, années 2000-2020). Une fraction faible
d'agents contrariants empêche le consensus et produit des oscillations
persistantes. Une fraction faible d'inflexibles peut déterminer l'attracteur.
Travaux plus récents de Galam : la polarisation comme sous-produit d'un
attribut sain de la démocratie — la discussion ouverte et informelle entre
agents ; et une lecture des chambres d'écho comme système de type Ising à
température nulle.

**1.2 Modèles à opinion continue.**

*Deffuant-Weisbuch* (2000) : rencontres par paires ; si l'écart d'opinion est
inférieur au seuil de confiance, les deux se rapprochent. *Hegselmann-Krause*
(2002) : chaque agent prend simultanément la moyenne des opinions situées
dans son rayon de confiance. Résultat commun : selon le seuil, on obtient un
consensus global, deux camps polarisés ou une poussière de groupes
fragmentés. **La transition entre ces régimes est brutale.**

*Statut empirique* : c'est le point faible. Il existe un large consensus en
psychologie sociale expérimentale sur le fait que les opinions restent dans
l'enveloppe convexe des positions initiales et que la sensibilité à
l'influence varie fortement d'un individu à l'autre — mais **l'existence d'un
seuil de confiance net n'est pas documentée empiriquement**. Une étude
longitudinale récente (JASSS, 2025) utilisant des modèles orientés acteur
conclut que l'influence négative contribue à expliquer les changements
d'opinion observés, mais accorde **peu de poids à la confiance bornée**. Deux
limites méthodologiques structurelles y sont pointées : la validité externe
limitée des expériences de laboratoire, et l'impossibilité, dans les
protocoles existants, de démêler l'influence négative de la confiance bornée
et des autres mécanismes d'influence.

*Conséquence pratique pour ce projet* : un modèle à confiance bornée est un
bon outil d'illustration et un mauvais argument de preuve.

**1.3 Modèles de seuil, cascades, contagion.**

Le pont avec la sociologie (FND-003). *Granovetter* (1978) fournit le modèle
de seuil ; *Watts* (2002) en donne la version sur réseau aléatoire et
identifie une **fenêtre critique de connectivité** : trop peu de liens, rien
ne se propage ; trop de liens, chaque agent est trop stabilisé par ses
voisins pour basculer. *Centola* (2010) établit expérimentalement la
contagion complexe : les comportements coûteux se propagent mieux sur des
réseaux groupés que sur des réseaux aléatoires bien connectés — l'inverse de
la prédiction épidémique.
*Modèles épidémiques* (SIR, SIS) appliqués à l'information : simples, bien
compris, souvent trop optimistes sur la vitesse de diffusion parce qu'ils
supposent une contagion simple.
*Percolation* : donne le langage du seuil de connectivité au-delà duquel une
composante géante apparaît.

**1.4 Ségrégation et structuration spatiale.**

*Schelling* (1969, 1971) : modèle de ségrégation résidentielle. Une
préférence individuelle faible pour un voisinage partiellement semblable
produit une ségrégation collective forte. **Résultat de portée générale : ne
pas inférer une intention extrême d'un résultat extrême.** Formellement
apparenté aux modèles d'Ising, ce que la physique a montré ensuite.

**1.5 Régularités statistiques des élections.**

*Costa Filho et al.*, puis *Fortunato et Castellano* (2007) : la distribution
du nombre de voix par candidat, normalisée par le nombre moyen de voix du
parti, présente une forme **universelle** à travers plusieurs pays et
plusieurs élections — une invariance d'échelle que les auteurs relient à un
modèle de diffusion sur réseau.
*Chatterjee, Galam* et d'autres : régularités dans les taux de participation
et les marges de victoire.
*Klimek, Hanel, Thurner* et al. : usage de la statistique des résultats
électoraux pour **détecter la fraude** — des signatures anormales dans le plan
participation/part de voix (le « doigt » caractéristique des bourrages
d'urnes). **C'est l'application défensive la plus tangible de toute la
sociophysique, et elle mérite d'être connue d'un public de cybersécurité.**

*Réserve* : l'existence d'une régularité statistique n'implique pas la
validité du mécanisme proposé pour l'expliquer. Plusieurs modèles distincts
produisent la même distribution.

**1.6 Foules et dynamiques physiques.**

*Dirk Helbing* : modèle de force sociale pour la dynamique piétonne ;
analyse des mouvements de foule et des bousculades mortelles ; identification
du « turbulence de foule » comme régime distinct. C'est la partie de la
sociophysique la **mieux validée empiriquement** — parce que ses grandeurs
(position, vitesse, densité) sont physiquement mesurables. Contraste
instructif : la sociophysique réussit quand elle modélise des corps, et peine
quand elle modélise des croyances.

**1.7 Ce qu'un modèle sociophysique apporte réellement.**

Trois choses, et pas davantage.
1. *Une intuition de mécanisme* : montrer qu'un comportement collectif
   surprenant peut découler de règles individuelles simples, sans coordination
   ni intention.
2. *Une topologie du possible* : identifier les régimes (consensus,
   polarisation, fragmentation) et les valeurs critiques qui les séparent.
3. *Une analyse de sensibilité* : dire quel paramètre déplace le seuil et
   dans quel sens.

Ce qu'un modèle n'apporte pas : une prédiction datée et chiffrée sur une
population réelle.

### 2. Évolution de la discipline, intervenants et contributions

**Préhistoire (1830-1945).** *Adolphe Quetelet* invente au XIXe siècle la
« physique sociale » et l'homme moyen, appliquant la statistique aux faits
sociaux — au point qu'*Auguste Comte*, qui avait employé le premier
l'expression, forge le mot « sociologie » pour s'en distinguer. *Ettore
Majorana*, dans un texte écrit vers 1942 et publié après sa disparition,
soutient que les lois statistiques des sciences sociales et de la physique
sont de même nature. Rien ne se cumule avant les années 1970.

**Fondation (1970-1990).**
- *Thomas Schelling* (1969, 1971) : modèle de ségrégation. Un économiste, pas
  un physicien, mais le résultat est structurellement sociophysique.
- *Wolfgang Weidlich* : la « sociodynamique », application systématique de la
  physique statistique aux sciences sociales à partir des années 1970.
  Contribution : le formalisme de l'équation maîtresse pour les transitions
  d'opinion.
- *Serge Galam* : à partir de 1982, avec Yuval Gefen et Yonathan Shapir,
  publie les premiers articles revendiquant explicitement la sociophysique
  comme programme. **Contribution décisive : imposer le nom et la légitimité
  du domaine, contre une hostilité initiale forte des deux disciplines.** Puis
  quarante ans de modèles : vote hiérarchique, prise de décision, coalitions
  et fragmentation, terrorisme, dynamique d'opinion — les cinq familles que
  sa propre revue de 2008 identifie.

**Expansion (1990-2010).**
- *Dietrich Stauffer* : diffuseur infatigable, forme une génération de
  physiciens à ces objets.
- *Katarzyna Sznajd-Weron* et *Józef Sznajd* (2000) : le modèle de Sznajd.
- *Guillaume Deffuant*, *Gérard Weisbuch* (2000) ; *Rainer Hegselmann*,
  *Ulrich Krause* (2002) : les modèles à confiance bornée. Ce sont ces deux
  familles qui dominent aujourd'hui la littérature.
- *Robert Axelrod* (1997) : modèle de dissémination de la culture, qui
  produit des régions culturelles stables — un politologue, encore une fois.
- *Duncan Watts*, *Steven Strogatz*, *Albert-László Barabási*, *Réka Albert* :
  la science des réseaux fournit au domaine ses topologies réalistes (petit
  monde, sans échelle).
- *Claudio Castellano*, *Santo Fortunato*, *Vittorio Loreto* : « Statistical
  physics of social dynamics », *Reviews of Modern Physics*, 2009. **Revue de
  référence, point d'entrée obligé** ; elle organise le domaine et en fait une
  discipline citable.
- *Dirk Helbing* : dynamique des foules et des piétons ; la partie la plus
  empiriquement solide.
- *Didier Sornette* : bulles financières, ruptures et signatures
  log-périodiques ; introduit l'idée de **prédiction de transition critique**,
  transposable au diagnostic de fragilité d'un système social.

**Maturation et confrontation aux données (2010-2026).**
- *Parongama Sen* et *Bikas Chakrabarti*, *Sociophysics: An Introduction*
  (Oxford UP, 2013) : manuel de référence.
- *Serge Galam* poursuit : polarisation comme sous-produit de la discussion
  démocratique ; relecture du modèle de majorité avec contrariants du point
  de vue de la mécanique statistique ; chambres d'écho comme système d'Ising
  à température nulle. Un numéro spécial de la revue *Physics* lui est
  consacré pour ses soixante-dix ans et quarante ans de sociophysique.
  **Vérifié.**
- *Michele Starnini*, *Fabian Baumann*, *Tobias Galla*, *David Garcia*,
  *Gerardo Iñiguez*, *Márton Karsai*, *Jan Lorenz*, *Katarzyna
  Sznajd-Weron*, « Opinion dynamics: Statistical physics and beyond »,
  arXiv:2507.11521 (2025, révisé 2026). **Vérifié.** Revue la plus récente :
  elle classe les modèles par phénomène macroscopique (consensus,
  polarisation, chambres d'écho) et par mécanisme microscopique (homophilie,
  assimilation), systématise la terminologie, et identifie explicitement comme
  **frontières ouvertes** la connexion des modèles aux données empiriques et
  l'usage d'agents d'intelligence artificielle comme bancs d'essai de
  phénomènes sociaux nouveaux.
- *Bernardo, Altafini, Proskurnikov et al.*, « Bounded confidence opinion
  dynamics: A survey », *Automatica*, 2024 : synthèse du versant contrôle
  automatique.
- Littérature de validation empirique : études longitudinales et
  expérimentales (dont JASSS, 2025) qui **ne confirment pas** la confiance
  bornée comme mécanisme dominant.
- *Peter Klimek*, *Rudolf Hanel*, *Stefan Thurner* et al. : statistique
  électorale et détection de fraude.

**Ce sur quoi la discipline ne s'entend pas.**
- Les modèles doivent-ils être validés empiriquement, ou suffit-il qu'ils
  montrent qu'un mécanisme est *possible* ? Clivage réel entre physiciens et
  sociologues computationnels.
- L'universalité des distributions électorales reflète-t-elle un mécanisme
  social, ou une propriété générique de tout processus d'agrégation ?
- Les agents fondés sur de grands modèles de langage sont-ils un progrès
  méthodologique ou une nouvelle source d'artefacts ? Question ouverte,
  identifiée comme frontière par la revue de 2025.

### 3. Questions de recherche principales, et qui d'autre s'en occupe

**Q1 — Quelles règles microscopiques produisent quels états macroscopiques ?**
La question centrale du domaine.
*Autres disciplines* : sociologie analytique et modélisation à base d'agents
(Hedström) ; économie des agents hétérogènes ; informatique ; sciences des
systèmes complexes.

**Q2 — Comment valider empiriquement un modèle d'opinion ?**
La question qui décide de la crédibilité du domaine, et elle est ouverte.
*Autres disciplines* : psychologie sociale expérimentale ; statistique et
inférence pour modèles à base d'agents (calibration bayésienne, inférence par
simulation) ; sociologie computationnelle ; méthodologie d'enquête.

**Q3 — Une minorité déterminée peut-elle renverser une majorité, et à quelles
conditions ?**
Le résultat le plus politiquement chargé du domaine (Galam : inflexibles,
vote hiérarchique).
*Autres disciplines* : psychologie sociale de l'influence minoritaire
(Moscovici, FND-003 — convergence remarquable, obtenue expérimentalement) ;
science politique des groupes d'intérêt ; théorie du choix social (FND-005).

**Q4 — Quelle est la structure du réseau réel, et combien cela change-t-il ?**
*Autres disciplines* : science des réseaux ; sociologie des réseaux sociaux ;
informatique et fouille de données ; science des données de plateformes —
domaine désormais entravé par la fermeture des accès aux données.

**Q5 — Peut-on détecter à l'avance une transition critique sociale ?**
*Autres disciplines* : écologie théorique (signaux précurseurs :
ralentissement critique, variance et autocorrélation croissantes) ; finance
(Sornette) ; climatologie ; théorie du contrôle. **Piste directe pour le
mécanisme de contrôle attendu par le projet.**

**Q6 — Peut-on détecter la fraude électorale par la statistique des
résultats ?**
*Autres disciplines* : statistique judiciaire ; science politique de
l'intégrité électorale (FND-005) ; **cybersécurité et criminalistique
numérique**. Application défensive, directement présentable à un public
d'experts.

**Q7 — Que valent les agents artificiels comme substituts d'humains dans une
simulation ?**
Frontière identifiée par la revue de 2025.
*Autres disciplines* : intelligence artificielle ; psychologie
expérimentale ; épistémologie de la simulation.

## Synthèse

Six points à retenir.

1. **Le seuil de bascule n'est pas 50 %** (Galam). Selon la règle
   d'agrégation, la structure hiérarchique et la présence d'agents
   inflexibles, une minorité peut l'emporter. Ce résultat, obtenu par la
   physique, converge avec l'influence minoritaire de Moscovici, obtenue
   expérimentalement, et avec les modèles de seuil de Granovetter, obtenus
   sociologiquement. **La convergence de trois traditions indépendantes est
   l'argument le plus fort du dépôt sur ce point.**
2. **Une préférence individuelle faible peut produire un résultat collectif
   extrême** (Schelling). Corollaire défensif : ne jamais inférer une
   intention extrême — ni une manipulation — d'un résultat extrême.
3. **Les transitions sont brutales et les régimes sont peu nombreux** :
   consensus, polarisation en deux camps, fragmentation. Le paramètre de
   contrôle (seuil de confiance, densité du réseau, taux de pompage) déplace
   la frontière entre ces régimes.
4. **La topologie du réseau est un paramètre de contrôle**, pas un décor
   (Watts, Centola, et le modèle de champ moyen du laser social en FND-007,
   où le seuil dépend du degré moyen ⟨k⟩).
5. **Le domaine produit beaucoup de modèles et peu de tests.** C'est le
   constat des revues les plus récentes, y compris de celle de 2025-2026, qui
   fait de la connexion aux données une frontière ouverte. La confiance bornée,
   modèle le plus populaire, n'est **pas** confirmée par les études
   longitudinales disponibles.
6. **La sociophysique a une application défensive tangible** : la détection
   statistique d'anomalies dans les résultats électoraux. C'est le point du
   domaine le plus susceptible d'intéresser un public de cybersécurité, et le
   mieux fondé.

## Limites

- **Peu de validation empirique.** C'est la limite principale, et elle est
  reconnue par le domaine lui-même. Un modèle sociophysique montre qu'un
  mécanisme est *suffisant* pour produire un phénomène ; il ne montre pas que
  c'est *le* mécanisme à l'œuvre. Toute présentation publique doit énoncer
  cette distinction.
- **Sous-détermination.** Plusieurs modèles distincts produisent les mêmes
  régularités macroscopiques. Reproduire une distribution observée ne
  sélectionne pas un mécanisme.
- **Aucun paramètre québécois.** Ni distribution de seuils, ni topologie de
  réseau, ni taux de contrariants pour une population québécoise. Une
  simulation devra poser ces valeurs comme hypothèses et faire de l'analyse de
  sensibilité son résultat principal.
- **Références fondatrices non re-vérifiées.** Les dates et références des
  articles de 1982 à 2009 sont données de mémoire. Elles sont faciles à
  retrouver mais doivent être contrôlées avant citation.
- **Le corpus est fortement masculin, européen et physicien**, et sa réception
  en sociologie est réservée. Présenter ses résultats comme des acquis des
  sciences sociales serait inexact : ce sont des résultats de physique
  appliquée à des objets sociaux, et une partie de la sociologie les conteste.
- **Ce qu'il faudrait pour aller plus loin** : la lecture intégrale de la revue
  de Castellano, Fortunato et Loreto (2009) et de celle de Starnini et al.
  (2025-2026) ; la vérification des articles fondateurs ; et une revue ciblée
  sur les méthodes de détection statistique de fraude électorale, seule
  application du domaine directement présentable comme défense.

## Sources

**Revues de synthèse — porte d'entrée.**
- Claudio Castellano, Santo Fortunato, Vittorio Loreto, « Statistical physics
  of social dynamics », *Reviews of Modern Physics*, vol. 81, 2009. **Revue
  de référence du domaine.** Non re-vérifiée dans cette session.
- Serge Galam, « Sociophysics: A Review of Galam Models », *International
  Journal of Modern Physics C*, 2008 ; arXiv:0803.1800. **Vérifié.**
  Classification en cinq familles : vote hiérarchique, prise de décision,
  fragmentation et coalitions, terrorisme, dynamique d'opinion.
  https://arxiv.org/abs/0803.1800
- Michele Starnini, Fabian Baumann, Tobias Galla, David Garcia, Gerardo
  Iñiguez, Márton Karsai, Jan Lorenz, Katarzyna Sznajd-Weron, « Opinion
  dynamics: Statistical physics and beyond », arXiv:2507.11521, 15 juillet
  2025 (rév. 20 mai 2026). **Vérifié. Revue la plus récente**, et celle qui
  énonce le mieux les frontières ouvertes du domaine.
  https://arxiv.org/abs/2507.11521
- Parongama Sen et Bikas Chakrabarti, *Sociophysics: An Introduction*, Oxford
  UP, 2013. Manuel.
- Serge Galam, *Sociophysics: A Physicist's Modeling of Psycho-Political
  Phenomena*, Springer, 2012. Exposé d'auteur.

**Modèles fondateurs — références à re-vérifier avant citation.**
- Thomas Schelling, « Models of Segregation » (1969) et « Dynamic Models of
  Segregation », *Journal of Mathematical Sociology* (1971).
- Serge Galam, Yuval Gefen, Yonathan Shapir, premiers articles de
  sociophysique, à partir de 1982.
- Katarzyna Sznajd-Weron et Józef Sznajd, modèle de Sznajd, *International
  Journal of Modern Physics C*, 2000.
- Guillaume Deffuant, David Neau, Frédéric Amblard, Gérard Weisbuch, modèle à
  confiance bornée, *Advances in Complex Systems*, 2000.
- Rainer Hegselmann et Ulrich Krause, « Opinion Dynamics and Bounded
  Confidence », *JASSS*, 2002.
- Robert Axelrod, « The Dissemination of Culture », *Journal of Conflict
  Resolution*, 1997.
- Mark Granovetter, modèle de seuil, *AJS*, 1978 (voir FND-003).
- Duncan Watts, « A simple model of global cascades on random networks »,
  *PNAS*, 2002.

**Validation empirique — le point faible, documenté.**
- « Bounded confidence opinion dynamics: A survey », *Automatica*, 2024.
  **Vérifié comme existant.**
  https://www.sciencedirect.com/science/article/pii/S0005109823004661
- « An Empirical and Simulation Investigation of Bounded Confidence and
  Negative Influence in Opinion Dynamics Using Stochastic Actor-Oriented
  Modelling », *JASSS*, vol. 28, n° 1, 2025. **Vérifié comme existant.**
  Conclut à un faible soutien empirique pour la confiance bornée.
  https://www.jasss.org/28/1/2.html

**Applications électorales.**
- Santo Fortunato et Claudio Castellano, travaux sur l'universalité des
  distributions de voix, *Physical Review Letters*, 2007.
- Peter Klimek, Yuri Yegorov, Rudolf Hanel, Stefan Thurner, travaux sur la
  détection statistique de fraude électorale, *PNAS*, 2012. **Application
  défensive** ; référence à vérifier.

**Foules.**
- Dirk Helbing et Péter Molnár, modèle de force sociale pour la dynamique
  piétonne, 1995 ; travaux ultérieurs sur les catastrophes de foule. Partie la
  mieux validée du domaine.

**Transitions critiques.**
- Didier Sornette, *Why Stock Markets Crash*, Princeton UP, 2003. Prédiction
  de transitions critiques ; méthode transposable au diagnostic de fragilité.

**Repères historiques.**
- Adolphe Quetelet, *Sur l'homme et le développement de ses facultés, ou
  Essai de physique sociale*, 1835.
- Ettore Majorana, « Il valore delle leggi statistiche nella fisica e nelle
  scienze sociali », texte des années 1940, publié en 1942.

**Reconnaissance du domaine.**
- Numéro spécial de la revue *Physics* en l'honneur de Serge Galam, pour ses
  soixante-dix ans et quarante ans de sociophysique. **Vérifié.**
  https://www.mdpi.com/si/153410

**Relations.** Référence FND-003 (seuils, cascades, contagion complexe) et
FND-005 (agrégation des votes) ; concurrent direct de FND-007, avec lequel il
doit être comparé sur pièces. Alimente le script de simulation numérique
attendu par la session.
