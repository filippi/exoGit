```markdown
# Tutoriel Git pour Débutants Absolus

Niveau : Master 1  DFS Corte
Mode : Console Bash*

---

## Introduction à Git

Git est un système de contrôle de version distribué qui permet de suivre les modifications apportées aux fichiers et de collaborer efficacement avec d'autres développeurs. Ce tutoriel est conçu pour les débutants absolus et vous guidera à travers les bases de Git en utilisant la console Bash. Nous utiliserons des fichiers de recettes de cuisine pour les exercices pratiques.

---

## Table des Matières

1. [Configuration Initiale](#configuration-initiale)
2. [Création d'un Nouveau Dépôt Git](#création-dun-nouveau-dépôt-git)
3. [Les Bases de Git](#les-bases-de-git)
    - [Vérifier l'État du Dépôt](#vérifier-létat-du-dépôt)
    - [Ajouter des Fichiers au Staging](#ajouter-des-fichiers-au-staging)
    - [Committer les Changements](#committer-les-changements)
    - [Visualiser l'Historique des Commits](#visualiser-lhistorique-des-commits)
4. [Gestion des Branches](#gestion-des-branches)
    - [Créer une Nouvelle Branche](#créer-une-nouvelle-branche)
    - [Changer de Branche](#changer-de-branche)
    - [Fusionner des Branches](#fusionner-des-branches)
    - [Résoudre les Conflits de Fusion](#résoudre-les-conflits-de-fusion)
5. [Exercices Pratiques](#exercices-pratiques)
    - [Exercice 1 : Initialiser un Dépôt et Créer une Recette](#exercice-1-initialiser-un-dépôt-et-créer-une-recette)
    - [Exercice 2 : Modifier une Recette et Utiliser `git status`](#exercice-2-modifier-une-recette-et-utiliser-git-status)
    - [Exercice 3 : Utiliser `git log` pour Explorer l'Historique](#exercice-3-utiliser-git-log-pour-explorer-lhistorique)
    - [Exercice 4 : Travailler avec des Branches](#exercice-4-travailler-avec-des-branches)
    - [Exercice 5 : Fusionner des Branches avec Conflits](#exercice-5-fusionner-des-branches-avec-conflits)
    - [Exercice 6 : Utiliser `git log` avec Options Avancées](#exercice-6-utiliser-git-log-avec-options-avancées)
6. [Bonnes Pratiques](#bonnes-pratiques)
7. [Ressources Supplémentaires](#ressources-supplémentaires)

---

## Configuration Initiale

Après l'installation, configurez votre nom d'utilisateur et votre adresse e-mail. Ces informations seront associées à vos commits.

```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```

Pour vérifier votre configuration :

```bash
git config --list
```

---

## Création d'un Nouveau Dépôt Git

Pour initialiser un nouveau dépôt Git dans un répertoire existant :

1. **Naviguez vers le répertoire souhaité :**

    ```bash
    cd /chemin/vers/votre/projet
    ```

2. **Initialisez Git :**

    ```bash
    git init
    ```

Cela crée un sous-répertoire `.git` contenant tous les fichiers nécessaires au dépôt.

---

## Les Bases de Git

### Vérifier l'État du Dépôt

Pour voir les modifications non enregistrées et les fichiers suivis/non suivis :

```bash
git status
```

### Ajouter des Fichiers au Staging

Pour ajouter un fichier spécifique :

```bash
git add nom_du_fichier
```

Pour ajouter tous les fichiers modifiés :

```bash
git add .
```

### Committer les Changements

Pour enregistrer les changements ajoutés au staging avec un message descriptif :

```bash
git commit -m "Votre message de commit"
```

### Visualiser l'Historique des Commits

Pour afficher l'historique des commits :

```bash
git log
```

Pour un affichage plus condensé :

```bash
git log --oneline
```

---

## Gestion des Branches

Les branches permettent de travailler sur différentes fonctionnalités ou correctifs sans affecter la branche principale.

### Créer une Nouvelle Branche

```bash
git branch nom_de_la_branche
```

### Changer de Branche

```bash
git checkout nom_de_la_branche
```

### Créer et Changer de Branche en une Seule Commande

```bash
git checkout -b nom_de_la_branche
```

### Fusionner des Branches

Pour fusionner une branche dans la branche actuelle :

1. **Assurez-vous d'être sur la branche cible (par exemple, `master`) :**

    ```bash
    git checkout master
    ```

2. **Fusionnez la branche souhaitée :**

    ```bash
    git merge nom_de_la_branche
    ```

### Résoudre les Conflits de Fusion

Lors de la fusion, des conflits peuvent survenir si les mêmes lignes de code ont été modifiées différemment dans les branches fusionnées. Git marquera les fichiers en conflit, et il faudra les résoudre manuellement.

1. **Identifier les fichiers en conflit :**

    ```bash
    git status
    ```

2. **Ouvrir les fichiers en conflit avec `vi` et résoudre les différences :**

    Les sections en conflit seront marquées comme suit :

    ```plaintext
    <<<<<<< HEAD
    Contenu de la branche actuelle
    =======
    Contenu de la branche à fusionner
    >>>>>>> nom_de_la_branche
    ```

    **Exemple de résolution :**

    ```plaintext
    # Recette de Poulet Rôti

    ## Ingrédients

    - 1 poulet entier
    - 2 cuillères à soupe d'huile d'olive
    - Sel et poivre
    - Herbes de Provence
    + Marinade spéciale

    ## Instructions

    1. Préchauffer le four à 200°C.
    2. Frotter le poulet avec l'huile d'olive.
    3. Assaisonner avec le sel, le poivre et les herbes.
    4. Rôtir pendant 1 heure.
    ```

3. **Ajouter les fichiers résolus au staging :**

    ```bash
    git add nom_du_fichier
    ```

4. **Finaliser la fusion :**

    ```bash
    git commit
    ```

---

## Exercices Pratiques

### Exercice 1 : Initialiser un Dépôt et Créer une Recette

1. **Créer un Répertoire de Projet**

    ```bash
    mkdir recettes
    cd recettes
    ```

2. **Initialiser Git**

    ```bash
    git init
    ```

3. **Créer un Fichier de Recette avec `vi`**

    ```bash
    vi recette_poulet.md
    ```

    **Contenu suggéré :**

    ```markdown
    # Recette de Poulet Rôti

    ## Ingrédients

    - 1 poulet entier
    - 2 cuillères à soupe d'huile d'olive
    - Sel et poivre
    - Herbes de Provence

    ## Instructions

    1. Préchauffer le four à 200°C.
    2. Frotter le poulet avec l'huile d'olive.
    3. Assaisonner avec le sel, le poivre et les herbes.
    4. Rôtir pendant 1 heure.
    ```

4. **Ajouter le Fichier au Staging et Committer**

    ```bash
    git add recette_poulet.md
    git commit -m "Ajouter la recette de poulet rôti"
    ```

### Exercice 2 : Modifier une Recette et Utiliser `git status`

1. **Modifier le Fichier avec `vi`**

    ```bash
    vi recette_poulet.md
    ```

    **Ajoutez une section :**

    ```markdown
    ## Temps de Préparation

    - 15 minutes
    ```

2. **Vérifier l'État du Dépôt**

    ```bash
    git status
    ```

3. **Ajouter les Changements au Staging et Committer**

    ```bash
    git add recette_poulet.md
    git commit -m "Ajouter le temps de préparation à la recette de poulet"
    ```

### Exercice 3 : Utiliser `git log` pour Explorer l'Historique

1. **Afficher l'Historique des Commits**

    ```bash
    git log
    ```

2. **Afficher l'Historique en Mode Condensé**

    ```bash
    git log --oneline
    ```

3. **Ajouter des Informations Supplémentaires à `git log`**

    ```bash
    git log --graph --decorate --all
    ```

### Exercice 4 : Travailler avec des Branches

1. **Créer une Nouvelle Branche pour une Nouvelle Recette**

    ```bash
    git checkout -b ajouter_recette_pizza
    ```

2. **Créer un Nouveau Fichier de Recette avec `vi`**

    ```bash
    vi recette_pizza.md
    ```

    **Contenu suggéré :**

    ```markdown
    # Recette de Pizza Margherita

    ## Ingrédients

    - Pâte à pizza
    - Sauce tomate
    - Mozzarella
    - Basilic frais
    - Huile d'olive

    ## Instructions

    1. Étaler la pâte à pizza sur une plaque.
    2. Étaler la sauce tomate sur la pâte.
    3. Ajouter la mozzarella.
    4. Cuire au four à 220°C pendant 15 minutes.
    5. Garnir de basilic frais et d'un filet d'huile d'olive.
    ```

3. **Ajouter et Committer le Nouveau Fichier**

    ```bash
    git add recette_pizza.md
    git commit -m "Ajouter la recette de pizza margherita"
    ```

4. **Retourner à la Branche Principale et Fusionner**

    ```bash
    git checkout master
    git merge ajouter_recette_pizza
    ```

5. **Supprimer la Branche Fusionnée**

    ```bash
    git branch -d ajouter_recette_pizza
    ```

### Exercice 5 : Fusionner des Branches avec Conflits

1. **Créer une Nouvelle Branche pour Modifier une Recette Existante**

    ```bash
    git checkout -b modifier_recette_poulet
    ```

2. **Modifier le Fichier `recette_poulet.md` avec `vi`**

    ```bash
    vi recette_poulet.md
    ```

    **Ajoutez ou modifiez une ligne dans la section Instructions :**

    ```markdown
    5. Laisser reposer le poulet avant de servir.
    ```

3. **Ajouter et Committer les Changements**

    ```bash
    git add recette_poulet.md
    git commit -m "Ajouter une étape de repos à la recette de poulet"
    ```

4. **Retourner à la Branche Principale et Modifier la Même Ligne**

    ```bash
    git checkout master
    vi recette_poulet.md
    ```

    **Modifiez la même ligne dans la section Instructions :**

    ```markdown
    5. Servir avec des légumes frais.
    ```

5. **Ajouter et Committer les Changements**

    ```bash
    git add recette_poulet.md
    git commit -m "Ajouter des légumes frais à la recette de poulet"
    ```

6. **Fusionner la Branche avec Conflit dans la Branche Principale**

    ```bash
    git merge modifier_recette_poulet
    ```

    **Résolution du Conflit :**

    Ouvrez `recette_poulet.md` avec `vi` :

    ```bash
    vi recette_poulet.md
    ```

    **Identifiez et résolvez le conflit marqué par Git :**

    ```plaintext
    <<<<<<< HEAD
    5. Servir avec des légumes frais.
    =======
    5. Laisser reposer le poulet avant de servir.
    >>>>>>> modifier_recette_poulet
    ```

    **Choisissez de combiner les deux modifications :**

    ```markdown
    5. Laisser reposer le poulet avant de servir.
    6. Servir avec des légumes frais.
    ```

7. **Ajouter le Fichier Résolu au Staging et Finaliser la Fusion**

    ```bash
    git add recette_poulet.md
    git commit -m "Résoudre le conflit de fusion dans recette_poulet.md"
    ```

### Exercice 6 : Utiliser `git log` avec Options Avancées

1. **Afficher l'Historique des Commits avec Graphique**

    ```bash
    git log --graph --oneline --all
    ```

2. **Afficher les Commits avec les Noms des Branches**

    ```bash
    git log --decorate --oneline
    ```

3. **Afficher les Différences Entre les Commits**

    ```bash
    git log -p
    ```

4. **Limiter le Nombre de Commits Affichés**

    ```bash
    git log -n 3
    ```

5. **Afficher les Commits Affectant un Fichier Spécifique**

    ```bash
    git log -- recette_poulet.md
    ```

---

## Bonnes Pratiques

- **Commits Fréquents :** Faites des commits réguliers avec des messages clairs et descriptifs pour faciliter le suivi des changements.
- **Branches Thématiques :** Utilisez des branches pour chaque fonctionnalité ou correctif afin de maintenir la branche principale stable.
- **Descriptions Claires :** Rédigez des messages de commit explicites pour faciliter la compréhension de l'historique.
- **Résolution des Conflits :** Prenez le temps de bien comprendre et résoudre les conflits lors des fusions.
- **Utilisation de `git log` :** Explorez régulièrement l'historique des commits pour mieux comprendre l'évolution du projet.
- **Organisation des Fichiers :** Maintenez une structure de répertoire organisée pour vos projets, facilitant ainsi la navigation et la gestion des fichiers.

---

## Ressources Supplémentaires

- [Documentation Officielle de Git](https://git-scm.com/doc)
- [Pro Git Book (Gratuit)](https://git-scm.com/book/fr/v2)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Tutoriels Git en Français](https://www.atlassian.com/fr/git/tutorials)
- [Git Immersion](https://gitimmersion.com/)
- [Try Git (Interactif)](https://try.github.io/)

---
