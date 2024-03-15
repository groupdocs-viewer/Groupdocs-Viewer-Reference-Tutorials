---
title: Rendre les images SVG et SVGZ
linktitle: Rendre les images SVG et SVGZ
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer des images SVG et SVGZ à l'aide de GroupDocs.Viewer pour .NET. Convertissez facilement des graphiques vectoriels en HTML, JPG, PNG et PDF.
type: docs
weight: 16
url: /fr/net/image-rendering/render-svg-svgz-images/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de rendu des images SVG et SVGZ à l'aide de GroupDocs.Viewer pour .NET. GroupDocs.Viewer pour .NET est une puissante API de rendu de documents qui permet aux développeurs de restituer différents formats de documents dans leurs applications .NET. SVG et SVGZ sont des formats d'image populaires utilisés pour les graphiques vectoriels, et avec GroupDocs.Viewer pour .NET, vous pouvez facilement les restituer dans différents formats de sortie tels que HTML, JPG, PNG et PDF.
## Conditions préalables
Avant de commencer, assurez-vous que les prérequis suivants sont installés et configurés :
1.  GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET à partir de[ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : assurez-vous de disposer d'un environnement de développement fonctionnel pour le développement .NET, tel que Visual Studio.
3. Exemple de fichier SVGZ : préparez un exemple de fichier SVGZ pour le test.

## Importer des espaces de noms
Avant de plonger dans le code, importons les espaces de noms nécessaires :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Étape 1 : rendre SVGZ en HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Étape 2 : rendre SVGZ en JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Étape 3 : rendre SVGZ en PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Étape 4 : rendre SVGZ en PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à restituer des images SVG et SVGZ à l'aide de GroupDocs.Viewer pour .NET. En quelques étapes simples, vous pouvez convertir des images SVGZ en différents formats de sortie tels que HTML, JPG, PNG et PDF, les rendant ainsi accessibles et visibles dans différents environnements.
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
Oui, vous pouvez télécharger une version d'essai gratuite de GroupDocs.Viewer à partir de[ici](https://releases.groupdocs.com/) pour évaluer ses fonctionnalités avant de faire un achat.