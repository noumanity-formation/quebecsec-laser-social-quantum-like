---
type: fondation
id: FND-012
titre: "Social hacking : ingénierie sociale et manipulation des systèmes sociaux"
version: 0.1.0
status: actif
date: 2026-08-27
---

# FND-012 - Social hacking : ingénierie sociale et manipulation des systèmes sociaux

- **Objectif** : établir ce que la recherche en sécurité sait de l'attaque de
  la couche humaine — à l'échelle de l'individu (ingénierie sociale) et à
  l'échelle du système social (opérations d'influence, comportement
  inauthentique coordonné). Pour qui : un public d'experts en cybersécurité,
  qui connaît la première échelle et beaucoup moins la seconde, et à qui il
  faut montrer que ce sont deux régimes distincts d'un même problème.

## Note de rigueur

Cette fondation traite d'un domaine où **la littérature académique est mince
et la littérature commerciale est abondante**. C'est le fait méthodologique
dominant, et il doit être énoncé avant tout chiffre.

**Vérifié en ligne le 2026-08-27** : l'existence et le contenu de deux
systématisations des connaissances — « SoK: Human-Centered Phishing
Susceptibility » (arXiv:2202.07905) et « Social Engineering Attacks: A
Systemisation of Knowledge on People Against Humans » (Thomson, Bewong,
Mahboubi et Zia, arXiv:2601.04215, soumis le 19 décembre 2025), qui organise
le domaine en trois dimensions — humaine (connaissances, aptitudes,
comportements), organisationnelle (culture et normes informelles) et
adversariale (motivations, techniques, économie de l'attaquant). A également
été vérifiée l'existence d'une littérature académique appliquant les
principes de persuasion de Cialdini à l'hameçonnage (Ferreira et Lenzini,
2015 ; travaux ultérieurs sur personnalité et susceptibilité).

**Vérifié, mais non fiable** : les statistiques de prévalence et de coût
(pertes déclarées, taux de succès des campagnes assistées par IA, réduction
du taux de clic après formation) proviennent de **rapports de fournisseurs de
sécurité et de blogues commerciaux**, sans méthodologie publiée, sans
échantillonnage documenté et avec un conflit d'intérêt direct — ces
organisations vendent la solution au problème qu'elles mesurent. Elles sont
signalées comme telles dans les sources et **ne doivent pas être présentées
comme des résultats de recherche**. Une exception partielle : les rapports
d'agences publiques et le rapport annuel d'enquêtes sur les brèches, dont la
méthodologie est au moins décrite.

**Non vérifié dans cette session** : les ouvrages praticiens (Mitnick,
Hadnagy), les cadres opérationnels (MITRE ATT&CK, DISARM), et la littérature
sur les opérations d'information, tous rapportés de mémoire.

**Cadre d'usage.** Cette fondation est une revue de littérature destinée à
une présentation devant un public de sécurité, dans un cadre défensif et
d'évaluation de faisabilité. Elle décrit des **catégories d'attaque et leurs
mécanismes documentés** ; elle ne fournit ni procédure, ni gabarit, ni outil.
C'est un choix délibéré : le niveau taxonomique est celui qui sert l'analyse
et la défense, et le niveau opératoire ne l'est pas.

Vitesse de vieillissement : **rapide**. Les techniques suivent les
plateformes et les outils ; l'arrivée des modèles génératifs a modifié
l'économie de l'attaque en deux ans.

## Cadrage

**Dans le périmètre.** Deux échelles, et leur articulation.
- *Échelle individuelle* : l'ingénierie sociale au sens de la sécurité
  informatique — obtenir d'une personne une action ou une information qu'elle
  n'aurait pas donnée à un demandeur légitimement identifié.
- *Échelle systémique* : la manipulation des mécanismes d'un système social —
  amplification artificielle, comportement inauthentique coordonné,
  détournement des règles d'une plateforme ou d'une institution.

**Hors périmètre.** Les techniques d'exploitation logicielle. La sécurité
opérationnelle des campagnes électorales (infrastructure, listes, machines),
qui relèverait d'une fondation distincte. Les fondements psychologiques de
la persuasion, traités dans FND-011.

**Définitions de travail.**

- *Ingénierie sociale* : au sens sécuritaire, toute attaque exploitant
  l'interaction humaine pour contourner un contrôle. Lastdrager (2014) en
  propose une définition de synthèse à partir d'une revue systématique des
  usages du terme — la profusion de définitions concurrentes étant elle-même
  un symptôme de l'immaturité du domaine.
- *Prétexte* : scénario fabriqué qui rend la demande plausible. C'est la pièce
  centrale de presque toute attaque documentée.
- *Comportement inauthentique coordonné* : usage coordonné de faux comptes ou
  de personas pour manipuler une conversation publique, en trompant sur
  l'identité de l'émetteur plutôt que sur le contenu du message.
- *Astroturfing* : simulation d'un mouvement spontané de la base.
- *Hacking d'un système* : au sens de Schneier, exploitation d'une règle
  conformément à sa lettre et contre son intention. **Cette définition est la
  plus utile au projet** : elle unifie l'exploit logiciel, l'optimisation
  fiscale et la manipulation d'un règlement électoral sous une même
  description.

## Corps

### 1. Le domaine, sa structure, ses résultats et ses usages

**1.1 L'échelle individuelle : ce que la recherche établit.**

*Le vecteur humain domine.* Les rapports d'incidents concordent depuis plus
d'une décennie : une part majoritaire des brèches implique un élément humain,
et l'hameçonnage reste le principal moyen d'accès initial. Les chiffres
précis varient d'un rapport à l'autre et méritent la réserve énoncée plus
haut, mais l'**ordre de grandeur et la direction** sont constants et
recoupés.

*Les principes de persuasion structurent les attaques.* La recherche
académique confirme que les messages d'hameçonnage se laissent classer par
les principes de Cialdini (voir FND-011), avec une prédominance de
l'**autorité**, de l'**urgence et de la rareté**, de l'**affect fort** et de la
**réciprocité**. Un résultat plus fin mérite d'être retenu : les messages
fondés sur la **sympathie** seraient les plus efficaces, tandis que la
combinaison **autorité + rareté** éveille davantage la suspicion. Autrement
dit, la technique la plus intuitive n'est pas la plus performante — et c'est
exactement ce que prédit la théorie de la réactance et de la connaissance de
la persuasion (FND-011).

*La susceptibilité individuelle est mal prédite.* La systématisation
« SoK: Human-Centered Phishing Susceptibility » conclut que le domaine manque
d'un modèle unifié : les prédicteurs individuels — traits de personnalité,
âge, expérience, charge cognitive — donnent des résultats inconstants d'une
étude à l'autre, et les protocoles ne sont pas comparables entre eux. **La
susceptibilité tient probablement davantage au contexte, à la charge de
travail et à la plausibilité du prétexte qu'à la personne.**

*Trois principes structurels de Stajano et Wilson* (« Understanding scam
victims: seven principles for systems security », *Communications of the
ACM*, 2011), issus de l'analyse d'escroqueries réelles : la fenêtre
temporelle (l'urgence supprime la vérification), le principe de distraction,
et l'exploitation de la conformité aux normes sociales — refuser coûte
socialement, et ce coût est le levier. **C'est le texte le plus utile du
domaine pour un public technique**, parce qu'il raisonne en termes de
propriétés systémiques et non de faiblesses individuelles.

*Le cadre à trois dimensions de Thomson et al. (2025)* : la susceptibilité se
comprend par la combinaison de la dimension **humaine** (connaissances,
aptitudes, comportements), de la dimension **organisationnelle** (culture et
normes informelles, qui déterminent si signaler un doute est coûteux ou
valorisé) et de la dimension **adversariale** (motivations et calcul de
rentabilité de l'attaquant). Les auteurs identifient des grappes de risque
persistantes autour de l'usage d'Internet et des médias sociaux, et proposent
un entraînement adaptatif segmenté plutôt qu'uniforme.

*L'efficacité de la sensibilisation est contestée.* Les chiffres de réduction
du taux de clic après formation proviennent presque exclusivement des
fournisseurs qui vendent la formation. La littérature académique est plus
réservée : les effets décroissent rapidement, les exercices simulés ont des
coûts organisationnels (érosion de la confiance, sous-déclaration), et le
taux de clic est un indicateur médiocre de la posture réelle. **Le parallèle
avec l'inoculation psychologique de FND-010 est exact, et instructif : dans
les deux domaines, la contre-mesure la plus déployée est celle dont la preuve
est la plus faible.**

**1.2 L'échelle systémique : manipuler un système plutôt qu'une personne.**

*Le changement de nature.* À l'échelle individuelle, l'attaque trompe une
cible sur l'identité ou l'intention d'un interlocuteur. À l'échelle
systémique, elle trompe un **public et un algorithme** sur la
**distribution** d'une opinion : elle fabrique l'apparence d'un nombre. Ce
n'est plus de la persuasion, c'est de la **falsification de preuve sociale**.
Le lien théorique est direct : la preuve sociale (FND-011), la conformité
d'Asch (FND-009), la falsification des préférences de Kuran et les modèles de
seuil de Granovetter (FND-003) disent tous que la perception de ce que font
les autres détermine l'action. Manipuler cette perception coûte beaucoup moins
cher que persuader.

*Techniques documentées, au niveau taxonomique.* Astroturfing et personas
inauthentiques ; comptes automatisés et semi-automatisés ; détournement de
mots-clics et de tendances ; recyclage de contenu authentique dans un cadrage
faux ; ciblage de journalistes comme relais involontaires ; exploitation des
règles de modération et de signalement contre des cibles légitimes ;
manipulation des systèmes de recommandation par l'engagement artificiel.

*La désinformation participative* (Kate Starbird, voir FND-003) : les
campagnes les plus efficaces ne fabriquent pas le contenu, elles **amorcent**
et laissent des participants sincères faire la diffusion. Conséquence
défensive majeure : chercher les faux comptes ne suffit pas, puisque
l'essentiel du volume est produit par des comptes authentiques.

*L'échelle de percée* (Ben Nimmo) : cadre d'évaluation de l'impact réel d'une
opération, de la simple existence sur une plateforme jusqu'à la reprise par
des médias grand public ou par des responsables politiques. **Outil
d'évaluation honnête** : la grande majorité des opérations documentées
n'atteignent jamais les niveaux supérieurs. Le taux d'échec est la donnée la
plus souvent omise.

*Cadres de description.* MITRE ATT&CK couvre l'accès initial par hameçonnage
et l'ingénierie sociale du côté informatique. Le cadre **DISARM** (issu du
travail antérieur connu sous le nom d'AMITT) transpose la logique
tactiques-techniques-procédures aux opérations d'influence, ce qui permet de
décrire une campagne d'influence dans le même vocabulaire qu'une intrusion.
**C'est le pont conceptuel dont un public de cybersécurité a besoin** pour
aborder le sujet de ce projet.

**1.3 Le hacking des systèmes sociaux, au sens de Schneier.**

*Bruce Schneier* (*A Hacker's Mind*, 2023) généralise la notion : un
*hack* est l'exploitation d'un système conforme à ses règles et contraire à
son intention, qui subvertit l'objectif du système sans en violer la lettre.
Sous cette définition, l'optimisation fiscale, l'obstruction parlementaire,
le charcutage électoral et le détournement d'un règlement d'assemblée sont
des hacks au même titre qu'un débordement de tampon. Trois propriétés en
découlent, et elles structurent le projet :
1. *Un hack révèle une faille de spécification*, pas une faute morale
   individuelle.
2. *Les systèmes sociaux se corrigent lentement* — leur cycle de correctif se
   mesure en années et passe par un processus politique, lui-même attaquable.
3. *La puissance de calcul et l'automatisation changent l'échelle* : ce qui
   demandait un cabinet de juristes peut être recherché systématiquement.

Cette perspective est celle qui permet de présenter une attaque contre un
processus démocratique à un public de sécurité **sans changer de vocabulaire
ni de méthode d'analyse**. Elle est aussi celle qui impose la conclusion
défensive : la contre-mesure n'est pas de former les citoyens, c'est de
corriger la spécification.

**1.4 Ce que l'IA générative change.**

Trois changements, dont deux sont établis et un est spéculatif.
1. *Le coût marginal de la personnalisation tombe à zéro.* Le prétexte
   crédible, adapté à la cible, dans sa langue et son registre, ne demande
   plus de travail humain. C'est le changement le mieux documenté, y compris
   par les rapports de fournisseurs — dont les chiffres précis restent à
   traiter avec la réserve indiquée.
2. *L'usurpation de voix et d'image devient accessible*, ce qui affecte
   directement les procédures de vérification fondées sur la reconnaissance
   d'un interlocuteur.
3. *L'automatisation des personas à grande échelle*, permettant une
   falsification de preuve sociale plus difficile à détecter par les
   signatures comportementales classiques. **Effet réel sur l'opinion non
   établi** : la contrainte de FND-011 tient toujours — produire du volume
   n'est pas produire de la persuasion, et l'échelle de percée reste le bon
   test.

**1.5 Cadre éthique et légal.**

Le domaine ne se pratique légitimement que sous **mandat écrit** : règles
d'engagement, périmètre, personnes exclues, procédure d'arrêt, gestion des
données personnelles collectées, et débriefing. En recherche, les tests
impliquant des sujets humains relèvent d'un comité d'éthique ; au Canada, le
cadre applicable est l'Énoncé de politique des trois Conseils, et la
collecte de renseignements personnels est encadrée par les lois fédérale et
québécoise sur la protection des renseignements personnels. **Ces éléments
n'ont pas été vérifiés sur source primaire dans cette session** et doivent
l'être avant toute affirmation juridique dans un livrable.

Pour ce projet en particulier : une démonstration de faisabilité présentée
devant un panel d'experts se situe dans le registre de la **modélisation de
menace**, pas de l'opération. La distinction entre décrire un mécanisme et
fournir un moyen est celle qui rend le travail présentable, et elle doit être
tenue explicitement dans le rapport comme dans la présentation.

### 2. Évolution du domaine, intervenants et contributions

**Préhistoire (1960-1990).** Le *phreaking* téléphonique établit le motif
fondateur : le système technique est solide, l'opérateur humain ne l'est pas.
La littérature de l'escroquerie confidentielle est bien plus ancienne et
décrit déjà tous les mécanismes ; le domaine informatique la redécouvre sans
la citer.

**L'ère Mitnick (1990-2005).** *Kevin Mitnick* devient la figure publique du
domaine, puis en écrit la première synthèse praticienne (*The Art of
Deception*, 2002). **Contribution** : imposer l'idée que l'humain est un
composant du système de sécurité, et non son environnement. Limite : un
corpus d'anecdotes, sans méthode.

**Formalisation praticienne (2005-2015).** *Christopher Hadnagy* (*Social
Engineering: The Art of Human Hacking*, 2011) construit un cadre méthodique
et fonde une pratique professionnelle. *Frank Stajano* et *Paul Wilson*
(2011) apportent la contribution la plus solide de la période : sept
principes tirés de l'analyse d'escroqueries réelles, formulés en termes
systémiques. *Elmer Lastdrager* (2014) : revue systématique et définition de
synthèse. **Contribution collective** : sortir de l'anecdote.

**Institutionnalisation (2013-2020).** MITRE publie ATT&CK, qui donne au
domaine un vocabulaire commun d'adversaire. La sensibilisation devient une
industrie. La recherche académique s'organise autour de la susceptibilité à
l'hameçonnage, avec le *Phish Scale* du NIST pour mesurer la difficulté d'un
message — contribution méthodologique utile, car elle permet enfin de comparer
des campagnes entre elles.

**Le tournant informationnel (2016-2022).** L'ingérence documentée dans des
processus électoraux fait entrer les opérations d'influence dans le champ de
la sécurité. *Ben Nimmo* et l'Atlantic Council, la *Stanford Internet
Observatory*, *Graphika*, les équipes de politique publique des plateformes
produisent les corpus d'analyse. *Renée DiResta* : synthèse et diffusion.
*AMITT*, devenu *DISARM* : transposition du modèle tactiques-techniques aux
opérations d'influence. **Contribution collective** : donner à la
désinformation un vocabulaire d'attaquant plutôt qu'un vocabulaire de
véracité — ce qui est un progrès analytique décisif, puisque l'objet devient
le comportement et non le contenu.

**L'ère générative (2022-2026).** Modèles de langage et synthèse
audiovisuelle. La production académique est encore instable, la production
commerciale abondante et intéressée. *Bruce Schneier* (*A Hacker's Mind*,
2023) fournit le cadre conceptuel le plus général et le plus utile à ce
projet. *Thomson, Bewong, Mahboubi et Zia* (2025) proposent la
systématisation à trois dimensions la plus récente.

**Ce sur quoi le domaine ne s'entend pas.**
- La sensibilisation fonctionne-t-elle, et comment le mesurer autrement que
  par le taux de clic ?
- La susceptibilité est-elle un trait individuel ou un état contextuel ?
- Les opérations d'influence ont-elles un effet mesurable sur les
  comportements, ou seulement sur la visibilité et la confiance ?
- Faut-il publier les techniques ? Le débat sur la divulgation, ancien en
  sécurité logicielle, est bien moins tranché pour les attaques sociales,
  parce qu'il n'existe pas de correctif à déployer.

### 3. Questions de recherche principales, et qui d'autre s'en occupe

**Q1 — Qui est susceptible, quand, et pourquoi ?**
*Autres disciplines* : psychologie de la persuasion (FND-011) ; psychologie
différentielle ; facteurs humains et ergonomie cognitive ; sociologie des
organisations (culture du signalement).

**Q2 — La sensibilisation change-t-elle durablement les comportements ?**
*Autres disciplines* : sciences de l'éducation ; santé publique (modèles de
campagne) ; psychologie politique (l'inoculation pose la même question,
FND-010) ; économie comportementale.

**Q3 — Comment détecter un comportement inauthentique coordonné ?**
*Autres disciplines* : science des réseaux ; apprentissage automatique et
détection d'anomalies ; linguistique computationnelle ; statistique
judiciaire — et, du côté électoral, la détection statistique de fraude
(FND-008).

**Q4 — Quel est l'effet réel d'une opération d'influence ?**
La question la plus mal résolue du domaine.
*Autres disciplines* : science politique (effets minimaux, FND-004) ;
sciences de la communication ; économétrie causale ; sociologie
computationnelle (FND-003).

**Q5 — Comment concevoir un système social résistant aux hacks ?**
*Autres disciplines* : théorie des mécanismes et choix social résistant à la
manipulation (FND-005) ; droit et rédaction législative ; ingénierie de la
sûreté ; théorie du contrôle (FND-013, FND-014).

**Q6 — Que change l'IA générative à l'économie de l'attaque ?**
*Autres disciplines* : intelligence artificielle ; économie de la sécurité
(coût de l'attaque contre coût de la défense, à la manière de Ross
Anderson) ; droit ; criminologie.

**Q7 — Quelles règles de divulgation pour des vulnérabilités sociales ?**
*Autres disciplines* : éthique de la recherche ; droit ; études des sciences
et techniques ; politiques publiques.

## Synthèse

Six points à retenir.

1. **Deux échelles, deux mécanismes.** À l'échelle individuelle, on trompe une
   personne sur une identité. À l'échelle systémique, on trompe un public et
   un algorithme sur une **distribution**. Le second est une falsification de
   preuve sociale, il coûte beaucoup moins cher que la persuasion, et c'est
   celui qui concerne un processus démocratique.
2. **Le prétexte plausible fait le travail, pas la technique.** La recherche
   converge : la susceptibilité tient au contexte, à l'urgence et à la
   plausibilité, davantage qu'aux caractéristiques de la personne.
3. **La technique intuitive n'est pas la meilleure.** Autorité et rareté
   combinées éveillent la suspicion ; la sympathie fonctionne mieux. Ce
   résultat est cohérent avec la réactance (FND-011) : ce qui se donne à voir
   comme une pression échoue.
4. **La contre-mesure la plus déployée est celle dont la preuve est la plus
   faible.** La sensibilisation en sécurité et l'inoculation psychologique
   partagent ce diagnostic, et les deux domaines l'ignorent mutuellement. Le
   signaler est une contribution que ce projet peut faire.
5. **Un hack est une faille de spécification, pas une faute morale**
   (Schneier). Sous cette définition, un processus démocratique s'analyse
   exactement comme un système technique — et sa faiblesse principale est que
   son cycle de correctif se compte en années et passe par le processus
   politique lui-même.
6. **Le taux d'échec est la donnée manquante.** L'échelle de percée de Nimmo
   rappelle que la plupart des opérations documentées n'atteignent jamais la
   reprise médiatique. Une présentation honnête doit donner ce dénominateur.

## Limites

- **Les chiffres du domaine ne sont pas des résultats de recherche.** Les
  taux de succès, de réduction et de coût circulent depuis des rapports
  commerciaux sans méthode. Cette fondation refuse d'en faire des faits, et
  toute reprise dans un livrable doit nommer la source et son intérêt.
- **Aucune mesure d'effet sur l'opinion.** Le domaine sait décrire des
  techniques et compter des comptes supprimés ; il ne sait pas mesurer un
  déplacement d'opinion attribuable. C'est la limite qui pèse le plus lourd
  sur l'évaluation de faisabilité attendue par le projet.
- **Rien de spécifique au Québec** : ni incidents documentés, ni écosystème
  informationnel, ni cadre juridique vérifié.
- **Le cadre juridique et éthique n'est pas sourcé.** Les mentions de l'Énoncé
  de politique des trois Conseils et des lois sur la protection des
  renseignements personnels sont données de mémoire et doivent être vérifiées.
- **Niveau taxonomique assumé.** Cette fondation décrit des catégories et des
  mécanismes, pas des procédures. C'est un choix, pas un oubli : le niveau
  opératoire ne sert ni l'analyse ni la présentation, et il déplacerait le
  travail hors du registre défensif dans lequel il est mené.
- **Ce qu'il faudrait pour aller plus loin** : la lecture intégrale des deux
  systématisations vérifiées ; la consultation du cadre DISARM sur source
  primaire ; et une recherche sur les incidents d'influence documentés au
  Canada, notamment les travaux des commissions et organismes fédéraux sur
  l'ingérence étrangère, non couverts ici.

## Sources

**Vérifiées en ligne le 2026-08-27.**
- Scott Thomson, Michael Bewong, Arash Mahboubi, Tanveer Zia, « Social
  Engineering Attacks: A Systemisation of Knowledge on People Against
  Humans », arXiv:2601.04215, soumis le 19 décembre 2025. **Systématisation
  la plus récente** : dimensions humaine, organisationnelle et adversariale.
  https://arxiv.org/abs/2601.04215
- « SoK: Human-Centered Phishing Susceptibility », arXiv:2202.07905.
  Constate l'absence de modèle unifié de la susceptibilité.
  https://arxiv.org/pdf/2202.07905
- Ana Ferreira et Gabriele Lenzini, « Principles of Persuasion in Social
  Engineering and Their Use in Phishing », Springer, 2015.
  DOI 10.1007/978-3-319-20376-8_4.
- « A Survey on the Principles of Persuasion as a Social Engineering
  Strategy », arXiv:2412.18488 ; « Persuasion and Phishing: Analysing the
  Interplay of Persuasion Tactics in Cyber Threats », arXiv:2412.18485.
- Littérature sur personnalité et susceptibilité à l'hameçonnage,
  *Applied Ergonomics* (2020) et *Computers in Human Behavior* (2019) :
  la sympathie est le principe le plus efficace, autorité et rareté combinées
  éveillent la suspicion.

**Non vérifiées dans cette session — corpus praticien et académique.**
- Frank Stajano et Paul Wilson, « Understanding scam victims: seven
  principles for systems security », *Communications of the ACM*, 2011.
  **Le meilleur texte du domaine pour un public technique.**
- Kevin Mitnick et William Simon, *The Art of Deception*, Wiley, 2002.
  Fondateur, anecdotique.
- Christopher Hadnagy, *Social Engineering: The Art of Human Hacking*, Wiley,
  2011 (et éditions ultérieures). Cadre praticien de référence.
- Elmer Lastdrager, « Achieving a consensual definition of phishing based on
  a systematic review of the literature », *Crime Science*, 2014.
- NIST, *Phish Scale* : instrument de mesure de la difficulté d'un message
  d'hameçonnage.
- MITRE ATT&CK, techniques d'accès initial par hameçonnage.
- Cadre **DISARM** (anciennement AMITT) : tactiques et techniques des
  opérations d'influence.
- Bruce Schneier, *A Hacker's Mind*, Norton, 2023. **Cadre conceptuel central
  de cette fondation** : le hack comme exploitation d'une faille de
  spécification.
- Ben Nimmo, échelle de percée (*breakout scale*), Brookings, 2020.
- Renée DiResta, travaux de la Stanford Internet Observatory sur les
  opérations d'influence.
- Kate Starbird, désinformation participative (voir FND-003).
- Ross Anderson, *Security Engineering* : économie de la sécurité et
  incitations mal alignées.

**Sources commerciales — à traiter comme telles, jamais comme résultats.**
Les rapports annuels de fournisseurs de sécurité et les compilations de
statistiques d'ingénierie sociale consultées le 2026-08-27 rapportent des
chiffres de prévalence, de coût et d'efficacité de la formation, sans
méthodologie publiée et avec un conflit d'intérêt direct. Exemple de ce
corpus, cité pour mémoire et non comme preuve :
https://www.thesslstore.com/blog/social-engineering-statistics/
Le rapport annuel d'enquêtes sur les brèches de données (Verizon DBIR) et les
publications des agences publiques de cybersécurité offrent une méthodologie
au moins décrite et sont préférables ; **ils n'ont pas été consultés dans
cette session.**

**Relations.** Référence FND-003 (désinformation participative, cascades),
FND-005 (manipulation des règles électorales), FND-009 et FND-011
(mécanismes psychologiques exploités), FND-010 (efficacité contestée des
contre-mesures) ; alimente le rapport d'analyse et la présentation attendus
par la session.
