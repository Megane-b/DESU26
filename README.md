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