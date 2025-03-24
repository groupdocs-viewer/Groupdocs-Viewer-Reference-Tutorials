---
title: Rendre les images FODG et ODG
linktitle: Rendre les images FODG et ODG
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer des images FODG et ODG au format HTML, JPG, PNG et PDF à l'aide de GroupDocs.Viewer pour .NET. Améliorez la gestion de vos documents.
weight: 15
url: /fr/net/image-rendering/render-fodg-odg-images/
---
## Introduction
Dans le monde du développement de logiciels, une gestion efficace des formats de documents est primordiale. GroupDocs.Viewer pour .NET est un outil puissant conçu pour simplifier le processus de rendu des images FODG et ODG dans les applications .NET. Ce didacticiel vous guidera à travers les étapes nécessaires au rendu de ces images dans différents formats, tels que HTML, JPG, PNG et PDF, à l'aide de GroupDocs.Viewer pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1.  GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET à partir de[ici](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework : assurez-vous que .NET Framework est installé sur votre système.
3. Connaissance de base de C# : Une connaissance du langage de programmation C# sera utile.

## Importer des espaces de noms
Avant de commencer l'implémentation, importez les espaces de noms nécessaires :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
 Remplacer`"Your Document Directory"`avec le chemin du répertoire dans lequel vous souhaitez enregistrer les images rendues.
## Étape 2 : Rendu au format HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Cette étape restitue l'image FODG au format HTML.
## Étape 3 : Rendu au format JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Ici, l'image FODG est rendue au format JPG.
## Étape 4 : Rendu au format PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Cette étape convertit l'image FODG au format PNG.
## Étape 5 : Rendu au format PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Enfin, l'image FODG est rendue au format PDF.

## Conclusion
Dans ce didacticiel, nous avons exploré comment restituer des images FODG et ODG dans différents formats à l'aide de GroupDocs.Viewer pour .NET. En suivant ces étapes, vous pouvez intégrer de manière transparente les fonctionnalités de rendu de documents dans vos applications .NET.
## FAQ
### GroupDocs.Viewer pour .NET est-il compatible avec toutes les versions de .NET Framework ?
GroupDocs.Viewer pour .NET est compatible avec une large gamme de versions de .NET Framework, y compris les dernières.
### Puis-je restituer des documents de manière asynchrone avec GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer pour .NET fournit des fonctionnalités de rendu asynchrone pour des performances améliorées.
### GroupDocs.Viewer pour .NET prend-il en charge le rendu des documents cryptés ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu des documents cryptés avec les clés de déchiffrement appropriées.
### Est-il possible de personnaliser la sortie de rendu avec GroupDocs.Viewer pour .NET ?
Absolument, GroupDocs.Viewer pour .NET propose diverses options de personnalisation pour adapter la sortie de rendu en fonction de vos besoins.
### Puis-je restituer des documents à partir d’emplacements de stockage distants à l’aide de GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu des documents à partir d'emplacements de stockage locaux et distants.