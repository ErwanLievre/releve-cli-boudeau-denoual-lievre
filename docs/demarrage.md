# Guide de démarrage de releve-cli

Ce guide décrit la préparation de la configuration et le lancement prévu de l'outil. Dans ce TP, le programme `releve.py` et les relevés CSV ne sont pas fournis : seule la préparation de la configuration peut être réalisée.

## Prérequis

- Un éditeur de texte et un terminal ouvert à la racine du dépôt.
- Python 3 pour la future application ; sa version minimale reste à confirmer.
- Un fichier CSV (valeurs séparées par des virgules) de mesures horodatées pour la future application ; son schéma reste à préciser.

## Préparer la configuration

1. Vérifier que vous êtes à la racine du dépôt :

   ```bash
   git rev-parse --show-toplevel
   ```

   Le chemin affiché doit correspondre au dossier de votre dépôt.

2. Si `config.txt` n'existe pas encore, copier l'exemple. S'il existe, conserver votre fichier et passer à l'étape suivante :

   ```bash
   cp config.example.txt config.txt
   ```

3. Ouvrir `config.txt` dans l'éditeur et adapter les paramètres. Pour le TP, utiliser uniquement les valeurs fictives suivantes :

   ```text
   CHEMIN_RELEVES=exemples/releves.csv
   DOSSIER_RAPPORT=rapports/
   API_KEY=cle-d-exemple-a-remplacer
   INTERVALLE=300
   ```

   Le chemin de relevés est un exemple : ce fichier n'est pas fourni. Consulter la [référence des réglages](reglages.md) pour le rôle de chaque champ.

4. Vérifier l'exclusion de la configuration :

   ```bash
   git check-ignore config.txt
   ```

   **Résultat attendu :** la commande affiche `config.txt`. Ne jamais ajouter de valeur réelle au dépôt.

## Lancement prévu

Lorsque le programme et un fichier de relevés compatible seront fournis, lancer depuis la racine du dépôt :

```bash
python3 releve.py --config config.txt
```

Dans l'état actuel du TP, cette commande échouerait car `releve.py` n'existe pas. Il n'est pas nécessaire de l'exécuter pour vérifier la documentation.

## Résultat attendu de l'application

Le rapport de synthèse doit être écrit dans le dossier indiqué par `DOSSIER_RAPPORT` et contenir :

- le nombre de mesures ;
- la moyenne ;
- le minimum et le maximum ;
- le signalement des doublons.

Le nom du fichier, le format du rapport, les colonnes CSV et les messages d'erreur restent à confirmer avec l'implémentation. `INTERVALLE=300` décrit un délai de 5 minutes entre deux rapports.

## Vérifications en cas de problème

- Si `config.example.txt` est introuvable, vérifier le dossier courant.
- Si `git check-ignore config.txt` n'affiche rien, vérifier la règle `config.txt` dans `.gitignore`.
- Si `releve.py` est introuvable, rappeler que le code n'est pas fourni dans ce TP.

Retour à la [présentation du projet](../README.md).
