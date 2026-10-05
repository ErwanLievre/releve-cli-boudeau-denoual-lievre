# releve-cli — outil de synthèse de relevés

> Dépôt-modèle du module *Travail collaboratif & documentation technique* (Bachelor 2).
> Cliquez sur **Use this template** pour créer le dépôt de votre équipe, nommé
> `releve-cli-nom1-nom2`, puis invitez votre binôme comme collaborateur.

`releve-cli` est un petit outil en ligne de commande, développé et documenté en équipe. Il lit un
fichier de relevés au format CSV (des mesures horodatées) et produit un rapport de synthèse :
nombre de mesures, moyenne, maximum, minimum, et signalement des doublons.

## Démarrage

Avant la première utilisation, suivez le [guide de démarrage](docs/demarrage.md).

## Configuration

Copiez `config.example.txt` sous le nom `config.txt` et complétez-le avec vos propres réglages.
Ne versionnez jamais `config.txt` : il est exclu par `.gitignore`.

## Contribution

Pour proposer une modification de la documentation ou du projet, suivez ces conventions :

1. Une branche par sujet. Partir de `main` à jour et créer une branche dont le nom indique le sujet :

```
   git switch main && git pull
   git switch -c docs/nom-du-sujet
```

2. Un message d'enregistrement préfixé par son type, par exemple `docs:` pour la documentation ou `fix:` pour une correction :

```
   git commit -m "docs: préciser le résultat attendu du démarrage"
```

3. Publier la branche, puis ouvrir une demande de fusion sur GitHub :

```
   git push -u origin docs/nom-du-sujet
```

4. Faire relire la demande de fusion par un autre membre avant de fusionner. Personne ne fusionne sa propre demande sans relecture.

Aucune valeur réelle (mot de passe, jeton d'accès, courriel ou téléphone personnel) ne doit être ajoutée au dépôt : il est public et son historique est conservé.

## Contact

Ce projet est maintenu par le trinôme Erwan Lievre, Kilian Boudeaud et Ewen Denoual.

Pour poser une question sur le projet, signaler une erreur dans la documentation ou proposer une amélioration, ouvrez un ticket dans l'onglet **Issues** de ce dépôt. Nous y répondrons à cet endroit, afin que la réponse profite aussi aux autres lecteurs.