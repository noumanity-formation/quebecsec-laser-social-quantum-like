# Présentation QuébecSec — laser social multi-couleur

Support de présentation (44 diapositives, 16:9) répondant à la tâche 14 de
SES-001.

## Provenance de la chaîne de génération

Les répertoires `scripts/` et `templates/`, ainsi que `activate`, sont **repris
tels quels** du dépôt `noumanity-formation/linux-and-quantum-computers`
(LuaLaTeX + Beamer + metropolis, thème Noumanity). Ils ne sont pas modifiés
ici. Seul `src/` appartient à ce dépôt.

## Générer

```sh
. ./activate
dev.sh gen            # dist/presentation.pdf
dev.sh gen --prod     # dist/<date>_presentation.pdf
dev.sh model ls       # modèles disponibles
```

Dépendances : `texlua`, `lualatex`, `inkscape`, `convert`.

## Structure

- `src/slide-NN/content.md` — une diapositive, en-tête YAML + corps Markdown
- `src/slide-NN/*.csv` — données des diapositives à modèle `tableau`
- `src/global-params.yaml`, `src/theme.yaml` — design

## ⚠️ Diapositives à chiffres fabriqués

**Les diapositives 30, 32 et 33 contiennent des résultats FABRIQUÉS.** Les
calculs n'ont pas été exécutés ; ce sont des maquettes montrant la forme du
livrable. Leur titre porte la mention « CHIFFRES FABRIQUÉS » et leur section de
pied de page indique « MAQUETTE ». Les diapositives 2 et 43 encadrent le
support par un avertissement.

**Ne jamais retirer ces mentions** tant que les calculs n'ont pas été faits et
que les nombres n'ont pas été remplacés par des résultats réels.

## Vérifié contre fabriqué

- **vérifié à la source** : diapositives 5, 6, 7, 8, 11, 12, 36, 38 — chiffres
  électoraux, démographiques et médiatiques
- **déduit du modèle** : les mécanismes, notamment la diapositive 34
- **fabriqué** : les diapositives 30, 32, 33
