---
type: fondation
id: FND-003
titre: "Autres théories sociologiques mobilisables"
version: 0.1.0
status: actif
date: 2026-08-27
---

# FND-003 - Autres théories sociologiques mobilisables

- **Objectif** : couvrir les traditions sociologiques utiles au projet que ni
  FND-001 (champs) ni FND-002 (identité) ne traitent — action collective,
  diffusion et réseaux, opinion publique et médias, sociologie des rumeurs et
  des paniques, sociologie computationnelle. Pour qui : quiconque doit
  choisir un mécanisme sociologique à formaliser dans une simulation, et
  savoir ce qui est déjà établi sur ce mécanisme.

## Note de rigueur

Cette fondation est un **catalogue raisonné**, pas une revue exhaustive : elle
couvre large et peu profond, par construction. Chaque tradition y est réduite
à son résultat central et à ce qu'elle apporte au projet.

Ce qui est solide : les modèles de seuil de Granovetter, la théorie de la
falsification des préférences de Kuran, le two-step flow, la thèse des liens
faibles, la contagion complexe de Centola — tous abondamment cités et
répliqués, et tous formalisés, donc directement utilisables. Ce qui l'est
moins : la spirale du silence de Noelle-Neumann, dont les tests empiriques
sont **contradictoires** et qu'il ne faut pas présenter comme un acquis ; et
la littérature sur la désinformation numérique, dont les résultats varient
fortement selon les plateformes et les périodes.

Sources : **primaires** pour les modèles formels (Granovetter 1978,
Kuran 1995, Watts 2002, Centola 2010), **secondaires** pour les panoramas
disciplinaires. Aucune vérification en ligne n'a été effectuée pour la
majorité des références de cette fondation ; les dates et titres sont donnés
de mémoire à partir de la littérature canonique et doivent être re-vérifiés
avant citation dans un livrable public.

Vitesse de vieillissement : **hétérogène**. Les modèles formels
(sections 1.1 à 1.3) sont stables depuis des décennies. La section sur la
sociologie numérique vieillit en deux à trois ans.

## Cadrage

**Dans le périmètre.** Cinq familles :
1. action collective et mobilisation ;
2. diffusion, contagion et réseaux ;
3. opinion publique, médias et cadrage ;
4. rumeurs, paniques morales et croyances collectives ;
5. sociologie numérique et computationnelle.

**Hors périmètre.** Les grandes synthèses théoriques générales — Parsons,
Luhmann, Habermas, Giddens — ne sont mentionnées qu'en repère, sans
traitement. La sociologie économique, la sociologie du travail, la sociologie
de la santé ne sont pas couvertes. Les théories des champs et de l'identité
sont traitées dans FND-001 et FND-002.

**Définitions de travail.**

- *Seuil* : proportion d'autrui déjà engagés à partir de laquelle un individu
  s'engage à son tour. Propriété individuelle, dont la **distribution** dans
  la population détermine le comportement collectif.
- *Cascade* : enchaînement où l'action des uns fait franchir leur seuil aux
  autres, jusqu'à une bascule collective.
- *Contagion simple / complexe* : simple, un seul contact suffit
  (épidémiologie) ; complexe, il faut plusieurs sources indépendantes de
  renforcement.
- *Cadrage* : sélection d'aspects d'une réalité perçue, rendus saillants pour
  promouvoir une définition du problème, une cause, une évaluation morale ou
  une solution (définition d'Entman).

## Corps

### 1. Les théories, leur portée, leurs résultats et leurs usages

**1.1 Action collective et seuils.**

*Mancur Olson* (*The Logic of Collective Action*, 1965) : problème du
passager clandestin — un intérêt commun ne produit pas spontanément une
action commune ; il faut des incitations sélectives ou de petits groupes.
Point de départ obligé de toute théorie de la mobilisation.

*Thomas Schelling* (*Micromotives and Macrobehavior*, 1978) : les
comportements individuels modérés produisent des résultats collectifs
extrêmes ; le modèle de ségrégation résidentielle montre qu'une préférence
faible pour la similarité suffit à produire une ségrégation forte. **Résultat
capital** : il ne faut pas inférer une intention extrême à partir d'un
résultat extrême.

*Mark Granovetter* (« Threshold Models of Collective Behavior »,
*American Journal of Sociology*, 1978) : le modèle de seuil. Chaque individu
a un seuil ; le résultat collectif dépend de la **distribution complète** des
seuils, non de la moyenne. Deux foules aux moyennes identiques peuvent
produire, l'une, rien du tout, l'autre, une émeute générale, si une seule
personne diffère. *C'est le modèle sociologique le plus directement
implémentable pour la simulation attendue, et le plus solidement établi.*

*Timur Kuran* (*Private Truths, Public Lies*, 1995) : **falsification des
préférences**. Sous pression sociale, les individus déclarent publiquement
autre chose que ce qu'ils pensent ; la distribution des préférences privées
reste donc invisible. Conséquence : les révolutions sont imprévisibles, y
compris pour ceux qui les font, parce que personne ne connaît le niveau réel
de mécontentement. Une petite variation peut déclencher une **cascade de
disponibilité** où la vérité privée se libère en chaîne. *Résultat central
pour ce projet : la mesure publique de l'opinion sous-estime structurellement
la charge mobilisable, et un déclencheur bien placé peut la libérer d'un
coup.*

*Charles Tilly*, *Doug McAdam*, *Sidney Tarrow* : mobilisation des
ressources, **structure des opportunités politiques**, répertoires d'action.
*Dynamics of Contention* (2001) : programme de recherche par mécanismes plutôt
que par modèles généraux — courtage, diffusion, escalade, changement d'échelle.
*Sidney Tarrow* (*Power in Movement*) : les **cycles de contestation**, où
une mobilisation initiale abaisse le coût des suivantes.

*David Snow et Robert Benford* : cadrage de mobilisation — diagnostic
(qui est coupable), pronostic (que faire), motivationnel (pourquoi
maintenant). L'alignement de cadres est le travail par lequel un mouvement
recrute.

**1.2 Diffusion, contagion, réseaux.**

*Everett Rogers* (*Diffusion of Innovations*, 1962) : courbe en S, catégories
d'adoptants, rôle des leaders d'opinion. Cadre canonique, formalisé plus tard
par le modèle de Bass.

*Mark Granovetter* (« The Strength of Weak Ties », *AJS*, 1973) : les liens
faibles font circuler l'information nouvelle entre communautés denses ; les
liens forts font circuler la confiance et la pression. Les deux jouent des
rôles distincts et non substituables dans une opération d'influence.

*Duncan Watts et Steven Strogatz* (1998) : réseaux petit monde ; *Watts*
(2002) : modèle de cascade globale sur réseau — une cascade exige à la fois
un déclencheur et une **connectivité dans une fenêtre critique** ; trop peu
de liens, rien ne se propage ; trop de liens, chacun est trop influencé par
la majorité pour basculer.

*Damon Centola* (*Science*, 2010, expérience sur réseaux en ligne ; *How
Behavior Spreads*, 2018) : la **contagion complexe**. Les comportements
coûteux ou controversés ne se propagent pas comme un virus : ils exigent un
renforcement social multiple. Conséquence contre-intuitive et bien
établie : les réseaux **groupés** (clustered) diffusent mieux ce type de
comportement que les réseaux aléatoires bien connectés — l'inverse de ce que
prédit le modèle épidémique. *Résultat opératoire : pour un comportement
engageant, viser des communautés denses vaut mieux que viser large.*

*Nicholas Christakis et James Fowler* (*Connected*, 2009) : diffusion de
comportements dans les réseaux réels. Résultats influents, mais leurs
estimations causales ont été **sérieusement contestées** (problème
d'homophilie contre influence) ; à citer avec cette réserve.

*Sinan Aral*, *Dean Eckles* : identification causale de l'influence sociale
par expérimentation à grande échelle ; travaux sur la séparation
influence/homophilie et sur la manipulation de l'information en ligne.

**1.3 Opinion publique, médias, cadrage.**

*Walter Lippmann* (*Public Opinion*, 1922) : les « images dans nos têtes »,
le pseudo-environnement, la fabrication du consentement. Fondateur du champ ;
sa thèse est que le citoyen agit sur une carte, jamais sur le territoire.

*Paul Lazarsfeld, Bernard Berelson, Elihu Katz* : *The People's Choice*
(1944), *Personal Influence* (1955) : **two-step flow** — les médias agissent
sur les leaders d'opinion, qui agissent sur leur entourage. Le premier
résultat empirique contre le modèle de l'aiguille hypodermique.

*Maxwell McCombs et Donald Shaw* (1972) : **mise à l'agenda** — les médias ne
disent pas quoi penser, mais à quoi penser. Solidement répliqué ; l'un des
effets médiatiques les mieux établis.

*Robert Entman* (1993) : cadrage. *Shanto Iyengar* (*Is Anyone
Responsible?*, 1991) : cadrage épisodique contre thématique, et son effet sur
l'attribution de responsabilité.

*Elisabeth Noelle-Neumann* (*The Spiral of Silence*, 1984) : ceux qui se
perçoivent minoritaires se taisent, ce qui renforce la perception de leur
minorité, et ainsi de suite. **Statut empirique contesté** : effets faibles et
inconstants selon les réplications. À traiter comme hypothèse, jamais comme
acquis — mais l'idée est cousine de celle de Kuran, mieux établie.

*George Gerbner* : théorie de la cultivation — l'exposition cumulée à la
télévision aligne les perceptions du monde sur celles de la fiction
télévisuelle. Effets petits mais persistants.

*John Zaller* (*The Nature and Origins of Mass Opinion*, 1992) : modèle
RAS (recevoir-accepter-échantillonner). Les réponses d'enquête ne révèlent
pas une opinion stable mais un échantillon de considérations rendues
accessibles au moment de la question. Convergence remarquable avec Bourdieu
(FND-001) et avec les modèles d'ordre des questions (FND-007), obtenue par un
tout autre chemin.

*Jürgen Habermas* (*L'Espace public*, 1962) : la sphère publique bourgeoise,
sa formation et sa dégradation par la publicité et les médias de masse.
Repère normatif ; fournit le critère à l'aune duquel une dégradation
délibérée se juge.

**1.4 Rumeurs, paniques, croyances collectives.**

*Gordon Allport et Leo Postman* (*The Psychology of Rumor*, 1947) : la rumeur
comme fonction de l'importance et de l'ambiguïté ; nivellement, accentuation,
assimilation dans la transmission.

*Tamotsu Shibutani* (*Improvised News*, 1966) : la rumeur est une
**intelligence collective improvisée** en situation de déficit
d'information institutionnelle — pas une pathologie, une réponse rationnelle
à un vide. Conséquence directe : le vide informationnel est la ressource.

*Stanley Cohen* (*Folk Devils and Moral Panics*, 1972) : la panique morale,
avec ses entrepreneurs de morale et son amplification médiatique en spirale.
*Erich Goode et Nachman Ben-Yehuda* en donnent la version systématisée
(critères : préoccupation, hostilité, consensus, disproportion, volatilité).

*Neil Smelser* (*Theory of Collective Behavior*, 1962) : modèle de la
valeur ajoutée — six conditions cumulatives pour un comportement collectif
(propice structurel, tension, croyance généralisée, facteur déclenchant,
mobilisation, défaillance du contrôle social). Daté dans sa psychologie, mais
sa structure « conditions nécessaires cumulatives » reste un bon canevas de
diagnostic de vulnérabilité.

*Serge Moscovici* : représentations sociales, et influence de la minorité
active — une minorité cohérente et constante peut convertir une majorité,
contre l'idée que l'influence va toujours du plus nombreux au moins nombreux.
*Résultat directement pertinent : ce n'est pas le nombre qui convertit, c'est
la constance perçue.*

**1.5 Sociologie numérique et computationnelle.**

*David Lazer et al.* (« Computational Social Science », *Science*, 2009) :
manifeste fondateur de la discipline. *Lazer et al.* (« The Science of Fake
News », *Science*, 2018) : état des lieux sur la désinformation.

*Yochai Benkler, Robert Faris, Hal Roberts* (*Network Propaganda*, 2018) :
analyse de l'écosystème médiatique états-unien ; thèse principale — la
dynamique de désinformation s'explique mieux par **l'asymétrie structurelle
de l'écosystème médiatique** que par les plateformes ou par les acteurs
étrangers. Argument à confronter sérieusement avant d'attribuer un pouvoir
excessif à une opération d'influence exogène.

*Zeynep Tufekci* (*Twitter and Tear Gas*, 2017) : capacités et fragilités des
mouvements en réseau ; les plateformes abaissent le coût de la mobilisation
et augmentent celui de la durée.

*Shoshana Zuboff* (*The Age of Surveillance Capitalism*, 2019) : économie
politique de la captation comportementale. Cadre critique ; contesté sur
l'ampleur de la manipulabilité effective.

*danah boyd* : pratiques des publics en réseau, contextes effondrés.

*Kate Starbird* : travaux sur la participation involontaire du public aux
campagnes de désinformation — la thèse de la **désinformation
participative**, où l'audience fait le travail. Directement pertinent.

**Repères non traités mais à connaître.** Durkheim (fait social,
effervescence collective, anomie), Merton (anomie, prophétie
autoréalisatrice — pertinente ici), Parsons (systèmes), Luhmann (systèmes
autopoïétiques et médias), Giddens (structuration), Garfinkel
(ethnométhodologie), Latour (acteur-réseau).

### 2. Évolution de la discipline, intervenants et contributions

**1890-1940 — la sociologie du collectif naît contre la psychologie des
foules.** Le Bon (1895) et Tarde (*Les Lois de l'imitation*, 1890) posent la
question de l'imitation et de la contagion. Durkheim leur oppose le fait
social et l'effervescence collective. Lippmann (1922) invente l'étude
moderne de l'opinion. *Contribution de Tarde, longtemps oubliée puis
redécouverte* : l'imitation comme mécanisme social élémentaire — ancêtre
direct des modèles de diffusion.

**1940-1965 — l'empirisme américain.** Lazarsfeld et l'école de Columbia
fondent l'analyse d'enquête et découvrent le two-step flow. Allport et
Postman formalisent la rumeur. Merton produit l'appareil conceptuel de portée
moyenne. Olson (1965) importe l'économie dans l'analyse de l'action
collective et détruit l'hypothèse du groupe naturellement agissant.

**1965-1985 — le tournant structural et formel.** Granovetter publie les
liens faibles (1973) puis les seuils (1978) : la sociologie se dote de
modèles formels compatibles avec la simulation. Schelling (1971, 1978) fait
la même chose depuis l'économie. Tilly refonde l'étude de la contestation sur
les ressources et les opportunités plutôt que sur la frustration. McCombs et
Shaw établissent la mise à l'agenda. Moscovici établit l'influence
minoritaire.

**1985-2005 — cadrage, cognition, cascades.** Snow et Benford introduisent le
cadrage dans l'étude des mouvements. Zaller (1992) refonde l'étude de
l'opinion sur un modèle cognitif. Kuran (1995) explique l'imprévisibilité des
révolutions par la falsification des préférences — écrit dans le sillage de
1989. Watts et Strogatz (1998) ouvrent la science des réseaux.
Bikhchandani, Hirshleifer et Welch (1992) formalisent les **cascades
informationnelles** en économie : il devient rationnel d'ignorer son
information privée pour suivre le troupeau.

**2005-2026 — la sociologie computationnelle.** Lazer et al. (2009)
institutionnalisent le domaine. Centola (2010) établit expérimentalement la
contagion complexe. Aral et Eckles attaquent l'identification causale de
l'influence. Après 2016, une littérature massive sur la désinformation :
Benkler et al. (2018), Lazer et al. (2018), Starbird, Tucker et al. Le
résultat le plus robuste et le plus inconfortable de cette vague est
**négatif** : les effets persuasifs mesurés des campagnes de désinformation en
ligne sont généralement **petits**, l'exposition est très concentrée sur de
petites minorités d'utilisateurs, et l'effet principal passe par l'agenda et
la crédibilité des institutions plutôt que par la conversion directe.
*Ce résultat doit encadrer toute revendication d'efficacité dans ce projet.*

**Ce sur quoi la discipline ne s'entend pas.**
- L'ampleur réelle des effets médiatiques : la tradition des « effets
  minimaux » (Lazarsfeld, Klapper, puis Kalla et Broockman sur les campagnes)
  contre la tradition des effets structurels d'agenda.
- Influence sociale ou homophilie : la plupart des corrélations de réseau
  sont compatibles avec les deux.
- La désinformation change-t-elle des comportements, ou surtout des
  perceptions et des affects ?

### 3. Questions de recherche principales, et qui d'autre s'en occupe

**Q1 — Qu'est-ce qui déclenche une bascule collective ?**
*Autres disciplines* : physique statistique et théorie des transitions de
phase (FND-008) ; économie (cascades informationnelles, Bikhchandani et
al.) ; épidémiologie mathématique ; théorie du laser social (FND-007).

**Q2 — Comment se distribue le pouvoir d'influence dans un réseau ?**
*Autres disciplines* : informatique (maximisation de l'influence, problème
NP-difficile de Kempe, Kleinberg et Tardos, 2003) ; théorie des graphes ;
marketing ; **cybersécurité**, sous l'angle de la sélection de cibles.

**Q3 — Distinguer influence et homophilie dans des données observationnelles.**
*Autres disciplines* : statistique et inférence causale ; économétrie ;
apprentissage automatique.

**Q4 — Quelle est la taille réelle des effets médiatiques ?**
*Autres disciplines* : psychologie expérimentale ; science politique
expérimentale (Kalla et Broockman sur l'efficacité quasi nulle de la
persuasion en campagne générale) ; méta-analyse et méta-science.

**Q5 — Pourquoi les gens taisent-ils leurs préférences, et quand cessent-ils ?**
*Autres disciplines* : économie politique (Kuran) ; psychologie sociale de la
conformité (Asch) ; études des régimes autoritaires (FND-006) ; théorie des
jeux (jeux de coordination avec information incomplète).

**Q6 — Comment naissent et se stabilisent les croyances collectives fausses ?**
*Autres disciplines* : psychologie cognitive (raisonnement motivé, effet de
vérité illusoire) ; épistémologie sociale ; philosophie des sciences ;
informatique (systèmes de recommandation).

**Q7 — Quel est l'effet propre des plateformes sur la structure de l'espace
public ?**
*Autres disciplines* : économie de l'attention ; droit et régulation ;
informatique (audit d'algorithmes) ; sciences de la communication.

**Q8 — Que faut-il pour qu'une mobilisation dure au-delà du pic ?**
*Autres disciplines* : théorie des organisations ; science politique des
partis ; histoire sociale.

## Synthèse

Cinq mécanismes formalisables, à retenir pour la modélisation.

1. **Seuils hétérogènes** (Granovetter) : le comportement collectif dépend de
   la distribution des seuils, pas de leur moyenne. Le mécanisme le mieux
   établi et le plus simple à implémenter.
2. **Falsification des préférences** (Kuran) : l'état public de l'opinion
   masque l'état privé ; une petite perturbation peut libérer une cascade. Ce
   mécanisme explique pourquoi une bascule paraît soudaine et pourquoi
   personne ne la voit venir — y compris ceux qui la mesurent.
3. **Contagion complexe** (Centola) : un comportement engageant exige un
   renforcement social multiple. Les communautés denses diffusent mieux ce
   type de comportement que les réseaux largement connectés.
4. **Cascade en fenêtre critique** (Watts) : une cascade globale exige à la
   fois un déclencheur bien placé et une connectivité ni trop faible ni trop
   forte.
5. **Mise à l'agenda plutôt que persuasion** (McCombs et Shaw ; effets
   minimaux) : l'effet médiatique le mieux établi n'est pas de changer les
   opinions mais de déterminer sur quoi porte l'attention.

Et un avertissement, qui vaut résultat : la littérature empirique récente
mesure des effets persuasifs **faibles** pour les campagnes de désinformation
en ligne, avec une exposition très concentrée. Une analyse qui postulerait un
pouvoir de conversion massif contredirait l'état des connaissances.

## Limites

- **Catalogue, pas synthèse.** Cette fondation juxtapose des traditions qui ne
  sont pas commensurables entre elles. Elle ne dit pas laquelle est correcte,
  ni comment les combiner sans incohérence.
- **Dates et titres non re-vérifiés.** Contrairement à FND-007 et FND-008,
  aucune vérification en ligne systématique n'a été faite pour ce corpus.
  Avant toute citation publique, vérifier chaque référence.
- **Aucune valeur de paramètre.** Les modèles de seuil et de cascade
  s'implémentent, mais la littérature ne fournit pas de distribution de
  seuils empiriquement calibrée sur une population réelle, encore moins
  québécoise. C'est le principal obstacle à une simulation qui prétendrait
  autre chose que l'exploration qualitative.
- **Le débat sur la taille des effets n'est pas tranché ici.** Cette fondation
  signale la controverse « effets minimaux contre effets structurels » sans
  la trancher, faute d'une revue méta-analytique.
- **Ce qu'il faudrait pour aller plus loin** : une revue ciblée et
  méta-analytique sur la taille d'effet des opérations d'influence
  documentées, plutôt que la littérature théorique rassemblée ici.

## Sources

**Action collective et seuils.**
- Mancur Olson, *The Logic of Collective Action*, Harvard UP, 1965.
- Thomas Schelling, *Micromotives and Macrobehavior*, Norton, 1978.
- Mark Granovetter, « Threshold Models of Collective Behavior », *American
  Journal of Sociology*, vol. 83, n° 6, 1978. **Modèle de référence pour la
  simulation.**
- Timur Kuran, *Private Truths, Public Lies*, Harvard UP, 1995. **Mécanisme
  central de la bascule invisible.**
- Doug McAdam, Sidney Tarrow, Charles Tilly, *Dynamics of Contention*,
  Cambridge UP, 2001.
- Sidney Tarrow, *Power in Movement*, Cambridge UP (éditions successives).
- David Snow et Robert Benford, travaux sur le cadrage de mobilisation, à
  partir de 1986.

**Diffusion et réseaux.**
- Mark Granovetter, « The Strength of Weak Ties », *AJS*, vol. 78, 1973.
- Everett Rogers, *Diffusion of Innovations*, Free Press, 1962 et éditions
  suivantes.
- Duncan Watts et Steven Strogatz, « Collective dynamics of small-world
  networks », *Nature*, 1998 ; Duncan Watts, « A simple model of global
  cascades on random networks », *PNAS*, 2002.
- Damon Centola, « The Spread of Behavior in an Online Social Network
  Experiment », *Science*, 2010 ; *How Behavior Spreads*, Princeton UP, 2018.
  **Contagion complexe** — résultat expérimental, pas seulement modèle.
- Nicholas Christakis et James Fowler, *Connected*, 2009. **À citer avec la
  réserve sur l'identification causale.**
- David Kempe, Jon Kleinberg, Éva Tardos, « Maximizing the Spread of
  Influence through a Social Network », KDD, 2003. Versant algorithmique.

**Opinion publique et médias.**
- Walter Lippmann, *Public Opinion*, 1922.
- Elihu Katz et Paul Lazarsfeld, *Personal Influence*, 1955.
- Maxwell McCombs et Donald Shaw, « The Agenda-Setting Function of Mass
  Media », *Public Opinion Quarterly*, 1972.
- Robert Entman, « Framing: Toward Clarification of a Fractured Paradigm »,
  *Journal of Communication*, 1993.
- John Zaller, *The Nature and Origins of Mass Opinion*, Cambridge UP, 1992.
  **Modèle cognitif de la réponse d'enquête.**
- Elisabeth Noelle-Neumann, *The Spiral of Silence*, 1984. **Statut empirique
  contesté ; à présenter comme hypothèse.**
- Jürgen Habermas, *L'Espace public*, 1962 (trad. fr. Payot).

**Rumeurs et paniques.**
- Gordon Allport et Leo Postman, *The Psychology of Rumor*, 1947.
- Tamotsu Shibutani, *Improvised News*, 1966.
- Stanley Cohen, *Folk Devils and Moral Panics*, 1972.
- Neil Smelser, *Theory of Collective Behavior*, 1962. Daté, mais bon canevas
  de conditions cumulatives.
- Serge Moscovici, travaux sur l'influence minoritaire et les représentations
  sociales, à partir des années 1970.

**Sociologie numérique et computationnelle.**
- David Lazer et al., « Computational Social Science », *Science*, 2009 ;
  « The Science of Fake News », *Science*, 2018.
- Yochai Benkler, Robert Faris, Hal Roberts, *Network Propaganda*, Oxford UP,
  2018. **Contre-argument à prendre au sérieux** : l'asymétrie de
  l'écosystème médiatique explique plus que l'ingérence.
- Zeynep Tufekci, *Twitter and Tear Gas*, Yale UP, 2017.
- Kate Starbird, travaux sur la désinformation participative.
- Shoshana Zuboff, *The Age of Surveillance Capitalism*, 2019. Cadre critique,
  contesté sur l'ampleur des effets.

**Économie des cascades.**
- Sushil Bikhchandani, David Hirshleifer, Ivo Welch, « A Theory of Fads,
  Fashion, Custom, and Cultural Change as Informational Cascades », *Journal
  of Political Economy*, 1992.

**Relations.** Référence FND-001, FND-002 ; alimente FND-007 et FND-008, qui
formalisent plusieurs des mécanismes catalogués ici.
