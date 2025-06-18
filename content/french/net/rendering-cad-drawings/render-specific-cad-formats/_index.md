---
"description": "Découvrez comment restituer des formats CAO spécifiques tels que CF2 en HTML, JPG, PNG et PDF à l'aide de Groupdocs.Viewer pour .NET."
"linktitle": "Rendu de formats CAO spécifiques (CF2)"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu de formats CAO spécifiques (CF2)"
"url": "/fr/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Rendu de formats CAO spécifiques (CF2)

## Introduction
Dans ce tutoriel, nous découvrirons comment restituer des formats CAO spécifiques avec Groupdocs.Viewer pour .NET. Groupdocs.Viewer est une puissante API de visualisation de documents qui permet aux développeurs d'afficher plus de 170 types de documents dans leurs applications sans installation de logiciel externe. Plus précisément, nous nous concentrerons sur le rendu de formats CAO tels que CF2 vers différents formats de sortie comme HTML, JPG, PNG et PDF.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Visual Studio installé sur votre système.
- Groupdocs.Viewer pour SDK .NET. Vous pouvez le télécharger depuis [ici](https://releases.groupdocs.com/viewer/net/).
- Connaissances de base du langage de programmation C#.
## Importer des espaces de noms
Tout d’abord, importons les espaces de noms nécessaires au rendu des formats CAO.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Maintenant, décomposons chaque exemple en plusieurs étapes :
## Rendre CF2 en HTML
### Étape 1 : définissez le répertoire de sortie dans lequel le code HTML rendu sera enregistré.
```csharp
string outputDirectory = "Your Document Directory";
```
### Étape 2 : définissez le format du chemin d’accès au fichier pour la sortie HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Étape 3 : initialisez l’objet Viewer et spécifiez le fichier CF2 d’entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Définissez des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendu CF2 en JPG
### Étape 1 : définissez le format du chemin de fichier pour la sortie JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Étape 2 : initialisez l’objet Viewer et spécifiez le fichier CF2 d’entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Définissez des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendu CF2 en PNG

### Étape 1 : définissez le format du chemin de fichier pour la sortie PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Étape 2 : initialisez l’objet Viewer et spécifiez le fichier CF2 d’entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Définissez des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Convertir CF2 en PDF
### Étape 1 : définissez le format du chemin d’accès au fichier pour la sortie PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Étape 2 : initialisez l’objet Viewer et spécifiez le fichier CF2 d’entrée.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Définissez des options de rendu supplémentaires si nécessaire
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusion
Dans ce tutoriel, nous avons appris à générer des rendus de formats CAO spécifiques, tels que CF2, à l'aide de Groupdocs.Viewer pour .NET. En suivant ce guide étape par étape, vous pourrez facilement intégrer des fonctionnalités de rendu de documents à vos applications .NET.
## FAQ
### Groupdocs.Viewer peut-il restituer d'autres formats CAO en dehors de CF2 ?
Oui, Groupdocs.Viewer prend en charge une large gamme de formats CAO, notamment DWG, DXF, DGN, etc.
### Groupdocs.Viewer est-il adapté au rendu de documents dans des applications Web ?
Absolument, Groupdocs.Viewer peut être intégré de manière transparente dans les applications Web pour restituer les documents directement dans le navigateur.
### Groupdocs.Viewer nécessite-t-il des dépendances externes pour le rendu ?
Non, Groupdocs.Viewer est une API autonome et ne nécessite aucune dépendance externe ni installation de logiciel.
### Puis-je personnaliser les options de rendu en fonction de mes besoins ?
Oui, Groupdocs.Viewer fournit diverses options de rendu qui peuvent être personnalisées pour répondre à vos besoins spécifiques.
### Existe-t-il une version d'essai disponible pour Groupdocs.Viewer ?
Oui, vous pouvez obtenir une version d'essai gratuite de Groupdocs.Viewer à partir de [ici](https://releases.groupdocs.com/).