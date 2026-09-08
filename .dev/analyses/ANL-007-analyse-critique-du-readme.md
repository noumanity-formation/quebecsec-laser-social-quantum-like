---
type: analyse
id: ANL-007
titre: "Analyse critique du README de présentation"
version: 0.1.0
status: actif
date: 2026-09-08
---

# ANL-007 - Analyse critique du README de présentation

> Le README est publiable en l'état sur la forme, mais il annonce une
> présentation qui n'est pas celle du dépôt : il promet un mode d'emploi que la
> présentation refuse d'être, désigne comme surface d'attaque l'électeur que la
> présentation disculpe, et pose en titre une question à laquelle il ne répond
> pas alors que la réponse est le résultat du travail. L'écart est
> rhétorique, pas factuel — mais il porte sur les trois points où la
> présentation tient sa valeur.

## Question posée

Le README de la racine, dans sa version du 8 septembre 2026, doit être envoyé
aux organisateurs de QuébecSec. Deux questions : **ce qu'il annonce
correspond-il à ce que le dépôt a produit**, et **où s'écarte-t-il de ce que le
dépôt lui-même établit** ?

La seconde question n'est pas de style. Le dépôt contient vingt-trois
fondations et sept analyses ; un README qui les contredit n'est pas seulement
mal écrit, il est réfutable par son propre dépôt.

## Méthode

**Artefact analysé** : `README.md` à la racine, 45 lignes, 495 mots, quatre
sections (titre et chapeau, Résumé, Auteur, noumanity). Version en cours au
2026-09-08, non suivie par git (`?? README.md`).

**Déclaration d'intérêt.** La version initiale de ce fichier a été rédigée par
l'agent à la tâche 1 de SES-002. La version analysée ici est une **réécriture
humaine** qui l'a remplacée. L'analyse porte donc en partie sur le
remplacement d'un texte produit par l'analyste. Les constats ci-dessous sont
formulés par confrontation à des artefacts tiers — diapositives, fondations,
analyses — et non par comparaison à la version antérieure, sauf aux constats
9 à 12 où la suppression est le fait constaté.

**Confrontations effectuées** :

- résumé contre diapositives 2, 3, 35, 39, 41, 42 (`.dev/presentations/quebecsec-2026/src/`) ;
- affirmation sur « l'humain » contre FND-012 §1.1 et FND-023 §1.2 ;
- affirmation sur l'ingérence étrangère contre FND-023 §3 et diapositive 35 ;
- qualification d'Andrei Khrennikov contre FND-007 l. 248, plus vérification
  en ligne le 2026-09-08 ;
- chiffres implicites contre FND-020 et ANL-003 ;
- graphie « multi-couleur » : `grep -roh` sur `.dev/`, 34 occurrences au
  singulier, aucune au pluriel ;
- titre contre `src/slide-01/content.md` l. 5 ;
- dates : calcul de l'écart entre le 24 septembre 2026, le déclenchement
  (27 août) et le scrutin (5 octobre).

**Non fait** : aucune modification du fichier. Aucune vérification de la
disponibilité de l'URL de photo. Aucune consultation des organisateurs sur
le format ou la longueur attendus.

## Constats

### A. Écart entre ce que le README annonce et ce que la présentation livre

**1. Le résumé promet un mode d'emploi ; la présentation refuse d'en être un.**
La phrase d'ouverture pose deux questions : « est-il possible de hacker une
élection? Et, si oui, comment faire pour y parvenir? » (l. 8). La diapositive 3
énonce : « **Ce n'est pas** un manuel : aucune donnée collectée, aucune
plateforme sollicitée, aucun individu ciblé, aucun contenu de campagne
rédigé. » La diapositive 43 le répète en clôture. La seconde question du
résumé promet exactement ce que la présentation passe deux diapositives à
retirer.

**2. Le résumé désigne l'humain comme surface d'attaque ; la présentation
conclut l'inverse.** Le résumé annonce « les techniques standards de hacking
social qui exploitent la plus grande faille de vos systèmes et organisations:
l'humain » (l. 10). La diapositive 35, premier point des considérations de
sécurité : « **La surface d'attaque n'est pas l'électeur** : c'est la couche de
cadrage, moins de 15 000 personnes pour 6,4 millions d'électeurs. » Le résumé
ne signale pas qu'il s'agit d'un point de départ destiné à être renversé ; il
l'énonce à l'affirmative.

**3. Le résumé annonce l'ingérence étrangère comme axe ; le dépôt conclut que
l'origine n'est pas le facteur pertinent.** Le résumé pose « la question de
l'ingérence étrangère et des opérations d'influence de masse » (l. 10). La
diapositive 35, point 4 : « **Attribution quasi impossible** : le mécanisme est
disponible à n'importe quelle campagne domestique. Rien ne distingue une
attaque d'une stratégie. » FND-023 §3.4 cite verbatim le rapport final de la
Commission Hogue : « la manipulation de l'information (**qu'elle soit d'origine
étrangère ou non**) représente le plus grand risque pour notre démocratie ».

**4. Le titre pose une question ; le résumé n'y répond pas, même
partiellement.** Le titre demande si la démocratie québécoise pourrait résister
(l. 1). Le résumé se termine sur « nous tenterons d'évaluer la faisabilité »
(l. 12) — une annonce d'intention, pas un résultat. La réponse existe et elle
est tranchée : diapositive 39, « **Pas faisable** » pour la persuasion de
masse et le contrôle par peu de points d'entrée, « **Peut-être faisable** »
pour le déplacement de la base de mesure, et la formule de clôture
« L'attaque efficace n'est pas persuasive. Elle est métrologique. »

**5. La contribution défensive est absente du README.** La diapositive 41
énonce une signature de détection en cinq signes, mesurable sur corpus,
présentée comme le résultat original du travail du côté de la défense. Le
résumé n'en dit rien. Pour une audience de praticiens de la sécurité, c'est le
seul élément du travail directement actionnable, et c'est celui qui n'est pas
annoncé.

### B. Affirmations du README que le dépôt contredit

**6. « la plus grande faille de vos systèmes et organisations: l'humain »
(l. 10) est une thèse que les fondations du dépôt réfutent.** FND-012 §1.1
rapporte que la susceptibilité « tient probablement davantage au contexte, à
la charge de travail et à la plausibilité du prétexte qu'à la personne », et
retient Stajano et Wilson (2011) parce qu'ils « raisonn[ent] en termes de
propriétés systémiques et non de faiblesses individuelles ». FND-023 §1.2
pose que sous la définition de Schneier, retenue comme celle du projet, « un
hack révèle une faille de spécification, pas une faute morale individuelle ».
La formule du README est le lieu commun que les deux fondations démontent, et
elle est énoncée dans la voix de l'auteur, sans distance.

**7. « le mathématicien russe Andrei Khrennikov » (l. 12) est incomplet, et
mal placé.** Vérification faite le 2026-09-08 : Khrennikov est un
mathématicien-physicien **russo-suédois**, né en 1958 à Volgograd, professeur
de mathématiques appliquées à l'**université Linnaeus de Växjö, en Suède**,
où il dirige l'International Center for Mathematical Modeling. FND-007 l. 248
l'identifie par cette affiliation et ne le qualifie nulle part de « russe ».
Le fait constaté n'est pas seulement l'imprécision : c'est que la seule
mention d'une nationalité dans tout le document apparaît **deux phrases après**
l'annonce d'un développement sur l'ingérence étrangère, dans un texte qui, par
ailleurs, ne nomme aucun État.

**8. « un scénario d'attaque exotique » (l. 12) qualifie le travail plus
faiblement que le dépôt ne le fait.** Le rapport préliminaire présente le
modèle comme « une contribution originale » assortie d'un programme de
falsification, et la diapositive 42 liste cinq travaux dont deux peuvent
**réfuter** le modèle — « une violation tue le modèle ». « Exotique » désigne
une curiosité ; le dépôt revendique une hypothèse réfutable.

### C. Éléments présents ailleurs dans le dépôt et absents du README

**9. Aucune mention du statut des résultats.** Le README de la présentation
(`.dev/presentations/quebecsec-2026/README.md`) prescrit : « **Ne jamais
retirer ces mentions** tant que les calculs n'ont pas été faits ». Les
diapositives 2, 30, 32, 33 et 43 portent l'avertissement. Le README de la
racine — **la seule pièce que les organisateurs et le public liront avant la
soirée** — ne dit nulle part que les calculs n'ont pas été exécutés ni que les
résultats de simulation sont fabriqués.

**10. Aucune mention du contexte temporel.** La présentation a lieu le
24 septembre 2026, soit le **28e jour** d'une campagne déclenchée le 27 août et
**11 jours avant** le scrutin du 5 octobre. La diapositive 3 le pose
explicitement : « Nous parlons d'un système **en cours de fonctionnement**. »
Le README donne la date sans la situer. Constat connexe, établi par FND-023
§4.2 : depuis juillet 2026, la propagation sciemment fausse d'information
visant le processus électoral ou une candidature est une **infraction pénale**
au Québec (loi 98, sanctionnée le 30 mai 2025). Le README ne contient aucun
énoncé faux et n'est donc pas visé ; le constat est que le document ne
manifeste aucune conscience du régime dans lequel il paraît.

**11. Plus aucun pointeur vers le travail.** Le README ne référence ni les
vingt-trois fondations, ni les sept analyses, ni le rapport préliminaire, ni le support de
présentation. Un lecteur qui arrive sur le dépôt par ce fichier n'a aucun
chemin vers son contenu.

**12. Le lien avec les travaux antérieurs de l'auteur a disparu de la bio.**
La bio s'achève sur « En décembre 2021, Jérémy a fondé noumanity, une
compagnie qui se consacre à la recherche DeepTech » (l. 26). Les README des
présentations antérieures (`linux-and-quantum-computers`,
`intentional-doers-governance`) rattachent chacun le travail présenté à un
programme de recherche nommé — la Triade Cyber-IA-Quantique, la
recherche-action en théorie des organisations. Ici, rien ne relie la
présentation à un programme.

### D. Cohérence interne et forme

**13. Deux titres coexistent dans le dépôt.** README l. 1 : « QuébecSec Spécial
Élection: la démocratie québécoise pourrait-elle résister à une attaque de
"laser social multi-couleurs" ? ». `slide-01/content.md` l. 5 : « Laser social
multi-couleur : attaquer une démocratie par la question de l'urne ». Le second
est le titre affiché à l'écran le soir même.

**14. La graphie du mécanisme diffère du reste du dépôt.** Le README écrit
« multi-couleurs » au pluriel (l. 1). Le dépôt compte **34 occurrences de
« multi-couleur » au singulier et aucune au pluriel**, y compris dans le titre
du rapport, celui de ANL-005 et celui de la diapositive 1.

**15. L'atout de crédibilité le plus direct est en dernière position du
document.** Le dernier point de la section noumanity (l. 43) mentionne la
« recherche fondamentale en Intelligence Quantique (application des théories
quantum-like de Khrennikov […]) ». C'est le seul énoncé du README qui établit
que l'auteur travaille déjà sur le formalisme employé dans la présentation.
Il figure au dernier item d'une liste, dans la section entreprise, après la
bio.

**16. Coquilles et accords relevés.**
- l. 8 : « système électorale québécois » → *électoral*.
- l. 40 : « infrastructures souveraines résitientes et décentralisée » →
  *résilientes et décentralisées*.
- l. 40 : « l'université de Montréal » → *l'Université de Montréal*.
- l. 41 : « recyclage d'énergie résiduel » → *résiduelle* ; « datacenters
  décentralisées » → *décentralisés*, et anglicisme (*centres de données*) ;
  « bio-masse » → *biomasse*.
- l. 42 : « les usages de l'Intelligence Artificielle en recherche appliquées »
  → *appliquée*.
- l. 8 : espace en fin de ligne.

**17. Typographie instable.** Guillemets ASCII (`"laser social multi-couleurs"`,
`"Laser Social"`) là où le reste du dépôt emploie les guillemets français.
Casse instable pour le même objet : « Laser Social » l. 12 contre « laser
social » l. 1. Le titre porte « Élection: » sans espace avant le
deux-points, alors que la même ligne écrit « ? » précédé d'une espace.

**18. Deux éléments non résolus depuis la version précédente.** Le lien vers la
page de l'événement est toujours un commentaire `<!-- À COMPLÉTER -->` (l. 3).
L'URL de la photo (l. 22) porte un jeton d'expiration
(`e=1784930400`) et cessera de fonctionner.

## Réponse

**Ce qu'il annonce ne correspond pas à ce que le dépôt a produit** — mais
l'écart est d'un type particulier, et il faut le nommer précisément pour ne pas
sur-corriger.

Aucun énoncé du README n'est **faux**. Les trois temps annoncés existent bien
dans la présentation : l'ingénierie sociale y est traitée, l'ingérence étrangère
aussi, le laser social multi-couleur en est le cœur. Le résumé est un plan
fidèle du **déroulé**.

L'écart est ailleurs : **le README annonce les prémisses de la présentation
comme s'il s'agissait de ses conclusions.** L'humain comme maillon faible,
l'ingérence étrangère comme menace, le mode d'emploi comme livrable : ce sont
les trois positions que la présentation prend une heure à défaire. Un lecteur
qui décide d'assister sur la foi de ce résumé vient chercher ce que la
présentation lui retirera, et un lecteur qui décide de ne pas venir écarte un
travail dont il n'a lu que le point de départ. Le résumé décrit le voyage sans
jamais dire où il mène, dans un cas où **la destination est tout le
résultat**.

Trois conséquences, par ordre de gravité décroissante.

1. **La promesse « comment faire pour y parvenir » est le seul point qui
   engage autre chose que l'efficacité rhétorique** (constats 1, 9, 10). Une
   présentation donnée à 11 jours d'un scrutin, dans un dépôt public, sous un
   titre qui annonce une attaque, et dont la page d'accueil promet le mode
   d'emploi sans mentionner nulle part que rien n'a été calculé ni qu'aucun
   contenu de campagne n'a été rédigé : l'écart entre cette page et les
   diapositives 2, 3 et 43 est ce qui, dans tout le dossier, se cite le plus
   facilement hors contexte.

2. **Les constats 2, 3 et 6 sont réfutables par le dépôt lui-même.** Un
   membre du panel qui lit le README puis une fondation y trouve une
   contradiction, et la formule « la plus grande faille : l'humain » est
   exactement celle qu'un auditoire de sécurité expérimenté a appris à
   entendre comme un signal de superficialité.

3. **Les constats 4 et 5 sont un manque à gagner, pas un défaut.** Le
   résumé ne dit ni la thèse — l'attaque efficace n'est pas persuasive, elle
   est métrologique — ni la contribution défensive — la signature en cinq
   signes. Ce sont les deux seules choses que ce travail apporte et que
   l'auditoire ne connaît pas déjà.

**Sur la forme** : les constats 13 à 18 se corrigent en une passe et ne
conditionnent rien. Le seul qui porte à conséquence est le 13 : deux titres
coexistent, et c'est celui du README qui sera imprimé dans le programme de la
soirée tandis que c'est celui de la diapositive 1 qui sera projeté.

**Le fichier est-il envoyable en l'état ?** Oui, sans risque factuel. Mais il
vend une présentation moins bonne que celle qui existe, et il l'expose sur son
seul point sensible. La décision appartient à l'humain ; l'analyse ne
modifie pas le fichier.

## Limites

- **Le format attendu par les organisateurs est inconnu.** Longueur maximale
  de l'abstract, présence ou non d'un champ « bio » séparé, existence d'une
  page publique de l'événement : rien de tout cela n'a été vérifié. Plusieurs
  constats (5, 11, 15) supposent que le README sert à la fois de page de dépôt
  et de texte soumis. Si les organisateurs attendent un abstract court, le
  constat 5 change de nature — la signature de détection ne tient peut-être
  pas dans le format.
- **Aucun jugement sur l'efficacité rhétorique effective.** L'analyse
  confronte le README au dépôt, pas à ce qui fait venir du monde à une soirée
  QuébecSec. Il est possible que « comment faire pour y parvenir? » remplisse
  la salle et que ce soit, tout compte fait, le bon calcul — c'est un
  arbitrage qui appartient à l'auteur.
- **La question juridique n'est pas tranchée** et ne peut pas l'être ici. Le
  constat 10 relève une absence de mention, pas une infraction ; FND-023 §4
  signale elle-même que la portée exacte de la nouvelle infraction n'a pas été
  établie sur le texte de loi.
- **Conflit d'intérêt de l'analyste**, déclaré en Méthode : l'agent analyse le
  texte qui a remplacé le sien. Les constats 9, 11 et 12 portent sur des
  suppressions par rapport à cette version antérieure et doivent être lus en
  sachant qui les formule.
- **Non examiné** : la section noumanity au fond (exactitude des partenariats
  nommés, statut des projets de recherche listés), et l'accord de l'auteur sur
  la bio, qui est un texte personnel.

**Relations.** Référence FND-007 (Khrennikov), FND-012 et FND-023 (hacking
social, sens du terme, ancrage canadien et juridique), FND-020 (conjoncture),
ANL-003 (offre par champ), et le support `.dev/presentations/quebecsec-2026/`.
Analyse le `README.md` de la racine dans sa version du 2026-09-08.
