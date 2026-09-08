---
type: fondation
id: FND-023
titre: "Approfondissement du hacking social : trois sens du terme, cadres opératoires, ancrage canadien et mesure d'effet"
version: 0.1.0
status: actif
date: 2026-09-08
---

# FND-023 - Approfondissement du hacking social : trois sens du terme, cadres opératoires, ancrage canadien et mesure d'effet

- **Objectif** : reprendre FND-012 là où elle s'est arrêtée. Cette fondation ne
  refait pas la revue du domaine ; elle traite les cinq manques que FND-012
  s'avoue à elle-même dans sa section « Limites » — l'ambiguïté du terme
  lui-même, le cadre DISARM non consulté sur source primaire, l'absence totale
  d'ancrage canadien et québécois, le cadre juridique donné de mémoire, et la
  mesure d'effet manquante. Pour qui : la rédaction du rapport et la
  présentation QuébecSec, qui ont besoin de dire *sous quel sens du mot* elles
  parlent, et de s'appuyer sur des sources canadiennes que l'auditoire
  reconnaîtra.

## Note de rigueur

**Vérifié sur source primaire le 2026-09-08.**

- Le **rapport final de la Commission sur l'ingérence étrangère** (commissaire
  Marie-Josée Hogue, 28 janvier 2025), volume 1, téléchargé depuis le site de
  la Commission et lu au texte. Les citations données plus bas sont
  **verbatim**, extraites du PDF, et non rapportées par voie de presse.
- Le communiqué d'**Élections Québec** sur les mesures issues du **projet de
  loi 98** : dates d'entrée en vigueur, seuils, sanctions.
- La **FAQ de la DISARM Foundation** : gouvernance, licence, structure
  Red/Blue, filiation AMITT, numéro d'enregistrement de l'entité.
- La notice arXiv de **« Engineered Persuasion »** (2609.04410) : auteurs,
  date, protocole, chiffres.

**Vérifié partiellement — résumé et notice, pas texte intégral.** L'article
« Five Myths About Influence Operations » (*Systems*, 2026) : l'existence, les
auteurs, la taille du corpus et le protocole statistique sont confirmés par
deux requêtes indépendantes et par la notice de la revue, mais **le texte
intégral n'a pas pu être obtenu** (MDPI et preprints.org ont retourné HTTP
403). Les verdicts mythe par mythe rapportés ici proviennent du résumé publié.
**Ils ne doivent pas être cités comme des résultats lus.**

**Vérifié, et jugé faible.** La définition grand public de « social hacking »
(encyclopédie collaborative, blogues de fournisseurs). Elle est rapportée ici
non comme autorité mais comme **objet** : c'est l'usage dominant du terme, et
c'est précisément ce qui rend le terme inutilisable tel quel.

**Non vérifié dans cette session.** Le texte intégral de *A Hacker's Mind* ;
la littérature sur le civic hacking, connue par notices et résumés ; les
recommandations 1 à 51 du rapport Hogue prises une à une ; les volumes 2 et
suivants du même rapport.

Vitesse de vieillissement : **hétérogène**, et c'est important. Le socle
conceptuel (sens du mot, Schneier, DISARM) est stable à l'échelle de
plusieurs années. L'ancrage juridique québécois est **frais de quelques
semaines et en cours d'application pour la première fois** : l'infraction de
désinformation électorale entre en vigueur en juillet 2026 et la campagne
courante est le premier scrutin général où elle s'applique. Les chiffres sur
l'IA générative vieillissent en mois.

## Cadrage

**Dans le périmètre.** Cinq questions, une par manque de FND-012 :
que veut dire « hacking social » ; comment un cadre opératoire décrit une
opération d'influence ; ce qu'une enquête publique canadienne a établi ; ce
que le droit québécois interdit depuis 2026 ; et ce que la mesure d'effet
donne aujourd'hui.

**Hors périmètre.** Tout ce que FND-012 couvre déjà et qui n'est pas
contredit ici : taxonomie de l'hameçonnage, principes de Cialdini appliqués,
histoire du domaine, susceptibilité individuelle. La sécurité opérationnelle
des campagnes. Les fondements psychologiques (FND-009 à FND-011).

**Définitions de travail.** Cette fondation **refuse** de donner une
définition unique de « hacking social » et soutient à la place qu'il y en a
trois, incommensurables, dont une seule sert le projet. C'est le résultat
principal de la section 1 et non un préalable.

## Corps

### 1. Le terme « hacking social » recouvre trois choses distinctes

C'est le manque le plus embarrassant de FND-012 : elle emploie l'expression
tout du long sans jamais dire laquelle des acceptions est retenue. Or il y en
a trois, et elles n'ont ni le même objet, ni la même échelle, ni le même
statut moral.

**1.1 Sens A — synonyme dégradé d'« ingénierie sociale ».** C'est l'usage
dominant hors littérature académique. Il désigne la manipulation psychologique
d'une personne pour obtenir un accès, une information ou une action :
prétexte, hameçonnage ciblé, jeu de rôle, talonnage, fouille de rebuts. La
seule nuance que l'usage introduit parfois est que le « social hacking »
serait la variante **numérique et médiatisée** de l'ingénierie sociale — celle
qui passe par les réseaux sociaux et le renseignement en source ouverte
plutôt que par le téléphone et le vestiaire.

*Jugement.* Ce sens est **inutilisable pour le projet**, pour deux raisons.
D'abord parce que la distinction avec l'ingénierie sociale n'est pas stable :
elle varie d'un auteur commercial à l'autre et n'est reprise par aucune
systématisation académique. Ensuite parce que son unité d'analyse est
l'individu trompé — exactement l'échelle dont ce projet démontre qu'elle
**n'est pas** la surface d'attaque pertinente.

**1.2 Sens B — hacking d'un système social, au sens de Schneier.** Un *hack*
est une activité **permise par le système** qui en **subvertit l'objectif**,
en exploitant une vulnérabilité de sa spécification. Schneier applique
délibérément la notion à l'économie, au droit fiscal, au processus législatif
et au politique : l'optimisation fiscale, l'obstruction parlementaire, le
charcutage électoral sont des hacks au même titre qu'un débordement de
tampon.

*Jugement.* **C'est le sens qui porte le projet**, et il faut le dire
explicitement dans le rapport comme dans la présentation. Il a trois
propriétés que le sens A n'a pas : son unité d'analyse est **la règle**, pas
la personne ; il rend l'attaque descriptible sans imputer de faute morale
individuelle ; et il désigne une classe de défenses — corriger la
spécification — plutôt que la seule sensibilisation. Schneier y ajoute la
notion de *cognitive hack*, l'exploitation des mécanismes attentionnels et
tribaux, qui est le pont entre le sens B et la psychologie de FND-011.

**1.3 Sens C — le hacking social constructif (« civic hacking »).** Un
courant distinct, documenté en études des sciences et techniques et en design
urbain, reprend l'éthique hacker d'origine — partage, ouverture, amélioration
du monde — pour désigner l'intervention citoyenne outillée sur les
institutions : hackathons civiques, ouverture de données, prototypage de
politiques publiques. La littérature le décrit comme une **réponse d'urgence
à une crise institutionnelle**, mobilisée dans des contextes de défiance
envers les institutions représentatives, et souligne qu'à la différence des
autres cultures hacker, il assume une **appartenance** et une identité
communautaire.

*Jugement.* Ce sens n'est pas décoratif pour ce projet, pour une raison
précise : **le sens B et le sens C décrivent le même geste et se distinguent
uniquement par l'intention**. Étudier la spécification d'un processus
électoral pour montrer où elle cède est du sens C ; l'étudier pour exploiter
la cession est du sens B. Rien dans le mécanisme ne les sépare. C'est la
formulation la plus honnête de la position dans laquelle ce travail se place,
et elle mérite d'être tenue devant l'auditoire plutôt qu'esquivée.

**1.4 Conséquence pour le projet.** Le titre de la présentation parle
d'attaquer une démocratie. Sous le sens A, cette formule promet un manuel et
la présentation décevra — c'est tant mieux. Sous le sens B, elle annonce une
recherche de faille de spécification, ce qu'elle est. Sous le sens C, elle
annonce une contribution défensive, ce qu'elle revendique. **Poser les trois
sens en ouverture désamorce la lecture la plus dommageable** et coûte une
diapositive.

### 2. DISARM : ce qu'un cadre opératoire apporte, et ce qu'il ne dit pas

FND-012 identifiait DISARM comme « le pont conceptuel dont un public de
cybersécurité a besoin », sans l'avoir consulté. Consultation faite.

**2.1 Gouvernance et statut.** DISARM est maintenu par la **DISARM
Foundation**, organisation à but non lucratif non partisane, constituée aux
États-Unis et enregistrée comme *Community Interest Company* au Royaume-Uni
(n° 15833044). Le cadre est publié sous **licence Creative Commons** et
librement réutilisable. Le financement initial (2022) provient de la Alfred
Landecker Foundation, et la fondation déclare **ne recevoir aucun financement
gouvernemental** — point non trivial pour un cadre destiné à qualifier des
opérations attribuées à des États. Le développement repose largement sur des
contributions bénévoles.

**2.2 Filiation.** Le cadre naît en 2019 sous le nom **AMITT** (*Adversarial
Misinformation and Influence Tactics and Techniques*), transposition
explicite de la logique MITRE ATT&CK au domaine informationnel. La fusion
d'AMITT dans DISARM date de 2022.

**2.3 Structure.** Deux cadres jumeaux. Le **Red Framework** codifie les
tactiques et techniques de l'attaquant ; il est le plus mature et il est
utilisé pour **étiqueter** des rapports d'analyse — la Commission européenne
et la France figurent parmi les utilisateurs déclarés. Le **Blue Framework**
codifie les contre-mesures du défenseur et la fondation le reconnaît
elle-même comme **moins mature**. Chaque tactique et chaque technique porte
un code alphanumérique unique, que la fondation s'engage à ne pas modifier
lors des réorganisations, afin que les rapports déjà étiquetés restent
comparables.

**2.4 Ce que cela apporte au projet.** Une opération d'influence devient
descriptible dans le même vocabulaire qu'une intrusion : tactique (le but
opérationnel), technique (le moyen), procédure (la combinaison observée, qui
signe l'intention). C'est exactement le geste que la présentation demande à
son auditoire — analyser un processus démocratique avec les outils qu'il
utilise déjà.

**2.5 Ce que cela ne dit pas, et c'est le point important.** L'asymétrie de
maturité entre Red et Blue n'est pas un accident de calendrier : elle
reproduit au niveau du cadre le constat que FND-012 tirait de la littérature
— **le domaine sait décrire l'attaque bien mieux qu'il ne sait décrire ou
évaluer la défense**. Un cadre qui étiquette des comportements ne mesure
aucun effet ; il permet de dire qu'une campagne a eu lieu, jamais qu'elle a
produit quelque chose. La section 5 revient là-dessus.

### 3. L'ancrage canadien : ce que la Commission Hogue a établi

FND-012 signalait comme manque « une recherche sur les incidents d'influence
documentés au Canada ». Le document de référence existe, il est public, il est
récent, et il est bien plus utile au projet que la littérature américaine
généralement citée.

**3.1 Le document.** *Enquête publique sur l'ingérence étrangère dans les
processus électoraux et les institutions démocratiques fédéraux*, rapport
final de la commissaire **Marie-Josée Hogue**, déposé le **28 janvier 2025**,
volume 1 (synthèse), **51 recommandations**.

**3.2 Le constat d'effet — verbatim.** Sur les élections générales de 2019 et
2021 :

> « Je n'ai trouvé aucune preuve que le résultat global d'une élection ait été
> influencé par un acteur étranger et je n'ai identifié qu'un petit nombre de
> circonscriptions individuelles où l'ingérence étrangère a pu avoir un certain
> effet. Je n'ai trouvé aucune preuve que la législation, la réglementation ou
> une politique fédérale ait été adoptée ou abandonnée en raison de
> l'ingérence d'un État étranger. »

Et plus loin, sur la portée de l'ingérence avérée :

> « [C]ette ingérence n'a pas porté atteinte à l'intégrité du système électoral
> lui-même et n'a pas eu d'incidence sur l'identité du parti qui a pris le
> pouvoir. »

**3.3 Le constat de dommage — verbatim.** Le même rapport conclut néanmoins :

> « [L]'ingérence étrangère ait eu une incidence sur l'écosystème électoral
> dans son ensemble et ait ébranlé la confiance du public envers la démocratie
> canadienne. Au contraire, mes travaux depuis le dépôt du rapport initial
> n'ont fait que renforcer cette conclusion. »

**3.4 La qualification de la désinformation — verbatim.** Dans son mot
d'ouverture, la commissaire écrit :

> « À mon avis, il n'est pas exagéré de dire qu'à l'heure actuelle, la
> manipulation de l'information (qu'elle soit d'origine étrangère ou non)
> représente le plus grand risque pour notre démocratie. Il s'agit d'une menace
> existentielle. »

**3.5 Pourquoi ces trois citations comptent, ensemble.** Prises séparément
elles se contredisent en apparence ; prises ensemble elles énoncent
exactement la thèse du projet, et par une autorité canadienne indépendante
plutôt que par nous. Le rapport dit : *l'attaque n'a pas déplacé de vote, et
elle a quand même fait des dégâts mesurables — sur la couche de confiance*.
C'est la distinction entre déplacer un état et dégrader l'appareil de mesure.

La parenthèse de la troisième citation — **« qu'elle soit d'origine étrangère
ou non »** — est le point le plus fort disponible pour la diapositive sur
l'attribution. Une commissaire d'enquête mandatée sur l'**ingérence étrangère**
conclut que l'origine étrangère n'est pas ce qui fait le risque. C'est
l'énoncé institutionnel du constat de la présentation : rien, dans le
mécanisme, ne distingue une attaque d'une stratégie de campagne domestique.

**3.6 Ce que le rapport dit de la Russie**, contre l'intuition courante : la
Russie a la **capacité** d'une ingérence importante contre le Canada mais ne
semble pas en avoir l'**intention**, le Canada n'étant pas perçu comme une
menace existentielle pour elle ; aucune ingérence russe propre aux processus
démocratiques n'a été observée. Utile pour couper court à la lecture
géopolitique réflexe pendant la période de questions.

**3.7 Réserve.** La Commission avait pour mandat l'ingérence **étrangère**
dans les processus **fédéraux**. Elle ne dit rien du provincial ni du
municipal, et rien des opérations domestiques. L'absence de preuve d'effet
qu'elle rapporte est aussi, en partie, une **limite de son mandat et de ses
moyens de mesure** — elle-même reproche au SCRS un partage d'information
« parfois problématique ». Ne pas la citer comme si elle avait mesuré ce que
personne ne sait mesurer (section 5).

### 4. Le cadre juridique québécois a changé, et il change pendant la campagne

FND-012 donnait ses mentions juridiques de mémoire et demandait leur
vérification. Voici l'état vérifié, et il est plus contraignant que prévu.

**4.1 La loi.** **Projet de loi 98**, *Loi modifiant la Loi électorale
principalement afin de préserver l'intégrité du processus électoral*,
**sanctionnée le 30 mai 2025**. Ses dispositions entrent en vigueur par
étapes en **janvier et juillet 2026**.

**4.2 Une infraction de désinformation électorale.** Depuis **juillet 2026**,
le directeur général des élections peut intenter une poursuite pénale contre
quiconque propage **une information fausse en sachant qu'elle l'est**, ou
**usurpe l'identité** d'une personne élue ou d'un membre du personnel
électoral, lorsque cela vise le processus électoral, une candidature ou la
confiance du public. Sanctions : amende de **1 000 $ à 10 000 $** pour une
personne physique, **5 000 $ à 30 000 $** pour un organisme ou une entreprise,
majorées en cas de récidive dans les dix ans, assorties de la **perte des
droits électoraux — voter et se porter candidat — pendant cinq ans**.

**4.3 Transparence de la publicité préélectorale.** Depuis le **1er janvier
2026**, tout **tiers** — entreprise, organisation — dont la publicité
partisane dépasse **1 000 $** doit s'enregistrer auprès du DGEQ par un avis
d'intention, puis déclarer ses dépenses après le scrutin. Depuis le **1er
juillet 2026** et jusqu'au début de la période électorale, les partis doivent
déclarer leurs coûts de **publicité partisane, de sondages et de ciblage
électoral**, publiés sur le site d'Élections Québec.

**4.4 Ce que cela change pour le projet.** Trois choses.

*Premièrement, le calendrier.* L'élection du 5 octobre 2026 est **le premier
scrutin général québécois** où ces dispositions s'appliquent. Le projet ne
décrit pas un système hypothétique : il décrit un système dont la
spécification vient d'être amendée précisément sur le point qui nous
intéresse.

*Deuxièmement, une borne de faisabilité supplémentaire, et elle est nette.*
L'infraction vise l'**information fausse sciemment propagée**. Le mécanisme
étudié ici — déplacer la base de mesure, la question de l'urne — ne repose
sur **aucun énoncé faux**. Une proposition faîtière ambiguë et non
falsifiable n'est pas une information fausse. **Le mécanisme le plus
plausible du modèle est donc aussi celui que la nouvelle infraction
n'atteint pas.** C'est un résultat, et il devrait figurer dans les
considérations de sécurité de la présentation : le législateur québécois
vient de corriger la spécification contre la fausseté, pas contre le
cadrage.

*Troisièmement, une exigence de visibilité nouvelle.* L'obligation faite aux
partis de déclarer leur **ciblage électoral** est la première exigence
québécoise de transparence sur la couche par laquelle un pompage différencié
par champ passerait.

*Réserve.* Ce sont des mesures de transparence et une infraction pénale
décrites d'après le communiqué de l'autorité électorale, non d'après le texte
de loi ni d'après une analyse juridique. **Aucune affirmation sur la portée
exacte de l'infraction ne doit être faite dans un livrable sans lecture du
texte adopté.**

### 5. La mesure d'effet : ce qui a bougé depuis FND-012

FND-012 concluait que « le domaine ne sait pas mesurer un déplacement
d'opinion attribuable » et en faisait sa limite la plus lourde. Le constat
tient, mais il faut le préciser : il y a maintenant une littérature qui
mesure **rigoureusement l'absence d'effet**, ce qui n'est pas la même chose
qu'une littérature qui ne mesure rien.

**5.1 Le socle.** Le programme de Princeton (*Empirical Studies of Conflict*)
et la synthèse Carnegie de 2021 posent l'état du champ : des opérations
étudiées ont produit des déplacements de croyances et de comportements
— sentiments discriminatoires, scepticisme vaccinal — mais l'influence
documentée est **persuasive et de courte durée**, et la recherche empirique
« ne répond pas encore adéquatement aux questions les plus pressantes ». Du
côté électoral, la méta-analyse d'essais de terrain sur le contact de
campagne en élection générale estime l'effet moyen à **zéro**.

**5.2 L'apport de 2026 : cinq croyances mises à l'épreuve.** L'article « Five
Myths About Influence Operations: What 25 Million Tweets Across Seven State
Campaigns Reveal » (*Systems*, vol. 14, art. 970, 10 août 2026) rassemble les
**archives complètes attribuées par des gouvernements de sept campagnes
étatiques — 25 076 853 messages, 9 071 comptes** — avec une **base de
comparaison d'utilisateurs organiques appariés** pour cinq d'entre elles, et
reteste cinq affirmations sous un protocole unique : préenregistrement,
contrôle du taux de fausses découvertes (Benjamini-Hochberg), nuls par
permutation, placebo de réception future, décomposition par instantané de
retrait.

Les cinq croyances testées : que l'opération est une **armée de trolls
monolithique** agissant de concert ; qu'elle **gagne par l'émotion**, le
langage moral-émotionnel et l'indignation ; qu'elle **fabrique sa propre
viralité** par auto-amplification de faux comptes ; qu'elle est un
**adversaire sophistiqué et optimisateur** qui apprend de la réception et
s'adapte ; et qu'elle est devenue **indiscernable** des utilisateurs réels.
Selon le résumé publié, **chacune s'affaiblit ou s'inverse** une fois
confrontée aux données de campagne réelles.

Les auteurs adressent au champ un reproche méthodologique explicite : les
affirmations antérieures reposent sur des **études à campagne unique, des
comparaisons non contrôlées, et de la significativité en grand échantillon
rapportée sans base de référence ni contrôle des comparaisons multiples**, et
elles sont **rarement rejouées**.

*Statut de cette source.* Résumé et notice vérifiés ; **texte intégral non
obtenu**. À traiter comme une indication forte et une piste de lecture, pas
comme un résultat lu. Si un seul texte devait être lu avant la présentation,
c'est celui-là.

**5.3 Pourquoi cela sert le projet plutôt que de le fragiliser.** Les cinq
croyances démenties sont toutes des variantes d'un même modèle implicite :
l'attaquant **produit un contenu persuasif** et le pousse jusqu'à ce que
l'opinion cède. C'est le modèle que la présentation rejette. Un champ qui
découvre que ses opérations ne sont ni coordonnées, ni émotionnellement
optimisées, ni auto-amplifiées, ni adaptatives, ni indiscernables **cherche
peut-être le mauvais objet**. La thèse du projet — l'attaque efficace n'est
pas persuasive, elle est métrologique — prédit exactement ce résultat.

*Réserve intellectuelle, à tenir.* Cette convergence est **compatible** avec
la thèse ; elle ne la démontre pas. Un mécanisme non observé parce qu'on
regarde ailleurs, et un mécanisme inexistant, produisent la même absence de
preuve. Ce qui distingue les deux est la signature de détection proposée par
le projet, et elle n'a pas été mesurée.

**5.4 L'IA générative, avec enfin un chiffre académique.** FND-012 devait s'en
remettre à des rapports de fournisseurs. Une source contrôlée existe :
*Engineered Persuasion: Evaluating Personalized Pretexts in LLM-Generated
Spear Phishing* (Francia, Hansen, Schooley et Murray, arXiv:2609.04410, 3
septembre 2026). Protocole : **180 adultes en emploi aux États-Unis, 1 436
évaluations valides**, messages construits par quatre niveaux cumulatifs de
personnalisation — employeur ; nom et titre du destinataire ; responsabilités ;
contexte de collègues et de projets partagés. Résultats : la **conviction
augmente de 2,40 points par niveau** de personnalisation et la **cote
d'intention de clic augmente de 28 % par niveau**. Un émetteur nommé
renvoyant à un collègue réel obtient de meilleurs résultats qu'une source
départementale ou institutionnelle. Point de nuance essentiel : l'efficacité
dépend de **l'ajustement contextuel** — un détail inexact ou inadapté au canal
**augmente la suspicion**.

*Ce que cela établit, et ce que cela n'établit pas.* Cela établit que le
rendement de la personnalisation est réel, gradué et mesurable à l'échelle
d'un message adressé à une personne. **Cela n'établit rien sur l'opinion
politique d'une population** : c'est une mesure d'intention déclarée, en
enquête, sur une tâche de sécurité. La contrainte de FND-011 tient
intégralement — produire du volume personnalisé n'est pas produire de la
persuasion collective.

## Synthèse

1. **Le mot recouvre trois choses.** Sens A, la manipulation d'une personne :
   inutilisable ici, mauvaise échelle. Sens B, le hack d'un système au sens de
   Schneier : c'est celui du projet, l'unité d'analyse est la règle. Sens C, le
   hacking civique constructif. **B et C sont le même geste et ne se
   distinguent que par l'intention** — le dire est plus honnête que le
   dissimuler.
2. **DISARM donne le vocabulaire, pas la mesure.** Cadre libre, gouvernance
   non gouvernementale, codes stables, transposition d'ATT&CK au domaine
   informationnel. Son Blue Framework est reconnu moins mature que son Red :
   l'asymétrie attaque/défense du domaine est inscrite jusque dans ses outils.
3. **Le Canada a un document de référence, et il énonce la thèse du projet.**
   Rapport Hogue, 28 janvier 2025 : aucune preuve d'effet sur le résultat
   global d'une élection, et pourtant une incidence sur l'écosystème électoral
   et sur la confiance du public. Attaque non persuasive, dommage
   métrologique.
4. **La citation la plus utile est une parenthèse.** « [L]a manipulation de
   l'information (**qu'elle soit d'origine étrangère ou non**) représente le
   plus grand risque pour notre démocratie. Il s'agit d'une menace
   existentielle. » Une commissaire mandatée sur l'ingérence étrangère conclut
   que l'origine étrangère n'est pas ce qui fait le risque.
5. **Le droit québécois vient de changer, et il rate le mécanisme étudié.**
   Loi 98, sanctionnée le 30 mai 2025 : infraction de désinformation
   électorale en vigueur depuis juillet 2026, jusqu'à 10 000 $ et cinq ans de
   privation des droits électoraux. Elle vise l'**information fausse
   sciemment propagée**. Un déplacement de la question de l'urne ne repose sur
   aucun énoncé faux : **la correction apportée à la spécification ne couvre
   pas le mécanisme.**
6. **La mesure d'effet a progressé — dans le sens du démenti.** Sur
   25 millions de messages et sept campagnes étatiques, les cinq croyances
   dominantes sur les opérations d'influence s'affaiblissent ou s'inversent.
   Toutes présupposent un attaquant persuasif. C'est compatible avec la thèse
   du projet ; ce n'en est pas la preuve.
7. **Un chiffre académique remplace enfin les chiffres de fournisseurs sur
   l'IA.** +28 % de cote d'intention de clic par niveau de personnalisation,
   sur 1 436 évaluations — mais à l'échelle du message individuel, et en
   intention déclarée.

## Limites

- **Le texte intégral de la source la plus importante n'a pas été lu.**
  L'article *Systems* 2026 est connu par son résumé. Les verdicts mythe par
  mythe sont rapportés, non vérifiés. C'est la première lecture à faire.
- **Le rapport Hogue n'a été lu qu'en volume 1.** Les 51 recommandations n'ont
  pas été dépouillées ; certaines portent probablement sur la régulation des
  partis et la lutte à la désinformation, ce qui intéresserait directement la
  section « défense » de la présentation.
- **La loi 98 n'a pas été lue.** Seul le communiqué de l'autorité électorale
  l'a été. L'affirmation de la section 4.4 selon laquelle le mécanisme échappe
  à l'infraction est une **inférence à partir d'un résumé administratif**, pas
  une analyse juridique. Elle est plausible et elle est importante : elle doit
  être validée sur le texte, et idéalement par une personne compétente en
  droit électoral, avant d'être énoncée devant un auditoire.
- **Le sens C est le moins solidement établi** des trois : notices et résumés,
  pas de lecture de fond. L'argument « B et C ne se distinguent que par
  l'intention » est une position défendue ici, pas un résultat rapporté.
- **Rien sur le municipal ni sur le provincial en matière d'incidents.** La
  Commission Hogue ne couvre que le fédéral. Aucun incident documenté
  d'opération d'influence visant une élection québécoise n'a été trouvé dans
  cette session, et **cette absence n'a pas été cherchée systématiquement** :
  ne pas la présenter comme un constat.
- **Aucune vérification du cadre éthique de la recherche** (Énoncé de
  politique des trois Conseils, lois sur la protection des renseignements
  personnels), signalé comme manquant par FND-012 et toujours manquant. Non
  bloquant ici, puisque le travail ne collecte aucune donnée.

## Sources

**Primaires, vérifiées le 2026-09-08.**

- Commission sur l'ingérence étrangère dans les processus électoraux et les
  institutions démocratiques fédéraux, *Rapport final*, volume 1 (synthèse),
  commissaire Marie-Josée Hogue, 28 janvier 2025, 51 recommandations. PDF lu
  au texte ; toutes les citations de la section 3 en sont extraites verbatim.
  https://commissioningerenceetrangere.ca/fileadmin/rapport_volume_1.pdf
- Élections Québec, « Loi électorale : de nouvelles mesures de transparence et
  d'intégrité dès 2026 » — projet de loi 98 sanctionné le 30 mai 2025, seuils,
  sanctions, dates d'entrée en vigueur.
  https://www.electionsquebec.qc.ca/communiques/loi-electorale-de-nouvelles-mesures-de-transparence-et-dintegrite-des-2026/
- DISARM Foundation, FAQ — gouvernance, licence Creative Commons, CIC
  britannique n° 15833044, filiation AMITT 2019, cadres Red et Blue, stabilité
  des codes. https://www.disarm.foundation/faqs
- Jerson Francia, Derek Hansen, Benjamin Schooley, Shydra Valynn Murray,
  « Engineered Persuasion: Evaluating Personalized Pretexts in LLM-Generated
  Spear Phishing », arXiv:2609.04410, 3 septembre 2026. 180 participants,
  1 436 évaluations. https://arxiv.org/abs/2609.04410

**Vérifiée partiellement — résumé et notice seulement, texte intégral
inaccessible (HTTP 403).**

- « Five Myths About Influence Operations: What 25 Million Tweets Across Seven
  State Campaigns Reveal », *Systems*, vol. 14, art. 970, 10 août 2026.
  25 076 853 messages, 9 071 comptes, sept campagnes étatiques attribuées.
  https://doi.org/10.3390/systems14080970 — **à lire avant la présentation.**

**Secondaires, notices et résumés consultés.**

- Carnegie Endowment for International Peace / Princeton ESOC, « Measuring the
  Effects of Influence Operations: Key Findings and Gaps From Empirical
  Research », 2021.
  https://carnegieendowment.org/research/2021/06/measuring-the-effects-of-influence-operations-key-findings-and-gaps-from-empirical-research
- Méta-analyse du contact de campagne en élection générale (49 essais de
  terrain), effet moyen estimé à zéro — via MediaWell/SSRC.
- Bruce Schneier, *A Hacker's Mind*, Norton, 2023 — page de l'auteur et
  recensions. Le *hack* comme activité permise par le système qui en subvertit
  l'objectif ; les *cognitive hacks*. https://www.schneier.com/books/a-hackers-mind/
- Littérature sur le civic hacking : « Hacking, Making, and Prototyping for
  Social Change » (Springer) ; « Civic Hacking: Redefining Hackers and Civic
  Participation » ; travaux du MIT sur le civic hacking et le droit de savoir.
  Notices et résumés seulement.
- EclecticIQ, Debunk.org, DISARM Framework Explorer — usages documentés du
  cadre. https://www.debunk.org/disarm-framework

**Rapportée comme objet, non comme autorité.**

- Article « Social hacking » d'une encyclopédie collaborative et corpus de
  blogues de fournisseurs de sécurité : source du sens A tel qu'il circule.
  Cité en section 1.1 pour établir l'usage dominant, jamais comme définition
  de référence. https://en.wikipedia.org/wiki/Social_hacking

**Relations.** Dérive de FND-012 (qu'elle prolonge sans la remplacer :
FND-012 reste le point fixe du 2026-08-27). Référence FND-011 (contrainte de
persuasion), FND-020 et FND-022 (conjoncture et offre 2026), FND-021
(mécanisme du laser social). Alimente le rapport préliminaire — sections
sécurité, faisabilité et attribution — et les diapositives 3, 35, 39 et 40 de
la présentation QuébecSec.
