---
title: Ajuster la qualité de l'image dans un PDF
linktitle: Ajuster la qualité de l'image dans un PDF
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment ajuster la qualité de l'image dans les documents PDF à l'aide de GroupDocs.Viewer pour .NET. Suivez notre tutoriel étape par étape pour une intégration transparente.
weight: 10
url: /fr/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## Introduction
GroupDocs.Viewer for .NET est une bibliothèque puissante qui permet aux développeurs d'intégrer sans effort des fonctionnalités de rendu de documents dans leurs applications .NET. L'une des fonctionnalités clés de cette bibliothèque est la possibilité d'ajuster la qualité de l'image lors du rendu des documents PDF. Dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus d'ajustement de la qualité de l'image à l'aide de GroupDocs.Viewer pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Connaissance de base de la programmation C#.
2. Visual Studio installé sur votre système.
3. Bibliothèque GroupDocs.Viewer pour .NET téléchargée et installée. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires pour travailler avec GroupDocs.Viewer for .NET :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
 Remplacer`"Your Document Directory"` avec le chemin où vous souhaitez enregistrer les pages HTML rendues.
## Étape 2 : Définir le format du chemin du fichier de page
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Cette ligne définit le format du chemin de fichier de chaque page HTML rendue.`{0}` est un espace réservé pour le numéro de page.
## Étape 3 : Ajuster la qualité de l'image
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 Remplacer`"Your PDF File Path"` avec le chemin d'accès à votre document PDF.
## Étape 4 : Afficher le chemin de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cette ligne affiche le chemin où les pages HTML rendues sont enregistrées.

## Conclusion
Dans ce didacticiel, nous avons appris à ajuster la qualité de l'image lors du rendu de documents PDF à l'aide de GroupDocs.Viewer pour .NET. En suivant les étapes simples décrites ci-dessus, vous pouvez facilement personnaliser la qualité de l'image en fonction de vos besoins.
## FAQ
### Puis-je ajuster la qualité de l’image pour d’autres formats de documents que le PDF ?
Oui, GroupDocs.Viewer pour .NET prend en charge différents formats de documents et vous pouvez ajuster la qualité de l'image pour la plupart d'entre eux.
### Quelles sont les options de qualité d’image disponibles ?
GroupDocs.Viewer pour .NET propose des options de qualité d'image faible, moyenne et élevée.
### Existe-t-il un moyen de prévisualiser le document avant de le restituer avec une qualité d'image ajustée ?
Oui, vous pouvez utiliser GroupDocs.Viewer pour .NET pour générer des aperçus de documents avec différents paramètres de qualité d'image.
### GroupDocs.Viewer pour .NET nécessite-t-il une licence pour une utilisation commerciale ?
 Oui, vous devez obtenir une licence pour un usage commercial. Vous pouvez acheter une licence auprès de[ici](https://purchase.groupdocs.com/buy).
### Où puis-je obtenir de l’assistance pour GroupDocs.Viewer pour .NET ?
 Vous pouvez obtenir de l'aide sur le forum GroupDocs.Viewer[ici](https://forum.groupdocs.com/c/viewer/9).