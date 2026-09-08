---
type: analyse
id: ANL-009
titre: "Réévaluation du README après la révision du 8 septembre 2026"
version: 0.1.0
status: actif
date: 2026-09-08
---

# ANL-009 - Réévaluation du README après la révision du 8 septembre 2026

> La révision a réparé l'architecture du résumé : le fil qui manquait entre
> les trois parties existe désormais, et il est bon. Elle a corrigé les
> qualifications fautives. Elle n'a touché à aucun des constats qui portent sur
> ce que le lecteur repart avec — pas de résultat annoncé, pas de capacité
> offerte, pas de mention du statut du travail — et elle a alourdi le
> troisième paragraphe de 32 à 86 mots. Le texte est meilleur ; ce qu'il
> engage l'est moins.

## Question posée

Le `README.md` a été révisé après ANL-007 et ANL-008, le 2026-09-08 à 04:14.
Trois questions : **quels constats la révision a-t-elle levés**, **lesquels
restent ouverts**, et **la révision en a-t-elle introduit de nouveaux** ?

Sous-question qui commande la suite : le fichier est-il maintenant envoyable ?

## Méthode

**Artefact analysé** : `README.md` à la racine, version du 2026-09-08 04:14,
4 297 octets, 547 mots, quatre sections.

**Référence de comparaison** : la version analysée par ANL-007 et ANL-008
(495 mots), telle que ces deux analyses la citent. La version antérieure n'est
pas sous git (`?? README.md`) ; **la comparaison repose donc sur les citations
littérales faites dans ANL-007 et ANL-008, non sur un diff**. Les constats de
la section A sont fondés sur des passages que ces analyses citaient
textuellement ; ceux dont la formulation antérieure n'était pas citée ne sont
pas déclarés levés.

**Ce qui a été fait** :

- reprise des 18 constats de ANL-007 et des 17 constats de ANL-008, un par un,
  contre le texte courant ;
- recomptage par section : titre et chapeau 35 mots (6,4 %), Résumé 150
  (27,4 %), Auteur 158 (28,9 %), noumanity 204 (37,3 %) ; résumé en trois
  paragraphes de 28, 35 et 86 mots ;
- relecture orthographique ciblée sur les lignes signalées par ANL-007 ;
- décodage du jeton d'expiration de la nouvelle URL de photo.

**Non fait** : aucune modification du fichier ; aucune confrontation nouvelle
au matériel du dépôt au-delà de ce que ANL-007 avait déjà établi.

## Constats

### A. Constats levés par la révision

**1. Le fil manquant entre les trois parties existe désormais** (levée de
ANL-008 §2, et pour partie de son §3). La phrase d'ouverture du troisième
paragraphe — « un scénario d'attaque qui combine simultanément les 2 niveaux
d'analyse: la composante individuelle et les dynamiques de groupe » — donne
rétroactivement leur fonction aux deux premières parties : la première
installe le niveau individuel, la seconde le niveau collectif, la troisième
les compose. **C'est la correction la plus importante de la révision**, et elle
répond au reproche central de ANL-008 : la succession est devenue une
progression.

**2. Le titre et le résumé posent maintenant la même question** (levée de
ANL-008 §1). Le premier paragraphe ajoute « Est-ce que le système électoral
québécois est sensible à une attaque de ce type? », qui est la question de
robustesse du titre. Le titre a par ailleurs perdu le préfixe événementiel
« QuébecSec Spécial Élection: ».

**3. « multi-couleur » est défini** (levée partielle de ANL-008 §4) : « en
sélectionnant une question de l'urne assez vague pour entrer en résonnance
avec l'énergie de pompage de plusieurs groupes identitaires ». Le
qualificatif du titre cesse d'être opaque. Voir toutefois le constat 12.

**4. « exotique » a disparu** (levée de ANL-007 §8 et, pour moitié, de
ANL-008 §5). Il est remplacé par « Le coeur de la présentation », qui promeut
la troisième partie au lieu de l'excuser. « techniques standards » subsiste
au deuxième paragraphe, mais le contraste joue maintenant en faveur de la
troisième partie.

**5. La qualification de Khrennikov est corrigée** (levée de ANL-007 §7 et
ANL-008 §17) : « mathématicien russo-suédois ». L'adjacence avec le
paragraphe sur l'ingérence étrangère subsiste, mais la mention n'est plus
inexacte.

**6. Une contribution est annoncée** : « Nous **adapterons** le modèle […] afin
de prendre en compte un découpage sociologique du Québec et les principaux
partis politiques provinciaux ». Le texte cesse de se présenter comme une
revue de travaux tiers. Ce point n'était formulé dans aucune des deux analyses
antérieures ; il est relevé ici parce qu'il change le statut du document.

**7. Cinq coquilles sur huit sont corrigées** (levée partielle de ANL-007
§16) : « système électoral », « décentralisées », « Université de Montréal »,
« recherche appliquée », « datacenters décentralisés ».

**8. La proportion s'est rééquilibrée** (levée partielle de ANL-008 §13) : le
résumé passe de 20 % à 27,4 % du texte, la section entreprise de 41 % à
37,3 %. L'entreprise reste néanmoins plus longue que le résumé — 204 mots
contre 150.

### B. Constats restés ouverts

**9. La promesse du mode d'emploi est intacte** (ANL-007 §1). « Et, si oui,
comment faire pour y parvenir? » figure toujours en ouverture. C'est le
constat que ANL-007 classait premier par gravité, et le seul de sa liste qui
engageait autre chose que l'efficacité rhétorique.

**10. Aucune mention du statut du travail** (ANL-007 §9). Le document ne dit
nulle part où en est le travail, ni ce qui a été calculé. Le futur du résumé
reste ambigu entre le futur du déroulé et le futur de la production (ANL-008
§15) — et la révision l'a rendu plus ambigu encore, puisque « Nous adapterons
le modèle » peut se lire comme « nous l'adapterons devant vous » ou « il reste
à l'adapter ».

**11. Aucun contexte temporel, aucun pointeur, aucun programme de recherche**
(ANL-007 §10, §11, §12). La date du 24 septembre n'est pas située dans la
campagne. Le dépôt n'est pas navigable depuis sa page d'accueil. La bio ne
rattache toujours la présentation à aucun programme.

**12. Le paragraphe qui définit un terme en introduit trois** (ANL-008 §4,
résiduel). « laser social », « question de l'urne » et « énergie de pompage »
apparaissent tous trois sans définition dans la même phrase que la définition
de « multi-couleur ». Le lecteur non spécialiste sort du paragraphe avec plus
de termes inconnus qu'il n'y est entré.

**13. « la plus grande faille de vos systèmes et organisations: l'humain » est
inchangé** (ANL-007 §6, ANL-008 §8 et §9). Thèse contestée, posée sans
attribution, et seul moment où le texte s'adresse au lecteur — pour lui parler
de son entreprise dans un document consacré à une élection. Le constat est
partiellement atténué par le constat 1 : le niveau individuel est désormais
présenté comme **une** des deux composantes et non comme la surface d'attaque.
La phrase, elle, dit toujours le contraire.

**14. L'ingérence étrangère reste annoncée comme un axe** (ANL-007 §3).

**15. Aucun résultat, aucune capacité** (ANL-007 §4 et §5, ANL-008 §6 et §7).
« Nous évaluerons la faisabilité » : le titre pose une question fermée, le
résumé ne dit toujours pas de quel côté penche la réponse. Rien n'est offert
au praticien — rien à détecter, rien à mesurer, rien à corriger.

**16. Le lien entre la bio et le sujet n'est toujours pas fait** (ANL-008
§10). La bio dit « interaction **laser**-molécules en champ intense » et
« équation de Schrödinger dépendant du temps » ; le résumé dit « modèle
**quantum-like** de **laser** social ». Les deux formulations sont maintenant
plus proches qu'avant — la révision a enrichi le vocabulaire physique du
résumé — et **aucune phrase ne les rapproche**. Le constat n'est pas
seulement toujours vrai : son coût a augmenté.

**17. La crédibilité arrive toujours en dernière ligne** (ANL-008 §11). Le
dernier point de la section entreprise révèle que l'auteur mène de la
recherche sur les théories quantum-like de Khrennikov, quatre paragraphes
après les avoir attribuées à leur auteur comme à un tiers.

**18. Deux dénominations de l'entreprise** (ANL-008 §12). La bio dit « une
compagnie qui se consacre à la recherche DeepTech » ; le titre de section dit
maintenant « Studio DeepTech noumanity » et le corps « Groupe Innovation
Numanity inc. ». La révision a ajouté une troisième formulation au lieu d'en
retirer une.

**19. Deux titres coexistent dans le dépôt** (ANL-007 §13). Le titre du README
a changé, celui de la diapositive 1 non. L'écart demeure.

**20. Typographie et lien d'événement** (ANL-007 §17, §18). Guillemets ASCII
maintenus dans le titre et au troisième paragraphe. « Deeptech » en ligne 38
contre « DeepTech » ailleurs. Le lien vers la page de l'événement est toujours
un commentaire `<!-- À COMPLÉTER -->`.

### C. Constats nouveaux ou aggravés

**21. Le titre et le corps ne s'accordent plus sur le nom du mécanisme.** Le
titre écrit « laser social multi-**couleurs** » (l. 1), le troisième
paragraphe écrit « laser social "multi-**couleur**" » (l. 12). ANL-007 §14
signalait un désaccord entre le README et le reste du dépôt ; il est
maintenant **interne au README**, à onze lignes d'écart, sur le concept qui
donne son titre à la présentation.

**22. La charge annoncée a augmenté.** Le troisième paragraphe passe de 32 à
86 mots et engage désormais, en plus de ce qu'il engageait : adapter un
modèle, construire un découpage sociologique du Québec, couvrir les principaux
partis provinciaux, et expliquer résonance et pompage. ANL-008 §14 constatait
que l'abstract, pris comme spécification, décrivait trois présentations ; la
révision a amélioré l'articulation entre elles **et alourdi la troisième**.
Les deux mouvements sont indépendants et le second n'annule pas le premier.

**23. La nouvelle URL de photo expire le jour de la présentation.**
L'ancienne portait le jeton `e=1784930400`, soit le 24 juillet 2026 — déjà
échue. La nouvelle porte `e=1790208000`, soit le **24 septembre 2026**, date
de la présentation. L'image cessera de s'afficher au plus tard ce jour-là.

**24. Une coquille corrigée l'a été à moitié, et une nouvelle est apparue.**
Ligne 41 : « recyclage d'énergie **résiduelles** » — le mot était au masculin
singulier fautif, il est maintenant au féminin pluriel fautif ; « énergie »
appelle *résiduelle*. Ligne 12 : « entrer en **résonnance** » — deux *n*, la
graphie correcte est *résonance*. Restent de la liste antérieure :
« résitientes » (l. 40, pour *résilientes*) et « bio-masse » (l. 41, pour
*biomasse*). Ligne 12 également : « les **2** niveaux d'analyse », chiffre en
toutes lettres attendu dans un texte suivi.

## Réponse

**Ce que la révision a levé, elle l'a bien levé.** Les huit constats de la
section A ne sont pas des retouches : le premier d'entre eux répare le défaut
que ANL-008 tenait pour le plus structurant. Un lecteur comprend maintenant
pourquoi la présentation traverse trois sujets, et la troisième partie a cessé
d'être présentée par son auteur comme une curiosité. Le document est
sensiblement meilleur qu'il y a quelques heures.

**Ce qu'elle n'a pas touché forme un ensemble, et c'est ce qui frappe.** Les
douze constats restés ouverts ne sont pas un reliquat dispersé : ils portent
tous, sans exception, sur **ce que le lecteur repart avec**. Pas de résultat
annoncé (15). Pas de capacité offerte (15). Pas de mention de l'état du
travail (10). Pas de chemin vers le travail (11). Pas de raison de croire
l'orateur compétent sur ce sujet précis, alors que la preuve est dans le
document (16, 17). La révision a travaillé la **structure de l'exposé** et
laissé intacte la **proposition de valeur**.

Deux lectures sont possibles, et l'analyse ne peut pas trancher entre elles.
Soit ces éléments sont volontairement réservés à la soirée, auquel cas le
choix est assumé et il n'y a rien à corriger. Soit ils ont été omis, auquel
cas le document sous-vend un travail qui, à en juger par le seul troisième
paragraphe, est plus avancé que ce qu'il en dit.

**Trois points appellent une décision avant envoi, par ordre décroissant.**

1. **La contradiction du constat 21** — « multi-couleurs » au titre,
   « multi-couleur » au corps, sur le concept-titre. C'est le seul défaut du
   document qu'un lecteur attentif peut relever contre l'auteur sans quitter
   la page, et il porte sur le mot que la présentation doit rendre mémorable.
2. **La promesse du constat 9** — « comment faire pour y parvenir? » — reste
   le point que ANL-007 classait premier par gravité, pour une présentation
   donnée pendant une campagne électorale. Rien dans la révision n'y touche.
3. **La photo du constat 23** expire le jour même. Correction mécanique.

**Le fichier est-il envoyable ?** Oui, et davantage qu'avant : il est
maintenant cohérent avec lui-même sur son architecture, exact sur ses
qualifications, et il annonce une contribution. Il reste un document qui
décrit un parcours sans dire où il mène et qui laisse dormir, à quatre
paragraphes d'intervalle, le seul argument que personne d'autre ne pourrait
avancer. La décision appartient à l'humain ; l'analyse ne modifie pas le
fichier.

## Limites

- **La comparaison ne repose pas sur un diff.** La version antérieure n'est
  pas sous git. Les levées de la section A sont établies à partir des passages
  cités littéralement par ANL-007 et ANL-008 ; une modification portant sur un
  passage qu'aucune des deux ne citait ne peut pas être détectée ici. Mettre
  le README sous suivi de version rendrait la prochaine réévaluation exacte au
  lieu d'inférée.
- **Le taux de levée n'est pas une mesure de qualité.** Huit constats levés sur
  trente-cinq n'a de sens que si tous pesaient pareil, ce qui est faux : le
  constat 1 de la section A vaut à lui seul plusieurs des constats restés
  ouverts. Aucun décompte n'est proposé pour cette raison.
- **L'intention de l'auteur n'est pas connue.** Les constats 15 et 16 sont des
  omissions **ou** des réserves délibérées. L'analyse relève l'absence, pas
  l'oubli.
- **Le format attendu par les organisateurs reste inconnu**, comme dans les
  deux analyses précédentes. Le résumé fait maintenant 150 mots ; si une limite
  existe, elle n'a pas été vérifiée.
- **Rien n'a été réexaminé du fond de la section noumanity** ni de la bio, qui
  sont des textes personnels et dont l'exactitude relève de leur auteur.

**Relations.** Dérive de ANL-007 et ANL-008, dont elle reprend les constats un
à un. Analyse le `README.md` de la racine dans sa version du 2026-09-08 04:14.
