---
title: Rendu des nombres
linktitle: Rendu des nombres
second_title: API GroupDocs.Viewer .NET
description: Découvrez la puissance de Groupdocs.Viewer pour .NET pour restituer les fichiers Numbers de manière transparente. Convertissez en HTML, JPG, PNG et PDF sans effort.
weight: 15
url: /fr/net/spreadsheet-rendering-options/rendering-numbers/
---
## Introduction
Bienvenue dans ce didacticiel étape par étape sur le rendu des fichiers Numbers à l'aide de Groupdocs.Viewer pour .NET. Que vous soyez un développeur chevronné ou un débutant, ce guide vous guidera tout au long du processus de conversion de documents Numbers dans différents formats. Groupdocs.Viewer for .NET est un outil puissant qui vous permet d'intégrer de manière transparente des fonctionnalités de visualisation de documents dans vos applications .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Une connaissance pratique du développement C# et .NET.
-  Groupdocs.Viewer pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.groupdocs.com/viewer/net/).
- Chemin du répertoire de votre document où les fichiers de sortie seront enregistrés.
## Importer des espaces de noms
Dans votre projet C#, assurez-vous d'importer les espaces de noms nécessaires pour utiliser la bibliothèque Groupdocs.Viewer :
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : configurer le répertoire de sortie
Avant de commencer le rendu, définissez le répertoire de sortie dans lequel les fichiers convertis seront enregistrés. Remplacez « Votre répertoire de documents » par le chemin réel :
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Rendu au format HTML multipage
Utilisez le code suivant pour convertir le fichier Numbers en HTML multipage :
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Étape 3 : Rendu au format JPG
Convertissez le fichier Numbers au format JPG avec le code suivant :
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Étape 4 : Rendu au format PNG
Transformez le fichier Numbers au format PNG en utilisant le code suivant :
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Étape 5 : Rendu au format PDF
Enfin, convertissez le fichier Numbers au format PDF à l'aide du code suivant :
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Toutes nos félicitations! Vous avez réussi à restituer des fichiers Numbers dans différents formats à l'aide de Groupdocs.Viewer pour .NET.
## Conclusion
Dans ce didacticiel, nous avons couvert les bases du rendu des fichiers Numbers à l'aide de Groupdocs.Viewer pour .NET. Cette puissante bibliothèque offre une intégration transparente pour afficher et convertir des documents dans vos applications .NET.
## FAQ
### Puis-je utiliser Groupdocs.Viewer pour .NET avec d’autres types de documents ?
Oui, Groupdocs.Viewer prend en charge un large éventail de formats de documents, notamment Word, Excel, PDF, etc.
### Une licence temporaire est-elle disponible à des fins de test ?
 Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.groupdocs.com/temporary-license/) pour tester.
### Où puis-je trouver de l’assistance pour Groupdocs.Viewer pour .NET ?
 Visiter le[Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pour de l'aide et des discussions.
### Comment puis-je acheter la version complète de Groupdocs.Viewer pour .NET ?
 Vous pouvez acheter la version complète[ici](https://purchase.groupdocs.com/buy).
### Existe-t-il une version d'essai gratuite disponible ?
 Oui, vous pouvez explorer la version d'essai gratuite[ici](https://releases.groupdocs.com/).