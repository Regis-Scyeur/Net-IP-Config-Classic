# NetIPConfig Classic

![NetIPConfig Logo](ScreenShots/NetIPConfigLogo.png)

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/Regis-Scyeur/Net-IP-Config-Classic)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-blue)](https://github.com/Regis-Scyeur/Net-IP-Config-Classic)
[![Python Version](https://img.shields.io/badge/python-3.7%2B-blue)](https://www.python.org/downloads/)

---

## 📋 Table des Matières

- [Description](#description)
- [Fonctionnalités](#fonctionnalités)
- [Captures d'écran](#captures-décran)
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Architecture](#architecture)
- [Technologies Utilisées](#technologies-utilisées)
- [Contributeurs](#contributeurs)
- [Licence](#licence)

---

## 📖 Description

**NetIPConfig Classic** est une application graphique multi-plateforme développée en Python avec PyQt5. Elle permet de :
- Visualiser et gérer les configurations réseau de votre système
- Afficher les informations détaillées des interfaces réseau (adresses IP, masques de sous-réseau, passerelles, DNS, etc.)
- Activer ou désactiver les interfaces réseau
- Effectuer des tests de connectivité (ping)
- Gérer les connexions réseau de manière intuitive

Cette application est compatible avec **Windows**, **Linux** et **macOS**.

---

## ✨ Fonctionnalités

### Fonctionnalités Principales

- **Multi-plateforme** : Fonctionne sur Windows, Linux et macOS
- **Interface graphique moderne** : Utilisation de PyQt5 pour une expérience utilisateur fluide
- **Gestion des interfaces réseau** :
  - Affichage de toutes les interfaces réseau disponibles
  - Activation/Désactivation des interfaces
  - Affichage des détails (IP, masque, passerelle, DNS, MAC, etc.)
- **Tests de connectivité** :
  - Fonction ping intégrée
  - Affichage des résultats en temps réel
- **Actualisation automatique** :
  - Mise à jour des informations réseau en temps réel
- **Filtrage des interfaces** :
  - Affichage uniquement des interfaces actives ou toutes les interfaces

### Fonctionnalités Avancées

- **Détection automatique du système d'exploitation**
- **Support des privilèges administrateur** (nécessaire pour certaines opérations)
- **Gestion des erreurs robuste**
- **Logs détaillés pour le débogage**

---

## 📸 Captures d'écran

### Interface sur Windows

<div align="center">
  <img src="https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/NetIPConfig-Windows.PNG" alt="NetIPConfig sur Windows" width="600">
</div>

### Interface sur Linux

<div align="center">
  <img src="https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/NetIpConfig-Linux.png" alt="NetIPConfig sur Linux" width="600">
</div>

### Interface sur macOS

<div align="center">
  <img src="https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/NetIPConfig-MacOSX.png" alt="NetIPConfig sur macOS" width="600">
</div>

---

## 🔧 Prérequis

Avant d'installer et d'utiliser NetIPConfig Classic, assurez-vous d'avoir les éléments suivants :

- **Python 3.7+** : [Télécharger Python](https://www.python.org/downloads/)
- **pip** : Gestionnaire de paquets Python (généralement installé avec Python)
- **Privilèges administrateur** : Nécessaires pour activer/désactiver les interfaces réseau

---

## 📦 Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/Regis-Scyeur/Net-IP-Config-Classic.git
cd Net-IP-Config-Classic
```

### 2. Créer un environnement virtuel (recommandé)

#### Sur Windows :

```bash
python -m venv venv
venv\Scripts\activate
```

#### Sur Linux/macOS :

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Installer les dépendances

```bash
pip install -r requirements.txt
```

Le fichier `requirements.txt` contient :

```
PyQt5>=5.15.0
psutil>=5.8.0
```

---

## 🚀 Utilisation

### Lancer l'application

#### Sur Windows :

```bash
python NetIPConfig.py
```

Ou double-cliquez sur `NetIPConfig.py` après avoir associé les fichiers `.py` à Python.

#### Sur Linux :

```bash
sudo python3 NetIPConfig.py
```

> **Note** : Les privilèges root sont nécessaires pour activer/désactiver les interfaces réseau.

#### Sur macOS :

```bash
sudo python3 NetIPConfig.py
```

> **Note** : Les privilèges administrateur sont nécessaires pour certaines opérations.

### Interface Utilisateur

1. **Liste des interfaces** : Affiche toutes les interfaces réseau détectées
2. **Détails de l'interface** : Affiche les informations détaillées de l'interface sélectionnée
3. **Boutons d'action** :
   - **Actualiser** : Met à jour les informations réseau
   - **Activer/Désactiver** : Active ou désactive l'interface sélectionnée
   - **Ping** : Teste la connectivité vers une adresse IP
4. **Barre de statut** : Affiche les messages d'état et d'erreur

---

## 🏗️ Architecture

### Structure du projet

```
NetIPConfig/
│
├── NetIPConfig.py          # Fichier principal de l'application
├── requirements.txt        # Dépendances Python
├── README.md              # Documentation
├── LICENSE                # Licence du projet
│
├── ScreenShots/           # Captures d'écran
│   ├── NetIPConfigLogo.png
│   ├── NetIPConfig-Windows.PNG
│   ├── NetIpConfig-Linux.png
│   └── NetIPConfig-MacOSX.png
│
└── venv/                  # Environnement virtuel (non inclus dans le dépôt)
```

### Composants principaux

- **NetIPConfig.py** : Contient toute la logique de l'application
  - Classe `NetIPConfigApp` : Gère l'interface graphique et les interactions utilisateur
  - Méthodes de gestion réseau :
    - `get_network_interfaces()` : Récupère les interfaces réseau
    - `enable_interface()` / `disable_interface()` : Active/désactive une interface
    - `ping_test()` : Effectue un test ping

---

## 🛠️ Technologies Utilisées

- **Python 3.7+** : Langage de programmation principal
- **PyQt5** : Framework pour l'interface graphique
- **psutil** : Bibliothèque pour la gestion des informations système et réseau
- **subprocess** : Module pour exécuter des commandes système (ping, ifconfig, etc.)

---

## 👥 Contributeurs

- **Regis-Scyeur** - Développeur principal - [GitHub](https://github.com/Regis-Scyeur)

---

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

**Copyright (c) 2015-2025 Regis-Scyeur**

---

## 📞 Contact

Pour toute question ou suggestion, n'hésitez pas à ouvrir une issue sur GitHub.

---

## 🙏 Remerciements

- Merci à la communauté Python pour les excellentes bibliothèques
- Merci à Qt pour le framework PyQt5
- Merci à tous les contributeurs potentiels

---

**Développé avec ❤️ par Regis-Scyeur**
