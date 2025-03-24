---
title: Rendre les archives sur une ou plusieurs pages HTML
linktitle: Rendre les archives sur une ou plusieurs pages HTML
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer des archives sur des pages HTML à l'aide de GroupDocs.Viewer pour .NET. Intégrez sans effort les fonctionnalités de visualisation de documents dans vos applications .NET.
weight: 12
url: /fr/net/rendering-archive-files/render-archives-html/
---
## Introduction
GroupDocs.Viewer for .NET est une puissante bibliothèque de rendu de documents qui permet aux développeurs d'intégrer sans effort des fonctionnalités de visualisation de documents dans leurs applications .NET. Que vous ayez besoin de restituer des archives sur une ou plusieurs pages HTML, ce didacticiel vous guidera étape par étape tout au long du processus.
## Conditions préalables
Avant de vous lancer dans ce didacticiel, assurez-vous d'avoir les prérequis suivants :
1.  GroupDocs.Viewer pour .NET : assurez-vous que la bibliothèque est installée dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : disposez d'un environnement de développement fonctionnel pour le développement .NET.
3. Répertoire de documents : préparez un répertoire dans lequel vos documents sont stockés.
4. Compréhension de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.

## Importer des espaces de noms
Dans votre code C#, assurez-vous d'importer les espaces de noms nécessaires :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Suivez ces étapes pour restituer les archives sur une ou plusieurs pages HTML à l'aide de GroupDocs.Viewer pour .NET :
## Étape 1 : Définir le répertoire de sortie
Définissez le répertoire dans lequel vous souhaitez que les pages HTML rendues soient enregistrées :
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Définir le format du chemin de fichier
Spécifiez le format du chemin de fichier pour les pages HTML. Pour le rendu sur une seule page :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Pour le rendu sur plusieurs pages :
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Étape 3 : Rendu au format HTML d'une seule page
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Étape 4 : Rendre sur plusieurs pages HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Définir les éléments par page
    viewer.View(options);
}
```
## Étape 5 : Vérifier la sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Le rendu des archives sur des pages HTML à l'aide de GroupDocs.Viewer pour .NET est un processus simple. En suivant les étapes décrites dans ce didacticiel, vous pouvez intégrer de manière transparente les fonctionnalités de visualisation de documents dans vos applications .NET.
## FAQ
### Puis-je restituer d'autres formats de documents que les archives ?
Oui, GroupDocs.Viewer prend en charge un large éventail de formats de documents, notamment PDF, DOCX, XLSX, PPTX, etc.
### GroupDocs.Viewer est-il adapté aux applications de bureau et Web ?
Absolument, GroupDocs.Viewer peut être utilisé de manière transparente dans les applications de bureau et Web.
### GroupDocs.Viewer propose-t-il des options de personnalisation pour l'interface de la visionneuse ?
Oui, vous pouvez personnaliser l'interface de la visionneuse en fonction de vos besoins.
### Puis-je restituer des documents de manière asynchrone avec GroupDocs.Viewer ?
Oui, GroupDocs.Viewer fournit des fonctionnalités de rendu asynchrone pour des performances améliorées.
### GroupDocs.Viewer prend-il en charge les annotations de documents ?
Oui, GroupDocs.Viewer permet aux utilisateurs d'afficher et de gérer efficacement les annotations de documents.