# releve-cli — outil de synthèse de relevés

## Présentation

`releve-cli` est un outil en ligne de commande permettant de lire des relevés stockés dans un fichier CSV et de produire un rapport de synthèse.

Il est destiné aux membres de l'Atelier Logiciel Nantais qui souhaitent obtenir rapidement des informations sur leurs relevés, notamment le nombre de mesures, la moyenne, le maximum et le minimum.

## Installation et démarrage

### Prérequis

Avant de commencer, vous devez disposer de :

- Python 3 ;
- un fichier de relevés au format CSV ;
- un éditeur de texte.

### Démarrage

1. Copier le fichier de configuration d'exemple :

   ```bash
   cp config.example.txt config.txt
   ```

2. Ouvrir `config.txt` et adapter les paramètres nécessaires :

   - `CHEMIN_RELEVES` : chemin du fichier CSV à traiter ;
   - `DOSSIER_RAPPORT` : dossier dans lequel écrire le rapport ;
   - `API_KEY` : jeton d'accès au service de dépôt des rapports ;
   - `INTERVALLE` : intervalle de rafraîchissement du rapport, en secondes.

3. Lancer le programme :

   ```bash
   python3 releve.py --config config.txt
   ```

**Résultat attendu :** un rapport de synthèse s'affiche avec le nombre de mesures, la moyenne, le maximum et le minimum.

Pour plus de détails, consultez le [guide de démarrage](docs/demarrage.md).

## Usage

### Traiter un autre fichier de relevés

Pour analyser un autre fichier CSV, modifier la valeur de `CHEMIN_RELEVES` dans `config.txt`.

Par exemple :

```text
CHEMIN_RELEVES=exemples/releves.csv
```

Puis lancer :

```bash
python3 releve.py --config config.txt
```

### Modifier l'intervalle de rafraîchissement

Le paramètre `INTERVALLE` définit le délai entre deux rapports, en secondes.

Par exemple, pour utiliser un intervalle de 5 minutes :

```text
INTERVALLE=300
```

Après modification, lancer de nouveau :

```bash
python3 releve.py --config config.txt
```

## Architecture

`releve-cli` s'organise autour du fichier de configuration, des relevés au format CSV et de la génération d'un rapport de synthèse.

Une description plus détaillée de l'architecture sera disponible dans `docs/architecture.md`.

## Organisation

Le dépôt est organisé autour des fichiers et dossiers suivants :

| Fichier / dossier | Rôle |
|---|---|
| `README.md` | Présentation générale du projet et instructions principales |
| `config.example.txt` | Exemple de configuration à copier et adapter |
| `docs/` | Documentation détaillée du projet |
| `docs/demarrage.md` | Guide détaillé de démarrage |
| `exemples/` | Fichiers de relevés d'exemple |
| `.gitignore` | Liste des fichiers qui ne doivent pas être versionnés, notamment `config.txt` |

## Contribution

Pour proposer une modification de la documentation ou du projet, suivez ces conventions :

1. Une branche par sujet. Partir de `main` à jour et créer une branche dont le nom indique le sujet :

   ```bash
   git switch main
   git pull
   git switch -c docs/nom-du-sujet
   ```

2. Un message d'enregistrement préfixé par son type, par exemple `docs:` pour la documentation ou `fix:` pour une correction :

   ```bash
   git commit -m "docs: préciser le résultat attendu du démarrage"
   ```

3. Publier la branche, puis ouvrir une demande de fusion sur GitHub :

   ```bash
   git push -u origin docs/nom-du-sujet
   ```

4. Faire relire la demande de fusion par un autre membre avant de fusionner. Personne ne fusionne sa propre demande sans relecture.

Aucune valeur réelle (mot de passe, jeton d'accès, courriel ou téléphone personnel) ne doit être ajoutée au dépôt : il est public et son historique est conservé.

## Contact

Ce projet est maintenu par le trinôme Erwan Lievre, Kilian Boudeaud et Ewen Denoual.

Pour poser une question sur le projet, signaler une erreur dans la documentation ou proposer une amélioration, ouvrez un ticket dans l'onglet **Issues** de ce dépôt. Nous y répondrons à cet endroit, afin que la réponse profite aussi aux autres lecteurs.