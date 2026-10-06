# Fiche de lecture critique du README

## 1. Objectif annoncé

**Constat :**
Partiellement présent.

Dès la section « Présentation », le README explique que `releve-cli` est un outil en ligne de commande qui lit des relevés CSV et produit une synthèse comprenant le nombre de mesures, la moyenne, le minimum, le maximum et les doublons.

Cependant, le document ne dit pas explicitement ce que le lecteur saura faire à la fin de sa lecture.

**Renvoi :**
Section `Présentation`.

---

## 2. Prérequis explicites

**Constat :**
Oui.

Une section `Prérequis` indique clairement les éléments nécessaires :
- Python 3 ;
- un fichier de relevés CSV ;
- un éditeur de texte ;
- un terminal ouvert à la racine du dépôt.

Le document précise aussi que la version minimale de Python et le format exact du CSV restent à confirmer.

**Renvoi :**
Section `Installation et démarrage` → `Prérequis`.

---

## 3. Contexte et périmètre

**Constat :**
Oui, en grande partie.

Le README précise que ce dépôt sert de support au TP de documentation et que le programme `releve.py` ainsi que les fichiers de mesures ne sont pas fournis.

Il indique donc clairement une limite importante : les commandes présentées décrivent l'utilisation prévue, mais l'application ne peut pas encore réellement être exécutée dans ce dépôt.

La section `Architecture` précise également que certaines modalités du service de dépôt ne sont pas encore spécifiées.

**Renvoi :**
Sections `Présentation` et `Architecture`.

---

## 4. Étapes numérotées

**Constat :**
Oui.

La section `Installation et démarrage` propose une procédure en trois étapes numérotées :
1. copier la configuration d'exemple ;
2. modifier `config.txt` ;
3. lancer l'application lorsqu'elle sera disponible.

La section `Contribution` propose également quatre étapes pour créer une branche, modifier les fichiers, ouvrir une PR et la faire relire.

Les étapes sont globalement vérifiables une par une.

**Exemple d'étape bien écrite :**
« Copier la configuration d'exemple si `config.txt` n'existe pas encore », avec la commande correspondante.

**Exemple qui pourrait être davantage découpé :**
L'étape 2 de la section `Contribution` regroupe plusieurs actions : modifier, vérifier le rendu Markdown, sélectionner les fichiers et choisir le préfixe du commit.

**Renvoi :**
Sections `Installation et démarrage` → `Procédure` et `Contribution`.

---

## 5. Encadrés typés

**Constat :**
Partiellement présent.

Le README met en évidence un `Résultat vérifiable dans ce TP` et un `Résultat prévu de l'application`, ce qui aide le lecteur à distinguer ce qu'il peut vérifier immédiatement de ce qui sera possible plus tard.

Cependant, il n'existe pas de véritables encadrés clairement typés comme :
- avertissement ;
- définition ;
- vérification.

La consigne indiquant qu'aucune valeur réelle de configuration ne doit être ajoutée au dépôt est importante, mais elle apparaît comme du texte normal.

**Renvoi :**
Fin de la section `Installation et démarrage` et section `Contribution`.

---

## 6. Liste de contrôle finale

**Constat :**
Non dans le README lui-même.

Le document ne contient pas de checklist finale permettant de vérifier rapidement que toutes les actions demandées ont été réalisées.

Une liste de contrôle externe est toutefois référencée dans la section `Contribution`, via le fichier :

`docs/modeles/liste-controle-relecture.md`

Le lecteur doit donc ouvrir un autre document pour effectuer cette vérification.

**Renvoi :**
Fin de la section `Contribution`.

---

## 7. Lexique et sources

**Constat :**
Partiellement présent.

Certains termes sont correctement explicités :
- `CSV` est présenté comme « valeurs séparées par des virgules » ;
- `PR` est développé en « pull request » ;
- `INTERVALLE=300` est expliqué comme correspondant à 300 secondes, soit 5 minutes.

En revanche, certains termes comme `API_KEY` ne sont pas réellement définis.

Le README ne contient pas non plus de section de sources ni de références datées.

**Renvoi :**
Sections `Présentation`, `Installation et démarrage` et `Contribution`.

---

# Ce que je corrige dans notre propre documentation

## Correction 1 — Rendre le périmètre explicite

Le README analysé montre l'intérêt d'indiquer clairement ce qui fait partie du projet et ce qui reste extérieur ou indisponible.

Dans notre fichier `docs/architecture.md`, nous indiquons donc explicitement que le service de dépôt externe est représenté pour montrer le flux sortant, mais que son fonctionnement interne et sa maintenance sont hors du périmètre de `releve-cli`.

**Correction appliquée :** oui, dans `docs/architecture.md`.

## Correction 2 — Ajouter une vérification finale

Nous devons permettre à une personne qui découvre notre documentation de vérifier rapidement qu'elle contient tous les éléments nécessaires.

Nous ajoutons donc une courte liste de contrôle finale permettant de vérifier notamment :
- que tous les flux du schéma sont étiquetés ;
- que le périmètre est indiqué ;
- que la date de validité est présente ;
- que les décisions techniques importantes sont documentées.