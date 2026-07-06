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


### 1. Initialiser Git et faire le premier commit

```bash
git init
git add .
git commit -m "Initial commit"
```

---

### 2. Installer GitHub CLI (si nécessaire)

```bash
sudo apt install gh
```

---

### 3. Se connecter à GitHub

```bash
gh auth login
```

Choisir :
- GitHub.com
- HTTPS
- login via navigateur

---

### 4. Créer le repository GitHub + push automatique

```bash
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