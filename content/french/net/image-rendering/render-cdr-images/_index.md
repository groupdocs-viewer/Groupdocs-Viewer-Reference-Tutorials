---
"description": "Apprenez à convertir des images CDR en HTML, JPG, PNG et PDF avec GroupDocs.Viewer pour .NET. Convertissez facilement des fichiers CorelDRAW grâce à ce tutoriel."
"linktitle": "Rendu des images CDR"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu des images CDR"
"url": "/fr/net/image-rendering/render-cdr-images/"
"weight": 12
---

# Rendu des images CDR

## Introduction
Dans ce tutoriel, nous vous guiderons dans le rendu d'images CDR (CorelDRAW) avec GroupDocs.Viewer pour .NET. CDR est un format de fichier principalement associé à CorelDRAW, un éditeur de graphiques vectoriels. Avec GroupDocs.Viewer, vous pouvez facilement convertir des fichiers CDR en différents formats, tels que HTML, JPG, PNG et PDF.

![Rendu d'images CDR avec GroupDocs.Viewer pour .NET](/viewer/image-rendering/render-cdr-images.png)

## Prérequis
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
1. GroupDocs.Viewer pour .NET : Assurez-vous d'avoir installé GroupDocs.Viewer pour .NET. Vous pouvez le télécharger depuis [ici](https://releases.groupdocs.com/viewer/net/).
2. Répertoire de documents : préparez un répertoire dans lequel vous souhaitez enregistrer les images rendues.
3. Connaissances de base de C# : Une familiarité avec le langage de programmation C# est nécessaire pour comprendre les exemples de code.
## Importer des espaces de noms
Avant de plonger dans les exemples de code, importez les espaces de noms nécessaires dans votre fichier C# :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Maintenant, décomposons chaque exemple en plusieurs étapes :
## Rendu en HTML
1. Définissez le répertoire de sortie dans lequel vous souhaitez enregistrer les fichiers HTML rendus :
```csharp
string outputDirectory = "Your Document Directory";
```
2. Spécifiez le format du chemin d'accès au fichier pour les fichiers HTML :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Utilisez la classe Viewer pour restituer le fichier CDR au format HTML :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendu au format JPG
1. Définir le format du chemin d'accès au fichier pour les fichiers JPG :
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
## Rendu au format PNG
1. Définir le format du chemin d'accès au fichier pour les fichiers PNG :
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
1. Définir le format du chemin d'accès au fichier PDF :
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
3. En option, vous pouvez spécifier des options de rendu ou restituer des pages spécifiques en transmettant des paramètres supplémentaires au `viewer.View()` méthode.
## Conclusion
Le rendu d'images CDR dans différents formats (HTML, JPG, PNG et PDF) avec GroupDocs.Viewer pour .NET est simple. En suivant les étapes décrites dans ce tutoriel, vous pourrez convertir efficacement vos fichiers CDR dans différents formats selon vos besoins.
## FAQ
### GroupDocs.Viewer pour .NET est-il compatible avec toutes les versions des fichiers CDR ?
GroupDocs.Viewer pour .NET prend en charge le rendu des fichiers CDR créés par différentes versions de CorelDRAW.
### Puis-je personnaliser la sortie des fichiers rendus ?
Oui, GroupDocs.Viewer pour .NET fournit diverses options pour personnaliser la sortie, telles que le réglage de la qualité de l'image, la définition d'un filigrane, etc.
### GroupDocs.Viewer pour .NET nécessite-t-il des dépendances externes ?
Non, GroupDocs.Viewer pour .NET est une bibliothèque autonome et ne nécessite aucune dépendance externe pour le rendu des documents.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite de GroupDocs.Viewer pour .NET à partir de [ici](https://releases.groupdocs.com/).
### Où puis-je obtenir de l'aide pour GroupDocs.Viewer pour .NET ?
Vous pouvez obtenir de l'aide sur le forum communautaire GroupDocs.Viewer [ici](https://forum.groupdocs.com/c/viewer/9).