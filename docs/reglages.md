# Réglages de releve-cli

Les paramètres sont écrits dans `config.txt`, sous la forme `NOM=valeur`, une ligne par réglage. `config.example.txt` contient des exemples fictifs à copier : les valeurs ci-dessous ne sont pas des valeurs de repli garanties par un programme.

| Réglage | Valeur de l'exemple | Valeurs attendues | Rôle |
|---|---|---|---|
| `CHEMIN_RELEVES` | `exemples/releves.csv` | Chemin d'un fichier CSV existant, relatif à la racine du dépôt dans les exemples | Relevés à analyser |
| `DOSSIER_RAPPORT` | `rapports/` | Chemin du dossier de sortie accessible en écriture | Destination du rapport de synthèse |
| `API_KEY` | `cle-d-exemple-a-remplacer` | Jeton fourni par le futur service de dépôt ; conserver la valeur fictive dans ce TP | Authentification au service de dépôt des rapports |
| `INTERVALLE` | `300` | Entier positif en secondes ; `300` correspond à 5 minutes | Délai entre deux rapports |

`CSV` désigne un fichier de valeurs séparées par des virgules. `API` désigne une interface de programmation ; `API_KEY` est le nom du champ du jeton d'accès.

## Modifier un réglage

1. Préparer `config.txt` en suivant le [guide de démarrage](demarrage.md).
2. Modifier la ligne du paramètre concerné et enregistrer le fichier.
3. Lorsque l'application sera disponible, la relancer :

   ```bash
   python3 releve.py --config config.txt
   ```

Par exemple, un délai de 10 minutes s'écrit :

```text
INTERVALLE=600
```

## Informations à confirmer

Le programme n'est pas fourni dans ce TP. Les règles de validation, les colonnes et le séparateur CSV, la création automatique du dossier, le format du rapport et les modalités du service de dépôt restent à définir. Le tableau décrit les réglages prévus, sans prétendre valider leur implémentation.

## Configuration locale

Ne publier aucune valeur réelle de configuration. `config.txt` est exclu par `.gitignore` ; vérifier cette exclusion avec :

```bash
git check-ignore config.txt
```

**Résultat attendu :** `config.txt` est affiché. La configuration d'exemple conserve uniquement des valeurs fictives.

Retour au [README](../README.md).
