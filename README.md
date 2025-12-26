# 🌐 Net IP Config Classic

<div align="center">

![Net IP Config Classic](https://img.shields.io/badge/Windows-Forms-blue?logo=windows)
![.NET Framework](https://img.shields.io/badge/.NET-Framework%204.7.2-purple?logo=.net)
![C#](https://img.shields.io/badge/C%23-Language-239120?logo=c-sharp)
![Status](https://img.shields.io/badge/status-active-success)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>

---

## 📋 Table des Matières

- [À Propos](#-à-propos)
- [Fonctionnalités](#-fonctionnalités)
- [Technologies Utilisées](#-technologies-utilisées)
- [Captures d'Écran](#-captures-décran)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Configuration](#-configuration)
- [Structure du Projet](#-structure-du-projet)
- [Contribution](#-contribution)
- [Licence](#-licence)
- [Auteur](#-auteur)

---

## 📖 À Propos

**Net IP Config Classic** est une application Windows Forms développée en C# avec .NET Framework 4.7.2. Elle permet de gérer facilement les configurations réseau de votre ordinateur, incluant les adresses IP, les serveurs DNS, et bien plus encore.

Cette application est particulièrement utile pour :
- Les administrateurs réseau
- Les développeurs qui travaillent avec plusieurs environnements
- Les utilisateurs qui doivent fréquemment changer de configuration réseau

### 🎯 Objectifs du Projet

- Fournir une interface simple et intuitive pour la gestion des configurations réseau
- Permettre la sauvegarde et le chargement de profils de configuration
- Automatiser les tâches de configuration réseau répétitives
- Offrir un accès rapide aux informations réseau importantes

---

## ✨ Fonctionnalités

### 🔧 Gestion des Configurations Réseau

- **Configuration IP Automatique (DHCP)**
  - Activation/Désactivation en un clic
  - Détection automatique des paramètres réseau
  - Support de l'IPv4 et IPv6

- **Configuration IP Manuelle**
  - Définition de l'adresse IP
  - Masque de sous-réseau
  - Passerelle par défaut
  - Validation des entrées en temps réel

- **Gestion des DNS**
  - Configuration des serveurs DNS préférés et alternatifs
  - DNS Google (8.8.8.8, 8.8.4.4)
  - DNS Cloudflare (1.1.1.1, 1.0.0.1)
  - DNS personnalisés
  - Flush du cache DNS

### 💾 Profils de Configuration

- **Sauvegarde de Profils**
  - Enregistrement de configurations complètes
  - Nommage personnalisé des profils
  - Export au format JSON

- **Chargement de Profils**
  - Import rapide de configurations sauvegardées
  - Application automatique des paramètres
  - Gestion de multiples profils

### 📊 Informations Réseau

- **Détails de la Carte Réseau**
  - Nom de l'interface
  - Adresse MAC
  - Adresse IP actuelle
  - Masque de sous-réseau
  - Passerelle par défaut
  - Serveurs DNS configurés
  - État de la connexion

- **Diagnostic Réseau**
  - Test de connectivité (Ping)
  - Traceroute
  - Informations détaillées sur les adaptateurs réseau

### 🎨 Interface Utilisateur

- **Design Moderne**
  - Interface claire et intuitive
  - Thème sombre/clair (à venir)
  - Icônes informatives
  - Messages de confirmation et d'erreur

- **Facilité d'Utilisation**
  - Navigation simple
  - Raccourcis clavier
  - Tooltips explicatifs
  - Mise à jour en temps réel

---

## 🛠 Technologies Utilisées

### Langage et Framework

- **C# 7.3**
  - Langage principal de développement
  - Programmation orientée objet
  - LINQ pour les requêtes de données

- **.NET Framework 4.7.2**
  - Framework stable et éprouvé
  - Support Windows 7, 8, 10, 11
  - Bibliothèques complètes

### Interface Utilisateur

- **Windows Forms**
  - Création d'interfaces de bureau
  - Composants natifs Windows
  - Personnalisation avancée

### Gestion Réseau

- **System.Net.NetworkInformation**
  - Accès aux informations réseau
  - Gestion des adaptateurs réseau
  - Statistiques et état de la connexion

- **System.Management**
  - WMI (Windows Management Instrumentation)
  - Configuration avancée du système
  - Gestion des paramètres réseau

### Sérialisation et Stockage

- **Newtonsoft.Json**
  - Sérialisation/Désérialisation JSON
  - Sauvegarde des profils de configuration
  - Import/Export de données

---

## 📸 Captures d'Écran

### Fenêtre Principale
![Fenêtre Principale](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/main-window.png)

### Configuration IP
![Configuration IP](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/ip-configuration.png)

### Gestion des Profils
![Gestion des Profils](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/profile-management.png)

---

## 🚀 Installation

### Prérequis

- **Système d'Exploitation**
  - Windows 7 SP1 ou supérieur
  - Windows Server 2008 R2 SP1 ou supérieur

- **.NET Framework 4.7.2**
  - Téléchargeable depuis [Microsoft](https://dotnet.microsoft.com/download/dotnet-framework/net472)
  - Vérifier l'installation : `reg query "HKLM\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" /v Release`

- **Droits Administrateur**
  - Nécessaire pour modifier les paramètres réseau
  - Exécuter l'application en tant qu'administrateur

### Installation depuis les Sources

1. **Cloner le dépôt**
   ```bash
   git clone https://github.com/Regis-Scyeur/Net-IP-Config-Classic.git
   cd Net-IP-Config-Classic
   ```

2. **Ouvrir le projet**
   - Ouvrir `NetIPConfigClassic.sln` avec Visual Studio 2017 ou supérieur
   - Restaurer les packages NuGet si nécessaire

3. **Compiler le projet**
   - Configuration : Release
   - Plateforme : Any CPU ou x64
   - Compiler (Ctrl+Shift+B)

4. **Exécuter l'application**
   - Localiser l'exécutable dans `bin/Release/`
   - Clic droit → Exécuter en tant qu'administrateur

### Installation depuis les Binaires

1. **Télécharger la dernière version**
   - Aller sur la page [Releases](https://github.com/Regis-Scyeur/Net-IP-Config-Classic/releases)
   - Télécharger `NetIPConfigClassic-vX.X.X.zip`

2. **Extraire l'archive**
   - Extraire le contenu dans un dossier de votre choix
   - Exemple : `C:\Program Files\NetIPConfigClassic\`

3. **Exécuter l'application**
   - Clic droit sur `NetIPConfigClassic.exe`
   - Sélectionner "Exécuter en tant qu'administrateur"

---

## 📖 Utilisation

### Démarrage Rapide

1. **Lancer l'application**
   - Exécuter en tant qu'administrateur
   - L'application détecte automatiquement vos cartes réseau

2. **Sélectionner une carte réseau**
   - Choisir l'adaptateur à configurer dans la liste déroulante
   - Les informations actuelles s'affichent automatiquement

3. **Configurer les paramètres**
   - **Mode DHCP** : Cocher "Obtenir une adresse IP automatiquement"
   - **Mode Manuel** : Décocher et remplir les champs (IP, Masque, Passerelle)

4. **Appliquer les modifications**
   - Cliquer sur "Appliquer"
   - Confirmer les changements
   - Attendre la confirmation

### Gestion des Profils

#### Créer un Profil

1. Configurer les paramètres réseau souhaités
2. Cliquer sur "Sauvegarder le profil"
3. Entrer un nom descriptif (ex: "Bureau", "Maison", "VPN")
4. Confirmer la sauvegarde

#### Charger un Profil

1. Cliquer sur "Charger un profil"
2. Sélectionner le profil dans la liste
3. Confirmer l'application des paramètres
4. Les modifications sont appliquées automatiquement

#### Supprimer un Profil

1. Cliquer sur "Gérer les profils"
2. Sélectionner le profil à supprimer
3. Cliquer sur "Supprimer"
4. Confirmer la suppression

### Configuration DNS

#### DNS Prédéfinis

- **Google DNS**
  - Préféré : 8.8.8.8
  - Alternatif : 8.8.4.4

- **Cloudflare DNS**
  - Préféré : 1.1.1.1
  - Alternatif : 1.0.0.1

#### DNS Personnalisés

1. Sélectionner "DNS personnalisé"
2. Entrer les adresses DNS
3. Cliquer sur "Appliquer"

#### Flush Cache DNS

1. Cliquer sur "Outils"
2. Sélectionner "Flush DNS Cache"
3. Confirmer l'opération

### Diagnostic Réseau

#### Test de Connectivité

1. Aller dans l'onglet "Diagnostic"
2. Entrer une adresse (ex: google.com)
3. Cliquer sur "Ping"
4. Analyser les résultats

#### Traceroute

1. Dans l'onglet "Diagnostic"
2. Entrer l'adresse de destination
3. Cliquer sur "Traceroute"
4. Observer le chemin réseau

---

## ⚙ Configuration

### Fichiers de Configuration

Les fichiers de configuration sont stockés dans :
```
%APPDATA%\NetIPConfigClassic\
├── config.json          # Configuration de l'application
├── profiles\            # Profils sauvegardés
│   ├── profil1.json
│   ├── profil2.json
│   └── ...
└── logs\                # Fichiers de logs
    └── app.log
```

### Structure d'un Profil

```json
{
  "Name": "Profil Bureau",
  "AdapterName": "Ethernet",
  "UseDHCP": false,
  "IPAddress": "192.168.1.100",
  "SubnetMask": "255.255.255.0",
  "DefaultGateway": "192.168.1.1",
  "PreferredDNS": "8.8.8.8",
  "AlternateDNS": "8.8.4.4",
  "EnableIPv6": true
}
```

### Paramètres de l'Application

```json
{
  "Language": "fr-FR",
  "Theme": "Light",
  "AutoStart": false,
  "MinimizeToTray": true,
  "CheckUpdates": true,
  "LogLevel": "Info"
}
```

---

## 📁 Structure du Projet

```
Net-IP-Config-Classic/
├── NetIPConfigClassic/
│   ├── Forms/
│   │   ├── MainForm.cs
│   │   ├── ProfileForm.cs
│   │   └── DiagnosticForm.cs
│   ├── Models/
│   │   ├── NetworkAdapter.cs
│   │   ├── NetworkProfile.cs
│   │   └── AppSettings.cs
│   ├── Services/
│   │   ├── NetworkService.cs
│   │   ├── ProfileService.cs
│   │   └── DiagnosticService.cs
│   ├── Utils/
│   │   ├── Logger.cs
│   │   ├── Validator.cs
│   │   └── Helper.cs
│   ├── Resources/
│   │   └── Icons/
│   ├── App.config
│   └── Program.cs
├── ScreenShots/
├── LICENSE
└── README.md
```

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Voici comment vous pouvez contribuer :

1. **Fork le projet**
2. **Créer une branche** (`git checkout -b feature/AmazingFeature`)
3. **Commit vos changements** (`git commit -m 'Add some AmazingFeature'`)
4. **Push vers la branche** (`git push origin feature/AmazingFeature`)
5. **Ouvrir une Pull Request**

### Guidelines de Contribution

- Suivre les conventions de code C#
- Documenter les nouvelles fonctionnalités
- Ajouter des tests si applicable
- Mettre à jour la documentation

---

## 📄 Licence

Ce projet est sous licence MIT. Voir [LICENSE](LICENSE) pour plus de détails.

---

## 👤 Auteur

**Regis-Scyeur**

- GitHub: [@Regis-Scyeur](https://github.com/Regis-Scyeur)
- Email: [votre-email@example.com](mailto:votre-email@example.com)

---

<div align="center">

**⭐ Si vous aimez ce projet, n'hésitez pas à lui donner une étoile ! ⭐**

</div>
