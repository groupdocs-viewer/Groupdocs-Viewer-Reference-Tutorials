---
"description": "Apprenez à générer des images SVG et SVGZ avec GroupDocs.Viewer pour .NET. Convertissez facilement des graphiques vectoriels en HTML, JPG, PNG et PDF."
"linktitle": "Rendu d'images SVG et SVGZ"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu d'images SVG et SVGZ"
"url": "/fr/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# Rendu d'images SVG et SVGZ

## Introduction
Dans ce tutoriel, nous vous guiderons dans le rendu d'images SVG et SVGZ avec GroupDocs.Viewer pour .NET. GroupDocs.Viewer pour .NET est une puissante API de rendu de documents qui permet aux développeurs de générer différents formats de documents dans leurs applications .NET. SVG et SVGZ sont des formats d'image populaires pour les graphiques vectoriels. Avec GroupDocs.Viewer pour .NET, vous pouvez facilement les générer dans différents formats de sortie tels que HTML, JPG, PNG et PDF.

![Rendu d'images SVG et SVGZ avec GroupDocs.Viewer pour .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Prérequis
Avant de commencer, assurez-vous que les prérequis suivants sont installés et configurés :
1. GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET depuis [ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : assurez-vous de disposer d’un environnement de développement fonctionnel pour le développement .NET, tel que Visual Studio.
3. Exemple de fichier SVGZ : préparez un exemple de fichier SVGZ pour les tests.

## Importer des espaces de noms
Avant de plonger dans le code, importons les espaces de noms nécessaires :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Étape 1 : Convertir SVGZ en HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Étape 2 : Convertir SVGZ en JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Étape 3 : Convertir SVGZ en PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Étape 4 : Convertir SVGZ en PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusion
Dans ce tutoriel, nous avons appris à générer des images SVG et SVGZ avec GroupDocs.Viewer pour .NET. En quelques étapes simples, vous pouvez convertir des images SVGZ en différents formats de sortie, tels que HTML, JPG, PNG et PDF, pour les rendre accessibles et lisibles dans différents environnements.
## FAQ
### GroupDocs.Viewer peut-il restituer d’autres formats d’image ?
Oui, GroupDocs.Viewer prend en charge le rendu de divers formats d'image, notamment PNG, JPEG, BMP, TIFF, GIF, etc.
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer est compatible avec .NET Framework et .NET Core.
### Puis-je personnaliser les options de rendu ?
Oui, GroupDocs.Viewer fournit des options de rendu étendues vous permettant de personnaliser la sortie en fonction de vos besoins.
### GroupDocs.Viewer nécessite-t-il des dépendances tierces ?
Non, GroupDocs.Viewer est une API autonome et ne nécessite aucune dépendance tierce pour le rendu des documents.
### Existe-t-il une version d'essai disponible pour tester ?
Oui, vous pouvez télécharger une version d'essai gratuite de GroupDocs.Viewer à partir de [ici](https://releases.groupdocs.com/) pour évaluer ses caractéristiques avant de procéder à un achat.