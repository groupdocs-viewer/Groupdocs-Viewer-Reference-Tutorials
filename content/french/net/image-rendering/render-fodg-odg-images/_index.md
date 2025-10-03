---
"description": "Apprenez à convertir des images FODG et ODG en HTML, JPG, PNG et PDF avec GroupDocs.Viewer pour .NET. Optimisez la gestion de vos documents."
"linktitle": "Rendu des images FODG et ODG"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu des images FODG et ODG"
"url": "/fr/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# Rendu des images FODG et ODG

## Introduction
Dans le monde du développement logiciel, la gestion efficace des formats de documents est primordiale. GroupDocs.Viewer pour .NET est un outil puissant conçu pour simplifier le rendu des images FODG et ODG dans les applications .NET. Ce tutoriel vous guidera pas à pas pour restituer ces images dans différents formats, tels que HTML, JPG, PNG et PDF, grâce à GroupDocs.Viewer pour .NET.

![Rendu des images FODG et ODG avec GroupDocs.Viewer pour .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
1. GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET depuis [ici](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework : assurez-vous que .NET Framework est installé sur votre système.
3. Connaissances de base en C# : Une connaissance du langage de programmation C# sera utile.

## Importer des espaces de noms
Avant de commencer l’implémentation, importez les espaces de noms nécessaires :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Étape 1 : définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Remplacer `"Your Document Directory"` avec le chemin du répertoire où vous souhaitez enregistrer les images rendues.
## Étape 2 : Rendre au format HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Cette étape rend l’image FODG au format HTML.
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
Dans ce tutoriel, nous avons exploré comment restituer des images FODG et ODG dans différents formats à l'aide de GroupDocs.Viewer pour .NET. En suivant ces étapes, vous pourrez intégrer facilement les fonctionnalités de rendu de documents à vos applications .NET.
## FAQ
### GroupDocs.Viewer pour .NET est-il compatible avec toutes les versions de .NET Framework ?
GroupDocs.Viewer pour .NET est compatible avec une large gamme de versions de .NET Framework, y compris les plus récentes.
### Puis-je restituer des documents de manière asynchrone avec GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer pour .NET fournit des fonctionnalités de rendu asynchrone pour des performances améliorées.
### GroupDocs.Viewer pour .NET prend-il en charge le rendu de documents chiffrés ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu de documents chiffrés avec des clés de déchiffrement appropriées.
### Est-il possible de personnaliser la sortie de rendu avec GroupDocs.Viewer pour .NET ?
Absolument, GroupDocs.Viewer pour .NET propose diverses options de personnalisation pour adapter la sortie de rendu en fonction de vos besoins.
### Puis-je restituer des documents à partir d’emplacements de stockage distants à l’aide de GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu de documents à partir d’emplacements de stockage locaux et distants.