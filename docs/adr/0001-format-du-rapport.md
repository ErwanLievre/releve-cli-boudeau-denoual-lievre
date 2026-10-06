# 0001 - Produire le rapport en texte tabulaire, pas en JSON

Statut : proposé - 6 octobre 2026

## Contexte

Le rapport de synthèse est lu par des humains dans un terminal. Le service de dépôt accepte aussi le JSON, mais l'atelier n'a aucun outil de visualisation pour lire un rapport JSON.

## Options examinées

1. Rapport en JSON : lisible par une machine et directement acceptable par le service de dépôt, mais difficile à lire dans un terminal.
2. Rapport en texte tabulaire, converti en JSON au moment du dépôt : lisible immédiatement par une personne, mais une conversion de plus à maintenir.

## Décision

Option 2. Critère retenu : le premier lecteur du rapport est un humain devant un terminal.

## Conséquences

- Facile : vérifier un rapport à l'œil, sans outil.
- Difficile : le dépôt vers le service demande une conversion du texte en JSON.
- À surveiller : documenter le format exact des colonnes du rapport.

> Une fiche ne se réécrit pas. Si la décision change, créez la fiche suivante
> et passez celle-ci au statut « remplacé », avec un renvoi vers la nouvelle.
