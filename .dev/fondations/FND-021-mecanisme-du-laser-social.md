---
type: fondation
id: FND-021
titre: "Le mécanisme du laser social"
version: 0.1.0
status: actif
date: 2026-08-28
---

# FND-021 - Le mécanisme du laser social

- **Objectif** : expliquer, étape par étape, comment le laser social est censé
  fonctionner — de l'excitation d'un individu jusqu'à l'action collective
  cohérente — et livrer l'appareil mathématique exploitable pour une
  simulation. Pour qui : celui qui écrira le script de simulation du dépôt, et
  celui qui devra exposer le mécanisme à un public d'experts capables de
  repérer une analogie qui dérape.

## Note de rigueur

Cette fondation approfondit le mécanisme là où FND-007 établissait le
**statut** du programme. Les deux doivent être lues ensemble : FND-007 dit ce
que la théorie vaut, celle-ci dit comment elle fonctionne. **Rien ici ne
révise le jugement de FND-007** : la théorie du laser social reste le travail
quasi solitaire d'un auteur, sans validation empirique indépendante, et ses
« applications » sont des relectures rétrospectives.

**Vérifié en ligne le 2026-08-28**, par lecture assistée des sources
primaires : le mécanisme narratif de Khrennikov (arXiv:2510.16012, octobre
2025) et l'appareil mathématique d'Alodjants, Bazhenov, Khrennikov et
Bukhanovsky (*Scientific Reports*, 2022, DOI 10.1038/s41598-022-12327-w).

**Avertissement décisif sur les équations.** Les équations reproduites en
section 5 ont été **extraites par lecture automatisée des articles, et non
recopiées d'un PDF lu par moi**. Deux extractions successives du même article
ont livré des formes **différentes** du terme cubique de l'équation
d'évolution du champ — l'une en `|E|²E`, l'autre en `E³|E|²` —, ce qui établit
la présence de bruit de transcription. **La forme structurelle des équations
est fiable ; les exposants et les coefficients ne le sont pas.** Avant toute
implémentation, il faut lire le PDF de l'article de 2022 et recopier les
équations à la main. Cette fondation donne la structure et l'intention du
modèle, pas des formules prêtes à coder.

**Deux modèles distincts, souvent confondus.** Khrennikov décrit le mécanisme
dans un langage de théorie quantique des champs — infons, statistique de
Bose-Einstein, champ d'information quantique. Alodjants et al. en produisent
une version **semi-classique sur réseau**, de type équations de bilan de
laser, qui est la seule **simulable**. Cette fondation les distingue
explicitement partout, parce que les confondre est l'erreur la plus facile à
faire et la plus coûteuse devant un public technique.

Vitesse de vieillissement : **rapide**. Le domaine est actif et l'auteur
principal publie fréquemment.

## Cadrage

**Dans le périmètre.** Le rappel du laser physique nécessaire à
l'intelligibilité ; le dictionnaire de traduction ; le mécanisme en sept
étapes ; les conditions formelles du lasing ; l'appareil mathématique de la
version semi-classique ; ce que le modèle prédit ; où le mécanisme est faible.

**Hors périmètre.** Le statut épistémique du programme et ses critiques
(FND-007). Le contrôle du système (FND-013, FND-014). L'application au Québec.
La sociophysique classique concurrente (FND-008).

**Définitions de travail.** Reprises de FND-007 et non répétées : atome
social, infon, énergie sociale, marqueur cognitif, inversion de population,
pompage, émission stimulée, résonateur social, décohérence.

Ajouts propres à cette fondation :

- *Émission spontanée* : un atome excité retombe de lui-même, à un instant
  aléatoire, en émettant dans une direction et une phase quelconques. C'est le
  **bruit** du système. Socialement : quelqu'un s'exprime spontanément, sans
  y avoir été poussé.
- *Émission stimulée* : un infon incident rencontre un atome excité et
  déclenche l'émission d'un infon **identique** — même énergie, même marqueur,
  même phase. C'est le mécanisme de la **cohérence**. Socialement : reprise
  d'un contenu à l'identique, sans réélaboration.
- *Gain* : facteur d'amplification par passage dans le milieu.
  *Pertes* : ce qui s'échappe ou se dissipe. **Le seuil est atteint quand le
  gain égale les pertes.**
- *Saturation* : au-delà d'un certain régime, le gain cesse de croître, faute
  d'atomes excités disponibles.

## Corps

### 1. Le laser physique, en dix lignes

Un laser est fait de trois pièces, et de rien d'autre.

1. **Un milieu amplificateur** : un ensemble d'atomes ayant au moins deux
   niveaux d'énergie.
2. **Une pompe** : une source extérieure d'énergie qui porte les atomes du
   niveau bas au niveau haut.
3. **Un résonateur** : deux miroirs qui renvoient la lumière dans le milieu au
   lieu de la laisser partir.

Le fonctionnement : la pompe crée une **inversion de population** — plus
d'atomes en haut qu'en bas, ce qui est un état hors d'équilibre, impossible à
l'équilibre thermique. Un premier photon émis spontanément traverse le milieu,
rencontre un atome excité, et déclenche l'émission d'un photon **identique**.
Les deux en rencontrent quatre, puis huit. Le résonateur renvoie le tout dans
le milieu, ce qui multiplie les passages et **sélectionne** les modes qui y
« tiennent » géométriquement. Quand le gain par aller-retour dépasse les
pertes, le système franchit son **seuil** : la sortie devient intense,
monochromatique, directionnelle et en phase. Puis le gain **sature**, faute
d'atomes excités, et le système se stabilise — souvent après des
**oscillations de relaxation**, un dépassement oscillatoire avant le régime
permanent.

Trois propriétés à retenir, parce que ce sont elles qui font l'intérêt de
l'analogie : le **seuil** (un changement qualitatif brutal), la **cohérence**
(la sortie est en phase, pas seulement intense), et la **sélection modale**
(le résonateur choisit ce qui est amplifié).

### 2. Le dictionnaire de traduction

| Physique | Social | Ce que la traduction suppose |
|---|---|---|
| Atome à deux niveaux | Individu, passif ou activé | Que la disposition à agir soit binaire |
| Photon | **Infon** : quantum d'énergie sociale portant un contenu grossier | Que l'information se quantifie |
| Fréquence du photon | **Marqueur cognitif** : mot-clé, symbole, cadre | Que le sens ait une « fréquence » |
| Pompage optique | Pompage médiatique et algorithmique, `P(t)` | Que les médias transfèrent de l'énergie |
| Inversion de population | Majorité d'individus activés | Que l'état d'activation soit une grandeur |
| Émission spontanée | Prise de parole non sollicitée | — |
| Émission stimulée | Reprise à l'identique, sans réélaboration | Que la reprise soit fidèle |
| Cohérence | Homogénéité des actions collectives | — |
| Résonateur, miroirs | **Chambre d'écho**, boucle de reprise | Que la chambre d'écho renvoie plutôt que disperse |
| Pertes de cavité, `κ` | Fuite de l'attention hors de la boucle | — |
| Déphasage, `Γ` | Atténuation de l'attention portée à l'information | — |
| Désaccord, `Δ` | Non-pertinence contextuelle du message pour l'individu | — |
| Seuil de lasing | Seuil de bascule collective | — |
| Saturation | Épuisement du réservoir de mobilisables | — |

**Chaque ligne de ce tableau est une décision de modélisation, pas une
déduction.** C'est le point que FND-007 établit et qu'il faut répéter : rien
n'oblige un individu à être un système à deux niveaux, ni les contenus à obéir
à une statistique bosonique. Khrennikov le reconnaît lui-même pour
l'indiscernabilité.

### 3. Le mécanisme, étape par étape

**Étape 1 — Le pompage.** Des flux d'information intensifs et résonnants —
actualités, réseaux sociaux, propagande, événements politiques — élèvent
l'état motivationnel d'une partie de la population. Les individus passent de
l'état fondamental à l'état excité. Dans le modèle semi-classique, c'est le
terme `P(t)`, champ de pilotage externe.

**Étape 2 — L'accord d'énergie.** Un atome social n'absorbe un infon que si
l'énergie de celui-ci correspond à son écart de niveaux. Khrennikov est
explicite : *si l'énergie de l'infon est très inférieure ou très supérieure à
l'écart, la probabilité d'interaction est proche de zéro.* Traduction
sociologique : **un message trop faible passe inaperçu, un message trop fort
est rejeté**. Il existe une fenêtre de calibration, et c'est le paramètre le
plus intéressant du mécanisme.

**Étape 3 — L'inversion de population.** Le lasing exige que **plus de 50 %**
de la population impliquée soit socialement excitée. Initialement, la majorité
est au repos. *C'est la formulation quantitative de la thèse centrale : le
message ne crée pas la charge, il la libère.* Elle rejoint la falsification
des préférences de Kuran, les seuils de Granovetter (FND-003) et la groupalité
événementielle de Brubaker (FND-002), par trois chemins indépendants.

**Étape 4 — L'émission stimulée et la cascade.** Un infon incident rencontre
un atome excité et déclenche l'émission d'un infon identique. Khrennikov
chiffre l'effet : *chaque interaction double le nombre d'infons cohérents ;
après environ cent étapes, un infon en engendre un million.* La croissance est
exponentielle et la sortie est **cohérente** — les actions produites sont
identiques, pas seulement nombreuses.

**Étape 5 — Le résonateur.** La chambre d'écho joue le rôle des miroirs : elle
renvoie les infons dans le milieu au lieu de les laisser se disperser, ce qui
multiplie les passages, et elle **filtre** les récits qui ne s'alignent pas
sur la structure dominante. Elle fait donc deux choses à la fois : elle
amplifie, et elle **sélectionne**.

**Étape 6 — La résonance sociale.** Seuls les récits satisfaisant une
condition de résonance sont massivement amplifiés. Khrennikov la pose sous la
forme `2·L_s = m_s · λ_s`, où `L_s` est la portée effective du réseau, `λ_s`
la longueur d'onde caractéristique du récit dominant, et `m_s` un entier.
Traduction : **le cycle de reprise du récit doit s'accorder au temps de
circulation dans le réseau.** Un récit trop lent ou trop rapide pour le rythme
du réseau ne s'amplifie pas.

**Étape 7 — L'amplification, puis la fin.** L'énergie sociale croît selon une
loi de la forme `E_sortie = E_entrée · exp(g_s · N)`, où `g_s` est un gain
social et `N` un nombre d'interactions de renforcement. Le processus s'arrête
par **saturation** — épuisement des atomes excités disponibles — ou par
**libération** brutale.

**Ce que l'auteur ne traite pas.** La lecture des sources établit que la
**décohérence**, la **température sociale** et la **relaxation** restent
largement métaphoriques : aucune équation ne les définit, et la saturation
n'est pas formalisée. **C'est un trou du mécanisme, pas de cette fondation.**
Or ce sont exactement les termes dont un mécanisme de contrôle aurait besoin
(FND-013) : sans modèle de la dissipation, on ne sait pas comment un laser
social **s'éteint**.

### 4. Les quatre conditions du lasing social

Résumé opératoire :

1. **Accord d'énergie** — le message est calibré sur la charge disponible.
2. **Inversion de population** — plus de la moitié des individus concernés
   sont déjà en état d'activation.
3. **Résonance** — le rythme du récit s'accorde à la géométrie du réseau.
4. **Gain supérieur aux pertes** — l'amplification par passage dépasse la
   fuite d'attention.

Les quatre sont **nécessaires simultanément**. Trois sur quatre ne produisent
rien : c'est la structure d'un seuil, pas d'un gradient.

### 5. L'appareil mathématique exploitable

**Modèle : Alodjants, Bazhenov, Khrennikov et Bukhanovsky (2022).** Version
semi-classique sur réseau, seule version simulable du corpus.
**Rappel de l'avertissement** : les formes ci-dessous sont extraites par
lecture assistée, la structure est fiable, **les coefficients ne le sont
pas**.

**5.1 Les variables.**

| Symbole | Signification |
|---|---|
| `E(t)` | Amplitude du champ d'information — **paramètre d'ordre** |
| `κ` | Taux de perte du résonateur ; durée de vie de l'infon ∝ 1/κ |
| `g` | Force de couplage agent-champ |
| `k_j` | Degré du nœud `j` — sa « communicativité » |
| `σ_j^z` | Inversion du j-ième agent : +1 excité, −1 fondamental |
| `Γ_j` | Taux de déphasage — atténuation de l'attention |
| `Δ_j = ω_j − ω` | Désaccord — non-pertinence contextuelle |
| `τ_j` | Temps caractéristique d'émission spontanée |
| `P(t)` | Pompage médiatique — champ de pilotage externe |
| `N` | Nombre total d'agents |

**5.2 Les trois équations semi-classiques**, de structure identique aux
équations de Maxwell-Bloch d'un laser :

- évolution du champ : `Ė = (−iω − κ)E − i·g·Σ p_j + P(t)`
- polarisation de l'agent : `ṗ_j = (−iω_j − Γ_j)p_j + i·g·k_j·E·σ_j^z`
- inversion : `σ̇_j^z = (1/τ_j)(σ_{j,0}^z − σ_j^z) + 2i·g·k_j(p_j E* − p_j* E)`

**5.3 Réduction en champ moyen.** Sous hypothèse de résonance forte
(`Γ_j = Γ`, `τ_j = τ`, `Δ_j ≈ 0`), on obtient une équation de type
**Ginzburg-Landau**, de la forme structurelle :

> `Ė = (gain linéaire) · E − (pertes) · E − (terme cubique de saturation) + P`

où le gain linéaire est proportionnel à `g²⟨k⟩σ^z/Γ` et les pertes à `κ`.
**C'est cette structure — gain linéaire, saturation cubique, pompage — qui
importe ; c'est la forme canonique d'un système à seuil.**

**5.4 La condition de seuil** — le résultat central :

> `σ^z_seuil = κ·Γ / (g²·⟨k⟩)`

et le **paramètre de couplage collectif** :

> `G = g·⟨k⟩`

**Interprétation** : le réseau multiplie de fait le couplage par le degré
moyen `⟨k⟩`. Plus le réseau est dense, plus le seuil est bas.

**5.5 La topologie du réseau entre dans les équations.** Distribution des
degrés en loi de puissance `p(k) ∝ k^(−γ)`, avec trois régimes :

| Régime | γ | Comportement |
|---|---|---|
| Anomal | 1 < γ < 2 | Hubs massifs, `⟨k⟩` diverge |
| Sans échelle | 2 < γ < 3 | Régime des réseaux sociaux réels |
| Quasi aléatoire | γ > 3 | Comportement proche de l'aléatoire |

Les moments normalisés `ζ_n` divergent quand `γ → 1`, ce qui abaisse
fortement le seuil. **Les réseaux à faible γ favorisent les cascades
virales.**

**5.6 L'équation de taux du nombre d'infons**, forme structurelle :

> `ṅ = 2A·n − 2B·n² + 2P(t)·n`

avec `A ∝ (⟨k⟩/⟨k⟩_seuil − 1)/κ` et `B` fonction de `g`, `τ`, `κ`, `Γ` et des
moments du réseau.

**Résultat capital, et c'est celui qu'il faut retenir de toute la section :
lorsque le pompage est nul (`P = 0`), cette équation se réduit à la dynamique
épidémique standard de type SIS.** Autrement dit, **tout l'apport propre du
laser social par rapport à un modèle de contagion classique tient dans le
terme de pompage et dans la structure de résonateur.** C'est une propriété du
modèle, énoncée par ses auteurs, et c'est exactement le test que FND-007
signalait comme manquant : le dépôt est en position de comparer les deux
modèles sur les mêmes données.

**5.7 Le temps caractéristique de diffusion** :

> `t_k ≈ 1/(2A)`, avec `A ∝ g²⟨k⟩σ^z/Γ`

Le temps de diffusion est **inversement proportionnel à `⟨k⟩`**. Dans le
régime anomal, `⟨k⟩` explose et `t_k` tend vers zéro — ce qui est la
justification, par le modèle, des cascades ultrarapides observées sur les
plateformes.

**5.8 Le régime de couplage fort** :

> `G ≫ Γ, κ, ω_FSR`

Dans ce régime, selon les auteurs, **le seuil `σ_seuil` tend vers zéro** : il
n'est plus nécessaire qu'un consensus préalable existe pour déclencher une
cascade massive — **l'architecture du réseau suffirait**.

**Cette affirmation est la plus lourde de conséquences de tout le corpus, et
c'est aussi la plus fragile.** Elle contredit apparemment la condition
d'inversion de population de l'étape 3, qui exigeait plus de 50 % d'excitation.
La conciliation tient à ce que le seuil s'exprime en `σ^z`, et qu'un couplage
réseau suffisamment fort le rend atteignable à très faible excitation
moyenne. **Aucune de ses grandeurs n'a jamais été mesurée sur une population
réelle.** Elle doit être présentée comme une propriété d'un modèle non
calibré, jamais comme un résultat sur des sociétés.

### 6. Ce que le modèle prédit

Les simulations publiées portent sur l'évolution du nombre d'infons sous
différents profils de pompage :

| Pompage `P(t)` | Comportement |
|---|---|
| `P = 0` | Croissance logistique — courbe en S du modèle SIS |
| `P` constant | Accélération nette et soutenue |
| `P(t) = sin(νt)`, ν petit | Suivi adiabatique du pompage |
| `P(t) = P₀·e^(−νt)` | Décroissance dominée par le pompage |
| `P(t) = sin(1,3·t)` | Oscillations complexes suivant la fréquence de pompage |

**Conclusion des auteurs** : le pompage médiatique ne fait pas qu'amorcer les
cascades, il les **renforce et les accélère**.

Prédictions structurelles utilisables comme tests :
1. Existence d'un **seuil** net, non d'un gradient.
2. **Vitesse inversement proportionnelle au degré moyen** du réseau.
3. **Cohérence** de la sortie — les actions produites doivent être
   homogènes, pas seulement nombreuses. *C'est la prédiction qui distingue le
   plus nettement le laser social d'un modèle épidémique, et elle est
   mesurable* : l'homogénéité lexicale et argumentative d'un flux est
   observable.
4. **Sensibilité à la forme temporelle du pompage**, et non seulement à son
   intensité.

### 7. Où le mécanisme est faible

1. **La dissipation n'est pas modélisée.** Décohérence, température sociale,
   relaxation et saturation restent métaphoriques. Un mécanisme sans théorie
   de son extinction est inutilisable pour la conception d'un contrôle
   (FND-013).
2. **La condition de résonance sociale n'est pas opérationnalisée.** Ni `L_s`
   ni `λ_s` n'ont d'unité ni d'instrument.
3. **L'énergie sociale n'a pas d'instrument de mesure** — limite fondamentale
   déjà établie en FND-007, et non levée ici.
4. **Le modèle à deux niveaux est reconnu par l'auteur comme trop simple.**
5. **Deux tensions internes** : la condition d'inversion à 50 % contre le
   seuil tendant vers zéro en couplage fort ; et le caractère bosonique du
   champ, posé plutôt que dérivé.
6. **Aucune calibration.** Aucune des grandeurs `g`, `κ`, `Γ`, `τ`, `P` n'a
   jamais reçu de valeur mesurée sur une population humaine.

## Synthèse

Six points à retenir.

1. **Le mécanisme tient en trois pièces** : un milieu d'individus excitables,
   une pompe médiatique, un résonateur qui renvoie et filtre. Retirez le
   résonateur et il ne reste qu'une diffusion ; retirez la pompe et il ne
   reste qu'une épidémie.
2. **Quatre conditions simultanées** : accord d'énergie, inversion de
   population, résonance, gain supérieur aux pertes. C'est une structure de
   seuil : trois sur quatre ne produisent rien.
3. **La cohérence est la signature, pas l'intensité.** Ce qui distingue un
   laser d'une lampe puissante, c'est la phase. Socialement : des actions
   **identiques**, pas seulement nombreuses. **C'est la prédiction la plus
   testable du modèle**, et le dépôt peut la tester sur des corpus réels.
4. **Sans pompage, le modèle se réduit à un modèle épidémique SIS.** Ses
   auteurs l'écrivent. Tout l'apport propre du laser social tient donc dans le
   terme de pompage et dans le résonateur — ce qui rend la comparaison avec un
   modèle de cascade classique non seulement possible mais obligatoire.
5. **La topologie du réseau est le paramètre de contrôle** : le seuil varie en
   `κΓ/(g²⟨k⟩)` et le temps de diffusion en `1/⟨k⟩`. Densifier le réseau
   abaisse le seuil et accélère la cascade.
6. **En couplage fort, les auteurs affirment que le seuil tend vers zéro** —
   aucune excitation préalable ne serait requise, l'architecture du réseau
   suffirait. C'est l'affirmation la plus grave du corpus, portée par un modèle
   dont **aucun paramètre n'a jamais été mesuré**.

## Limites

- **Les équations n'ont pas été lues sur le PDF.** Deux extractions
  automatisées du même article ont donné des formes différentes du terme
  cubique. La structure est fiable, les coefficients ne le sont pas.
  **Recopier les équations à la main est le préalable obligatoire à toute
  implémentation.**
- **Aucun paramètre n'a de valeur.** Une simulation devra les poser en
  hypothèse et faire de l'analyse de sensibilité son résultat principal — c'est
  déjà la conclusion d'ANL-002, et elle est ici confirmée par le mécanisme
  lui-même.
- **La dissipation manque au modèle**, ce qui bloque la conception d'un
  mécanisme de contrôle tant qu'elle n'est pas ajoutée. Ce sera probablement
  une contribution propre du dépôt, à assumer comme telle.
- **Le modèle est décrit, pas testé.** Cette fondation rapporte ce que ses
  auteurs affirment et ce que leurs simulations montrent ; elle n'établit
  aucune adéquation à un phénomène social réel.
- **Ce qu'il faudrait pour aller plus loin** : la lecture intégrale du PDF
  d'Alodjants et al. (2022) ; la consultation de l'article de 2026 dans
  *Advances in Complex Systems*, toujours non consulté ; et la construction
  d'un modèle de cascade classique de référence, sans lequel le laser social
  ne peut pas être évalué.

## Sources

**Vérifiées en ligne le 2026-08-28.**

- Alexander P. Alodjants, A. Yu. Bazhenov, A. Yu. Khrennikov,
  A. V. Bukhanovsky, « Mean-field theory of social laser », *Scientific
  Reports*, 2022. DOI 10.1038/s41598-022-12327-w. **Source de tout
  l'appareil mathématique de la section 5** : hamiltonien, équations
  semi-classiques, équation de Ginzburg-Landau, condition de seuil, paramètre
  de couplage collectif, rôle de l'exposant γ, équation de taux et sa
  réduction au modèle SIS, temps caractéristique de diffusion, condition de
  couplage fort, simulations sous divers profils de pompage.
  https://pmc.ncbi.nlm.nih.gov/articles/PMC9123015/
- Andrei Khrennikov, « Social Laser Theory as a Natural Extension of
  Quantum-Like Modeling », arXiv:2510.16012, 15 octobre 2025. **Source du
  mécanisme narratif** : pompage, infons, accord d'énergie, inversion à 50 %,
  émission stimulée et doublement, résonateur et chambres d'écho, condition de
  résonance sociale, formule d'amplification. **Établit aussi, par ce qu'il
  n'y traite pas, l'absence de modèle de la dissipation.**
  https://arxiv.org/html/2510.16012

**Reprises de FND-007, non re-vérifiées ici.**
- Khrennikov, article fondateur, *Philosophical Transactions of the Royal
  Society A*, vol. 374, art. 20150094, 2016.
- Khrennikov, *Social Laser*, Jenny Stanford Publishing.
- Khrennikov, « Social Laser Model for the Bandwagon Effect », *Entropy*,
  vol. 22, art. 559, 2020 — analyse des chambres d'écho comme résonateurs.
- Khrennikov, « Coherent decision making stimulated within the social laser »,
  *Philosophical Transactions A*, vol. 381, art. 20220294, 2023.
- « Social Laser Theory: A Quantum-Like Framework for Collective Social
  Dynamics », *Advances in Complex Systems*. **Toujours non consulté.**

**Pour le rappel de physique de la section 1** : Anthony Siegman, *Lasers*,
1986 ; Orazio Svelto, *Principles of Lasers*. **Non re-vérifiés** ; contenu de
manuel.

**Relations.** Dérive de FND-007, dont elle approfondit le mécanisme sans en
réviser le jugement. Référence FND-002 (groupalité), FND-003 (seuils,
falsification des préférences, contagion), FND-008 (sociophysique, modèle
concurrent), FND-013 et FND-014 (contrôle, dissipation manquante). Alimente
directement le script de simulation attendu par la session.
