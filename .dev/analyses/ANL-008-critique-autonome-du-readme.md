---
type: analyse
id: ANL-008
titre: "Critique autonome du README : ce que le texte promet, lu sans le dépôt"
version: 0.1.0
status: actif
date: 2026-09-08
---

# ANL-008 - Critique autonome du README : ce que le texte promet, lu sans le dépôt

> Lu seul, le README annonce trois présentations différentes au lieu d'une,
> pose en titre une question que le résumé ne pose pas, et laisse son concept
> central — le « laser social multi-couleurs » — sans définition. Son défaut
> le plus coûteux n'est pas une erreur : c'est que la bio contient la preuve
> de compétence qui rendrait la troisième partie crédible, et que le texte ne
> fait jamais le lien.

## Question posée

ANL-007 a confronté le README au dépôt et lui a reproché de s'en écarter.
Cette analyse-ci fait l'inverse, à la demande de la session : **le README est
la source de vérité**, la présentation est en préparation et devra s'y
conformer.

La question devient donc : **lu seul, par quelqu'un qui n'a accès à rien
d'autre, ce texte tient-il debout ?** Trois sous-questions : annonce-t-il une
présentation cohérente ; annonce-t-il une présentation réalisable ;
donne-t-il à son lecteur une raison de venir ?

## Méthode

**Artefact analysé** : `README.md` à la racine, version du 2026-09-08, 45
lignes, 495 mots.

**Contrainte méthodologique posée par la tâche, et tenue.** Aucune
diapositive, aucune fondation, aucune analyse, aucun rapport du dépôt n'a été
consulté pour former les constats ci-dessous. Le texte est traité comme un
document autonome, tel que le recevrait un organisateur de QuébecSec ou un
lecteur du dépôt. Là où ANL-007 pouvait écrire « le README contredit la
diapositive 35 », cette analyse ne peut écrire que « le paragraphe 2
contredit le paragraphe 3 » — et c'est le seul type de contradiction qu'elle
retient.

**Ce qui a été fait** :

- lecture du document dans l'ordre, en notant à chaque paragraphe ce qu'un
  lecteur sait, ce qu'il attend et ce qu'il ne peut pas encore savoir ;
- confrontation du titre au résumé, du résumé à lui-même, du résumé à la bio,
  et de la bio à la section entreprise ;
- décompte par section : titre et chapeau 38 mots, Résumé 97, Auteur 158,
  noumanity 202 ;
- vérification externe d'une seule affirmation factuelle **portée par le
  texte lui-même** — la qualification d'Andrei Khrennikov (recherche en ligne,
  2026-09-08). C'est une vérification de fait, pas un recours au dépôt.

**Ce qui n'a pas été fait** : l'inventaire des coquilles et de la typographie,
déjà établi ailleurs et sans rapport avec la question posée ici. Aucune
modification du fichier. Aucune hypothèse sur le contenu réel de la
présentation, puisqu'elle n'existe pas encore au sens de cette analyse.

## Constats

### A. Ce que le document promet

**1. Le titre et le résumé ne posent pas la même question.** Le titre demande
si la démocratie québécoise **pourrait résister** à une attaque : c'est une
question de robustesse, posée du point de vue du défenseur, et elle appelle un
verdict. Le résumé demande « est-il possible de **hacker** une élection? Et, si
oui, **comment faire pour y parvenir**? » : c'est une question de faisabilité
et de méthode, posée du point de vue de l'attaquant, et elle appelle une
procédure. Un lecteur qui vient pour le titre et un lecteur qui vient pour le
résumé ne viennent pas à la même présentation.

**2. Le résumé annonce trois parties sans dire ce qui les relie.** « D'abord »
les techniques standards de hacking social ; « puis » l'ingérence étrangère et
les opérations d'influence de masse ; « finalement » un scénario d'attaque
fondé sur le laser social. Les trois connecteurs marquent une **succession**,
jamais une **progression** : rien n'indique ce que la première partie apporte à
la troisième, ni pourquoi il faut avoir vu les deux premières pour comprendre
la dernière. Le lecteur ne peut pas reconstituer l'argument, seulement le
sommaire.

**3. Les trois parties ne portent pas sur le même objet.** La première parle
de « vos systèmes et organisations » — une entreprise, un système
d'information. La deuxième parle d'États et d'opinion publique. La troisième
parle d'une élection québécoise. L'objet attaqué change deux fois en trois
phrases, sans que le texte le signale. La conséquence est visible sur le seul
« vous » du document (constat 8).

**4. Le concept central du titre n'est jamais défini.** « Laser social
multi-couleurs » figure dans le titre, entre guillemets. Le résumé reprend
« le mécanisme quantum-like du "Laser Social" » sans dire ce que c'est, et ne
reprend **jamais** le qualificatif « multi-couleurs », qui est pourtant ce qui
distingue la proposition. Un lecteur referme le document sans savoir ni ce
qu'est un laser social, ni ce qu'une couleur y désigne, ni pourquoi il en
faudrait plusieurs.

**5. L'auteur qualifie ses deux premières parties de « standards » et sa
troisième d'« exotique ».** Les deux mots sont dans le texte. Pris ensemble,
ils annoncent au lecteur deux tiers de contenu déjà connu et un tiers de
fantaisie. Aucun des trois segments n'est présenté comme un apport.

**6. Le document ne promet aucun résultat.** Le verbe de la troisième partie
est « nous tenterons d'évaluer la faisabilité ». Le titre pose une question
fermée — pourrait-elle résister ? — et rien dans le résumé n'indique de quel
côté penche la réponse, ni même qu'une réponse sera donnée.

**7. Le document ne promet aucune capacité au lecteur.** Rien à détecter, rien
à mesurer, rien à corriger, rien à surveiller. Le seul verbe adressé au public
est « demandons-nous ». Pour un public composé de praticiens de la sécurité,
le texte n'énonce aucune raison professionnelle d'être là.

### B. Cohérence interne

**8. Le seul « vous » du document vise le mauvais objet.** « la plus grande
faille de vos systèmes et organisations: l'humain ». C'est le seul moment où
le texte s'adresse directement au lecteur, et il lui parle de **son
entreprise**, dans un document dont le sujet annoncé est **une élection**. Le
lecteur est interpellé sur un terrain qui n'est pas celui de la présentation.

**9. L'affirmation la plus forte du document est aussi la seule qui ne soit
pas attribuée.** « la plus grande faille de vos systèmes et organisations:
l'humain » est posé comme un fait acquis, sans source ni nuance, dans un texte
qui prend par ailleurs soin d'attribuer le laser social à son auteur. C'est
une thèse contestée, et un auditoire de sécurité expérimenté l'a entendue
assez souvent pour la traiter comme un marqueur de niveau.

**10. La bio contient la preuve de compétence de la troisième partie, et le
texte ne fait jamais le lien.** La bio établit que l'auteur a travaillé sur
« l'interaction **laser**-molécules en champ intense et ultra-bref », sur « la
résolution de l'équation de Schrödinger dépendant du temps » et sur « les
mécanismes des dynamiques […] typiques de ce régime d'interaction ». Le titre
annonce un « **laser** social » et le résumé un mécanisme « quantum-like ». Le
mot *laser* et le formalisme quantique apparaissent des deux côtés du
document, à quatre paragraphes d'intervalle, **sans qu'une seule phrase les
rapproche**. C'est l'élément le plus favorable du dossier, et il est laissé au
lecteur à reconstituer seul.

**11. La crédibilité arrive après l'annonce, et dans la mauvaise section.** Le
résumé présente Khrennikov comme une référence extérieure — « imaginé par le
mathématicien russe Andrei Khrennikov ». La dernière puce du document, en
section entreprise, révèle que l'auteur mène de la « recherche fondamentale en
Intelligence Quantique (application des théories quantum-like de Khrennikov
[…]) ». Le lecteur apprend donc en dernière ligne que l'orateur travaille déjà
sur le formalisme qu'il annonçait comme celui d'un tiers.

**12. Deux dénominations et deux qualifications de l'entreprise.** La bio dit
« Jérémy a fondé noumanity, une compagnie qui se consacre à la recherche
DeepTech ». La section suivante dit « Groupe Innovation Numanity inc. ou, plus
simplement, **noumanity** est un Studio DeepTech ». Compagnie de recherche ou
studio, noumanity ou Groupe Innovation Numanity : le document ne tranche pas.

**13. La proportion des sections contredit l'objet du document.** Résumé
97 mots ; bio 158 ; entreprise 202. **La section entreprise fait plus du
double du résumé.** Un document dont la fonction est d'annoncer une
présentation consacre 41 % de son texte à l'entreprise et 20 % à la
présentation.

### C. Réalisabilité de ce qui est annoncé

**14. Pris comme spécification, le résumé décrit trois présentations.**
Chacune des deux premières parties est un sujet de conférence complet et
autonome : « les techniques standards de hacking social » est un exposé
d'introduction classique ; « l'ingérence étrangère et les opérations
d'influence de masse » en est un autre, avec sa propre littérature et ses
propres études de cas. La troisième exige en plus d'**enseigner un formalisme**
que le résumé lui-même ne définit pas (constat 4) avant de pouvoir l'appliquer.
À supposer un format de soirée d'une heure — hypothèse explicite, le document
ne dit rien de sa durée —, la troisième partie, seule originale, hérite du
tiers restant après deux mises en contexte.

**15. Le document ne dit pas où en est le travail.** Le résumé est
intégralement au futur : « nous aborderons », « nous soulèverons », « nous
tenterons ». Ce futur est ambigu entre le futur du déroulé — ce qui se passera
pendant l'heure — et le futur de la production — ce qui reste à faire. Un
organisateur ne peut pas savoir s'il programme un travail achevé ou un travail
en cours.

**16. Rien n'est dit du niveau requis, du format ni de la matière montrée.**
Ni prérequis, ni indication de technicité, ni mention d'une démonstration, de
chiffres, d'un modèle ou d'un code. Le lecteur ne sait pas s'il verra des
équations, des captures d'écran ou des diapositives de texte.

### D. Une vérification de fait

**17. « le mathématicien russe Andrei Khrennikov » est incomplet.**
Vérification en ligne le 2026-09-08 : Khrennikov est un mathématicien-physicien
**russo-suédois**, né en 1958 à Volgograd, professeur de mathématiques
appliquées à l'**université Linnaeus de Växjö, en Suède**, où il dirige
l'International Center for Mathematical Modeling. Constat interne qui
s'y ajoute : c'est la seule nationalité citée dans tout le document, et elle
apparaît **une phrase après** l'annonce d'un développement sur l'ingérence
étrangère, dans un texte qui ne nomme aucun État. Le rapprochement n'est
sûrement pas voulu ; il est disponible pour un lecteur pressé.

## Réponse

**Le document tient debout, mais il tient trois choses à la fois.**

*Est-il cohérent ?* Non, à deux endroits qui comptent. Le titre et le résumé
posent deux questions différentes — résister, et comment faire (constat 1) —
et l'objet attaqué change deux fois en trois phrases, de « vos systèmes » à
une élection (constats 3 et 8). Ce ne sont pas des maladresses de style :
elles empêchent le lecteur de savoir de quoi la présentation parle.

*Est-il réalisable ?* Pris comme spécification à laquelle la présentation
devra se conformer — ce que la tâche demande d'admettre — le résumé engage
deux exposés d'introduction complets avant d'arriver à la seule partie
originale, laquelle exige encore d'enseigner un formalisme que le document ne
définit pas (constats 4 et 14). C'est le constat le plus lourd de cette
analyse, parce qu'il ne se corrige pas à la rédaction : **si l'abstract fait
foi, la présentation est déjà surchargée avant d'être écrite.**

*Donne-t-il envie de venir ?* Faiblement, et par sa propre faute. L'auteur
qualifie deux de ses trois parties de standards et la troisième d'exotique
(constat 5), ne promet aucun résultat (constat 6), n'offre aucune capacité
nouvelle à un public de praticiens (constat 7), et consacre deux fois plus de
texte à son entreprise qu'à sa présentation (constat 13).

**Ce qui manque le plus n'est pourtant pas dans cette liste.** Le document
contient, à quatre paragraphes de distance, l'annonce d'un « laser social » et
la mention d'une carrière de recherche sur l'interaction laser-molécules et
l'équation de Schrödinger dépendant du temps — et il ne rapproche jamais les
deux (constat 10). C'est la seule chose dans ce texte qu'aucun autre
conférencier ne pourrait écrire. Un lecteur qui la reconstitue tient
immédiatement la réponse à « pourquoi lui » et à « pourquoi ce modèle » ; un
lecteur pressé ne la reconstitue pas. Le document révèle en dernière ligne, en
section entreprise, que l'auteur fait de la recherche sur le formalisme même
qu'il attribuait trois paragraphes plus haut à un tiers (constat 11).

En une phrase : **le texte se présente comme trois exposés de sujets connus
introduits par une thèse contestée, alors qu'il a de quoi se présenter comme
un travail que la trajectoire de son auteur rend singulier.** L'écart entre
ces deux lectures ne tient pas au contenu — il est déjà là — mais à quatre ou
cinq phrases qui ne sont pas écrites.

Cette analyse ne modifie pas le fichier et ne prescrit pas de rédaction : la
décision appartient à l'humain.

## Limites

- **Le format attendu n'est pas connu.** Ni la longueur maximale d'abstract
  admise par les organisateurs, ni la durée du créneau. Le constat 14 repose
  sur une hypothèse d'une heure, explicitement posée ; si le créneau est plus
  long, il s'affaiblit sans disparaître.
- **L'analyse ne dit rien de l'attractivité réelle.** Elle juge la cohérence
  d'un texte, pas sa capacité à remplir une salle. Il est possible que
  « comment faire pour y parvenir? » soit précisément ce qui fait venir du
  monde, et que le désordre relevé au constat 2 passe inaperçu à la lecture
  rapide qui est celle d'une annonce de meetup.
- **Elle ne dit rien de la justesse du contenu**, par construction : la
  contrainte de la tâche interdit de vérifier ce que le texte avance contre
  les travaux du dépôt. Un énoncé peut être parfaitement cohérent avec
  lui-même et faux. Le constat 9 signale une thèse contestée sans trancher, et
  le constat 17 est la seule vérification de fait menée.
- **Elle ne dit rien de ce que la présentation contient.** Sous le régime posé
  par la tâche — l'abstract fait foi — la présentation n'a pas encore
  d'existence opposable. Si le travail déjà produit diverge de l'abstract, ce
  n'est pas cette analyse qui le montrera ; c'est ANL-007, qui pose la
  question dans l'autre sens.
- **Deux constats recoupent ANL-007** (le 9 et le 17), atteints ici par un
  autre chemin. Leur convergence n'ajoute pas de preuve : c'est le même texte,
  lu deux fois.

**Relations.** Analyse le `README.md` de la racine dans sa version du
2026-09-08. Complémentaire de ANL-007, qui pose la question inverse — la
présentation comme référence, le README comme écart. Aucun autre artefact du
dépôt n'a été mobilisé, par contrainte de la tâche.
