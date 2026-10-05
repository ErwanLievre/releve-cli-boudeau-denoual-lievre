# releve-cli — outil de synthèse de relevés

## Présentation

`releve-cli` décrit un outil en ligne de commande qui lit un fichier CSV (valeurs séparées par des virgules) de mesures horodatées et produit une synthèse : nombre de mesures, moyenne, minimum, maximum et doublons. Il s'adresse aux membres de l'Atelier Logiciel Nantais qui souhaitent analyser leurs relevés.

Ce dépôt est le support du TP de documentation : le programme `releve.py` et les fichiers de mesures ne sont pas fournis. Les commandes ci-dessous décrivent l'utilisation prévue ; elles ne permettent pas encore d'exécuter l'outil dans ce dépôt.

## Installation et démarrage

### Prérequis

- Python 3 pour la future application (version minimale précise à confirmer lorsque le code sera fourni).
- Un fichier de relevés CSV pour la future application (colonnes et séparateur à confirmer).
- Un éditeur de texte et un terminal, ouvert à la racine du dépôt.

### Procédure

1. Copier la configuration d'exemple si `config.txt` n'existe pas encore :

   ```bash
   cp config.example.txt config.txt
   ```

2. Ouvrir `config.txt` et adapter le chemin `CHEMIN_RELEVES` et le dossier `DOSSIER_RAPPORT`. Dans ce TP, conserver les valeurs fictives de `API_KEY` et l'intervalle `INTERVALLE=300` (300 secondes, soit 5 minutes).

3. Lorsque le programme et les relevés seront fournis, lancer depuis la racine du dépôt :

   ```bash
   python3 releve.py --config config.txt
   ```

**Résultat vérifiable dans ce TP :** `config.txt` existe localement et reste exclu du suivi Git. **Résultat prévu de l'application :** un rapport dans `DOSSIER_RAPPORT` indique le nombre de mesures, la moyenne, le minimum, le maximum et les doublons. Le nom et le format du rapport restent à préciser.

Voir le [guide de démarrage](docs/demarrage.md) et la [référence des réglages](docs/reglages.md).

## Usage

### Choisir un autre fichier de relevés

Dans `config.txt`, remplacer le chemin par celui de votre fichier, par exemple :

```text
CHEMIN_RELEVES=mes-releves/octobre.csv
```

Le fichier doit exister avant de lancer la future application :

```bash
python3 releve.py --config config.txt
```

### Modifier l'intervalle entre deux rapports

Pour demander un intervalle de 10 minutes, modifier :

```text
INTERVALLE=600
```

Puis relancer la future application avec la même commande :

```bash
python3 releve.py --config config.txt
```

## Architecture

L'architecture prévue comprend la lecture de la configuration, la lecture des mesures CSV et le calcul d'une synthèse écrite dans le dossier de rapports. Le service de dépôt des rapports utilise un jeton d'accès ; ses modalités ne sont pas encore spécifiées.

Le schéma détaillé sera produit en séance 3 dans `docs/architecture.md` (fichier à venir).

## Organisation du dépôt

| Chemin | Contenu |
|---|---|
| `README.md` | Présentation et instructions principales |
| `config.example.txt` | Quatre réglages avec des valeurs fictives |
| `docs/demarrage.md` | Procédure détaillée et résultat attendu |
| `docs/reglages.md` | Référence des paramètres |
| `docs/modeles/` | Gabarits et liste de contrôle de relecture |
| `docs/aide-memoire-git-github.md` | Commandes Git et gestes GitHub |
| `docs/aide-memoire-markdown.md` | Syntaxe Markdown |
| `CHANGELOG.md` | Changements documentaires non publiés |
| `.gitignore` | Exclusions, notamment `config.txt` et `rapports/` |
| `LICENSE` | Licence du dépôt |

## Contribution

1. Partir de `main` à jour et créer une branche par sujet :

   ```bash
   git switch main
   git pull --ff-only
   git switch -c docs/nom-du-sujet
   ```

2. Modifier et vérifier le rendu Markdown, puis sélectionner uniquement les fichiers concernés. Préfixer le message d'enregistrement par `docs:`, `fix:`, `feat:` ou `chore:`.

3. Publier la branche et ouvrir une demande de fusion (PR, pour *pull request*) avec trois parties : contexte, changements, impact.
4. Faire relire la PR par un autre membre avant fusion. La PR de documentation détaillée reste ouverte pendant la relecture croisée.

Aucune valeur réelle de configuration ne doit être ajoutée au dépôt public. Consulter l'[aide-mémoire Git et GitHub](docs/aide-memoire-git-github.md) et la [liste de contrôle](docs/modeles/liste-controle-relecture.md).

## Contact

Équipe : Erwan Lievre, Kilian Boudeaud et Ewen Denoual. Pour signaler une erreur ou poser une question, ouvrir un ticket dans l'onglet **Issues** du dépôt.
