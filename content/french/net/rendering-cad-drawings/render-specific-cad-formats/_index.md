---
title: Formats CAO spécifiques au rendu (CF2)
linktitle: Formats CAO spécifiques au rendu (CF2)
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer des formats CAO spécifiques tels que CF2 en HTML, JPG, PNG et PDF à l'aide de Groupdocs.Viewer pour .NET.
type: docs
weight: 12
url: /fr/net/rendering-cad-drawings/render-specific-cad-formats/
---
## Introduction
Dans ce didacticiel, nous explorerons comment restituer des formats CAO spécifiques à l'aide de Groupdocs.Viewer pour .NET. Groupdocs.Viewer est une puissante API de visualisation de documents qui permet aux développeurs d'afficher plus de 170 types de documents dans leurs applications sans nécessiter d'installation de logiciel externe. Plus précisément, nous nous concentrerons sur le rendu des formats CAO tels que CF2 vers divers formats de sortie tels que HTML, JPG, PNG et PDF.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Visual Studio installé sur votre système.
-  Groupdocs.Viewer pour le SDK .NET. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).
- Connaissance de base du langage de programmation C#.
## Importer des espaces de noms
Tout d’abord, importons les espaces de noms nécessaires au rendu des formats CAO.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Maintenant, décomposons chaque exemple en plusieurs étapes :
## Rendre CF2 en HTML
### Étape 1 : Définissez le répertoire de sortie dans lequel le code HTML rendu sera enregistré.
```csharp
string outputDirectory = "Your Document Directory";
```
### Étape 2 : Définissez le format du chemin de fichier pour la sortie HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Étape 3 : initialisez l’objet Viewer et spécifiez le fichier CF2 d’entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Définir des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendu CF2 en JPG
### Étape 1 : Définissez le format du chemin de fichier pour la sortie JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Étape 2 : initialisez l'objet Viewer et spécifiez le fichier CF2 d'entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Définir des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendu CF2 en PNG

### Étape 1 : Définissez le format du chemin de fichier pour la sortie PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Étape 2 : initialisez l'objet Viewer et spécifiez le fichier CF2 d'entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Définir des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendre CF2 en PDF
### Étape 1 : Définissez le format du chemin de fichier pour la sortie PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Étape 2 : initialisez l'objet Viewer et spécifiez le fichier CF2 d'entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Définir des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à restituer des formats de CAO spécifiques tels que CF2 à l'aide de Groupdocs.Viewer pour .NET. En suivant le guide étape par étape, vous pouvez facilement intégrer des fonctionnalités de rendu de documents dans vos applications .NET.
## FAQ
### Groupdocs.Viewer peut-il restituer d'autres formats de CAO en dehors de CF2 ?
Oui, Groupdocs.Viewer prend en charge une large gamme de formats CAO, notamment DWG, DXF, DGN, etc.
### Groupdocs.Viewer est-il adapté au rendu de documents dans des applications Web ?
Absolument, Groupdocs.Viewer peut être intégré de manière transparente aux applications Web pour restituer des documents directement dans le navigateur.
### Groupdocs.Viewer nécessite-t-il des dépendances externes pour le rendu ?
Non, Groupdocs.Viewer est une API autonome et ne nécessite aucune dépendance externe ni installation de logiciel.
### Puis-je personnaliser les options de rendu en fonction de mes besoins ?
Oui, Groupdocs.Viewer propose diverses options de rendu qui peuvent être personnalisées pour répondre à vos besoins spécifiques.
### Existe-t-il une version d'essai disponible pour Groupdocs.Viewer ?
 Oui, vous pouvez obtenir une version d'essai gratuite de Groupdocs.Viewer à partir de[ici](https://releases.groupdocs.com/).