# La question de l'urne comme base de mesure

## Un modèle quantum-like multi-champ de la vulnérabilité électorale, avec application au Québec

**Rapport scientifique préliminaire** — version 0.1.0, 28 août 2026.
Dépôt `quebecsec-social-laser-hack`. Travail produit par agent sous direction
humaine, dans le cadre du dispositif clia ; les décisions relèvent de l'humain,
la production et ses réserves de l'agent.

**Statut : préliminaire au calcul.** Aucun résultat numérique n'est rapporté
ici. Ce rapport expose une démarche, argumente l'intérêt du problème et la
faisabilité du travail, et énonce le programme de falsification qui le rendra
évaluable.

---

## Résumé

Nous proposons un modèle formel de la vulnérabilité d'un scrutin démocratique,
construit sur trois déplacements par rapport à la littérature existante.
Premièrement, l'unité atomique du problème électoral n'est pas l'individu mais
le **champ** au sens de Bourdieu : la dynamique électorale est une lutte
inter-champ. Deuxièmement, la **question de l'urne** — quel enjeu est le plus
important — n'est pas un contenu mais un **choix de base de mesure** : les
observables associés aux enjeux ne commutent pas, et la distribution des
résultats dépend de l'observable mesuré sans que l'état ait changé.
Troisièmement, le mécanisme d'amplification pertinent n'est pas un laser
monochromatique mais un **laser multimode sur milieu à élargissement
inhomogène** : la décomposition en champs à enjeux existentiels distincts
*est* cet élargissement, ce qui rend un pompage multi-couleur stable là où un
pompage unique produirait une compétition de modes.

Nous instancions ce modèle sur l'élection générale québécoise du 5 octobre
2026, dont la campagne a été déclenchée le 27 août. Nous montrons que le
problème est d'intérêt — le système présente un levier mécanique mesuré, une
projection de gouvernement majoritaire à environ un tiers des voix, et deux
champs à très fort effet de levier entièrement dépourvus d'offre politique — et
que le travail est faisable : le modèle complet tient en 110 amplitudes
complexes, et l'un de ses résultats est calculable sans donnée nouvelle.

Nous soutenons enfin une thèse qui contredit l'intuition commune sur les
opérations d'influence : **une attaque qui cherche à changer les opinions n'est
pas faisable ; une attaque qui change la question à laquelle on répond
pourrait l'être.**

---

## 1. Introduction

### 1.1 Le problème

La littérature empirique sur la persuasion politique converge depuis une
décennie vers un résultat inconfortable : les effets persuasifs directs des
campagnes sont petits, souvent statistiquement indiscernables de zéro en
élection générale [1]. La littérature sur les opérations d'influence en ligne
va dans le même sens : l'exposition est très concentrée sur de petites
minorités, les effets mesurés sur les comportements sont faibles, et
l'attribution causale est fragile [2, 3].

Il en découle un paradoxe pratique. Les démocraties se dégradent — le rapport
V-Dem 2026 documente une vague d'autocratisation qui atteint désormais des
démocraties occidentales établies, la liberté d'expression étant la dimension
la plus atteinte [4] — mais le mécanisme par lequel une intervention externe
produirait cette dégradation résiste à la démonstration. Si l'on ne persuade
presque personne, comment un système démocratique bascule-t-il ?

Notre hypothèse est que la question est mal posée. **Une opération efficace ne
déplace pas les préférences ; elle déplace ce qui est mesuré.** C'est une thèse
ancienne en science politique — Riker l'appelle *heresthetics*, l'art de gagner
en restructurant la dimension du débat plutôt qu'en persuadant [5] — et en
sociologie — Bourdieu la formule comme lutte de classement, portant sur la
définition légitime d'un champ et non sur les positions à l'intérieur de
celui-ci [6]. Elle a aussi une expression cognitive : la réponse à une question
d'enquête est un échantillon des considérations rendues accessibles au moment
où la question est posée [7].

Ce que nous ajoutons est un cadre formel qui unifie ces trois énoncés et les
rend calculables.

### 1.2 Ce que ce rapport soutient

1. Que le problème est **d'intérêt** : le système québécois présente
   aujourd'hui une configuration où un déplacement marginal de voix produit un
   déplacement disproportionné de pouvoir, et où les points de plus fort levier
   sont structurellement inoccupés (§5).
2. Que le travail est **faisable** : le modèle est implémentable à coût
   négligeable, et un de ses résultats est obtenable sans donnée nouvelle (§6).
3. Que le modèle est **falsifiable** : nous énonçons quatre tests dont trois
   peuvent le réfuter (§6.3).
4. Que l'attaque décrite est **partiellement infaisable**, et que dire
   précisément *où* elle l'est constitue le principal apport défensif du
   travail (§7).

---

## 2. Travaux antérieurs

### 2.1 Modélisation quantum-like de la décision et du vote

Le programme *quantum-like* applique le formalisme probabiliste de la théorie
quantique — espaces de Hilbert, observables non commutants, interférences — à
des systèmes qui ne sont pas physiquement quantiques [8, 9]. Il ne postule
aucune quantique du cerveau ; il emprunte une structure probabiliste plus
générale que la structure classique.

Son résultat empirique le plus fort concerne les **effets d'ordre des
questions** : le formalisme quantique impose une contrainte quantitative sans
paramètre libre sur la façon dont l'ordre de deux questions d'enquête modifie
les proportions de réponses, et cette contrainte a été vérifiée sur un large
corpus de sondages réels [10]. C'est ce résultat qui fonde notre §3.2.

Appliqué au vote, le programme a un précédent direct : Khrennikova modélise le
*ticket splitting* américain — voter pour des partis différents à des scrutins
simultanés — et montre que ce comportement **viole la théorie classique des
probabilités**, en identifiant des interférences dans les préférences
reconstruites [11]. Un autre travail applique l'équation maîtresse de
Gorini-Kossakowski-Sudarshan-Lindblad à la dynamique de la décision électorale
[12]. Plus récemment, Dubois propose une méthode numérique pour déterminer un
opérateur densité sur la famille des candidats **à partir de sondages
d'opinion** [13], ce qui règle la question de l'initialisation.

### 2.2 Le laser social

Khrennikov propose depuis 2016 d'étendre le programme quantum-like par des
concepts de théorie quantique des champs, sous le nom de **laser social** [14,
15]. Le modèle décrit des individus comme des « atomes sociaux » à deux
niveaux, absorbant et émettant des quanta d'énergie sociale — les *infons* —
sous l'effet d'un pompage médiatique ; au-delà d'un seuil d'inversion de
population, l'émission stimulée produit une amplification exponentielle et
**cohérente** de l'action collective.

La seule version simulable du corpus est le modèle de champ moyen sur réseau
d'Alodjants *et al.* [16], qui fournit un hamiltonien, des équations
semi-classiques de type Maxwell-Bloch, une équation de type Ginzburg-Landau,
une condition de seuil `σ_seuil = κΓ/(g²⟨k⟩)` et un paramètre de couplage
collectif `G = g⟨k⟩`.

**Nous relevons dans ce corpus deux faits décisifs et rarement soulignés.**
D'abord, ses auteurs établissent que **lorsque le pompage est nul, l'équation de
taux se réduit à une dynamique épidémique classique de type SIS** : tout
l'apport propre du laser social par rapport à un modèle de contagion tient donc
dans le terme de pompage et dans la structure de résonateur. Ensuite, **le
modèle ne comporte aucun terme de dissipation** — décohérence, saturation et
relaxation y restent métaphoriques, sans équation. Un mécanisme dépourvu de
théorie de son extinction est inutilisable pour la conception d'un contrôle.

Nous ajoutons cette dissipation (§4.4).

### 2.3 Sociophysique électorale, et le modèle à battre

La sociophysique modélise les dynamiques d'opinion par des outils de physique
statistique : modèles du votant, modèles de Sznajd, modèles à confiance bornée,
modèles d'Ising et de Potts [17, 18]. Deux résultats structurent le domaine.
Galam établit que le **seuil de bascule n'est pas 50 %** : selon la règle
d'agrégation et la présence d'agents inflexibles, une minorité peut déterminer
l'attracteur d'un système. Granovetter, par une voie sociologique
indépendante, établit que le comportement collectif dépend de la **distribution
des seuils individuels** et non de leur moyenne [19].

Le domaine souffre d'un défaut reconnu par ses propres revues : beaucoup de
modèles, peu de validation empirique [18]. Une exception récente et importante
fait exception, et elle constitue notre référence : Korbel, Dahdoul et Thurner
proposent un modèle d'Ising à double champ aléatoire des élections,
`H = −J Σ A_ij s_i s_j − Σ h_i s_i`, et le **valident sur 6 357 courses
électorales américaines** de 1980 à 2020, avec un seuil critique de dépenses
estimé et une amélioration prédictive statistiquement significative [20].

**C'est le modèle à battre.** Nous soutenons qu'un modèle quantum-like qui ne
ferait pas mieux, hors échantillon et à nombre de paramètres comparable,
n'apporterait rien — et nous inscrivons cette comparaison au programme de
falsification plutôt que dans les travaux futurs.

### 2.4 Ce qui manque

Aucun de ces travaux ne prend le **champ** comme unité. Les modèles
quantum-like du vote portent sur l'électeur ; les modèles sociophysiques
portent sur des agents interchangeables sur un réseau ; le laser social postule
un milieu homogène. Or l'homogénéité du milieu est exactement ce qui interdit
un fonctionnement multimode (§3.3).

---

## 3. Cadre théorique

### 3.1 Le champ comme unité atomique

Nous suivons Bourdieu : un champ est un espace structuré de positions où des
agents luttent pour un **capital spécifique**, sous un **nomos** — le principe
de division qui le constitue — et une **doxa** — ce qui n'y est pas discuté
[6]. Nous décomposons la société québécoise en onze champs : politique,
journalistique, religieux, académique, syndical, bureaucratique, économique,
juridique, artistique, associatif, et un champ numérique en formation.

Une précision est nécessaire, et elle est une décision de modélisation
assumée. Un champ au sens strict est peuplé de quelques milliers d'agents
spécialisés, non de millions d'électeurs — c'est la thèse de Bourdieu sur la
délégation et la dépossession. Nous employons donc un **champ élargi** :
le champ *et sa population sous emprise*, c'est-à-dire les électeurs dont les
dispositions de vote sont structurées par ses catégories.

Nous définissons l'**enjeu existentiel** d'un champ comme ce qui, tranché
défavorablement, détruirait le champ lui-même — son nomos, son capital ou son
illusio — et non simplement ses intérêts. C'est cet enjeu qui fixe la fréquence
de résonance du champ.

### 3.2 La question de l'urne comme choix de base de mesure

Soit `Ψ` l'état de l'électorat et `{Q_a}` la famille des questions de l'urne
possibles — « quel enjeu est le plus important ? ». Le résultat du vote s'écrit

> `P(parti p | Q_a) = ‖Π_p^{(a)} Ψ‖²`

où `Π_p^{(a)}` projette sur le parti `p` dans la base propre de `Q_a`.

**Changer `a` change la distribution sans changer `Ψ`.** C'est possible parce
que les observables associés aux enjeux **ne commutent pas** : il n'existe
aucune distribution jointe de « importance de l'économie » et « importance de
l'environnement ». C'est précisément ce que mesurent les effets d'ordre des
questions [10].

Deux propriétés distinctes sont ici à l'œuvre, et les confondre nuit à la
clarté :

- la **non-commutativité** concerne un seul système mesuré de deux façons ;
  c'est ce qui fonde la question de l'urne ;
- l'**intrication** concerne deux sous-systèmes dont l'état conjoint ne se
  factorise pas ; c'est ce qui fonde la lutte inter-champ. L'état de l'électorat
  vit dans `H = H_1 ⊗ … ⊗ H_11` et n'est en général pas séparable.

**Conséquence stratégique.** Une campagne peut agir sur `Ψ` — c'est la
persuasion, dont §1.1 rappelle que l'effet mesuré est petit — ou sur `a` —
c'est la question de l'urne, dont le coût est faible et l'effet potentiellement
grand. Le modèle prédit donc que l'effort rationnel porte sur `a`. C'est ce que
la littérature empirique observe : effets persuasifs minimaux, effets d'agenda
robustes.

### 3.3 Le laser multi-couleur et l'élargissement inhomogène

Un laser est monochromatique par construction. Le fonctionnement **multimode**
existe, mais il n'est stable qu'à une condition connue : en milieu à
**élargissement homogène**, tous les atomes répondent à la même fréquence, les
modes se disputent le même gain, et un seul survit ; en milieu à
**élargissement inhomogène**, des sous-populations distinctes répondent à des
fréquences distinctes, chaque mode creuse son propre trou dans le gain, et les
modes coexistent.

**Notre proposition centrale : la décomposition en champs à enjeux existentiels
distincts est un élargissement inhomogène du milieu social.** C'est ce qui rend
un pompage multi-couleur cohérent — une proposition faîtière ambiguë excite
sans sélectionner, et **délègue la sélection spectrale au milieu** : chaque
champ émet ensuite sur la fréquence de son propre enjeu existentiel.

Le produit d'un tel mécanisme n'est pas un consensus. C'est une **coïncidence
de votes obtenus pour des raisons mutuellement incompatibles**.

Cette proposition a une conséquence immédiatement contraignante. Là où les
champs se recouvrent fortement, le milieu redevient localement homogène et la
compétition de modes reprend. La stabilité du mécanisme est donc bornée par la
structure de recoupement de la société considérée — une quantité mesurable.

---

## 4. Le modèle

### 4.1 Espace d'état

Onze champs, cinq partis, six contextes. Chaque champ porte
`ψ_j ∈ C² ⊗ C⁵` : un **qubit de mobilisation** — l'atome social, passif ou
mobilisé — et un **registre de préférence** sur les partis. Soit dix amplitudes
complexes par champ, **110 en représentation de champ moyen**.

L'intrication est conservée exactement sur le sous-ensemble de champs où la
structure de recoupement l'exige — dans le cas québécois, le triplet
`{syndical, bureaucratique, économique}`, soit mille amplitudes. **Le critère
de troncature n'est pas arbitraire : c'est la matrice de recoupement qui le
dicte.**

### 4.2 Observables de contexte

Pour chaque contexte `c`, on construit un observable `Q_c` à partir des
positions des partis sur cet enjeu, et l'on en extrait la base propre `U_c` par
diagonalisation. La non-commutativité est portée par le fait que `U_c† U_{c'}`
n'est ni l'identité ni une permutation.

**Ce point est important pour la falsifiabilité** : il rend le commutateur

> `κ_{c,c'} = ‖[Q_c, Q_{c'}]‖_F / (‖Q_c‖_F ‖Q_{c'}‖_F)`

numériquement évaluable. La structure de compatibilité que nous postulons —
une famille commutante autour de la légitimité, et une incompatibilité
irréductible entre l'État et le marché — cesse d'être un jugement argumenté et
devient un calcul, qui peut la réfuter.

### 4.3 Hamiltonien

> `H(t) = H₀ + H_ctx(t) + H_pump(t) + H_pref(t) + H_int`

- `H₀ = Σ_j (ω_j/2) σ_j^z` — énergie propre, où `ω_j` est l'écart de niveaux du
  champ, interprété comme sa **cadence de reprise interne**. C'est la lecture
  qui rend estimable la condition de résonance sociale : un message dont le
  rythme ne s'accorde pas à la cadence du champ ne s'y amplifie pas.
- `H_ctx(t) = Σ_c λ_c(t) Q_c` — les enjeux comme observables non commutants,
  pondérés par leur saillance `λ_c(t)`, seule fonction du modèle directement
  observable en pratique par la part du contexte dans la couverture médiatique.
- `H_pump(t) = Σ_j Ω_j(t) cos(ω_j^d t + φ_j)(σ_j^+ + σ_j^-)` — le **pompage
  multi-couleur**. Le désaccord `Δ_j = ω_j^d − ω_j` porte la condition de
  résonance ; hors résonance, le couplage s'annule. Les phases `φ_j`
  déterminent le **calendrier relatif des couleurs** ; verrouillées, elles
  produisent l'analogue d'un blocage de modes.
- `H_pref(t)` — l'offre différenciée des partis aux champs, active seulement sur
  la composante mobilisée. Traduction formelle de la thèse selon laquelle le
  message ne crée pas la charge mais la libère.
- `H_int` — couplage inter-champ, construit sur la matrice de recoupement, de
  signe négatif sur l'axe antagoniste.

### 4.4 Dissipation

Nous ajoutons ce que le modèle du laser social ne comporte pas :

> `dρ/dt = −i[H(t), ρ] + Σ_j ( D[√γ_j σ_j^-]ρ + D[√(Γ_j/2) σ_j^z]ρ )`

`γ_j` est la démobilisation, `Γ_j` le déphasage — la **température sociale**,
enfin dotée d'une définition opératoire : le taux auquel un champ perd la
cohérence de son cadrage.

**Conséquence directe et testable** : un système à gain et à pertes présente des
**oscillations de relaxation**. Sur une campagne de durée finie, une vague
pompée trop tôt retombe avant le scrutin. Le paramètre critique du mécanisme
est donc le **moment** du pompage, non son intensité — et c'est ce terme qui
permet de le calculer.

### 4.5 Mesure du vote

La mesure est projective et irréversible, dans la base des partis, mais sur un
état préalablement tourné par la question de l'urne : `V^{(a)} = U_a† V U_a`.
**Le modèle tient en une phrase : on projette toujours dans la base des partis,
mais l'état qu'on projette a été tourné par la question de l'urne.**

La participation d'un champ dépend de son inversion `⟨σ_j^z⟩` : un champ à
l'état fondamental ne vote pas. L'agrégation se fait par des **masses
effectives** `M_j` telles que `Σ_j M_j` égale exactement l'électorat — correction
nécessaire, faute de quoi une somme naïve sur des champs qui se recouvrent
surcompte d'un facteur voisin de 2,7 dans le cas québécois.

---

## 5. Le terrain : pourquoi le problème est d'intérêt

Toutes les données de cette section ont été vérifiées à des sources publiques
le 27 et le 28 août 2026.

### 5.1 Un précédent de décision à marge infinitésimale

Le référendum québécois du 30 octobre 1995 s'est joué à **50,58 % contre
49,42 %, un écart de 54 288 voix**, avec une participation de **93,52 %** — la
plus élevée de l'histoire québécoise [21]. Un déplacement de quelques dizaines
de milliers de voix aurait modifié l'ordre constitutionnel d'un pays du G7.

### 5.2 Un levier mécanique mesuré, non supposé

L'élection générale de 2022 a produit la répartition suivante : CAQ 40,98 % des
voix et 90 sièges ; Québec solidaire 15,43 % et 11 sièges ; Parti québécois
14,61 % et 3 sièges ; Parti libéral 14,37 % et 21 sièges ; Parti conservateur
**12,91 % et zéro siège** [22]. Quatre partis séparés par moins de trois points
obtiennent des rendements en sièges incomparables, et le parti arrivé quatrième
en voix forme l'opposition officielle.

Le Québec compte par ailleurs **trois inversions voix-sièges documentées** —
1944, 1966 et 1998 — où le parti arrivé deuxième en voix a formé le
gouvernement.

### 5.3 La configuration actuelle

La campagne pour l'élection générale du **5 octobre 2026** a été déclenchée le
**27 août**, pour une durée de 39 jours et **127 circonscriptions** — la carte
ayant été portée de 125 à 127 par une loi adoptée le 12 juin 2026 [23].

Au déclenchement : PQ 30 %, CAQ 23 %, PLQ 23 %, PCQ 16 %, QS 7 % [24]. Le
parti gouvernemental sortant, qui détenait 79 sièges à la dissolution après en
avoir remporté 90 en 2022, est projeté à **4 sièges, dans un intervalle allant
de 0 à 18** ; le parti en tête est projeté **majoritaire avec environ un tiers
des voix**, et le modèle public qui produit cette projection énonce lui-même
qu'un léger déplacement suffirait à faire basculer le résultat [25].

Enfin, un jugement de la Cour suprême du Canada sur la loi québécoise sur la
laïcité, entendu du 23 au 27 mars 2026, peut être rendu **à tout moment**, y
compris en pleine campagne [26].

### 5.4 Le fait structurel : les leviers les plus forts sont inoccupés

Le Québec compte environ **3 450 journalistes** pour **6,4 millions
d'électeurs inscrits** [27, 28] — un rapport d'un agent pour 1 850 électeurs ;
en incluant les métiers connexes de l'information, environ un pour 780. Le
champ numérique présente un rapport voisin d'un pour mille. **Moins de 15 000
personnes produisent le cadrage public offert à 6,4 millions d'électeurs.**

Or, dans l'inventaire systématique des propositions des cinq partis au
déclenchement de la campagne, **aucun parti n'adresse d'offre à ces deux
champs** : ni financement de l'information, ni réponse au blocage des contenus
d'information sur les plateformes, ni régulation algorithmique.

Ce n'est pas un paradoxe. Ces champs ne constituent pas un marché électoral :
leurs agents sont trop peu nombreux pour peser en voix, et une offre qui leur
serait explicitement adressée serait lue comme une tentative d'influence sur
eux — donc contre-productive, par réactance [29]. **Le levier le plus fort du
système est structurellement hors du marché politique.** C'est, à notre avis,
le fait le plus important établi par ce travail.

Le contexte informationnel en aggrave la portée : la confiance envers les
médias d'information chez les Canadiens francophones est passée de 55 % en 2016
à **46 %** ; les réseaux sociaux en sont devenus la première source ; et
**environ trois Canadiens sur quatre ignorent** que les médias d'information
sont bloqués sur les plateformes de Meta [30]. Une population dont
l'environnement informationnel a été amputé et qui ne le sait pas ne peut pas
corriger pour cette amputation.

---

## 6. Faisabilité

### 6.1 Faisabilité calculatoire

Le modèle est de très faible dimension. En représentation de champ moyen, l'état
complet tient en **110 amplitudes complexes**. La propagation se fait par
découpage symétrique de Strang, chaque terme de contexte étant appliqué par
rotation dans sa base propre — la méthode de découpage d'opérateur standard de
la dynamique quantique, où le changement de base joue le rôle de la transformée
de Fourier. Avec un pas de `0,01` jour, une campagne de 39 jours demande
**3 900 pas**, chacun coûtant quelques centaines de produits matrice-vecteur
`5 × 5`.

Ordres de grandeur visés : une trajectoire en **moins d'une milliseconde** ; un
ensemble de mille trajectoires en moins d'une seconde ; un balayage de 10⁴ jeux
de paramètres × 10³ trajectoires en **moins de quinze minutes** sur seize
cœurs. La dissipation est traitée par Monte-Carlo de fonction d'onde, ce qui
conserve le formalisme d'état pur et rend le parallélisme trivial.

**Le calcul n'est pas le goulot d'étranglement. Les paramètres le sont.**

### 6.2 Un résultat obtenable sans donnée nouvelle

La construction des observables `Q_c` à partir des positions des partis rend
les commutateurs `κ_{c,c'}` calculables immédiatement. Ce calcul confirme ou
réfute la structure de compatibilité que nous postulons — la famille commutante
et l'incompatibilité irréductible — **sans exiger la moindre donnée
supplémentaire et pour un coût de calcul nul**. C'est le premier résultat que
nous produirons, et nous nous engageons à le rapporter qu'il confirme ou qu'il
réfute.

### 6.3 Programme de falsification

Quatre tests, dont trois peuvent réfuter le modèle.

1. **La contrainte d'ordre des questions.** La contrainte quantitative de [10]
   est sans paramètre libre. Si la question de l'urne est bien un choix de base
   de mesure, elle doit être satisfaite par des paires de questions d'importance
   d'enjeux posées en ordres contrebalancés dans des sondages québécois. **Une
   violation réfute le noyau du modèle.** Le test est peu coûteux.
2. **Les commutateurs contre la structure postulée** (§6.2). Réfutable.
3. **La comparaison au modèle classique.** Le modèle d'Ising à double champ
   aléatoire de [20] est calibré et validé sur données réelles. À nombre de
   paramètres comparable et hors échantillon, si le modèle quantum-like ne fait
   pas mieux, il n'apporte rien — et nous le dirons.
4. **La signature de cohérence.** Le modèle prédit qu'un lasing multi-couleur
   produit une **montée de la cohérence à l'intérieur de chaque champ sans
   convergence entre champs**. L'homogénéité lexicale et argumentative d'un
   corpus médiatique est mesurable ; ce test est constructif plutôt que
   réfutant, mais il fournit un instrument.

### 6.4 Ce que le modèle ne peut pas encore faire

La conversion des parts de vote en sièges exige les résultats de 2022
transposés sur la carte à 127 circonscriptions. Ces données sont publiques et
n'ont pas encore été dépouillées. **Tant qu'elles ne le sont pas, le modèle
simule des intentions de vote agrégées, non une élection.**

---

## 7. La faisabilité de l'attaque, et ses bornes

C'est la section où nous soutenons une thèse qui contredit l'intuition commune.

### 7.1 Ce qui n'est pas faisable

**La persuasion de masse.** L'effet moyen du contact de campagne en élection
générale est statistiquement indiscernable de zéro [1]. Le seul protocole de
persuasion durable solidement établi — un échange non conflictuel d'une
vingtaine de minutes en porte-à-porte — ne passe pas à l'échelle [31]. Ce qui
est bon marché est volatil ; ce qui dure coûte cher.

**Le contrôle du réseau par peu de points d'entrée.** Si tous les nœuds d'un
réseau sont pilotés directement, l'énergie de contrôle croît de façon
sous-linéaire avec la taille du système ; si le contrôle passe par un seul
nœud, elle devient **exponentielle** dans certaines directions [32]. La
commandabilité structurelle d'un grand réseau est presque toujours vraie et
presque toujours sans intérêt pratique [33].

**L'opération visible.** La réactance et la connaissance de la persuasion font
que la visibilité de la tentative l'annule, voire l'inverse [29]. Le précédent
local le plus direct le confirme : une opération de communication étatique,
financée sur fonds publics et visant l'opinion québécoise sur une question
constitutionnelle, a réellement eu lieu à la fin des années 1990 — et son effet
net a été de **discréditer durablement son commanditaire**.

### 7.2 Ce qui pourrait l'être

**Le déplacement de la base de mesure.** Changer `a` plutôt que `Ψ` ne demande
pas de convaincre : il demande de rendre un enjeu saillant. C'est l'effet
médiatique le mieux établi de la littérature, et il est bon marché.

**La délégation de la sélection au milieu.** Une proposition faîtière ambiguë,
quasi diagonale dans toutes les bases, excite sans sélectionner et laisse chaque
champ choisir sa propre couleur. Elle est non falsifiable, donc robuste à la
vérification factuelle.

**Les fréquences libres.** Les deux champs de plus fort effet de levier ne
reçoivent aucune offre (§5.4). Ce sont, au sens strict du modèle, deux
fréquences non occupées du spectre.

**Le rendement mécanique.** Dans un scrutin uninominal à cinq forces
significatives et à vote fortement régionalisé, un déplacement marginal et
géographiquement ciblé produit un déplacement disproportionné en sièges (§5.2,
§5.3).

### 7.3 Les quatre bornes du mécanisme

Nous identifions quatre points de rupture, et les énoncer est le principal
apport défensif du travail.

1. **La compétition de modes.** Là où les champs se recouvrent — près d'un
   million de personnes à l'intersection la plus dense dans le cas québécois —
   deux couleurs tirent sur le même gain et l'une s'éteint.
2. **L'ambiguïté diffère l'arbitrage sans le supprimer.** Dès que le programme
   devient concret et chiffré, l'incompatibilité irréductible redevient visible.
   Le mécanisme pousse donc structurellement à ne pas publier de cadre
   financier consolidé — ce qui est en soi un indice.
3. **La détectabilité, qui est la vulnérabilité principale.** Un programme
   manifestement « tout à tout le monde » est la forme d'offre la plus facile à
   nommer, et **la nommer suffit à la neutraliser**. Le champ journalistique y
   est structurellement porté.
4. **Le calendrier.** Les oscillations de relaxation impliquent qu'une vague
   pompée trop tôt retombe avant le scrutin.

### 7.4 Une correction à l'hypothèse de départ

L'hypothèse d'une conjoncture de frustration disponible doit être corrigée.
L'énergie de « tenter autre chose » **n'est pas un réservoir indifférencié** :
elle est déjà canalisée vers deux formations, tandis qu'une troisième s'est
effondrée de 15,43 % à 7 %. Le milieu n'est pas au repos, il est déjà émetteur
— soit la configuration la plus défavorable à un fonctionnement multimode.

---

## 8. Considérations éthiques

Ce travail décrit un mécanisme d'attaque contre un processus démocratique,
pendant une campagne électorale en cours. Nous énonçons les précautions prises
et celles qui restent des décisions humaines.

**Ce que le travail produit.** Une modélisation formelle, une spécification de
programme, et une **signature de détection** en cinq signes, dont le
distinctif — cohérence intra-champ sans convergence inter-champ — est mesurable
sur corpus médiatique. Le versant défensif n'est pas un ajout de politesse : il
découle du même modèle, et c'est ce qui rend le travail présentable devant une
communauté de sécurité.

**Ce que le travail ne produit pas.** Aucune donnée n'est collectée, aucune
plateforme n'est sollicitée, aucun individu n'est ciblé. Aucun contenu de
campagne n'est rédigé. Les propositions par champ sont formulées au niveau de
l'orientation de politique publique, non de l'énoncé de campagne.

**Pourquoi le travail n'est pas directement opérationnalisable.** Aucun
paramètre du modèle n'est mesuré. L'énergie sociale n'a ni unité ni instrument ;
les seuils, couplages et cadences sont des estimations. Le livrable d'une
simulation ne sera donc pas une prédiction mais une **carte des régimes**.

**Ce qui reste une décision humaine.** Le calendrier et le périmètre de
publication. Les documents d'analyse portent une signature de détection, ce qui
leur confère une valeur défensive ; un exécutable paramétré n'a pas le même
statut qu'un texte. Publier le code, le publier après le scrutin, ne publier que
les documents, ou différer : cette décision n'appartient pas à l'agent qui
produit, et elle est portée comme objection ouverte dans le plan de codage.

---

## 9. Conclusion et travaux à venir

Nous avons proposé un modèle formel de la vulnérabilité électorale reposant sur
trois déplacements : le champ plutôt que l'individu comme unité, la question de
l'urne comme choix de base de mesure, et le laser multimode sur milieu
inhomogène plutôt que le laser monochromatique.

Notre thèse principale est que **l'attaque efficace n'est pas persuasive mais
métrologique** : elle ne change pas ce que les électeurs pensent, elle change
la question à laquelle leur vote répond. Cette thèse a l'avantage d'être
compatible avec le résultat empirique le mieux établi du domaine — la faiblesse
des effets persuasifs — au lieu de le contredire.

Nous soutenons que le problème est d'intérêt, sur un terrain où le levier
mécanique est mesuré, où une majorité est projetée à un tiers des voix, et où
les deux points de plus fort levier sont dépourvus d'offre politique. Nous
soutenons que le travail est faisable, à coût de calcul négligeable, et qu'un
de ses résultats est gratuit.

Nous soutenons enfin — et c'est ce qui nous paraît le plus utile — que
**l'attaque est bornée en quatre points identifiables**, et que sa vulnérabilité
principale est sa détectabilité.

Les travaux à venir sont ordonnés par coût croissant : le calcul des
commutateurs ; le test de la contrainte d'ordre sur données de sondage
québécoises ; le dépouillement des résultats par circonscription, qui seul
permettra de passer des parts de vote aux sièges ; la comparaison au modèle
classique ; et la mesure de la signature de cohérence sur corpus médiatique.

---

## Références

Les références marquées ⚑ ont été vérifiées à leur source les 27 et 28 août
2026 ; les autres proviennent du corpus canonique des disciplines concernées et
doivent être contrôlées avant publication.

[1] Kalla, J. et Broockman, D., « The Minimal Persuasive Effects of Campaign
Contact in General Elections », *American Political Science Review*, 2018.

[2] Benkler, Y., Faris, R. et Roberts, H., *Network Propaganda*, Oxford
University Press, 2018.

[3] Lazer, D. *et al.*, « The Science of Fake News », *Science*, 2018.

[4] ⚑ V-Dem Institute, *Democracy Report 2026 — Unraveling the Democratic
Era?*, 10ᵉ édition.

[5] Riker, W., *The Art of Political Manipulation*, Yale University Press,
1986.

[6] Bourdieu, P., *Les Règles de l'art*, Seuil, 1992 ; « La représentation
politique », *Actes de la recherche en sciences sociales*, 1981 ;
« L'opinion publique n'existe pas », 1973.

[7] Zaller, J., *The Nature and Origins of Mass Opinion*, Cambridge University
Press, 1992.

[8] Busemeyer, J. et Bruza, P., *Quantum Models of Cognition and Decision*,
Cambridge University Press, 2012.

[9] Haven, E. et Khrennikov, A., *Quantum Social Science*, Cambridge University
Press, 2013.

[10] Wang, Z. et Busemeyer, J., contrainte quantitative sur les effets d'ordre
des questions, *PNAS*, 2014.

[11] ⚑ Khrennikova, P., « Quantum like modelling of the non-separability of
voters' preferences in the U.S. political system », arXiv:1405.1029, 2014.

[12] ⚑ « An Application of the Theory of Open Quantum Systems to Model the
Dynamics of Party Governance in the US Political System », *International
Journal of Theoretical Physics*, 2013.

[13] ⚑ Dubois, F., « On quantum models for opinion and voting intention
polls », arXiv:2411.13593, 2024.

[14] ⚑ Khrennikov, A., « 'Social Laser': action amplification by stimulated
emission of social energy », *Philosophical Transactions of the Royal Society
A*, vol. 374, art. 20150094, 2016.

[15] ⚑ Khrennikov, A., « Social Laser Theory as a Natural Extension of
Quantum-Like Modeling », arXiv:2510.16012, 2025.

[16] ⚑ Alodjants, A. P., Bazhenov, A. Yu., Khrennikov, A. Yu. et Bukhanovsky,
A. V., « Mean-field theory of social laser », *Scientific Reports*, 2022,
DOI 10.1038/s41598-022-12327-w.

[17] Castellano, C., Fortunato, S. et Loreto, V., « Statistical physics of
social dynamics », *Reviews of Modern Physics*, vol. 81, 2009.

[18] ⚑ Starnini, M. *et al.*, « Opinion dynamics: Statistical physics and
beyond », arXiv:2507.11521, 2025-2026.

[19] Granovetter, M., « Threshold Models of Collective Behavior », *American
Journal of Sociology*, 1978.

[20] ⚑ Korbel, J., Dahdoul, R. et Thurner, S., « Empirical validation of the
polarization transition in a double-random field model of elections »,
arXiv:2510.00612, mars 2026.

[21] ⚑ Résultats du référendum québécois de 1995.

[22] ⚑ Résultats de l'élection générale québécoise de 2022.

[23] ⚑ Élections Québec et Assemblée nationale, nouvelle carte électorale à
127 circonscriptions, loi du 12 juin 2026.

[24] ⚑ Léger, intentions de vote, sondage du 21 au 24 août 2026, n = 1 010.

[25] ⚑ Qc125, projection de sièges, mise à jour du 6 août 2026.

[26] ⚑ Cour suprême du Canada, audience sur la *Loi sur la laïcité de l'État*,
23-27 mars 2026 ; jugement en délibéré.

[27] ⚑ Guichet-Emplois, effectif des journalistes au Québec.

[28] ⚑ Élections Québec, électeurs inscrits, 2026.

[29] Brehm, J., *A Theory of Psychological Reactance*, 1966 ; Friestad, M. et
Wright, P., « The Persuasion Knowledge Model », *Journal of Consumer
Research*, 1994.

[30] ⚑ Reuters Institute et Centre d'études sur les médias, Université Laval,
*Digital News Report* 2026.

[31] Broockman, D. et Kalla, J., « Durably reducing transphobia », *Science*,
2016.

[32] ⚑ Yan, G., Tsekenis, G., Barzel, B., Slotine, J.-J., Liu, Y.-Y. et
Barabási, A.-L., « Spectrum of controlling and observing complex networks »,
*Nature Physics*, vol. 11, 2015.

[33] ⚑ Cowan, N., Chastain, E., Vilhena, D., Freudenberg, J. et Bergstrom, C.,
« Nodal Dynamics, Not Degree Distributions, Determine the Structural
Controllability of Complex Networks », *PLOS ONE*, 2012.

---

## Annexe — provenance des documents du dépôt

Ce rapport synthétise vingt-deux fondations (FND) et six analyses (ANL)
produites entre le 27 et le 28 août 2026, ainsi qu'un plan de codage (PLN-001)
et trois documents d'architecture. Le détail des vérifications, les marques de
provenance paramètre par paramètre, et les limites de chaque pièce y figurent.
Les affirmations chiffrées de la section 5 sont toutes rattachées à une source
publique vérifiée à sa date.
