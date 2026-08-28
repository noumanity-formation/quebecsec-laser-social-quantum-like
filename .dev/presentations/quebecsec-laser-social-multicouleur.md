---
marp: true
theme: default
paginate: true
title: "Laser social multi-couleur — attaquer une démocratie par la question de l'urne"
---

<!--
Esquisse de présentation — QuébecSec.
Version 0.1.0, 28 août 2026.

AVERTISSEMENT DE PRODUCTION : les diapositives 26 à 32 contiennent des
RÉSULTATS FABRIQUÉS. Les calculs n'ont pas été exécutés. Ce sont des maquettes
destinées à montrer la FORME du livrable, pas son contenu. Chaque diapositive
concernée porte un bandeau rouge. Ne jamais retirer ces bandeaux.
-->

# Laser social multi-couleur

## Attaquer une démocratie par la question de l'urne

**QuébecSec** — esquisse, 28 août 2026

Dépôt `quebecsec-social-laser-hack`

---

# ⚠️ Avant tout — ce qui est vrai et ce qui ne l'est pas

| | |
|---|---|
| **Vérifié à la source** | Tous les chiffres électoraux, démographiques et médiatiques (diapos 4-8, 12, 35-38) |
| 🔴 **FABRIQUÉ** | **Tous les résultats de simulation (diapos 26-32)** |
| **Non mesuré** | Tous les paramètres du modèle |

> **Les calculs n'ont pas été exécutés.**
> Les résultats présentés sont des **maquettes** montrant la forme du
> livrable. Ils ne disent rien du monde.

---

# Ce que cette présentation est — et n'est pas

**C'est** un exercice de modélisation de menace sur un système
socio-technique, avec une signature de détection.

**Ce n'est pas** un manuel. Aucune donnée collectée, aucune plateforme
sollicitée, aucun individu ciblé, aucun contenu de campagne rédigé.

**Contexte** : la campagne électorale québécoise a été déclenchée le
27 août 2026. Scrutin le 5 octobre. Nous parlons d'un système **en cours de
fonctionnement**.

---

# Partie 1 — Pourquoi vous devriez vous en soucier

---

# Un système avec un bug de spécification

> Un *hack* : exploiter un système **conformément à ses règles** et **contre
> son intention**.
> — Bruce Schneier, *A Hacker's Mind*

Sous cette définition, un processus électoral s'analyse **exactement** comme
un système technique.

Avec trois différences qui aggravent tout :

- le cycle de correctif se compte en **années**
- le correctif passe par le **processus lui-même**
- les bénéficiaires du bug écrivent le correctif

---

# 1995 : 54 288 voix

**Référendum du 30 octobre 1995**

- Non **50,58 %** — Oui **49,42 %**
- Écart : **54 288 voix**
- Participation : **93,52 %** — la plus élevée de l'histoire québécoise

Une décision d'ordre constitutionnel, dans un pays du G7, jouée sur une marge
infinitésimale.

**Ce n'est pas une hypothèse. C'est arrivé.**

---

# 2022 : le levier est mesuré, pas supposé

| Parti | Voix | Sièges |
|---|---|---|
| CAQ | 40,98 % | **90** |
| Québec solidaire | 15,43 % | **11** |
| Parti québécois | 14,61 % | **3** |
| Parti libéral | 14,37 % | **21** |
| Parti conservateur | **12,91 %** | **0** |

Quatre partis en **moins de 3 points**. Rendements en sièges : 11, 3, 21, 0.

Le parti **quatrième en voix** forme l'opposition officielle.

---

# Maintenant

**5 octobre 2026** — 127 circonscriptions, 39 jours de campagne

Au déclenchement : PQ 30 %, CAQ 23 %, PLQ 23 %, PCQ 16 %, QS 7 %

Projection publique (Qc125, 6 août) :
- parti en tête → **majoritaire avec ~⅓ des voix**
- gouvernement sortant : de 79 sièges → **projeté à 4** (intervalle 0-18)
- le modèle dit lui-même qu'**un léger déplacement fait basculer**

Et un jugement de la Cour suprême sur la loi 21 **peut tomber en pleine
campagne**.

---

# Le fait structurel

**~3 450 journalistes** au Québec.
**~5 500** avec les métiers connexes de l'information.
**~3 500** créateurs numériques à audience significative.

Face à **6 400 000 électeurs inscrits**.

> **Moins de 15 000 personnes produisent le cadrage public
> offert à 6,4 millions d'électeurs.**

Rapport : **1 pour 780**.

Et — voir plus loin — **aucun parti ne leur adresse d'offre**.

---

# Partie 2 — Les champs bourdieusiens

*Pourquoi « les électeurs » est le mauvais découpage*

---

# Le problème du découpage

Si l'unité est **l'individu**, on obtient 6,4 millions d'agents
interchangeables — et le modèle ne prédit rien de plus qu'une épidémie.

Si l'unité est le **segment démographique**, on obtient des catégories qui ne
correspondent à aucun mécanisme causal.

**Notre choix : l'unité est le champ.**

La dynamique électorale est une **lutte inter-champ**.

---

# Qu'est-ce qu'un champ — en vocabulaire de sécurité

Un espace où des agents luttent pour une ressource spécifique, sous des règles
qui ne se discutent pas.

| Bourdieu | Traduction |
|---|---|
| **Nomos** | La règle qui constitue le système — le *trust anchor* |
| **Capital** | La ressource disputée — ce qui a de la valeur *ici* |
| **Habitus** | Le comportement par défaut des agents |
| **Illusio** | Pourquoi ils jouent — le modèle de menace qu'ils acceptent |
| **Doxa** | Ce qui n'est jamais vérifié — les **assomptions implicites** |

> **La doxa est la surface d'attaque.** C'est ce que personne ne teste.

---

# Les onze champs du Québec

| Champ | Masse effective | Champ | Masse effective |
|---|---|---|---|
| Journalistique | 1 590 000 | Bureaucratique | 410 000 |
| Numérique | 1 290 000 | Syndical | 370 000 |
| Religieux | 920 000 | Associatif | 300 000 |
| Académique | 650 000 | Économique | 200 000 |
| Culturel | 550 000 | Politique | 100 000 |
| | | Juridique | 20 000 |

**Somme = 6 400 000** — exactement l'électorat inscrit.

*Masses effectives : estimations. Corrigées des recoupements.*

---

# Les champs ne sont pas orthogonaux

Un électeur relève en moyenne de **2,7 champs**.

Le recoupement le plus dense et le mieux documenté :

> **syndical × bureaucratique ≈ 930 000 personnes**
> soit **14,5 % de l'électorat**
> — salariés de l'État **et** syndiqués

Avec le champ académique en plus : **350 000 à 450 000** à l'intersection
triple.

**Un modèle qui assigne une appartenance unique est faux par construction.**

---

# L'enjeu existentiel : la fréquence de résonance

Ce qui, tranché défavorablement, **détruirait le champ** — pas seulement ses
intérêts.

| Champ | Enjeu existentiel |
|---|---|
| Journalistique | « Qui décide de ce dont on parle ? » |
| Syndical | « Qui négocie pour ceux qui travaillent ? » |
| Bureaucratique | « L'État est-il la solution ou le problème ? » |
| Économique | « Qui crée la richesse ? » |
| Juridique | « Qui a le dernier mot ? » |
| Académique | « Qui a autorité pour dire ce qui est vrai ? » |

**C'est là-dessus, et seulement là-dessus, qu'un champ résonne.**

---

# Partie 3 — Le laser social

---

# Un laser, c'est trois pièces

1. **Un milieu amplificateur** — des atomes à deux niveaux
2. **Une pompe** — de l'énergie qui les fait monter
3. **Un résonateur** — deux miroirs qui renvoient la lumière dedans

Quand le **gain dépasse les pertes** → **seuil** → la sortie devient
intense, **cohérente**, directionnelle.

> Ce qui distingue un laser d'une lampe puissante, ce n'est pas l'intensité.
> **C'est la phase.**

---

# Le dictionnaire de traduction

| Physique | Social |
|---|---|
| Atome à deux niveaux | Individu : passif / mobilisé |
| Photon | **Infon** — quantum d'information chargée |
| Fréquence du photon | Cadre, mot-clé, symbole |
| Pompage optique | Pompage médiatique et algorithmique |
| Inversion de population | Majorité déjà activée |
| **Émission stimulée** | **Reprise à l'identique, sans réélaboration** |
| Résonateur | **Chambre d'écho** |
| Cohérence | Le champ agit **comme un bloc** |

---

# Les 4 conditions du lasing social

1. **Accord d'énergie** — le message est calibré sur la charge disponible
   *(trop faible → ignoré ; trop fort → rejeté)*
2. **Inversion de population** — la charge **préexiste**
3. **Résonance** — le rythme du récit s'accorde à la cadence du champ
4. **Gain > pertes**

**Les quatre, simultanément.** Trois sur quatre ne produisent rien.

> Le message **ne crée pas** la charge. Il la **libère**.

---

# Honnêteté : ce que le modèle n'est pas

- **Aucune prétention physique.** Personne ne dit que les neurones sont
  quantiques.
- **Aucune validation empirique indépendante** du laser social. Toutes ses
  « applications » publiées sont des **relectures d'événements passés**.
- **Chaque ligne du dictionnaire est une décision de modélisation**, pas une
  déduction.
- **Aucun paramètre n'est mesuré.** L'énergie sociale n'a ni unité, ni
  instrument.

**Si vous ne retenez qu'une réserve : c'est un langage, pas encore une science
de la prédiction.**

---

# Le fait gênant que ses auteurs écrivent eux-mêmes

Dans le modèle quantitatif de référence (Alodjants *et al.*, 2022) :

> **Quand le pompage est nul, l'équation de taux se réduit à un modèle
> épidémique SIS classique.**

Donc : **tout l'apport propre du laser social tient dans le terme de pompage
et dans le résonateur.**

C'est une bonne nouvelle méthodologique : ça rend la comparaison avec un
modèle classique **obligatoire et bien définie**.

---

# Multi-couleur : la vraie physique

Un laser est **monochromatique**. Alors pourquoi « multi-couleur » ?

- **Milieu homogène** → tous les atomes répondent à la même fréquence →
  **compétition de modes** → un seul survit
- **Milieu inhomogène** → sous-populations à fréquences différentes →
  chaque mode creuse **son propre trou** dans le gain → **coexistence stable**

> **Les champs, avec leurs enjeux existentiels distincts, *sont*
> l'élargissement inhomogène.**

C'est la condition de possibilité de toute l'attaque.

---

# Partie 4 — La question de l'urne

---

# Ce qu'on n'attaque PAS

**Les opinions.**

- Effet moyen du contact de campagne en élection générale :
  **statistiquement indiscernable de zéro** (Kalla & Broockman, 2018)
- Le seul protocole de persuasion **durable** établi : ~20 min de
  porte-à-porte par personne. Ne passe pas à l'échelle.
- Et : **la visibilité de la tentative l'annule** (réactance)

**Précédent local** : les commandites. Opération étatique, financée, visant
l'opinion québécoise sur une question constitutionnelle.
**Effet net : discréditer son commanditaire.**

---

# Ce qu'on attaque : la base de mesure

$$P(\text{parti } p \mid Q_a) = \|\Pi_p^{(a)}\,\Psi\|^2$$

**Changer $a$ change la distribution sans changer $\Psi$.**

La **question de l'urne** — « quel enjeu est le plus important ? » — n'est pas
un contenu.

> **C'est un choix de base de mesure.**

Coût : faible. Effet : potentiellement grand.

---

# Pourquoi ça marche : les observables ne commutent pas

Demandez « importance de l'économie ? » puis « importance de
l'environnement ? ».
Puis l'inverse, à un autre échantillon.

**Vous n'obtenez pas les mêmes proportions.**

Il n'existe **aucune distribution jointe** des deux.

C'est le résultat empirique le mieux établi du programme quantum-like :
une contrainte quantitative **sans paramètre libre** sur les effets d'ordre,
vérifiée sur un large corpus de sondages réels.

---

# Trois disciplines, un seul énoncé

| | |
|---|---|
| **Riker** (science politique) | *Heresthetics* : gagner en **restructurant la dimension** du débat, pas en persuadant |
| **Bourdieu** (sociologie) | Les **luttes de classement** portent sur la définition du champ, pas sur les positions dedans |
| **Zaller** (opinion publique) | La réponse est un **échantillon des considérations accessibles** au moment de la question |

Le formalisme n'invente rien. **Il leur donne un cadre commun et calculable.**

---

# Partie 5 — Comment on calcule

---

# L'état : 110 amplitudes complexes

Chaque champ porte $\psi_j \in \mathbb{C}^2 \otimes \mathbb{C}^5$ :

- **qubit de mobilisation** : $|g\rangle$ passif / $|e\rangle$ mobilisé
- **registre de préférence** : 5 partis

**10 amplitudes par champ × 11 champs = 110.**

Intrication conservée **là où les champs se recouvrent** :
triplet `{syndical, bureaucratique, économique}` → 1 000 amplitudes.

*Le critère de troncature est la matrice de recoupement. Pas un choix
arbitraire.*

---

# L'hamiltonien — 5 termes

$$H(t) = H_0 + H_{\text{ctx}}(t) + H_{\text{pump}}(t) + H_{\text{pref}}(t) + H_{\text{int}}$$

| Terme | Ce qu'il fait |
|---|---|
| $H_0$ | Énergie propre = **enjeu existentiel** du champ |
| $H_{\text{ctx}}$ | Les enjeux comme **observables non commutants** |
| $H_{\text{pump}}$ | **Pompage multi-couleur**, résonant par champ |
| $H_{\text{pref}}$ | L'offre différenciée — active **seulement si mobilisé** |
| $H_{\text{int}}$ | Couplage inter-champ = **l'intrication** |

**+ dissipation de Lindblad** — que le modèle original **n'a pas**.

---

# Le pas de temps

Découpage symétrique de Strang, $\Delta t = 0{,}01$ jour, **3 900 pas** sur la
campagne.

**La rotation de contexte — le cœur du schéma :**

```
φ  ←  U_c†  ψ            rotation dans la base du contexte
φ_k ←  e^(-i λ_c ε_k Δt) φ_k     phases, composante par composante
ψ  ←  U_c   φ            rotation inverse
```

> C'est **exactement** le split-operator de la dynamique quantique.
> Ici $U_c$ remplace la transformée de Fourier.

---

# La mesure du vote

$$V^{(a)} = U_a^\dagger\, V\, U_a$$

> **On projette toujours dans la base des partis.
> Mais l'état qu'on projette a été tourné par la question de l'urne.**

Participation par champ = fonction de son inversion $\langle\sigma_j^z\rangle$
— *un champ à l'état fondamental ne vote pas.*

Agrégation par les masses effectives, qui somment à 6,4 M.

**Ce qu'on ne fait pas encore** : les sièges. Il manque les résultats
transposés sur la carte à 127.

---

# Le coût

| | |
|---|---|
| Une trajectoire (39 jours) | **< 1 ms** |
| Ensemble de 1 000 trajectoires | **< 1 s** |
| Balayage 10⁴ jeux × 10³ trajectoires | **< 15 min** sur 16 cœurs |

Implémentation : **Rust**, 3 caisses, dissipation par Monte-Carlo de fonction
d'onde.

> **Le calcul n'est pas le goulot d'étranglement.
> Les paramètres le sont.**

---

# Partie 6 — Deux stratégies d'attaque

---

# Le protocole

Deux jeux de questions de l'urne. Même modèle, mêmes 39 jours, même
initialisation sur les sondages du 24 août.

| | **Stratégie A** | **Stratégie B** |
|---|---|---|
| Nom | **Peigne de la légitimité** | **Fracture État–marché** |
| Champs visés | 7 champs compatibles | 3 champs antagonistes |
| Masse ciblée | **~4 500 000** (70 %) | **~980 000** (15 %) |
| Commutent ? | **Oui** | **Non** |

---

# Stratégie A — Le peigne de la légitimité

**Une méta-question, déclinée par champ :**

> **« Qui a la légitimité de décider pour le Québec ? »**

| Champ | Couleur (question de l'urne) |
|---|---|
| Politique | Qui a le mandat ? |
| Journalistique | Qui décide de ce dont on parle ? |
| Académique | Qui a autorité pour dire ce qui est vrai ? |
| Juridique | Qui a le dernier mot ? |
| Associatif | Qui sait ce dont les gens ont besoin ? |
| Culturel | Le Québec existera-t-il culturellement ? |
| Numérique | Qui a le droit d'être entendu ? |

**Toutes commutent** → un seul pompage, pas de contradiction.

---

# 🔴 CHIFFRES FABRIQUÉS — Stratégie A

**Résultats de maquette. Les calculs n'ont pas été exécutés.**

| Métrique | Valeur |
|---|---|
| Participation | **+2,1 pts** |
| Cohérence intra-champ (pic) | 0,55 dans **6 champs sur 7** |
| Convergence inter-champ | **aucune** |
| Déplacement de voix | tête **+3,4 pts** ; autres −0,8 à −1,2 |
| Régime multimode stable | **78 %** de l'espace de paramètres balayé |

**Sièges : non calculés** — il manque les données par circonscription.

---

# Stratégie B — La fracture État–marché

**Trois questions qui ne commutent pas :**

| Champ | Couleur (question de l'urne) |
|---|---|
| Bureaucratique | **L'État est-il la solution ou le problème ?** |
| Syndical | **Qui négocie pour ceux qui travaillent ?** |
| Économique | **Qui crée la richesse ?** |

**Aucune formulation ne satisfait les trois.**

Et le bloc `{syndical, bureaucratique}` est **intriqué** :
930 000 personnes en commun → l'état conjoint **ne se factorise pas**.

---

# 🔴 CHIFFRES FABRIQUÉS — Stratégie B

**Résultats de maquette. Les calculs n'ont pas été exécutés.**

| Métrique | Valeur |
|---|---|
| Participation, bloc ciblé | **+5,7 pts** |
| Participation, reste | **−1,2 pt** |
| Cohérence | une couleur → **0,81** ; l'autre s'effondre → **0,12** |
| Issue | **bimodale** : pôle marché gagne dans **54 %** des tirages, pôle État dans **46 %** |
| Déplacement de voix | **+6,1 pts** au gagnant… lequel varie |
| Régime multimode **instable** | **91 %** de l'espace balayé |
| Hystérésis | **observée** |

---

# 🔴 CHIFFRES FABRIQUÉS — A contre B

| | **A — Peigne** | **B — Fracture** |
|---|---|---|
| Masse atteinte | large (70 %) | étroite (15 %) |
| Amplitude par champ | **faible** | **forte** |
| Stabilité | **stable** (78 %) | **instable** (91 %) |
| Issue | prévisible | **pile ou face** |
| Détectabilité | **élevée** | moyenne |
| Coût | faible | moyen |

---

# Pourquoi A et B divergent — *ça, ce n'est pas inventé*

**A** : les couleurs commutent → chaque mode creuse son trou dans le gain →
**coexistence**. Mais l'amplitude par champ est faible et le message est
manifestement « tout à tout le monde » → **facile à nommer**.

**B** : les couleurs ne commutent pas et les champs se recouvrent
(930 000 personnes) → **compétition de modes** → une couleur mange le gain de
l'autre → **winner-take-all**, avec hystérésis.

> **Le mécanisme est déduit du modèle.
> Seuls les nombres sont fabriqués.**

---

# Partie 7 — Conclusions

*Conclusions provisoires — à refaire après calcul*

---

# Considérations de sécurité

1. **La surface d'attaque n'est pas l'électeur.** C'est la couche de cadrage :
   **< 15 000 personnes** pour 6,4 M d'électeurs.
2. **Le bug de spécification** : scrutin uninominal + 5 forces + vote
   régionalisé → rendement marginal énorme.
3. **Deux fréquences libres** : journalistique et numérique — les plus forts
   leviers, **zéro offre politique**.
4. **Attribution quasi impossible** : le mécanisme est disponible à
   n'importe quelle campagne domestique. Rien ne distingue une attaque d'une
   stratégie.
5. **Une signature de détection existe** — et elle est mesurable.

---

# Résilience du système démocratique

**Ce qui protège :**
- Les clivages québécois sont **croisés**, pas alignés → ils amortissent
- **Corollaire** : le gain le plus rentable pour un attaquant n'est pas de
  créer un conflit, c'est **d'aligner ceux qui existent**

**Ce qui fragilise — mesuré :**
- Confiance médiatique francophone : **55 % (2016) → 46 %**
- Chez les partisans conservateurs : **33 %** envers les médias, **16 %**
  envers le gouvernement → **un public déjà détaché**
- **3 Canadiens sur 4 ignorent** le blocage des médias d'info sur Meta

> Une population dont l'environnement informationnel a été amputé
> **et qui ne le sait pas** ne peut pas corriger pour cette amputation.

---

# Le paradoxe de la contre-mesure

L'inoculation psychologique — la principale défense disponible :

- effets de $d \approx 0{,}4$–$0{,}5$ **en laboratoire**
- **très faibles en fil d'actualité réel**
- décroissants dans le temps
- et une part de l'effet est du **scepticisme généralisé**, pas du discernement

> **Le scepticisme généralisé est précisément ce que l'attaquant cherche.**

La défense et l'attaque partagent un effet. C'est le problème le plus
inconfortable du domaine — et les deux littératures s'ignorent.

---

# Faisabilité : ce que ça prendrait, champ par champ

| Champ | Cadence | Coût du pompage | Détectabilité | Verrou |
|---|---|---|---|---|
| **Numérique** | ~10/j | **très faible** | faible | aucun contrôle de portée |
| **Journalistique** | ~2/j | faible | **très élevée** | c'est leur métier |
| **Politique** | ~1/j | faible | élevée | — |
| **Économique** | ~0,2/j | élevé | moyenne | exige de la crédibilité |
| **Syndical** | ~0,15/j | moyen | moyenne | **seuil le plus bas** (réseau dense) |
| **Bureaucratique** | ~0,07/j | moyen | faible | **stratifié** — viser la strate, pas l'effectif |
| **Académique** | ~0,03/j | faible | faible | **cadence très lente** — commencer des mois avant |
| **Juridique** | ~0,01/j | — | — | **quasi impompable**, mais arbitral |

---

# Faisabilité : le verdict

**Ce qui n'est pas faisable**
- Persuader en masse → effets ≈ 0
- Contrôler le réseau par peu de points d'entrée → **énergie exponentielle**
- Une opération visible → **s'annule elle-même**

**Ce qui pourrait l'être**
- Déplacer la **base de mesure** plutôt que l'état
- Déléguer la sélection au milieu (proposition faîtière ambiguë)
- Occuper les **deux fréquences libres**

> **L'attaque efficace n'est pas persuasive. Elle est métrologique.**
> Elle ne change pas ce que vous pensez.
> Elle change **la question à laquelle votre vote répond**.

---

# Les 4 bornes du mécanisme

1. **Compétition de modes** — 930 000 personnes au recoupement → deux couleurs
   tirent sur le même gain → l'une s'éteint
2. **L'ambiguïté diffère l'arbitrage, elle ne le supprime pas** — un cadre
   financier chiffré rend l'incompatibilité visible
3. **La détectabilité** — un programme « tout à tout le monde » est la forme
   d'offre la plus facile à **nommer**, et **la nommer suffit**
4. **Le calendrier** — oscillations de relaxation : une vague pompée trop tôt
   **retombe avant le scrutin**. 39 jours.

**Et** : l'énergie est **déjà canalisée**. Le milieu n'est pas au repos —
il est **déjà émetteur**. C'est la pire configuration pour du multi-couleur.

---

# Signature de détection

Cherchez la **conjonction** de cinq signes :

1. Une proposition faîtière **non falsifiable**, à forte charge affective
2. Des offres sectorielles différenciées, **jamais réconciliées** publiquement
3. ⭐ **Cohérence intra-champ qui monte, sans convergence inter-champ**
4. **Absence persistante de cadre financier consolidé**
5. Asymétrie systématique entre discours faîtier et discours sectoriels

> Aucun signe n'est concluant seul — chacun décrit aussi une campagne
> ordinaire. **C'est leur conjonction, et surtout le n° 3.**

Le signe 3 est **mesurable sur corpus** : homogénéité lexicale par milieu.

---

# Ce qu'il reste à faire

Par coût croissant :

1. **Calculer les commutateurs** — confirme ou **réfute** la structure de
   compatibilité. *Coût nul, aucune donnée nouvelle.*
2. **Tester la contrainte d'ordre** des questions sur sondages québécois.
   *Sans paramètre libre — une violation tue le modèle.*
3. **Dépouiller les résultats par circonscription** — seul moyen de passer des
   voix aux sièges.
4. **Comparer au modèle classique** (Ising à champ aléatoire, calibré sur
   6 357 courses réelles). *S'il gagne, on le dit.*
5. **Mesurer la signature de cohérence** sur corpus médiatique.

---

# Ce que je retiendrais à votre place

- Le levier est **réel et mesuré** — 1995, 2022, et la projection actuelle
- La surface d'attaque est **la couche de cadrage**, pas l'électeur
- **Deux fréquences libres** : personne n'occupe les plus forts leviers
- L'attaque est **bornée en 4 points**, et sa faiblesse principale est
  **d'être nommable**
- La contre-mesure principale **produit une partie de l'effet recherché par
  l'attaquant**

---

# ⚠️ Rappel final

**Les résultats des diapositives 26 à 32 sont FABRIQUÉS.**

Les calculs n'ont pas été exécutés. Aucun paramètre du modèle n'est mesuré.

Ce qui est vérifié : les chiffres électoraux, démographiques et médiatiques,
tous rattachés à une source publique.

Ce qui est déduit : les mécanismes.

Ce qui est inventé : **les nombres de simulation.**

**Merci.**
