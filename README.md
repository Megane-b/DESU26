# DESU 2026 – Environnement Python

Ce dépôt contient les notebooks, les jeux de données et l'environnement Python utilisé pendant le DESU Data Science.

## Prérequis

- Python 3.11 ou supérieur
- Git

Vérifiez les versions installées :

```bash
python3 --version
git --version
```

---

## 1. Cloner le dépôt GitHub

Ouvrir un terminal puis exécuter :

```bash
git clone https://github.com/Megane-b/DESU26.git
```

Se placer dans le dossier :

```bash
cd DESU26
```

---

## 2. Créer un environnement virtuel

Créer un environnement nommé `env_desu` :

```bash
python3 -m venv env_desu
```

---

## 3. Activer l'environnement

### Linux / macOS

```bash
source env_desu/bin/activate
```

### Windows (Invite de commandes)

```cmd
env_desu\Scripts\activate
```

### Windows (PowerShell)

```powershell
env_desu\Scripts\Activate.ps1
```

Lorsque l'environnement est activé, son nom apparaît au début du terminal :

```text
(env_desu)
```

---

## 4. Installer les dépendances

Depuis le dossier contenant le fichier `pyproject.toml`, exécuter :

```bash
pip install .
```

Toutes les bibliothèques nécessaires au DESU seront installées automatiquement.

---

## 5. Vérifier l'installation

Par exemple :

```bash
python
```

Puis :

```python
import numpy
import pandas
import matplotlib
```

Si aucune erreur n'apparaît, l'installation est correcte.

Quitter Python :

```python
exit()
```

---

## 6. Réactiver l'environnement ultérieurement

Chaque fois que vous ouvrez un nouveau terminal :

```bash
cd DESU26
source env_desu/bin/activate
```

---

## 7. Mettre à jour le dépôt

Si de nouveaux fichiers sont ajoutés pendant la formation :

```bash
git pull
```

Si de nouvelles bibliothèques sont ajoutées dans le fichier `pyproject.toml` :

```bash
pip install .
```


---

## 8. Création du dépôt GitHub (première mise en place)

Cette étape est uniquement nécessaire lors de la création initiale du projet.

Un dépôt Git permet de :
- sauvegarder l’historique du projet
- travailler en collaboration
- synchroniser le code avec GitHub

Dans ce projet, on retrouve notamment :
- les notebooks et scripts du DESU
- un fichier `pyproject.toml` (environnement Python)
- un fichier `.gitignore` (fichiers à exclure de Git)

---

### 8.1 Initialiser un dépôt Git

Créer un dépôt Git local dans le dossier du projet :

```bash
git init
```

---

Ajouter tous les fichiers du projet :

```bash
git add .
```

---

Créer un premier enregistrement (commit) :

```bash
git commit -m "Initial commit"
```

---

### 8.2 Exemple de fichier `.gitignore`

Créer un fichier nommé `.gitignore` :

```bash
touch .gitignore
```

Contenu du fichier :

```text
# Environnement virtuel
env_desu/

# Fichiers Python temporaires
__pycache__/
*.pyc

# Jupyter Notebook checkpoints
.ipynb_checkpoints/

# VS Code
.vscode/
```

 Ce fichier empêche d’envoyer des fichiers inutiles sur GitHub.

---

### 8.3 Exemple de fichier `pyproject.toml`

Créer un fichier nommé :

```bash
touch pyproject.toml
```

Contenu minimal :

```toml
[project]
name = "desu26-environment"
version = "0.1.0"
description = "Environnement Python du DESU Data Science 2026"
requires-python = ">=3.11"

dependencies = [
    "numpy",
    "pandas",
    "matplotlib",
    "scipy",
    "scikit-learn",
    "jupyterlab"
]
```

 Ce fichier permet d’installer toutes les dépendances avec :

```bash
pip install .
```

---

### 8.4 Installer GitHub CLI (si nécessaire)

GitHub CLI permet de créer et gérer le dépôt directement depuis le terminal.

```bash
sudo apt install gh
```

---

### 8.5 Se connecter à GitHub

```bash
gh auth login
```

Choisir :
- GitHub.com
- HTTPS
- login via navigateur

---

### 8.6 Créer le repository GitHub et envoyer le projet

Créer le dépôt GitHub + envoyer le projet automatiquement :

```bash
gh repo create DESU26 --public --source=. --remote=origin --push
```

---

### Résumé du workflow complet

```bash
git init
git add .
git commit -m "Initial commit"

gh auth login
gh repo create DESU26 --public --source=. --remote=origin --push
```

## 9. Ajouter des collaborateurs

Pour donner accès au dépôt :

```bash
gh api -X PUT repos/Megane-b/DESU26/collaborators/username -f permission=push
```

### Permissions possibles
- pull : lecture seule
- push : modification (recommandé)
- admin : contrôle total

## 10. Envoyer des modifications sur GitHub (workflow Git)

Lorsque vous modifiez des fichiers (notebooks, scripts, etc.), voici la procédure pour mettre à jour le dépôt GitHub.

### 1. Vérifier les fichiers modifiés

```bash
git status
```

---

### 2. Ajouter les fichiers modifiés

Pour ajouter tous les fichiers :

```bash
git add .
```

Ou pour un fichier précis :

```bash
git add nom_du_fichier
```

---

### 3. Créer un commit

```bash
git commit -m "Description des modifications"
```

Exemple :

```bash
git commit -m "Version n°blabla"
```

---

### 4. Envoyer sur GitHub

```bash
git push
```

---

### 5. Vérification

Après `git push`, les modifications apparaissent sur GitHub dans quelques secondes.

## 11. Utilisation des branches Git

Les branches permettent de travailler sur différentes versions du projet sans modifier la branche principale (`main`).

---

### 11.1 Gestion des branches

Voir les branches :

```bash
git branch
```

Créer et se placer sur une branche :

```bash
git switch -c meg
```

Changer de branche :

```bash
git switch meg
```

Revenir sur `main` :

```bash
git switch main
```

---

### 11.2 Enregistrer et envoyer une branche

```bash
git add .
git commit -m "MEG"
git push -u origin meg
```

---

### 11.3 Fusionner une branche dans main

```bash
git switch main
git merge meg
```

---

### Résumé

```bash
git switch -c meg
git add .
git commit -m "MEG"
git push -u origin meg
```

---

## 12. Synchronisation et Pull Request

---

### 12.1 Récupérer les modifications

```bash
git pull
```

Permet de récupérer les changements du dépôt GitHub.

---

### 12.2 Principe d’une Pull Request

Une Pull Request est une demande de fusion d’une branche vers `master` sur GitHub.

Elle permet de :
- proposer des modifications
- faire relire le code
- valider avant intégration

---

### 12.3 Workflow d’une Pull Request

Créer une branche :

```bash
git switch -c meg
```

Modifier puis enregistrer :

```bash
git add .
git commit -m "Modification"
```

Envoyer sur GitHub :

```bash
git push -u origin meg
```

Puis ouvrir une Pull Request sur GitHub :
- base : `main`
- compare : `meg` (ou `lolo`, `mel`)

---

### 12.4 Après fusion de la Pull Request

```bash
git switch main
git pull
```

