---
"description": "Optimisez vos applications .NET avec GroupDocs.Viewer pour une visualisation fluide de vos documents. Suivez notre guide étape par étape et intégrez facilement de puissantes fonctionnalités de visualisation de documents."
"linktitle": "Définir la licence à partir du flux"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Définir la licence à partir du flux"
"url": "/fr/net/getting-started/set-license-from-stream/"
"weight": 11
---

# Définir la licence à partir du flux

## Introduction
Vous souhaitez doter vos applications .NET de fonctionnalités avancées de visualisation de documents ? GroupDocs.Viewer pour .NET offre une solution complète pour intégrer facilement des fonctionnalités de visualisation de documents à vos projets. Dans ce tutoriel, nous allons explorer comment exploiter GroupDocs.Viewer pour .NET pour enrichir vos applications de puissantes fonctionnalités de visualisation de documents. 

![Définir la licence du flux avec GroupDocs.Viewer pour .NET](/viewer/getting-started/set-license-from-stream.png)

## Prérequis
Avant de nous lancer dans le processus d’intégration, assurez-vous que les conditions préalables suivantes sont en place :
1. Connaissances de base du développement .NET : une familiarité avec C# et le framework .NET est essentielle pour suivre ce didacticiel.
   
2. Package GroupDocs.Viewer pour .NET : Assurez-vous d'avoir téléchargé et installé le package GroupDocs.Viewer pour .NET. Vous pouvez l'obtenir depuis le [lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Accès à la documentation GroupDocs : Conservez le [documentation](https://tutorials.groupdocs.com/viewer/net/) pratique pour les tutoriels pendant le processus d'intégration.

## Importer des espaces de noms
Pour commencer, importez les espaces de noms nécessaires dans votre application .NET. Suivez ces étapes :
### Étape 1 : ouvrez votre projet .NET.
Assurez-vous que votre projet .NET est ouvert dans votre environnement de développement préféré.
### Étape 2 : ajouter l’espace de noms GroupDocs.Viewer.
Dans votre fichier de code, ajoutez l'espace de noms suivant pour accéder aux fonctionnalités de GroupDocs.Viewer :
```csharp
using System;
using System.IO;
```
## Définir la licence à partir du flux
L'étape suivante consiste à définir la licence à partir d'un flux. Suivez ces étapes détaillées :
### Étape 1 : définir le répertoire de sortie.
Définissez le répertoire dans lequel vos documents seront stockés en définissant le répertoire de sortie :
```csharp
string outputDirectory = "Your Document Directory";
```
### Étape 2 : Vérifiez l’existence du fichier de licence.
Vérifiez si le fichier de licence existe dans le répertoire de votre projet :
```csharp
if (File.Exists(Utils.LicensePath))
```
### Étape 3 : définir la licence.
Si le fichier de licence existe, définissez la licence à l'aide du flux fourni :
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Étape 4 : Gérer l’absence de permis.
Si le fichier de licence n'est pas trouvé, fournissez des instructions pour obtenir une licence :
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Conclusion
Félicitations ! Vous avez appris à intégrer GroupDocs.Viewer pour .NET à vos applications. Grâce à cet outil performant, vous pouvez désormais visualiser facilement différents formats de documents dans vos projets .NET, améliorant ainsi l'expérience utilisateur et la productivité.
## FAQ
### Ai-je besoin d’une licence pour utiliser GroupDocs.Viewer pour .NET ?
Oui, vous avez besoin d'une licence pour utiliser GroupDocs.Viewer pour .NET. Vous pouvez obtenir une licence temporaire ou permanente sur le site web de GroupDocs.
### Puis-je intégrer GroupDocs.Viewer dans mon application ASP.NET ?
Absolument ! GroupDocs.Viewer pour .NET s'intègre parfaitement aux applications de bureau et Web, y compris ASP.NET.
### Quels formats de documents sont pris en charge par GroupDocs.Viewer ?
GroupDocs.Viewer prend en charge une large gamme de formats de documents, notamment PDF, Microsoft Office (Word, Excel, PowerPoint), images, etc.
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer pour .NET est compatible avec .NET Framework et .NET Core.
### Puis-je personnaliser l'interface de la visionneuse en fonction du thème de mon application ?
Oui, GroupDocs.Viewer fournit des options de personnalisation étendues, vous permettant d'adapter l'interface de la visionneuse pour qu'elle corresponde parfaitement au thème de votre application.