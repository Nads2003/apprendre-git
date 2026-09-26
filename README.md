# 📚 Git & GitHub — Cours complet

> Guide pratique de Git et GitHub, du niveau débutant au niveau avancé.

---

# 📑 Sommaire

- [1. Git vs GitHub](#1-git-vs-github)
- [2. Installation](#2-installation)
- [3. Configuration](#3-configuration)
- [4. Créer un repository](#4-créer-un-repository)
- [5. Comprendre les zones de Git](#5-comprendre-les-zones-de-git)
- [6. git status](#6-git-status)
- [7. git add](#7-git-add)
- [8. git commit](#8-git-commit)
- [9. git log](#9-git-log)
- [10. git diff](#10-git-diff)
- [11. git restore](#11-git-restore)
- [12. .gitignore](#12-gitignore)
- [13. Branches](#13-branches)
- [14. git switch](#14-git-switch)
- [15. git merge](#15-git-merge)
- [16. git rebase](#16-git-rebase)
- [17. GitHub](#17-github)
- [18. git clone](#18-git-clone)
- [19. git push](#19-git-push)
- [20. git pull](#20-git-pull)
- [21. git fetch](#21-git-fetch)
- [22. Pull Request](#22-pull-request)
- [23. git stash](#23-git-stash)
- [24. git reset](#24-git-reset)
- [25. git revert](#25-git-revert)
- [26. git cherry-pick](#26-git-cherry-pick)
- [27. git reflog](#27-git-reflog)
- [28. Résoudre les conflits](#28-résoudre-les-conflits)
- [29. SSH](#29-ssh)
- [30. Tags](#30-tags)
- [31. Conventional Commits](#31-conventional-commits)
- [32. Workflow professionnel](#32-workflow-professionnel)
- [33. Cheat Sheet](#33-cheat-sheet)

---

# 1. Git vs GitHub

## Git

Git est un système de contrôle de version distribué.

Il permet de :

- suivre les modifications ;
- créer des versions ;
- revenir à une ancienne version ;
- travailler avec des branches ;
- fusionner du code ;
- travailler à plusieurs.

## GitHub

GitHub est une plateforme qui permet notamment de :

- héberger des repositories Git ;
- collaborer avec une équipe ;
- créer des Pull Requests ;
- gérer des Issues ;
- faire des Code Reviews ;
- automatiser des workflows avec GitHub Actions.

### Résumé

```text
Git
↓
Outil installé sur ton ordinateur

GitHub
↓
Plateforme en ligne utilisant Git
```
---
 
# 2. Installation

## Ubuntu/Debian
 ```text
 sudo apt update
 sudo apt install git
 ```

### Verifier
 ```text
 git --version 
 ```

# 3. Configuration

## Configurer le nom
 ```text
  git config --global user.name "Ton Nom" 
  ```

### Configurer l'email
 ```text
 git config --global user.email "test@email.com" 
 ```

#### Verifier
 ```text
  git config --global --list
 ```

##### Voir une configuration précise
 ```text
    git config --global user.name
    git config --global user.email
```

##### Configurer l'editeur
 Exemple avec VS Code
  ```text 
  git config --global core.editor "code --wait"
  ```

# 4. Creer un repository

## Créer un dossier
```text
 mkdir nom-projet
 ```

### Entrer dans le dossier
```text
 cd nom-projet
 ```

#### Initialiser Git
```text
 git init
 ```
 Git crée: .git/
 .git contient les information du repository.

# 5. Comprendre les zones de Git
 ```text
 Git possède principalement trois zones :
 Working Directory(Ce sont les fichiers que tu modifies.)
       │
       │ git add
       ↓
 Staging Area (Zone dans laquelle tu sélectionnes   les modifications qui seront enregistrées.)
       │
       │ git commit
       ↓
 Repository(Historique des commits.) 
 ```

# 6. Git status
## commande essentielle
 ```text
 git status
 ```
### Elle permet de connaitre:
 - les fichierq modifiés;
 - les fichiers non suivis;
 - les fichiers dans le staging;
 - la branche actuelle;
 - les commit à envoyer

#### Exemple :
 modifeid: src/app.jsx

# 7. Git add
## Ajouter un fichier :
 ```text
 git add README.md
  ```
### Ajouter plusieurs fichiers :
 ```text
 git add fichier1.js fichier2.js
  ```
#### Ajouter tous les fichiers :
 ```tzxt
 git add .
  ```
#### Ajouter tous les fichiers modifiés et supprimés
 ```text
 git add -A
  ```
##### Vérifier
 ```text
 git status
  ```
# 8. Git commit
## Créer un commit
 ```text
 git status
  ```
-Exemple :
 ```text
git commit -m "feat: add authentication"
 ```
 Un commit représente une version enregistrée du projet.

### Voir le dernier commit

 ```text
 git show
  ```
#### Commit avec ajout automatique des fichiers déjà suivis
 ```text
 git commit -am "fix: update login"
  ```
  Cette commande ne prend pas les nouveaux fichiers non suivis.

# 9 Git log
## Voir l'historique
```text
git log
```
- Version courte :
```text
git log --oneline
```
- Avec les branches :
```text
git log --oneline --graph --all
```
- Version très pratique :
```text
git log --oneline --graph --decorate --all
```

