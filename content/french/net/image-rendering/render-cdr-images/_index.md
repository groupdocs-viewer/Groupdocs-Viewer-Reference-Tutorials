---
title: Rendre les images CDR
linktitle: Rendre les images CDR
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer des images CDR au format HTML, JPG, PNG et PDF à l'aide de GroupDocs.Viewer pour .NET. Convertissez facilement des fichiers CorelDRAW avec ce didacticiel.
weight: 12
url: /fr/net/image-rendering/render-cdr-images/
---

# Rendre les images CDR

## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de rendu d'images CDR (CorelDRAW) à l'aide de GroupDocs.Viewer pour .NET. CDR est un format de fichier principalement associé à CorelDRAW, un éditeur de graphiques vectoriels. Avec GroupDocs.Viewer, vous pouvez facilement convertir des fichiers CDR en différents formats tels que HTML, JPG, PNG et PDF.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des conditions préalables suivantes :
1.  GroupDocs.Viewer pour .NET : assurez-vous d'avoir installé GroupDocs.Viewer pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).
2. Répertoire de documents : préparez un répertoire dans lequel vous souhaitez enregistrer les images rendues.
3. Connaissance de base de C# : Une connaissance du langage de programmation C# est nécessaire pour comprendre les exemples de code.
## Importer des espaces de noms
Avant de plonger dans les exemples de code, importez les espaces de noms nécessaires dans votre fichier C# :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Maintenant, décomposons chaque exemple en plusieurs étapes :
## Rendu au format HTML
1. Définissez le répertoire de sortie dans lequel vous souhaitez enregistrer les fichiers HTML rendus :
```csharp
string outputDirectory = "Your Document Directory";
```
2. Spécifiez le format du chemin de fichier pour les fichiers HTML :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Utilisez la classe Viewer pour afficher le fichier CDR au format HTML :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendu au format JPG
1. Définissez le format du chemin de fichier pour les fichiers JPG :
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Utilisez la classe Viewer pour restituer le fichier CDR au format JPG :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendu en PNG
1. Définissez le format du chemin de fichier pour les fichiers PNG :
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Utilisez la classe Viewer pour restituer le fichier CDR au format PNG :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendu au format PDF
1. Définissez le format du chemin de fichier pour le PDF :
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Utilisez la classe Viewer pour restituer le fichier CDR au format PDF :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Facultativement, vous pouvez spécifier des options de rendu ou restituer des pages spécifiques en transmettant des paramètres supplémentaires au`viewer.View()` méthode.
## Conclusion
Le rendu des images CDR dans différents formats tels que HTML, JPG, PNG et PDF à l'aide de GroupDocs.Viewer pour .NET est un processus simple. En suivant les étapes décrites dans ce didacticiel, vous pouvez convertir efficacement les fichiers CDR en différents formats en fonction de vos besoins.
## FAQ
### GroupDocs.Viewer pour .NET est-il compatible avec toutes les versions des fichiers CDR ?
GroupDocs.Viewer pour .NET prend en charge le rendu des fichiers CDR créés par différentes versions de CorelDRAW.
### Puis-je personnaliser la sortie des fichiers rendus ?
Oui, GroupDocs.Viewer pour .NET propose diverses options pour personnaliser la sortie, telles que l'ajustement de la qualité de l'image, la définition d'un filigrane, etc.
### GroupDocs.Viewer pour .NET nécessite-t-il des dépendances externes ?
Non, GroupDocs.Viewer pour .NET est une bibliothèque autonome et ne nécessite aucune dépendance externe pour le rendu des documents.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
 Oui, vous pouvez télécharger une version d'essai gratuite de GroupDocs.Viewer pour .NET à partir de[ici](https://releases.groupdocs.com/).
### Où puis-je obtenir de l’assistance pour GroupDocs.Viewer pour .NET ?
 Vous pouvez obtenir de l'aide sur le forum de la communauté GroupDocs.Viewer[ici](https://forum.groupdocs.com/c/viewer/9).