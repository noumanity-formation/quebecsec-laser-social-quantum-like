---
type: fondation
id: FND-005
titre: "Théories des modes de scrutin"
version: 0.1.0
status: actif
date: 2026-08-27
---

# FND-005 - Théories des modes de scrutin

- **Objectif** : établir ce que l'on sait des règles qui transforment des
  voix en sièges, de leurs effets systématiques et de leur manipulabilité.
  Pour qui : quiconque doit identifier, dans un système électoral donné, où
  se trouve le **levier mécanique** — le point où un déplacement marginal de
  voix produit un déplacement disproportionné de pouvoir.

## Note de rigueur

Cette fondation combine trois corpus de fiabilité inégale.

**Très solide** : la théorie du choix social. Les théorèmes d'Arrow, de
Gibbard-Satterthwaite et de May sont des résultats mathématiques démontrés ;
ils ne vieillissent pas et ne se discutent pas, seule leur interprétation se
discute.

**Solide** : les régularités empiriques comparées (loi de Duverger sous sa
forme probabiliste, effet mécanique de la magnitude de circonscription,
modèle du produit des sièges de Taagepera). Fondées sur de larges bases de
données électorales comparées, avec des marges d'erreur connues.

**Vérifié en ligne pour cette session** : les faits relatifs à la réforme
québécoise du mode de scrutin — dépôt du projet de loi n° 39 le
25 septembre 2019 par Sonia LeBel, contenu du projet (système mixte avec
compensation régionale, 80 députés de circonscription et 45 députés
régionaux), abandon du référendum annoncé en avril 2021 faute de temps
parlementaire, et estimation selon laquelle la CAQ aurait obtenu 62 sièges
au lieu de 74 en 2022 sous les paramètres du projet de loi 39, perdant sa
majorité à un siège près. Ces éléments proviennent de sources journalistiques
et institutionnelles québécoises consultées le 2026-08-27.

**Non vérifié** : les pourcentages précis de voix et de sièges des élections
québécoises, qui ne sont **pas** avancés ici pour cette raison. Le lecteur
qui en aura besoin devra les tirer directement d'Élections Québec.

Vitesse de vieillissement : **très lente** pour les sections 1 et 2 ;
**rapide** pour l'ancrage québécois, qui dépend de l'état d'un dossier
législatif ouvert.

## Cadrage

**Dans le périmètre.** Les familles de modes de scrutin et leurs formules ;
les théorèmes d'impossibilité du choix social ; les effets systématiques
établis (nombre de partis, disproportionnalité, vote stratégique) ; les
formes de manipulation du système (vote stratégique, charcutage, dilution) ;
un ancrage factuel minimal sur le cas québécois.

**Hors périmètre.** Le droit électoral détaillé (financement, publicité,
inscription des électeurs), sauf mention. La sécurité technique du
dépouillement et des machines de vote — sujet distinct, qui relèverait d'une
fondation de cybersécurité. Les régimes politiques comme tels : FND-006.

**Définitions de travail.**

- *Magnitude de circonscription* (M) : nombre de sièges attribués dans une
  circonscription. **Variable la plus déterminante de tout le domaine.**
- *Disproportionnalité* : écart entre la répartition des voix et celle des
  sièges. Mesurée usuellement par l'indice de Gallagher (racine de la
  demi-somme des carrés des écarts).
- *Effet mécanique* : conversion des voix en sièges par la formule, à
  comportement électoral constant. *Effet psychologique* : anticipation par
  les électeurs et les partis de cet effet mécanique, qui modifie leur
  comportement en amont.
- *Vote stratégique* : voter pour autre chose que son option préférée, en
  fonction de ses chances de l'emporter.
- *Seuil* : proportion minimale de voix requise pour accéder à la répartition
  des sièges. Peut être légal (explicite) ou effectif (produit par la formule
  et la magnitude).

## Corps

### 1. Les théories, leur portée, leurs résultats et leurs usages

**1.1 Le choix social : ce qu'aucune règle ne peut faire.**

*Condorcet* (1785) : le **paradoxe de Condorcet** — des préférences
individuelles transitives peuvent produire une préférence collective
cyclique (A bat B, B bat C, C bat A). Il n'y a alors aucun vainqueur
majoritaire. *Jean-Charles de Borda* (1781) : méthode de comptage par rangs,
et démonstration que le scrutin à la pluralité peut élire un candidat que la
majorité rejette.

*Kenneth Arrow* (*Social Choice and Individual Values*, 1951, Nobel 1972) :
**théorème d'impossibilité**. Aucune règle d'agrégation de préférences
ordinales sur au moins trois options ne peut satisfaire simultanément un
petit ensemble de conditions raisonnables (domaine universel, unanimité,
indépendance des options non pertinentes, non-dictature). Portée exacte :
c'est un résultat sur les préférences **ordinales** ; il n'interdit pas
toute règle raisonnable, il interdit une règle parfaite au sens de ces
axiomes.

*Gibbard* (1973) et *Satterthwaite* (1975) : **toute règle de vote
déterministe, non dictatoriale, avec au moins trois issues possibles, est
manipulable** — il existe des situations où mentir sur ses préférences est
avantageux. Résultat central pour ce projet : *la manipulabilité n'est pas un
défaut de conception que l'on pourrait corriger ; c'est une propriété
mathématique de tout système de vote non trivial.* La question n'est jamais
« ce système est-il manipulable », mais « à quel coût et par qui ».

*Kenneth May* (1952) : pour **deux** options seulement, la règle de majorité
est l'unique règle satisfaisant anonymat, neutralité et monotonie. Corollaire
opératoire : **un référendum binaire est le seul dispositif électoral qui
échappe aux pathologies d'agrégation d'Arrow.** D'où l'intérêt stratégique,
pour qui veut manipuler, de réduire un enjeu à deux options — et l'intérêt
défensif de ne pas le faire.

*Duncan Black* (1948) : théorème de l'électeur médian — si les préférences
sont unimodales sur une seule dimension, la position médiane l'emporte et
aucun cycle n'apparaît. Corollaire inverse et essentiel : **les cycles et
l'instabilité apparaissent quand le débat devient multidimensionnel**. C'est
la base théorique de l'*heresthetics* de Riker (voir FND-004) : ajouter une
dimension au débat, c'est déstabiliser un équilibre.

*Choix social computationnel* : depuis les années 2000, un domaine à
l'intersection de l'informatique et de l'économie étudie la **complexité**
de la manipulation — l'idée étant qu'une manipulation NP-difficile à calculer
est pratiquement inoffensive. Résultat nuancé depuis : la difficulté au pire
cas ne protège pas dans le cas moyen. Voir Brandt, Conitzer, Endriss,
Lang et Procaccia, *Handbook of Computational Social Choice*, 2016.

**1.2 Les familles de modes de scrutin.**

*Majoritaires.* Scrutin uninominal majoritaire à un tour (SMUT / FPTP) :
utilisé au Canada, au Québec, au Royaume-Uni, aux États-Unis, en Inde.
Scrutin à deux tours (France). Vote alternatif ou préférentiel (Australie).
Bloc majoritaire plurinominal.

*Proportionnels.* Listes (fermées, ouvertes, libres) avec formule de
répartition : d'Hondt (favorise les grands partis), Sainte-Laguë (plus
neutre), quotients Hare et Droop. Vote unique transférable (STV : Irlande,
Malte).

*Mixtes.* Compensatoires (MMP : Allemagne, Nouvelle-Zélande, Écosse), où la
part proportionnelle corrige la part majoritaire ; parallèles (Japon), où
elle ne la corrige pas. **La distinction compensatoire / parallèle change
tout** : un système mixte parallèle reste globalement majoritaire.

*Le projet de loi 39 québécois relevait de la famille mixte compensatoire,
avec compensation régionale plutôt que nationale* — un choix qui limite
mécaniquement l'ampleur de la correction.

**1.3 Les effets établis.**

*Loi de Duverger* (1951) : le scrutin majoritaire à un tour tend vers le
bipartisme ; la proportionnelle et le scrutin à deux tours favorisent le
multipartisme. Deux mécanismes : mécanique (les petits partis perdent des
sièges) et psychologique (les électeurs et les donateurs les abandonnent).
Statut : c'est une **tendance probabiliste, pas une loi**. Le Canada et
l'Inde sont des contre-exemples permanents, expliqués par la concentration
géographique et régionale du soutien aux tiers partis. *Cela vaut
directement pour le Québec, où le scrutin majoritaire coexiste avec quatre à
cinq forces significatives.*

*Douglas Rae* (*The Political Consequences of Electoral Laws*, 1967) :
première étude comparative quantitative systématique.

*Rein Taagepera et Matthew Shugart* (*Seats and Votes*, 1989) ;
*Taagepera* (*Predicting Party Sizes*, 2007) : le **modèle du produit des
sièges**. Le nombre effectif de partis d'un pays est prédit, avec une
précision remarquable, par une seule quantité — le produit de la magnitude
moyenne des circonscriptions par la taille de l'assemblée. Ce résultat est
l'un des rares en science politique à ressembler à une loi quantitative.

*Arend Lijphart* (*Electoral Systems and Party Systems*, 1994) : les quatre
dimensions déterminantes sont la formule, la magnitude, le seuil et la taille
de l'assemblée. **La magnitude est la variable dominante.**

*Gary Cox* (*Making Votes Count*, 1997) : la règle « M+1 » — sous des
conditions de coordination stratégique complète, le nombre de candidats
viables dans une circonscription tend vers la magnitude plus un. Fournit une
théorie microfondée de l'effet psychologique.

*Michael Gallagher* (1991) : l'indice de moindres carrés, devenu la mesure
standard de disproportionnalité.

**1.4 Manipuler un système électoral : le catalogue.**

Cinq leviers, du plus institutionnel au plus opérationnel.

1. *Choisir la règle.* Le levier le plus puissant est de fixer les
   paramètres — magnitude, seuil, découpage — avant même que l'on vote. C'est
   l'enjeu de tout débat sur une réforme du mode de scrutin, y compris au
   Québec.
2. *Découper les circonscriptions* (charcutage électoral). Deux techniques
   classiques : le *packing* (concentrer les adversaires dans peu de
   circonscriptions) et le *cracking* (les disperser sous le seuil de
   victoire partout). Détection : l'*efficiency gap* (Stephanopoulos et
   McGhee, 2015), les méthodes de simulation d'ensembles de découpages
   (Duchin, Mattingly), les tests de symétrie partisane. **Au Canada et au
   Québec, le découpage relève de commissions indépendantes, ce qui réduit
   fortement ce levier par rapport au cas états-unien — une différence
   structurelle à ne pas effacer.**
3. *Induire du vote stratégique*, ou l'empêcher. Sous scrutin majoritaire,
   convaincre une partie de l'électorat qu'un tiers parti est viable — ou
   qu'il ne l'est pas — modifie mécaniquement le résultat sans changer
   aucune préférence. **Levier le moins coûteux et le plus discret** : il ne
   demande de convertir personne, seulement de déplacer une **croyance sur
   les chances**. C'est le point de jonction le plus direct entre la théorie
   électorale et une opération d'influence.
4. *Agir sur la participation différentielle.* Démobiliser sélectivement
   coûte moins que persuader (voir FND-004, Kalla et Broockman). Dans un
   système à faible magnitude, quelques milliers d'abstentions bien
   localisées suffisent à basculer des circonscriptions.
5. *Attaquer l'acceptation du résultat.* Norris : la perception
   d'irrégularité, même infondée, dégrade la confiance et la participation.
   Ce levier ne modifie pas le décompte ; il modifie la légitimité de ce que
   le décompte produit.

**1.5 Ancrage québécois (faits vérifiés seulement).**

Le Québec élit son Assemblée nationale au scrutin uninominal majoritaire à un
tour, dans 125 circonscriptions. Une réforme a été engagée puis abandonnée :
le projet de loi n° 39, *Loi établissant un nouveau mode de scrutin*, déposé
le 25 septembre 2019 par la ministre Sonia LeBel, proposait un système mixte
à compensation régionale — 80 députés de circonscription et 45 députés
régionaux désignés selon les résultats de chaque formation dans sa région
administrative. En avril 2021, le gouvernement a confirmé qu'aucun référendum
n'aurait lieu lors des élections générales de 2022, faute de temps pour
étudier et adopter le projet avant la fin de la session parlementaire. Une
estimation appliquant les paramètres du projet de loi 39 aux résultats de
2022 attribue à la CAQ 62 sièges au lieu des 74 obtenus, soit une perte de
majorité à un siège près.

*Deux conséquences structurelles, à établir formellement ailleurs mais
visibles ici.* D'une part, un scrutin majoritaire à faible magnitude
(M = 1) maximise l'effet de levier : de faibles déplacements de voix,
géographiquement ciblés, produisent de grands déplacements de sièges.
D'autre part, un système multipartite sous scrutin majoritaire maximise le
rendement d'une manipulation du **vote stratégique**, puisque le résultat
dépend fortement de la répartition des voix entre partis qui se disputent le
même électorat.

### 2. Évolution de la discipline, intervenants et contributions

**Préhistoire mathématique (1299-1800).** *Ramon Llull* et *Nicolas de
Cues* anticipent au Moyen Âge des méthodes de comparaison par paires et de
comptage par rangs. *Jean-Charles de Borda* (1781) et le *marquis de
Condorcet* (1785) fondent l'analyse mathématique du vote à l'Académie des
sciences ; leurs deux méthodes restent les deux pôles du domaine.
*Charles Dodgson* (Lewis Carroll), dans les années 1870, redécouvre
indépendamment plusieurs résultats.

**Fondation du choix social moderne (1948-1975).** *Duncan Black* (1948)
réintroduit Condorcet et démontre le théorème de l'électeur médian.
*Kenneth Arrow* (1951) démontre l'impossibilité et fonde la discipline.
*Kenneth May* (1952) caractérise la règle de majorité à deux options.
*Amartya Sen* (Nobel 1998) élargit le cadre : le libéral parétien (1970), la
critique de l'ordinalisme strict, et la démonstration que **relâcher
l'exigence d'information ordinale pure ouvre des issues** — sans elle,
l'impossibilité d'Arrow est incontournable. *Allan Gibbard* (1973) et *Mark
Satterthwaite* (1975) démontrent l'impossibilité de la non-manipulabilité.

**Science politique empirique comparée (1951-2000).** *Maurice Duverger*
(*Les Partis politiques*, 1951) énonce ses lois. *Douglas Rae* (1967)
inaugure la comparaison quantitative. *Markku Laakso et Rein Taagepera*
(1979) proposent l'indice du **nombre effectif de partis**, sans lequel le
domaine ne serait pas mesurable. *Taagepera et Shugart* (1989) puis
*Lijphart* (1994) établissent le corpus de résultats comparés.
*Michael Gallagher* (1991) fournit l'indice de disproportionnalité.
*Gary Cox* (1997) microfonde l'effet psychologique.

**Période contemporaine (2000-2026).** Trois axes.
1. *Choix social computationnel* : Conitzer, Procaccia, Brandt, Endriss,
   Lang — complexité de la manipulation, du contrôle et de la corruption d'une
   élection, et procédures d'agrégation pour l'intelligence artificielle.
   *Contribution* : reformuler la manipulation comme problème algorithmique,
   avec ses classes de complexité.
2. *Géométrie du découpage électoral* : Stephanopoulos et McGhee
   (*efficiency gap*, 2015) ; Moon Duchin et le Metric Geometry and Gerrymandering
   Group ; Jonathan Mattingly — méthodes de Monte-Carlo pour comparer un
   découpage à l'ensemble des découpages possibles. *Contribution* : rendre
   le charcutage détectable statistiquement, donc justiciable.
3. *Réformes et systèmes alternatifs* : évaluation empirique du vote
   alternatif, du vote par approbation, du jugement majoritaire (Balinski et
   Laraki, 2010, qui proposent un système cardinal échappant partiellement à
   Arrow), du STAR voting. *Contribution* : montrer que le choix d'une règle
   est un choix politique déguisé en choix technique.

**Ce sur quoi la discipline ne s'entend pas.**
- La proportionnelle produit-elle de meilleurs gouvernements, ou seulement
  des assemblées plus fidèles ? Débat Lijphart contre les tenants de la
  clarté de la responsabilité (Powell).
- La difficulté algorithmique de la manipulation protège-t-elle réellement ?
  Réponse majoritaire aujourd'hui : non, pas dans le cas moyen.
- Les systèmes cardinaux (jugement majoritaire, vote par approbation)
  échappent-ils vraiment aux impossibilités, ou déplacent-ils simplement le
  problème vers la comparabilité interpersonnelle ?

### 3. Questions de recherche principales, et qui d'autre s'en occupe

**Q1 — Existe-t-il une règle de vote « juste » ?**
Réponse mathématique : non, pas au sens des axiomes d'Arrow.
*Autres disciplines* : mathématiques et théorie de la décision ; philosophie
politique normative (que doit agréger une élection : des préférences, des
jugements, des intérêts ?) ; économie du bien-être.

**Q2 — Quel est l'effet causal d'un mode de scrutin sur le système
partisan ?**
*Autres disciplines* : économétrie et méthodes quasi-expérimentales ;
sociologie électorale (les clivages préexistent-ils à la règle ?) ; histoire
comparée ; sociophysique, qui modélise l'agrégation hiérarchique du vote
(Galam, voir FND-008).

**Q3 — Comment détecter un découpage manipulé ?**
*Autres disciplines* : mathématiques (géométrie, théorie des graphes,
échantillonnage de Monte-Carlo par chaînes de Markov) ; informatique ;
droit constitutionnel ; géographie.

**Q4 — À quelles conditions les électeurs votent-ils stratégiquement ?**
La question la plus directement utile ici, puisqu'elle porte sur des
**croyances manipulables**.
*Autres disciplines* : économie expérimentale et théorie des jeux ;
psychologie de la décision ; sondages et prévisions — les sondages étant
eux-mêmes l'instrument par lequel la croyance sur les chances se forme
(articulation avec FND-001, « l'opinion publique n'existe pas »).

**Q5 — Quelle est la robustesse d'une règle de vote face à une manipulation
coordonnée ?**
*Autres disciplines* : choix social computationnel ; théorie des mécanismes ;
**ingénierie de la sûreté et modélisation de menace** — c'est le pont avec la
cybersécurité, et le pont le moins exploré de tous.

**Q6 — Comment mesurer et interpréter la disproportionnalité ?**
*Autres disciplines* : statistique ; théorie de la mesure ; droit
constitutionnel (l'égalité du vote comme norme juridique).

**Q7 — Que produit une réforme du mode de scrutin, et pourquoi échoue-t-elle
si souvent ?**
*Autres disciplines* : sociologie politique des réformes ; théorie du choix
rationnel (les gagnants du système actuel décident de sa réforme —
conflit d'intérêt structurel) ; science administrative. **Le dossier
québécois est un cas d'école de cet échec.**

## Synthèse

Cinq résultats à retenir.

1. **Toute règle de vote non triviale est manipulable** (Gibbard,
   Satterthwaite). Ce n'est pas un défaut réparable, c'est un théorème. La
   question utile porte sur le coût et l'accessibilité de la manipulation,
   jamais sur son existence.
2. **La magnitude de circonscription domine tout le reste** (Lijphart,
   Taagepera). Un scrutin à magnitude 1 — celui du Québec — maximise l'effet
   de levier : un petit déplacement de voix, bien localisé, produit un grand
   déplacement de sièges.
3. **L'instabilité vient de la multidimensionnalité** (Black, Riker). Tant
   qu'un débat tient sur un axe, il a un équilibre médian stable. Y ajouter
   une dimension le déstabilise. C'est la manipulation la plus élégante, et
   la plus difficile à qualifier d'attaque.
4. **Le vote stratégique est le levier le moins coûteux.** Sous scrutin
   majoritaire multipartite, modifier la croyance des électeurs sur les
   *chances* d'un parti change le résultat sans changer aucune préférence.
   Ce levier ne demande pas de persuader ; il demande de faire croire.
5. **Un référendum binaire échappe aux pathologies d'agrégation** (May) —
   mais concentre en contrepartie tout l'enjeu sur la **formulation de la
   question** et sur le cadrage, c'est-à-dire sur ce que FND-001 et FND-003
   décrivent.

Sur le Québec, les faits vérifiés sont : scrutin majoritaire à un tour,
125 circonscriptions, réforme mixte compensatoire proposée en 2019 (projet de
loi 39), référendum abandonné en avril 2021, et une estimation selon laquelle
la réforme aurait privé le parti au pouvoir de sa majorité en 2022.

## Limites

- **Aucune donnée électorale québécoise chiffrée** n'est avancée : les
  pourcentages de voix et de sièges n'ont pas été vérifiés dans cette session
  et ne figurent donc pas ici. Il faut les tirer d'Élections Québec avant tout
  usage public.
- **Aucune analyse de sensibilité.** Cette fondation dit que le levier
  mécanique existe ; elle ne quantifie pas, pour le Québec, combien de voix
  déplacées dans combien de circonscriptions produiraient quel changement.
  C'est un calcul à faire, et il relève d'une analyse, pas d'une fondation.
- **La sécurité technique du vote n'est pas traitée** : ni les machines, ni
  le dépouillement, ni les listes électorales. Un public de cybersécurité
  attendra ce volet ; il faudra une fondation distincte.
- **Le charcutage est peu pertinent au Québec** — commissions indépendantes —
  et cette fondation n'a pas vérifié dans le détail les règles de délimitation
  québécoises. Ne pas importer le cadre états-unien sans cette vérification.
- **Ce qu'il faudrait pour aller plus loin** : les résultats officiels par
  circonscription des dernières élections générales québécoises ; les règles
  exactes de délimitation ; et une revue de la littérature sur le vote
  stratégique en contexte canadien, qui existe et n'a pas été dépouillée ici.

## Sources

**Choix social — résultats démontrés.**
- Marquis de Condorcet, *Essai sur l'application de l'analyse à la
  probabilité des décisions rendues à la pluralité des voix*, 1785.
- Kenneth Arrow, *Social Choice and Individual Values*, Wiley, 1951.
- Kenneth May, « A Set of Independent Necessary and Sufficient Conditions for
  Simple Majority Decision », *Econometrica*, 1952.
- Duncan Black, « On the Rationale of Group Decision-Making », *Journal of
  Political Economy*, 1948.
- Allan Gibbard, « Manipulation of Voting Schemes », *Econometrica*, 1973 ;
  Mark Satterthwaite, *Journal of Economic Theory*, 1975. **Résultat
  d'impossibilité central pour ce projet.**
- Amartya Sen, *Collective Choice and Social Welfare*, 1970.
- Michel Balinski et Rida Laraki, *Majority Judgment*, MIT Press, 2010.
  Proposition cardinale.
- Felix Brandt, Vincent Conitzer, Ulle Endriss, Jérôme Lang, Ariel Procaccia
  (dir.), *Handbook of Computational Social Choice*, Cambridge UP, 2016.
  Référence sur la complexité de la manipulation.

**Science politique comparée des systèmes électoraux.**
- Maurice Duverger, *Les Partis politiques*, Armand Colin, 1951.
- Douglas Rae, *The Political Consequences of Electoral Laws*, Yale UP, 1967.
- Markku Laakso et Rein Taagepera, « Effective Number of Parties », 1979.
- Rein Taagepera et Matthew Shugart, *Seats and Votes*, Yale UP, 1989 ;
  Rein Taagepera, *Predicting Party Sizes*, Oxford UP, 2007. **Modèle du
  produit des sièges** — le résultat quantitatif le plus fort du domaine.
- Arend Lijphart, *Electoral Systems and Party Systems*, Oxford UP, 1994.
- Gary Cox, *Making Votes Count*, Cambridge UP, 1997. Règle M+1.
- Michael Gallagher, « Proportionality, Disproportionality and Electoral
  Systems », *Electoral Studies*, 1991.

**Découpage et détection de manipulation.**
- Nicholas Stephanopoulos et Eric McGhee, « Partisan Gerrymandering and the
  Efficiency Gap », *University of Chicago Law Review*, 2015.
- Moon Duchin et le Metric Geometry and Gerrymandering Group ; Jonathan
  Mattingly et al. — méthodes d'échantillonnage de découpages.

**Cas québécois — vérifié en ligne le 2026-08-27.**
- Assemblée nationale du Québec, *Projet de loi n° 39, Loi établissant un
  nouveau mode de scrutin* (42e législature, 1re session).
  https://www.assnat.qc.ca/fr/travaux-parlementaires/projets-loi/projet-loi-39-42-1.html
- Élections Québec, *Audition sur le projet de loi n° 39*.
  https://electionsquebec.qc.ca/allocutions/audition-sur-le-projet-de-loi-no-39-loi-etablissant-un-nouveau-mode-de-scrutin
- Radio-Canada, « Pas de référendum en 2022 sur la réforme du mode de scrutin
  au Québec » (avril 2021).
  https://ici.radio-canada.ca/nouvelle/1788707/sonia-lebel-etude-projet-loi-39-caq-promesse
- Radio-Canada, « Et si la CAQ avait réformé le mode de scrutin ? » (2022) —
  source de l'estimation 62 sièges au lieu de 74.
  https://ici.radio-canada.ca/info/2022/elections-quebec/distorsion-vote-reforme-mode-scrutin-uninominal-majoritaire-proportionnelle/
- Le Devoir, « Comment la CAQ a largué la réforme du mode de scrutin ».
  https://www.ledevoir.com/politique/quebec/802210/politique-quebecoise-comment-caq-largue-reforme-mode-scrutin

**Source à consulter avant tout chiffre** : Élections Québec, résultats
officiels par circonscription. Non consultée dans cette session.

**Relations.** Référence FND-004 (heresthetics de Riker, effets de campagne) ;
complémentaire de FND-006 (régimes politiques) ; alimente les analyses de
levier mécanique du dépôt.
