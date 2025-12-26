# Net IP Config Classic

Application Windows Forms pour la configuration réseau et le diagnostic IP.

## Badges

![.NET Framework](https://img.shields.io/badge/.NET%20Framework-4.7.2-blue)
![Windows Forms](https://img.shields.io/badge/Windows%20Forms-C%23-purple)
![Version](https://img.shields.io/badge/version-1.0.0-green)
![License](https://img.shields.io/badge/license-MIT-yellow)

## 📋 Table des matières

- [Description](#description)
- [Fonctionnalités](#fonctionnalités)
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Structure du projet](#structure-du-projet)
- [Captures d'écran](#captures-décran)
- [Technologies utilisées](#technologies-utilisées)
- [Contribuer](#contribuer)
- [Licence](#licence)
- [Auteur](#auteur)

## Description

Net IP Config Classic est une application Windows Forms développée en C# qui permet de :
- Configurer les paramètres réseau (IP, DNS, passerelle)
- Effectuer des diagnostics réseau (ping, traceroute, lookup DNS)
- Gérer les profils de configuration réseau
- Afficher les informations détaillées des cartes réseau

## ✨ Fonctionnalités

### Configuration réseau
- ✅ Configuration IP statique ou DHCP
- ✅ Configuration DNS (primaire et secondaire)
- ✅ Configuration de la passerelle par défaut
- ✅ Sélection de la carte réseau à configurer
- ✅ Validation des adresses IP saisies
- ✅ Application immédiate des changements

### Diagnostic réseau
- 🔍 **Ping** : Test de connectivité réseau
- 🔍 **Traceroute** : Traçage du chemin réseau
- 🔍 **DNS Lookup** : Résolution de noms de domaine
- 🔍 **Informations système** : Affichage des détails des cartes réseau

### Gestion de profils
- 💾 Sauvegarde de profils de configuration
- 📂 Chargement rapide de profils existants
- 🗑️ Suppression de profils
- 📝 Export/Import de profils

### Interface utilisateur
- 🎨 Interface moderne et intuitive
- 📊 Affichage en temps réel des informations
- 🔔 Notifications et messages d'état
- 📋 Logs détaillés des opérations

## 🔧 Prérequis

- Windows 7 ou supérieur
- .NET Framework 4.7.2 ou supérieur
- Droits administrateur (pour modifier la configuration réseau)

## 📥 Installation

### Option 1 : Installation depuis les releases
1. Téléchargez la dernière release depuis la page [Releases](https://github.com/Regis-Scyeur/Net-IP-Config-Classic/releases)
2. Extrayez l'archive ZIP
3. Lancez `NetIPConfig.exe` en tant qu'administrateur

### Option 2 : Compilation depuis les sources
1. Clonez le dépôt :
```bash
git clone https://github.com/Regis-Scyeur/Net-IP-Config-Classic.git
```

2. Ouvrez le projet dans Visual Studio 2019 ou supérieur

3. Restaurez les packages NuGet si nécessaire

4. Compilez le projet en mode Release

5. L'exécutable se trouvera dans `bin/Release/`

## 🚀 Utilisation

### Lancement de l'application

**Important** : L'application doit être lancée avec des droits administrateur pour pouvoir modifier la configuration réseau.

1. Clic droit sur `NetIPConfig.exe`
2. Sélectionnez "Exécuter en tant qu'administrateur"

### Configuration d'une carte réseau

1. Sélectionnez la carte réseau dans la liste déroulante
2. Choisissez entre DHCP ou IP statique
3. Si IP statique :
   - Entrez l'adresse IP
   - Entrez le masque de sous-réseau
   - Entrez la passerelle par défaut
   - Entrez les serveurs DNS (primaire et secondaire)
4. Cliquez sur "Appliquer" pour enregistrer les modifications

### Utilisation des outils de diagnostic

#### Ping
1. Accédez à l'onglet "Diagnostic"
2. Entrez l'adresse IP ou le nom d'hôte
3. Cliquez sur "Ping"
4. Consultez les résultats dans la zone de texte

#### Traceroute
1. Accédez à l'onglet "Diagnostic"
2. Entrez l'adresse IP ou le nom d'hôte de destination
3. Cliquez sur "Traceroute"
4. Suivez le chemin réseau dans les résultats

#### DNS Lookup
1. Accédez à l'onglet "Diagnostic"
2. Entrez le nom de domaine
3. Cliquez sur "Lookup"
4. Visualisez les informations DNS retournées

### Gestion des profils

#### Sauvegarder un profil
1. Configurez les paramètres réseau souhaités
2. Cliquez sur "Sauvegarder le profil"
3. Entrez un nom pour le profil
4. Le profil est enregistré

#### Charger un profil
1. Cliquez sur "Charger un profil"
2. Sélectionnez le profil dans la liste
3. Les paramètres sont appliqués automatiquement

## 📁 Structure du projet

```
Net-IP-Config-Classic/
│
├── NetIPConfig/
│   ├── Forms/
│   │   ├── MainForm.cs              # Formulaire principal
│   │   ├── MainForm.Designer.cs
│   │   ├── DiagnosticForm.cs        # Formulaire de diagnostic
│   │   └── ProfileManagerForm.cs    # Gestion des profils
│   │
│   ├── Classes/
│   │   ├── NetworkAdapter.cs        # Classe pour la gestion des cartes réseau
│   │   ├── NetworkConfig.cs         # Configuration réseau
│   │   ├── NetworkDiagnostics.cs    # Outils de diagnostic
│   │   └── ProfileManager.cs        # Gestion des profils
│   │
│   ├── Resources/
│   │   └── Icons/                   # Icônes de l'application
│   │
│   ├── App.config                   # Configuration de l'application
│   ├── Program.cs                   # Point d'entrée
│   └── NetIPConfig.csproj          # Fichier projet
│
├── README.md
├── LICENSE
└── .gitignore
```

## 📸 Captures d'écran

### Fenêtre principale
![Main Window](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/screenshots/main-window.png)

### Configuration réseau
![Network Config](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/screenshots/network-config.png)

### Outils de diagnostic
![Diagnostic Tools](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/screenshots/diagnostic-tools.png)

### Gestion des profils
![Profile Manager](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/screenshots/profile-manager.png)

## 🛠️ Technologies utilisées

- **Langage** : C# 7.3
- **Framework** : .NET Framework 4.7.2
- **Interface** : Windows Forms
- **IDE** : Visual Studio 2019+

### Bibliothèques principales

- `System.Net.NetworkInformation` : Pour les informations réseau
- `System.Management` : Pour l'accès WMI et la configuration réseau
- `System.Diagnostics` : Pour l'exécution de commandes système

## 🤝 Contribuer

Les contributions sont les bienvenues ! Voici comment contribuer :

1. Forkez le projet
2. Créez une branche pour votre fonctionnalité (`git checkout -b feature/AmazingFeature`)
3. Committez vos changements (`git commit -m 'Add some AmazingFeature'`)
4. Poussez vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrez une Pull Request

### Guidelines de contribution

- Respectez le style de code existant
- Ajoutez des commentaires pour le code complexe
- Testez vos modifications avant de soumettre
- Mettez à jour la documentation si nécessaire

## 📋 Roadmap

- [ ] Support de IPv6
- [ ] Interface en dark mode
- [ ] Export des logs en fichier
- [ ] Planification de changements de profils
- [ ] Support multi-langue
- [ ] Interface web pour gestion à distance
- [ ] Notifications système
- [ ] Sauvegarde automatique de configuration

## 🐛 Problèmes connus

- Nécessite des droits administrateur pour fonctionner
- Peut ne pas détecter certaines cartes réseau virtuelles
- Le traceroute peut être lent sur certains réseaux

## 📝 Changelog

### Version 1.0.0 (2024-01-15)
- ✨ Release initiale
- ✅ Configuration IP/DNS/Gateway
- ✅ Outils de diagnostic (ping, traceroute, DNS lookup)
- ✅ Gestion de profils
- ✅ Interface utilisateur moderne

## 🔐 Sécurité

Si vous découvrez une faille de sécurité, veuillez nous envoyer un email à [votre-email] plutôt que d'utiliser le système d'issues.

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## 👤 Auteur

**Regis Scyeur**
- GitHub: [@Regis-Scyeur](https://github.com/Regis-Scyeur)

## 🙏 Remerciements

- Merci à tous les contributeurs du projet
- Inspiré par les outils réseau Windows classiques
- Communauté .NET pour les ressources et la documentation

## 📞 Support

Pour obtenir de l'aide :
- 📫 Ouvrez une issue sur GitHub
- 💬 Consultez la documentation
- 🌐 Visitez la page wiki du projet

---

⭐ Si ce projet vous a été utile, n'hésitez pas à lui donner une étoile !

**Note** : Ce projet est destiné à des fins éducatives et de démonstration. Utilisez-le à vos propres risques sur des réseaux de production.