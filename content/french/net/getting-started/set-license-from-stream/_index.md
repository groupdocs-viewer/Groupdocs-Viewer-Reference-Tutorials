---
title: Définir la licence à partir du flux
linktitle: Définir la licence à partir du flux
second_title: API GroupDocs.Viewer .NET
description: Améliorez vos applications .NET avec GroupDocs.Viewer pour une visualisation transparente des documents. Suivez notre guide étape par étape et intégrez sans effort de puissantes fonctionnalités de visualisation de documents.
type: docs
weight: 11
url: /fr/net/getting-started/set-license-from-stream/
---
## Introduction
Cherchez-vous à doter vos applications .NET de fonctionnalités avancées de visualisation de documents ? GroupDocs.Viewer for .NET offre une solution complète pour intégrer de manière transparente les fonctionnalités de visualisation de documents dans vos projets. Dans ce didacticiel, nous approfondirons le processus d'exploitation de GroupDocs.Viewer pour .NET pour enrichir vos applications avec de puissantes fonctionnalités de visualisation de documents. 
## Conditions préalables
Avant de nous lancer dans le processus d'intégration, assurez-vous que les conditions préalables suivantes sont remplies :
1. Connaissance de base du développement .NET : une connaissance du framework C# et .NET est essentielle pour suivre ce didacticiel.
   
2.  Package GroupDocs.Viewer pour .NET : assurez-vous d'avoir téléchargé et installé le package GroupDocs.Viewer pour .NET. Vous pouvez l'obtenir auprès du[lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
3.  Accès à la Documentation GroupDocs : conservez le[documentation](https://reference.groupdocs.com/viewer/net/) pratique pour référence pendant le processus d’intégration.

## Importer des espaces de noms
Pour commencer, importez les espaces de noms nécessaires dans votre application .NET. Suivez ces étapes:
### Étape 1 : Ouvrez votre projet .NET.
Assurez-vous que votre projet .NET est ouvert dans votre environnement de développement préféré.
### Étape 2 : ajoutez l’espace de noms GroupDocs.Viewer.
Dans votre fichier de code, ajoutez l'espace de noms suivant pour accéder aux fonctionnalités GroupDocs.Viewer :
```csharp
using System;
using System.IO;
```
## Définir la licence à partir du flux
L'étape suivante consiste à définir la licence à partir d'un flux. Suivez ces étapes détaillées :
### Étape 1 : Définir le répertoire de sortie.
Définissez le répertoire où seront stockés vos documents en définissant le répertoire de sortie :
```csharp
string outputDirectory = "Your Document Directory";
```
### Étape 2 : Vérifiez l’existence du fichier de licence.
Vérifiez si le fichier de licence existe dans le répertoire de votre projet :
```csharp
if (File.Exists(Utils.LicensePath))
```
### Étape 3 : Définir la licence.
Si le fichier de licence existe, définissez la licence à l'aide du flux fourni :
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Étape 4 : Gérer l’absence de licence.
Si le fichier de licence est introuvable, fournissez les instructions pour obtenir une licence :
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://buy.groupdocs.com/temporary-license.");
}
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment intégrer GroupDocs.Viewer pour .NET dans vos applications. Avec cet outil puissant, vous pouvez désormais visualiser sans effort différents formats de documents dans vos projets .NET, améliorant ainsi l'expérience utilisateur et la productivité.
## FAQ
### Ai-je besoin d’une licence pour utiliser GroupDocs.Viewer pour .NET ?
Oui, vous avez besoin d'une licence pour utiliser GroupDocs.Viewer pour .NET. Vous pouvez obtenir une licence temporaire ou permanente sur le site Web GroupDocs.
### Puis-je intégrer GroupDocs.Viewer dans mon application ASP.NET ?
Absolument! GroupDocs.Viewer pour .NET s'intègre de manière transparente aux applications de bureau et Web, y compris ASP.NET.
### Quels formats de documents sont pris en charge par GroupDocs.Viewer ?
GroupDocs.Viewer prend en charge un large éventail de formats de documents, notamment PDF, Microsoft Office (Word, Excel, PowerPoint), des images, etc.
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer pour .NET est compatible avec .NET Framework et .NET Core.
### Puis-je personnaliser l'interface du visualiseur en fonction du thème de mon application ?
Oui, GroupDocs.Viewer propose des options de personnalisation étendues, vous permettant d'adapter l'interface de la visionneuse pour qu'elle corresponde parfaitement au thème de votre application.