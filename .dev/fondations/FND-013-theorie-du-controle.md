---
type: fondation
id: FND-013
titre: "Théorie du contrôle (physique et automatique)"
version: 0.1.0
status: actif
date: 2026-08-27
---

# FND-013 - Théorie du contrôle (physique et automatique)

- **Objectif** : établir le vocabulaire et les résultats de la théorie du
  contrôle, y compris ses **limites fondamentales** — ce qu'aucun régulateur
  ne peut faire. Pour qui : quiconque doit esquisser un mécanisme de contrôle
  sur un système de type laser social, et doit savoir ce qu'exige la
  commandabilité, ce que coûte l'observation, et pourquoi supprimer une
  perturbation quelque part la fait réapparaître ailleurs.

## Note de rigueur

Cette fondation repose sur des **résultats mathématiques démontrés** et sur
des **manuels de référence**. C'est, avec le choix social de FND-005, le
corpus le plus stable du dépôt : un critère de stabilité ne se périme pas.

**Vérifié en ligne le 2026-08-27** : l'article de Liu, Slotine et Barabási,
« Controllability of complex networks », *Nature*, vol. 473, n° 7346,
p. 167-173, 2011 (DOI 10.1038/nature10011), et la **critique de Cowan,
Chastain, Vilhena, Freudenberg et Bergstrom**, qui soutient que le cadre de
commandabilité structurelle appliqué aux réseaux réels conduit à conclure
qu'une **seule** entrée de commande suffit, et que les questions
pertinentes sont plutôt celles de la quasi-incommandabilité, de la
quasi-inobservabilité et des quasi-simplifications pôle-zéro. A aussi été
vérifiée l'existence des tutoriels de Proskurnikov et Tempo sur la
modélisation et l'analyse des réseaux sociaux dynamiques (*Annual Reviews in
Control*, 2017 et 2018).

**Non vérifié dans cette session** : l'ensemble du corpus classique
(Maxwell, Nyquist, Bode, Kalman, Lyapunov, Zames, Doyle, Åström, Khalil,
Siegman) et la partie sur le contrôle des lasers physiques, donnés de mémoire.
Ces résultats sont des standards de manuel ; les références doivent néanmoins
être contrôlées avant citation publique.

**Avertissement d'usage.** Le transfert de cette théorie à un système social
est une **analogie**, pas une application. Les hypothèses qui la fondent —
un modèle connu, un état mesurable, des entrées de commande fiables, une
dynamique stationnaire — sont toutes fausses pour une société. La théorie
reste précieuse, mais **comme source de contraintes et d'impossibilités**,
non comme recette de pilotage. C'est d'ailleurs sa contribution la plus
solide au projet : elle dit surtout ce qui ne se peut pas.

Vitesse de vieillissement : **très lente**, sauf pour le contrôle des
réseaux, actif depuis 2011.

## Cadrage

**Dans le périmètre.** Rétroaction et boucle fermée ; représentation d'état ;
stabilité ; commandabilité et observabilité ; observateurs ; robustesse et
limites fondamentales ; contrôle non linéaire ; contrôle distribué et contrôle
de réseaux ; contrôle des lasers physiques, en raison du sujet du dépôt.

**Hors périmètre.** Le contrôle optimal, traité dans FND-014. Les détails
d'implémentation (discrétisation, identification de systèmes, réglage
industriel). La théorie de l'information de Shannon, sauf mention.

**Définitions de travail.**

- *Boucle ouverte* : la commande est calculée sans mesurer le résultat.
  *Boucle fermée* : la commande dépend de l'écart mesuré entre la sortie et la
  consigne. Toute la discipline tient dans cette différence.
- *Commandabilité* : possibilité d'amener le système d'un état initial à
  n'importe quel état final en un temps fini, avec les entrées disponibles.
  Propriété **binaire** et souvent trompeuse : un système peut être
  commandable en droit et inatteignable en pratique, faute d'énergie.
- *Observabilité* : possibilité de reconstruire l'état interne à partir des
  seules sorties mesurées. **Duale de la commandabilité** : sans elle, la
  rétroaction est aveugle.
- *Stabilité* : au sens de Lyapunov, propriété selon laquelle les
  trajectoires proches d'un équilibre y restent, ou y reviennent.
- *Marge de robustesse* : écart entre le système nominal et le point de perte
  de stabilité. Mesure la tolérance à l'erreur de modèle.
- *Perturbation* : entrée non commandée qui agit sur le système. Dans une
  analogie sociale, c'est tout ce que l'attaquant ne contrôle pas — et tout ce
  qu'un attaquant injecte est, du point de vue du défenseur, une perturbation.

## Corps

### 1. La théorie, sa portée, ses résultats et ses usages

**1.1 La rétroaction, et ce qu'elle achète.**

Le résultat fondateur de la discipline : une boucle de rétroaction négative
réduit la sensibilité du comportement d'un système aux variations de ses
composants et aux perturbations, **au prix** d'un risque d'instabilité. C'est
un échange, pas un gain gratuit. Harold Black en fait la démonstration
industrielle en 1934 avec l'amplificateur à contre-réaction ; toute la théorie
qui suit consiste à quantifier cet échange.

Trois propriétés que la rétroaction confère : rejet des perturbations,
insensibilité aux erreurs de modèle, et modification de la dynamique
(rapidité, amortissement). Une propriété qu'elle exige : **mesurer**. Sans
observation, pas de boucle fermée — seulement de la commande en aveugle, dont
la performance dépend entièrement de l'exactitude du modèle.

**1.2 Stabilité.**

*Critère de Routh-Hurwitz* : condition algébrique sur les coefficients du
polynôme caractéristique.
*Critère de Nyquist* (1932) : condition graphique et fréquentielle, qui donne
en prime les **marges de gain et de phase** — de combien le gain peut varier,
ou le retard s'allonger, avant instabilité. **Le retard est l'ennemi
principal de toute boucle** : il consomme de la marge de phase et finit par
déstabiliser. Transposé au social, c'est une remarque de première
importance : un dispositif de contre-mesure qui réagit trop lentement
n'est pas simplement inefficace, il peut amplifier l'oscillation qu'il
prétend amortir.
*Méthode directe de Lyapunov* : une fonction d'énergie décroissante le long
des trajectoires prouve la stabilité, y compris pour des systèmes non
linéaires, **sans les résoudre**. C'est l'outil le plus général de la
discipline, et le plus transposable à un modèle social, où l'on ne sait pas
résoudre mais où l'on peut parfois exhiber une quantité qui décroît.

**1.3 Représentation d'état, commandabilité, observabilité.**

*Rudolf Kalman* (1960) transforme la discipline en la faisant passer du
domaine fréquentiel à la représentation d'état ẋ = Ax + Bu, y = Cx.
Il y introduit les deux notions structurelles :
- **commandabilité**, testable par le rang de la matrice [B, AB, A²B, …] ;
- **observabilité**, testable de manière duale sur (A, C).
Suivent le placement de pôles (si commandable, la dynamique en boucle fermée
est arbitrairement assignable), les **observateurs** (Luenberger) qui
reconstruisent l'état non mesuré, et le **principe de séparation** : on peut
concevoir séparément l'estimateur et le régulateur, et les combiner.

**1.4 Robustesse et limites fondamentales — la section décisive.**

*L'intégrale de Bode et l'effet matelas d'eau.* Pour une large classe de
systèmes en boucle fermée, l'intégrale du logarithme de la sensibilité sur
toutes les fréquences est **conservée**. Conséquence : réduire la sensibilité
aux perturbations dans une bande de fréquences l'**augmente nécessairement**
dans une autre. On ne supprime pas une perturbation, on la déplace. **C'est,
de tout ce corpus, le résultat le plus riche de conséquences pour une
contre-mesure sociale** : une intervention qui étouffe une dynamique
d'amplification dans un registre doit être soupçonnée de l'amplifier dans un
autre — par exemple, une modération qui réduit la visibilité d'un contenu et
augmente la défiance envers le modérateur.

*Autres limites structurelles.* Les zéros dans le demi-plan droit (réponse
inverse : le système part d'abord dans la mauvaise direction) et les retards
imposent des bornes supérieures dures à la bande passante réalisable. Aucun
régulateur, si sophistiqué soit-il, ne les franchit.

*Doyle (1978), « Guaranteed margins for LQG regulators: none ».* Un article
d'une page, dont le titre est le résultat : le régulateur optimal au sens
quadratique gaussien n'offre **aucune garantie de marge de robustesse**.
L'optimalité selon un critère ne protège pas contre l'erreur de modèle. Ce
résultat a fondé la théorie de la commande robuste (*H*∞, Zames, Doyle,
Glover, Francis) et il porte une leçon générale immédiatement transposable :
**optimiser un mécanisme de contrôle social contre un modèle de société
supposé exact ne garantit rien du tout dès que le modèle est faux — et il
l'est.**

*Théorème du bon régulateur* (Conant et Ashby, 1970) : tout régulateur
efficace d'un système doit en contenir un modèle. Et la **loi de la variété
requise** d'Ashby : seule de la variété peut absorber de la variété — le
régulateur doit disposer d'au moins autant d'états distincts que les
perturbations qu'il doit compenser. Deux énoncés de cybernétique, moins
rigoureux que le reste de cette fondation, mais qui posent exactement la
bonne question pour un système social : *quel modèle de la société le
défenseur possède-t-il, et est-il aussi riche que l'espace des attaques ?*

**1.5 Au-delà du linéaire.**

Contrôle non linéaire : linéarisation par bouclage, mode glissant (robuste
mais sujet au broutement), *backstepping*, passivité. Contrôle adaptatif :
le régulateur estime les paramètres en ligne — puissant, et sujet à des
instabilités propres. Commande prédictive : à chaque pas, on résout un
problème d'optimisation sur un horizon glissant et on n'applique que la
première commande ; c'est la méthode dominante dans l'industrie, et elle est
traitée en FND-014.

**1.6 Contrôle distribué et contrôle de réseaux.**

*Consensus et systèmes multi-agents* : conditions sur la topologie
(connexité, existence d'un arbre couvrant) sous lesquelles des agents locaux
convergent vers une valeur commune. Le taux de convergence est gouverné par
la **connectivité algébrique** — la deuxième plus petite valeur propre du
laplacien du graphe. Résultat directement pertinent : *la vitesse à laquelle
une population s'aligne est une propriété spectrale du réseau, pas du
message.*

*Commandabilité des réseaux complexes* (Liu, Slotine et Barabási, 2011,
vérifié) : par la théorie de la commandabilité structurelle et un couplage
maximal, on identifie l'ensemble minimal de **nœuds pilotes** nécessaires
pour commander un réseau dirigé arbitraire ; leur nombre est principalement
déterminé par la distribution des degrés. Résultat très cité, et très
séduisant pour qui cherche « où frapper ».

**Il faut lui opposer immédiatement sa critique**, vérifiée : Cowan et al.
montrent que, sous ce cadre, presque tous les réseaux réels seraient
commandables par une **unique** entrée appliquée à un ensemble dominant, ce
qui vide le résultat de son contenu pratique ; et que les questions qui
comptent sont celles de la **quasi**-incommandabilité et de la
**quasi**-inobservabilité — c'est-à-dire du **coût énergétique** du contrôle,
non de sa possibilité de principe. **Conclusion à retenir pour le projet :
une démonstration de commandabilité structurelle d'un réseau social ne
démontre rien d'opérationnel.** L'argument sérieux est énergétique, et il est
traité en FND-014.

*Contrôle des dynamiques d'opinion* : il existe un champ constitué, à
l'intersection de l'automatique et des sciences sociales — Proskurnikov et
Tempo en donnent le panorama en deux tutoriels (*Annual Reviews in Control*,
2017 et 2018), et il existe des travaux sur le contrôle par le bruit des
dynamiques d'opinion. **Ce champ est le plus proche voisin méthodologique du
projet, et il n'a pas encore été dépouillé dans ce dépôt.**

**1.7 Contrôle des lasers physiques — pertinent par analogie directe.**

Puisque FND-007 modélise le social comme un laser, il faut savoir comment on
commande un laser réel.
- *Équations de bilan* : couplage entre l'inversion de population et le
  nombre de photons. Le système présente un **seuil** et, au-dessus, des
  **oscillations de relaxation** — un dépassement oscillatoire avant
  l'établissement du régime permanent. Toute analogie sociale sérieuse devrait
  chercher cet analogue : *une mobilisation devrait osciller avant de se
  stabiliser ou de retomber.*
- *Commande du pompage* : le levier le plus direct, mais lent devant la
  dynamique du champ.
- *Déclenchement (Q-switching)* : moduler les pertes de la cavité pour
  accumuler l'inversion puis la libérer d'un coup en impulsion géante.
  Traduction sociale immédiate : **retenir l'expression, puis relâcher, produit
  un pic bien supérieur à une libération continue** — cousin formel de la
  falsification des préférences de Kuran (FND-003).
- *Blocage de modes* : mise en phase de nombreux modes pour produire des
  impulsions ultracourtes et répétées. Analogue possible d'une cadence
  d'action synchronisée.
- *Injection et verrouillage (injection locking)* : un signal maître faible
  impose sa fréquence et sa phase à un oscillateur esclave beaucoup plus
  puissant, à condition de rester dans une plage d'accord étroite.
  **C'est l'analogie la plus prometteuse de tout ce corpus pour l'objet du
  dépôt** : peu d'énergie, à la bonne fréquence, capture la phase d'un système
  bien plus grand. Et elle vient avec sa propre limite — hors de la plage
  d'accrochage, le maître n'a aucun effet.
- *Rétroaction optique* : un retour même faible peut déstabiliser un laser et
  le faire basculer dans un régime chaotique. Rappel utile : **une boucle
  ajoutée sans soin déstabilise plus qu'elle ne régule.**

### 2. Évolution de la discipline, intervenants et contributions

**Régulateurs avant la théorie (Antiquité - 1868).** Horloge à eau de
Ktésibios ; régulateur à boules de Watt (1788), qui rend la machine à vapeur
utilisable. La pratique précède la théorie de deux millénaires.

**Naissance de la théorie (1868-1930).** *James Clerk Maxwell*, « On
Governors » (1868) : premier traitement mathématique de la stabilité d'un
système asservi — il montre que le problème se ramène aux racines d'un
polynôme. *Edward Routh* et *Adolf Hurwitz* : critères algébriques de
stabilité. *Aleksandr Lyapunov* (1892) : théorie générale de la stabilité du
mouvement, ignorée en Occident pendant un demi-siècle.

**L'ère des télécommunications (1927-1950).** *Harold Black* (1927-1934) :
l'amplificateur à contre-réaction, invention industrielle décisive.
*Harry Nyquist* (1932) : critère de stabilité fréquentiel. *Hendrik Bode*
(1945) : marges, tracés, et l'**intégrale de conservation de la
sensibilité** — la limite fondamentale. *Norbert Wiener* (*Cybernetics*,
1948) : généralise la rétroaction à l'animal, la machine et la société, et
fonde par là même l'ambition d'appliquer le contrôle au social ; ambition
féconde et jamais aboutie. *Claude Shannon* : théorie de l'information,
sœur jumelle.

**L'ère moderne (1955-1980).** *Rudolf Kalman* (1960) : représentation
d'état, commandabilité, observabilité, filtre de Kalman. **Contribution la
plus structurante de la discipline.** *David Luenberger* : observateurs.
*W. Ross Ashby* et *Roger Conant* : cybernétique — variété requise, théorème
du bon régulateur. *Lev Pontryagin* et *Richard Bellman* : contrôle optimal
(FND-014).

**Robustesse (1978-1995).** *John Doyle* (1978) démolit l'illusion de
robustesse du LQG. *George Zames* (1981) formule le problème *H*∞.
*Doyle, Glover, Khargonekar, Francis* (1989) en donnent la solution par
équations de Riccati. **Contribution collective** : reconnaître que le modèle
est faux et concevoir en conséquence.

**Non-linéaire, adaptatif, prédictif (1980-2005).** *Jean-Jacques Slotine* et
*Weiping Li* ; *Hassan Khalil* : manuels de référence du non-linéaire.
*Karl Johan Åström* : contrôle adaptatif, et plus tard le manuel *Feedback
Systems* avec *Richard Murray*, qui est la meilleure introduction moderne. La
commande prédictive s'impose dans l'industrie.

**Réseaux et systèmes complexes (2000-2026).** Consensus et systèmes
multi-agents. *Liu, Slotine et Barabási* (2011) : commandabilité des réseaux
complexes. *Cowan, Chastain, Vilhena, Freudenberg et Bergstrom* : la critique
qui recentre le débat sur le coût plutôt que sur la possibilité.
*Proskurnikov et Tempo* (2017, 2018) : les réseaux sociaux dynamiques comme
objet d'automatique. *Contribution collective de la période* : montrer que
la commandabilité structurelle d'un grand réseau est presque toujours vraie
et presque toujours sans intérêt pratique — ce qui compte est l'énergie.

**Ce sur quoi la discipline ne s'entend pas.**
- La commandabilité structurelle des réseaux réels a-t-elle un contenu
  pratique ?
- Les méthodes fondées sur l'apprentissage (apprentissage par renforcement)
  peuvent-elles offrir des garanties comparables à celles du contrôle
  classique ?
- Jusqu'où l'analogie avec les systèmes sociaux est-elle légitime ? La
  cybernétique en a fait un programme ; l'automatique contemporaine est
  nettement plus prudente.

### 3. Questions de recherche principales, et qui d'autre s'en occupe

**Q1 — Quelles sont les limites fondamentales de performance d'une boucle ?**
*Autres disciplines* : mathématiques (analyse complexe, théorie des
opérateurs) ; théorie de l'information (bornes de débit pour la
stabilisation) ; physique (bornes thermodynamiques).

**Q2 — Comment commander un système dont le modèle est faux ?**
*Autres disciplines* : statistique et identification ; apprentissage
automatique ; théorie de la décision robuste ; économie (théorie de
l'ambiguïté).

**Q3 — Où placer les entrées de commande dans un réseau ?**
*Autres disciplines* : science des réseaux ; optimisation combinatoire ;
informatique (complexité de la sélection de nœuds pilotes) ; biologie des
systèmes ; **et, du côté adverse, la maximisation d'influence, FND-003.**

**Q4 — Peut-on contrôler un système social ?**
*Autres disciplines* : sociologie (qui répond largement non, et pour de bonnes
raisons) ; science politique ; économie (politique monétaire comme cas de
contrôle assumé) ; sociophysique (FND-008) ; éthique et théorie politique —
car « qui tient la boucle » est une question politique avant d'être
technique.

**Q5 — Comment estimer un état non observable ?**
*Autres disciplines* : statistique bayésienne (filtrage) ; traitement du
signal ; économétrie (modèles à variables latentes) ; psychométrie —
et c'est le verrou de FND-007, où l'« énergie sociale » n'a pas d'instrument
de mesure.

**Q6 — Comment une boucle mal conçue déstabilise-t-elle ce qu'elle régule ?**
*Autres disciplines* : dynamique non linéaire et chaos ; économie (boucles de
rétroaction procycliques en finance) ; écologie ; épidémiologie.

## Synthèse

Six résultats à retenir pour le mécanisme de contrôle attendu par le projet.

1. **Pas d'observation, pas de rétroaction.** Toute boucle fermée exige une
   mesure de l'état. Le laser social (FND-007) n'a aucune grandeur
   opérationnellement mesurée : formellement, il n'est **pas observable**.
   C'est la première chose que doit résoudre toute proposition de contrôle, et
   c'est un problème d'instrumentation, pas de théorie.
2. **On ne supprime pas une perturbation, on la déplace** (intégrale de
   Bode). Toute contre-mesure qui atténue une dynamique dans un registre doit
   être soupçonnée de l'amplifier dans un autre. Ce résultat donne au projet
   son objection la plus forte contre les contre-mesures naïves — et il est
   empiriquement cohérent avec le constat de FND-010 sur le scepticisme
   généralisé produit par l'inoculation.
3. **Le retard tue la boucle.** Une contre-mesure lente ne se contente pas
   d'être inefficace : elle consomme la marge de phase et peut amplifier
   l'oscillation. Dans un cycle médiatique, le retard de détection et de
   décision est probablement le paramètre critique.
4. **L'optimalité ne garantit pas la robustesse** (Doyle, 1978). Un mécanisme
   optimisé contre un modèle de société sera fragile exactement dans la mesure
   où ce modèle est faux — et il l'est.
5. **La commandabilité structurelle d'un grand réseau ne prouve rien**
   (critique de Cowan et al.). Presque tout grand réseau est commandable en
   droit. Le seul argument sérieux est énergétique, et il est en FND-014.
6. **Le verrouillage par injection est l'analogie la plus prometteuse.** Un
   signal faible, à la bonne fréquence et dans une plage d'accrochage étroite,
   impose sa phase à un oscillateur bien plus puissant. C'est le mécanisme
   physique qui correspond le mieux à l'intuition d'une attaque à faible coût
   et à grand effet — **et sa plage d'accrochage étroite est exactement la
   contrainte qui rend l'attaque difficile.**

## Limites

- **L'analogie n'est pas une application.** Les hypothèses du contrôle —
  modèle connu, état mesurable, entrées fiables, dynamique stationnaire — sont
  toutes fausses pour une société. Cette fondation doit servir à formuler des
  contraintes et des impossibilités, pas à prétendre piloter.
- **Le corpus classique n'a pas été re-vérifié.** Résultats de manuel,
  stables, mais références à contrôler.
- **La section sur les lasers physiques est de mémoire**, y compris les
  analogies proposées (déclenchement, verrouillage par injection). Elles sont
  suggestives ; **aucune n'est établie dans la littérature du laser social**,
  qui ne traite ni du déclenchement ni du verrouillage par injection. Ce sont
  des hypothèses de ce dépôt, à présenter comme telles — et ce sont peut-être
  la contribution originale la plus accessible du projet.
- **Le champ « contrôle des dynamiques d'opinion » n'a pas été dépouillé**,
  alors qu'il est le plus proche voisin du travail. Les tutoriels de
  Proskurnikov et Tempo sont la première lecture à faire.
- **Aucune question normative n'est traitée.** « Qui tient la boucle » est la
  question politique décisive, et la théorie du contrôle n'a rien à en dire.

## Sources

**Vérifiées en ligne le 2026-08-27.**
- Yang-Yu Liu, Jean-Jacques Slotine, Albert-László Barabási, « Controllability
  of complex networks », *Nature*, vol. 473, n° 7346, p. 167-173, 2011.
  DOI 10.1038/nature10011.
  https://www.nature.com/articles/nature10011
- Noah Cowan, Erick Chastain, Daril Vilhena, James Freudenberg, Carl
  Bergstrom, « Nodal Dynamics, Not Degree Distributions, Determine the
  Structural Controllability of Complex Networks », *PLOS ONE*, 2012.
  **Critique essentielle** : recentre le problème sur la
  quasi-incommandabilité et le coût, non sur la possibilité.
  https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0038398
- Anton Proskurnikov et Roberto Tempo, « A tutorial on modeling and analysis
  of dynamic social networks », parties I et II, *Annual Reviews in Control*,
  vol. 43 (2017) et vol. 45 (2018). **Le champ voisin à dépouiller.**

**Non vérifiées dans cette session — corpus classique.**
- James Clerk Maxwell, « On Governors », *Proceedings of the Royal Society*,
  1868.
- Aleksandr Lyapunov, *Problème général de la stabilité du mouvement*, 1892.
- Harry Nyquist, « Regeneration Theory », *Bell System Technical Journal*,
  1932 ; Harold Black, amplificateur à contre-réaction, 1934.
- Hendrik Bode, *Network Analysis and Feedback Amplifier Design*, 1945.
  **Intégrale de sensibilité, effet matelas d'eau.**
- Norbert Wiener, *Cybernetics*, 1948.
- Rudolf Kalman, travaux de 1960 sur la représentation d'état, la
  commandabilité, l'observabilité et le filtrage. **Fondation de la théorie
  moderne.**
- W. Ross Ashby, *An Introduction to Cybernetics*, 1956 (loi de la variété
  requise) ; Roger Conant et W. Ross Ashby, « Every good regulator of a system
  must be a model of that system », 1970.
- John Doyle, « Guaranteed margins for LQG regulators: none », *IEEE
  Transactions on Automatic Control*, 1978. **Une page, un résultat décisif.**
- George Zames, formulation du problème *H*∞, 1981 ; Doyle, Glover,
  Khargonekar, Francis, solution par équations de Riccati, 1989.
- Karl Johan Åström et Richard Murray, *Feedback Systems: An Introduction for
  Scientists and Engineers*. **Meilleure introduction moderne, disponible en
  ligne.**
- Hassan Khalil, *Nonlinear Systems* ; Jean-Jacques Slotine et Weiping Li,
  *Applied Nonlinear Control*.

**Lasers physiques — de mémoire, à vérifier.**
- Anthony Siegman, *Lasers*, University Science Books, 1986 ; Orazio Svelto,
  *Principles of Lasers*. Équations de bilan, oscillations de relaxation,
  déclenchement, blocage de modes, verrouillage par injection, rétroaction
  optique et chaos.

**Relations.** Référence FND-007 (laser social, dont ce corpus fournit les
contraintes) et FND-008 (réseaux) ; complété par FND-014 (contrôle optimal),
qui traite du coût de la commande.
