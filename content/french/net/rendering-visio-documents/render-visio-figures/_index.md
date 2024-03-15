---
title: Rendu des figures Visio
linktitle: Rendu des figures Visio
second_title: API GroupDocs.Viewer .NET
description: Apprenez à restituer des figures Visio à l'aide de GroupDocs.Viewer pour .NET avec ce document complet. Améliorez les capacités de visualisation de documents dans vos applications .NET.
type: docs
weight: 10
url: /fr/net/rendering-visio-documents/render-visio-figures/
---
## Introduction
À l'ère numérique d'aujourd'hui, le rendu des documents joue un rôle crucial dans diverses applications. Qu'il s'agisse d'afficher des documents sur un site Web ou de les convertir dans différents formats, un rendu efficace est essentiel. GroupDocs.Viewer pour .NET fournit une solution robuste pour afficher et manipuler des documents dans les applications .NET. Dans ce didacticiel, nous aborderons le rendu des figures Visio à l'aide de GroupDocs.Viewer pour .NET, en décomposant le processus en étapes simples.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1. Configuration de l'environnement : assurez-vous de disposer d'un environnement de travail pour le développement .NET.
2.  GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET à partir du[lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Compréhension de base de C# : Familiarisez-vous avec les principes fondamentaux du langage de programmation C#.
4. Exemple de document Visio : préparez un exemple de document Visio pour le rendu.

## Importer des espaces de noms
Dans votre projet C#, commencez par importer les espaces de noms nécessaires :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Rendu au format HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Répertoire de sortie : définissez le répertoire dans lequel le HTML rendu sera enregistré.
- Format du chemin du fichier de page : spécifiez le format du chemin de la page HTML.
- Initialisation de la visionneuse : initialisez l'objet Visionneuse avec le chemin d'accès au document Visio.
- Options d'affichage HTML : configurez les options de rendu HTML.
- Options de rendu Visio : définissez les options spécifiques au rendu Visio, telles que le rendu uniquement des figures et de la largeur des figures.
## 2. Rendu au format JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Semblable au rendu au format HTML, configurez les options de rendu au format JPG.
## 3. Rendu au format PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- La configuration du rendu au format PNG suit un modèle similaire à celui du rendu JPG.
## 4. Rendu au format PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Pour le rendu au format PDF, configurez les options spécifiques au format PDF.

## Conclusion
Dans ce didacticiel, nous avons expliqué comment restituer des figures Visio à l'aide de GroupDocs.Viewer pour .NET. En suivant le guide étape par étape, vous pouvez intégrer de manière transparente les capacités de rendu de documents dans vos applications .NET, améliorant ainsi l'expérience utilisateur et la productivité.
## FAQ
### Puis-je personnaliser les options de rendu des figures Visio ?
Oui, GroupDocs.Viewer pour .NET fournit des options étendues pour personnaliser le rendu, notamment la largeur des figures, le rendu des figures uniquement, et bien plus encore.
### GroupDocs.Viewer pour .NET est-il adapté au rendu de documents à grande échelle ?
Absolument, GroupDocs.Viewer pour .NET est optimisé pour gérer efficacement le rendu de documents à grande échelle.
### GroupDocs.Viewer prend-il en charge d'autres formats de documents que Visio ?
Oui, GroupDocs.Viewer prend en charge un large éventail de formats de documents, notamment PDF, Microsoft Office, AutoCAD, etc.
### Puis-je intégrer GroupDocs.Viewer dans des applications Web ?
Oui, GroupDocs.Viewer peut être intégré de manière transparente aux applications Web pour la visualisation et la manipulation de documents.
### Existe-t-il une version d'essai disponible pour tester avant d'acheter ?
Oui, vous pouvez bénéficier d'un essai gratuit auprès du[site web](https://releases.groupdocs.com/) pour tester les capacités de GroupDocs.Viewer pour .NET.