# NetIPConfig

**Outil multi-plateforme de configuration réseau IP**

[![.NET Framework](https://img.shields.io/badge/.NET%20Framework-4.8-blue)](https://dotnet.microsoft.com/)
[![Mono](https://img.shields.io/badge/Mono-Compatible-green)](https://www.mono-project.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow. svg)](https://opensource.org/licenses/MIT)

Un projet créé en **2015** pour démontrer le développement cross-platform avec .NET Framework et Mono, permettant d'afficher les informations réseau (adresse IP, masque de sous-réseau, passerelle) sur Windows, Linux et macOS.

> 📜 **Note historique** : Ce projet témoigne d'une époque où le développement multi-plateforme en .NET était un véritable défi technique. Voir la section [Contexte historique](#-contexte-historique--le-cross-platform-avant-net-core) pour comprendre les enjeux de l'époque.

---

## 📖 Contexte historique : Le cross-platform avant .NET Core

### 🕰️ **L'époque (2002-2016)**

Lorsque ce projet a été créé en 2015, le développement multi-plateforme en .NET était **radicalement différent** d'aujourd'hui :

#### **Les défis techniques**

1. **.NET Framework = Windows uniquement**
   - .NET Framework (1.0 à 4.8) était exclusivement conçu pour Windows
   - Impossible d'exécuter du code C# nativement sur Linux ou macOS
   - Les développeurs devaient choisir entre .NET (Windows) ou Java (multi-plateforme)

2. **Mono : la solution communautaire**
   - **Mono** était une implémentation open-source indépendante de .NET Framework
   - Créé par Miguel de Icaza (Xamarin) en 2004
   - Reverse-engineering des API Microsoft pour les recréer sur Linux/macOS
   - **Problèmes majeurs** : 
     - ❌ Compatibilité partielle (certaines classes manquantes ou non implémentées)
     - ❌ Performances inférieures à .NET Framework natif
     - ❌ Bugs spécifiques à chaque plateforme
     - ❌ Documentation limitée et communauté restreinte

3. **Approches de contournement**
   ```csharp
   // Exemple réel du code de ce projet (IPInfo.cs, ligne 111)
   // SIR :06-08-2015 : Cannot rely on this method because 
   // of some classes are not implemented in Mono like : IPv4Mask
   ```
   - Il fallait **tester manuellement** chaque fonctionnalité sur chaque OS
   - Créer des **fallbacks** quand les API .NET ne fonctionnaient pas
   - Utiliser **P/Invoke** pour appeler des fonctions système natives
   - Parser des **commandes shell** (`ifconfig`, `ipconfig`) comme solution de secours

#### **Stratégies de développement cross-platform (2010-2016)**

| Approche | Avantages | Inconvénients |
|----------|-----------|---------------|
| **Mono** | Code C# partagé | Compatibilité partielle, bugs |
| **Xamarin** | UI natives iOS/Android | Coût élevé (license payante) |
| **Java** | Vrai cross-platform | Pas de C#, performance |
| **C/C++** | Performance maximale | Complexité, pas de GC |
| **Commandes shell** | Toujours disponible | Fragile, parsing manuel |

#### **Ce projet illustre ces défis**

```csharp
// Détection OS avec P/Invoke (OS.cs)
[DllImport("libc")]
static extern int uname(IntPtr buf); // Appel système Unix

// Fallback sur shell quand .NET échoue (IPInfo.cs)
switch (OS.Type)
{
    case OSType.Windows:
        Shell.Command = "ipconfig";
        break;
    case OSType.Linux:
        Shell.Command = "ifconfig";
        Shell.Arguments = "eth0";
        break;
    case OSType.MacOSX:
        Shell.Command = "ifconfig";
        Shell.Arguments = "en0";
        break;
}
```

### 🚀 **La révolution .NET Core (2016)**

En **2016**, Microsoft a tout changé avec .NET Core :
- ✅ Open-source complet (MIT License)
- ✅ Cross-platform **natif** (Windows, Linux, macOS)
- ✅ Performance supérieure à .NET Framework
- ✅ API unifiées fonctionnant partout
- ✅ Support officiel Microsoft sur toutes plateformes

**Aujourd'hui (.NET 6/7/8)**, le code de ce projet tiendrait en quelques lignes :
```csharp
// Version moderne (.NET 8)
var interfaces = NetworkInterface.GetAllNetworkInterfaces();
var ipProps = interfaces.First().GetIPProperties();
// Tout fonctionne partout, sans Mono ni shell !
```

### 💡 **Pourquoi ce projet reste pertinent**

1. **Témoignage historique** : comprendre d'où vient .NET
2. **Apprécier le progrès** : mesurer le chemin parcouru
3. **Techniques avancées** : P/Invoke, parsing, détection OS
4. **Expérience réelle** : résolution de problèmes complexes avant les outils modernes

---

## 🚀 Fonctionnalités

- ✅ Détection automatique du système d'exploitation (Windows/Linux/macOS)
- ✅ Récupération des informations réseau via : 
  - Commandes shell natives (`ipconfig`, `ifconfig`)
  - API .NET Framework (avec fallback pour Mono)
- ✅ Trois interfaces utilisateur :
  - **Application Windows Forms** - Interface graphique native
  - **Application Web ASP.NET** - Interface web responsive avec Bootstrap
  - **Application MVC ASP.NET** - Architecture MVC complète

## 📸 Captures d'écran

### Windows
![Windows ScreenShot](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/NetIPConfig-Windows.PNG)

![Linux ScreenShot](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/NetIpConfig-Linux.png)

![MacOSX ScreenShot](https://raw.githubusercontent.com/Regis-Scyeur/Net-IP-Config-Classic/master/ScreenShots/NetIPConfig-MacOSX.png)

## 🏗️ Structure du projet

```
NetIPConfig/
├── ZebraPuma.Forms.NetIPConfig/     # Application Windows Forms
├── ZebraPuma.Web.NetIPConfig/       # Application Web ASP.NET
├── ZebraPuma.Mvc.NetIPConfig/       # Application ASP.NET MVC
└── ZebraPuma.Tools.dll/             # Bibliothèque partagée
    ├── IPInfo.cs                    # Récupération des infos réseau
    ├── OS.cs                        # Détection du système d'exploitation
    ├── Shell.cs                     # Exécution de commandes shell
    └── ImageHelper.cs               # Utilitaires graphiques
```

## 🔧 Prérequis

- **Windows** : Visual Studio 2015+ avec .NET Framework 4.8
- **Linux/macOS** : Mono runtime (pour exécuter les applications .NET)

## 🚀 Installation et exécution

### Sur Windows

```bash
# Cloner le repository
git clone https://github.com/Regis-Scyeur/Net-IP-Config-Classic. git
cd Net-IP-Config-Classic

# Ouvrir avec Visual Studio
start NetIPConfig.sln

# Ou compiler en ligne de commande
msbuild NetIPConfig.sln /p:Configuration=Release
```

### Sur Linux/macOS (avec Mono)

```bash
# Installer Mono
# Ubuntu/Debian: 
sudo apt-get install mono-complete

# macOS (avec Homebrew):
brew install mono

# Compiler le projet
msbuild NetIPConfig.sln /p:Configuration=Release

# Exécuter l'application Forms
mono ZebraPuma.Forms.NetIPConfig/bin/Release/NetIPConfig.exe
```

### Application Web

```bash
# Lancer le serveur de développement IIS Express (Windows)
# ou configurer avec xsp4 (Mono)
xsp4 --port 8080 --path ZebraPuma.Web.NetIPConfig
```

## 💡 Utilisation de la bibliothèque

```csharp
using ZebraPuma.Tools;

// Détecter le système d'exploitation
OSType os = OS.Type; // Windows, Linux ou MacOSX
string hostname = OS.HostName;

// Récupérer les informations réseau via shell
IPInfo ipInfo = IPInfo.GetIPInfo(IPsource.Shell);
Console.WriteLine($"IP: {ipInfo.IPAddress}");
Console.WriteLine($"Masque: {ipInfo.SubNet}");
Console.WriteLine($"Passerelle: {ipInfo.Gateway}");

// Ou via .NET Framework (peut ne pas fonctionner sur Mono)
IPInfo ipInfo2 = IPInfo.GetIPInfo(IPsource.FrameWork);
```

## 📋 Technologies utilisées

- **.NET Framework 4.8**
- **Mono** (pour Linux/macOS)
- **Windows Forms** (interface graphique)
- **ASP.NET Web Forms & MVC**
- **Bootstrap** (pour l'interface web)
- **Regex** (parsing des sorties shell)
- **P/Invoke** (appels natifs pour détection macOS via `uname`)

## 🔍 Points techniques intéressants

### Détection macOS avec P/Invoke
```csharp
[DllImport("libc")]
static extern int uname(IntPtr buf);

private static bool IsMacOS()
{
    IntPtr buf = Marshal.AllocHGlobal(8192);
    if (uname(buf) == 0)
    {
        string os = Marshal.PtrToStringAnsi(buf);
        if (os == "Darwin") return true;
    }
    Marshal.FreeHGlobal(buf);
    return false;
}
```

### Parsing d'adresses IP hexadécimales
```csharp
// Gère les formats comme "0x0100007F" (127.0.0.1 en hex)
if (Address.StartsWith("0x"))
{
    Address = String.Join(".", 
        Split(Address.TrimStart("0x".ToCharArray()), 2)
        .Select(item => int.Parse(item, NumberStyles.HexNumber)));
}
```

## ⚠️ Limitations connues

- Sur Mono, certaines classes .NET ne sont pas implémentées (ex: `IPv4Mask`)
- Les commandes shell utilisées peuvent varier selon les distributions Linux
- Nécessite des privilèges appropriés pour exécuter `ifconfig` sur certains systèmes
- Pas de support IPv6
- Interface réseau fixe (`eth0`, `en0`) - pas de détection automatique

## 🔮 Évolution possible : Migration vers .NET moderne

Ce projet pourrait être modernisé avec .NET 8 :

### Avantages d'une migration
- ✅ Cross-platform natif (sans Mono)
- ✅ Performance 3-5x supérieure
- ✅ API réseau complètes et fiables
- ✅ Support à long terme (LTS)
- ✅ UI moderne (Avalonia, .NET MAUI, Blazor)

### Exemple de code moderne
```csharp
// .NET 8 - Remplacerait tout le parsing shell
using System.Net.NetworkInformation;

var interfaces = NetworkInterface.GetAllNetworkInterfaces()
    .Where(i => i.NetworkInterfaceType == NetworkInterfaceType.Ethernet 
             && i.OperationalStatus == OperationalStatus.Up);

foreach (var iface in interfaces)
{
    var props = iface.GetIPProperties();
    var ipv4 = props.UnicastAddresses
        .FirstOrDefault(a => a.Address.AddressFamily == AddressFamily.InterNetwork);
    
    Console.WriteLine($"IP: {ipv4?.Address}");
    Console.WriteLine($"Masque: {ipv4?.IPv4Mask}");
    Console.WriteLine($"Passerelle: {props.GatewayAddresses.FirstOrDefault()?.Address}");
}
```

### Roadmap potentielle
- [ ] Migration vers .NET 8 (cross-platform natif)
- [ ] Interface CLI avec `System.CommandLine`
- [ ] UI moderne avec Avalonia (desktop) ou Blazor (web)
- [ ] Support IPv6
- [ ] Détection automatique de toutes les interfaces réseau
- [ ] Tests unitaires
- [ ] Package NuGet
- [ ] Conteneurisation Docker

## 📚 Ressources et références

- [Histoire de .NET et Mono](https://en.wikipedia.org/wiki/Mono_(software))
- [.NET Framework vs .NET Core](https://learn.microsoft.com/en-us/dotnet/standard/choosing-core-framework-server)
- [Migration de .NET Framework vers .NET moderne](https://learn.microsoft.com/en-us/dotnet/core/porting/)

## 📄 Licence

Ce projet est sous licence MIT.  Voir le fichier [LICENSE](LICENSE) pour plus de détails. 

**Copyright (c) 2015-2025 Regis-Scyeur**

## 👤 Auteur

**Regis-Scyeur**
- GitHub: [@Regis-Scyeur](https://github.com/Regis-Scyeur)
- Expérience .NET : Framework (2010-2023) → .NET Core/Modern (2016-présent)

---

<div align="center">

**⭐ Projet créé en 2015 - Témoin de l'évolution .NET ⭐**

*De l'ère Mono au .NET moderne : un voyage de 10 ans dans l'écosystème .NET*

</div>
