---
"description": "Découvrez comment ajuster la qualité d'image de vos documents PDF avec GroupDocs.Viewer pour .NET. Suivez notre tutoriel étape par étape pour une intégration fluide."
"linktitle": "Ajuster la qualité de l'image dans un PDF"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Ajuster la qualité de l'image dans un PDF"
"url": "/fr/net/pdf-rendering-options/adjust-image-quality-pdf/"
"weight": 10
---

# Ajuster la qualité de l'image dans un PDF

## Introduction
GroupDocs.Viewer pour .NET est une bibliothèque puissante qui permet aux développeurs d'intégrer facilement des fonctionnalités de rendu de documents à leurs applications .NET. L'une de ses fonctionnalités clés est la possibilité d'ajuster la qualité d'image lors du rendu de documents PDF. Dans ce tutoriel, nous vous expliquerons étape par étape comment ajuster la qualité d'image avec GroupDocs.Viewer pour .NET.

![Ajuster la qualité de l'image dans un PDF avec GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/adjust-image-quality-in-pdf.png)

## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Connaissances de base de la programmation C#.
2. Visual Studio installé sur votre système.
3. Bibliothèque GroupDocs.Viewer pour .NET téléchargée et installée. Vous pouvez la télécharger depuis [ici](https://releases.groupdocs.com/viewer/net/).

## Importer des espaces de noms
Tout d’abord, vous devez importer les espaces de noms nécessaires pour travailler avec GroupDocs.Viewer pour .NET :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Remplacer `"Your Document Directory"` avec le chemin où vous souhaitez enregistrer les pages HTML rendues.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Cette ligne définit le format du chemin d'accès au fichier de chaque page HTML rendue. `{0}` est un espace réservé pour le numéro de page.
## Étape 3 : Ajuster la qualité de l’image
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
Remplacer `"Your PDF File Path"` avec le chemin vers votre document PDF.
## Étape 4 : Afficher le chemin de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cette ligne affiche le chemin où les pages HTML rendues sont enregistrées.

## Conclusion
Dans ce tutoriel, nous avons appris à ajuster la qualité d'image lors du rendu de documents PDF avec GroupDocs.Viewer pour .NET. En suivant les étapes simples décrites ci-dessus, vous pouvez facilement personnaliser la qualité d'image selon vos besoins.
## FAQ
### Puis-je ajuster la qualité de l'image pour d'autres formats de documents en plus du PDF ?
Oui, GroupDocs.Viewer pour .NET prend en charge divers formats de documents et vous pouvez ajuster la qualité de l'image pour la plupart d'entre eux.
### Quelles sont les options de qualité d’image disponibles ?
GroupDocs.Viewer pour .NET fournit des options pour une qualité d'image faible, moyenne et élevée.
### Existe-t-il un moyen de prévisualiser le document avant de le rendre avec une qualité d'image ajustée ?
Oui, vous pouvez utiliser GroupDocs.Viewer pour .NET pour générer des aperçus de documents avec différents paramètres de qualité d’image.
### GroupDocs.Viewer pour .NET nécessite-t-il une licence pour une utilisation commerciale ?
Oui, vous devez obtenir une licence pour une utilisation commerciale. Vous pouvez l'acheter auprès de [ici](https://purchase.groupdocs.com/buy).
### Où puis-je obtenir de l'aide pour GroupDocs.Viewer pour .NET ?
Vous pouvez obtenir de l'aide sur le forum GroupDocs.Viewer [ici](https://forum.groupdocs.com/c/viewer/9).