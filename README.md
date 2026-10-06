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

# 6. git status
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

# 7. git add
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
# 8. git commit
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

# 9 git log
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

# 10 git diff
## Voir les modifications non ajoutées
```text
git diff
```
### Voir les modifications dans le staging :
```text
git diff --staged
```
#### Comparer deux commits
```text
git diff commit1 commit2
```

# 11 Git restore 
## Annuler les modification d'un fichier
```text
git restore fichier.txt
```
### Retirer un fichier du staging
```text
git restore --staged fichier.txt
```
git restore fichier.txt peut supprimer les modifications locales non sauvegardées.

# 12 .gitignore
.gitignore permet d'empecher Git de suivre certains fichiers
## Exemple :
```text
node_modules/
.env
dist/
build/
*.log
.vscode/
```
## Pour un projet React :
```
node_modules/
dist/
.env
```
### Pour Spring Boot :
```text
target/
.env
```
#### Pour Python :
```
__pycache__/
*.pyc
.venv/
.env
```
Ne jamais envoyer des mots de passe, clés API ou secrets sur GitHub.

# 13. Branches
## Voir les branches
```text
git branch
```
### Créer une branche
```text
git branch feature/login
```
# 14. git switch
## Changer de branche :
```text
git switch feature/login
```
### Créer et changer directement
```text
git switch -c feature/login
```
# 15. git merge
- Supposons
```text
  main
 │
 └── feature/login
 ```
Une fois le développement terminé
 ```text
  git switch 
  ```
Puis :
```text
git merge feature/login
```
# 16.  git rebase
## Mettre à jour une branche avec les dernière modification de main:
```text
git switch feature/login
git rebase main
```
### Conceptuellement :
```text
Avant :

A---B---C main
     \
      D---E feature
Après :

A---B---C---D---E
```
Évite le rebase sur des commits déjà partagés avec une équipe sans comprendre ses conséquences.

# 17 git remote
## Voir les repositories distants
```text
git remote -v
```
### Ajouter Github
```text
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```
#### Voir les details :
```text
git remote show origin
```
##### Changer l'URL :
```text
git remote set-url origin URL
```
###### Supprimer un remote
```text
git remote remove origin
```

# 18. git clone
## Cloner un repository Github :
```text
git clone https://github.com/USERNAME/REPOSITORY.git
```
### Cloner dans un dossier particulier :
```text 
git clone URL mon-projet
```
Puis
```text
cd mon-projet
```

# 19. git push
## Envoyer les commits vers GitHub
```text 
git push
```
### Lors du premier push :
```text
git push -u origin main
```
Ensuite 
```text
git push
```
#### Envoyer une branche
```text
git push origin feature/login
```
# 20. git pull
## Récupérer les modifications de Github et les intégrer
```text
git pull
```
Avec une branche
```text
git pull origin main
```
### Conceptuellement
```text
GitHub
   ↓
git pull
   ↓
Repository local
```
# 21. git fetch
## Récupérer les informations du remote sans modifier directement ton travail
```text
git fetch
```
Toutes les branches:
```text
git fetch --all
```
### Différence importante :
```text
git fetch
↓
récupère les nouveautés

git pull
↓
fetch + intégration
```
# 22. Pull Request
Une Pull Request permet de proposer des modification avant de les intégrer à une branche

## Workflow
```text
feature/login
      ↓
git push
      ↓
GitHub
      ↓
Pull Request
      ↓
Code Review
      ↓
Merge
      ↓
main
```
### Une PR peut contenir :
- description;
- coommits;
- modifications;
- commentaires;
- reviewers;
- test;
- validation

# 23. Issues
Une Issue permet d suivre une tache ou un problème.
Exemple :
```text 
Issue #15

Titre :
Corriger le formulaire de connexion

Description :
Le formulaire accepte un mot de passe vide.
```

Une équipe put ensuite créer :
```text
feature/fix-login
```
pour resoudre le problème.

# 24. Fork
Un fork une copie d'un repository sur ton propre compte GitHub.
Utile notamment pour contribuer à un projet auquel tu n'as pas directement accès
## Workflow
```text
Repository original
        ↓
      Fork
        ↓
Ton repository
        ↓
Feature
        ↓
Pull Request
        ↓
Repository original
```
# 25. git stash
## Mettre temporairement de coté les modifications :
```text
git stash
```
### Voir les stash :
```text
git stash list
```
#### Appliquer sans supprimer :
```text
git stash apply
```
##### Supprimer un stash :
```text
git stash drop
```
###### Tout supprimer
```text
git stash clear
```
# 25. git reset

## Soft
```text
git reset --soft HEAD~1
```
Le commit est supprimé mais les modifications restent dan le staging

### Mixed
```text
git reset HEAD~1
```
Le commit est supprimé et les modifications restent dans le working directory

#### Hard 
```text
git reset --hard HEAD~1
```
Peut supprimer les modifications locales

# 27. git revert
Annuler un commit en créant un nouveau commit :
```text 
git commit COMMIT_ID
```
C'est généralement préférable à reset lorsqu'un commit a déjà été partagé avec l'équipe

# 28. git cherry-pick
Prendre un commit particulier et l'appliquer sur la branche actuelle
```text
git cherry-pick COMMIT_ID
```
## Exemple
```text
main
A---B---C

feature
A---B---C---D---E
```
On peut récupérer D
```text
git cherry-pick D
```

# 29. git reflog
Voir les mouvement récent de HEAD
```text
git reflog
```
Très utile pour récupérer un commit après une erreur
## Exemple :
```text
HEAD@{0}
HEAD@{1}
HEAD@{2}
```
Puis éventuellement
```text 
git reset --hard COMMIT_ID
```
A utiliser avec précaution

# 30 Résoudre un conflit

- Example :
```text
git merge feature/login
```
- Git indique :
```text
CONFLICT
```
- Le fichier peut contenir :
```text
<<<<<<< HEAD
code de main
=======
code de feature
>>>>>>> feature/login
```
On doit choisir ou combiner les deux versions.
- Puis
```text
git add fichier
```
- Et
```text
git commit
```
Pour un conflit pendant un rebase :
```trxt
git add fichier
git rebase --continue
```
- Annuler le rebase
```text
git rebase --abort
```
- Annuler le merge
```text
git merge --abort
```
# 31 SSH avec Github
## Créer une clé SSH :
```text
ssh-keygen -t ed25519 -C "ton-mail@example.com"
```
- Demarrer l'agent
```text
eval "$(ssh-agent -s)"
```
### Ajouter la clé
```text 
ssh-add ~/.ssh/id_ed25519
```
#### Affiche la clé publique :
```text
cat ~/.ssh/id_ed25519.pub
```
##### Copier cette clé dans GitHub
Tester :
```text
ssh -T git@github.com
```
###### Utiliser ensuite une URL SSH :
```text
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git"
```

# 32. Tags
## Créer un tag :
```text
git tag v1.0.0
```
### Tag annoté:
```text
git tag -a v1.0.0 -m "Version 1.0.0"
```
#### Voir les tags:
```text
git tag
```
##### Envoyer un tag:
```text
git push origin v1.0.0
```
###### Envoyer tous les tags
```text 
git push --tags
```




