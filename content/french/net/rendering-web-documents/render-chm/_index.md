---
"description": "Apprenez à afficher des fichiers CHM dans .NET avec GroupDocs.Viewer. Convertissez facilement des fichiers CHM aux formats HTML, JPG, PNG et PDF."
"linktitle": "Rendu des fichiers CHM"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu des fichiers CHM"
"url": "/fr/net/rendering-web-documents/render-chm/"
"weight": 10
---

# Rendu des fichiers CHM

## Introduction
Dans ce tutoriel, nous découvrirons comment afficher des fichiers CHM (aide HTML compilée) à l'aide de GroupDocs.Viewer pour .NET. GroupDocs.Viewer pour .NET est une puissante API de rendu de documents qui permet aux développeurs d'afficher plus de 170 types de documents dans leurs applications .NET sans aucune installation de logiciel externe.

## Prérequis

Avant de nous plonger dans le rendu des fichiers CHM, assurez-vous de disposer des prérequis suivants :

### Installation de GroupDocs.Viewer pour .NET

Pour commencer, vous devez installer GroupDocs.Viewer pour .NET. Vous pouvez télécharger la bibliothèque depuis le [Site Web GroupDocs](https://releases.groupdocs.com/viewer/net/) ou installez-le via le gestionnaire de packages NuGet en exécutant la commande suivante dans la console du gestionnaire de packages :

```bash
Install-Package GroupDocs.Viewer
```

## Importation d'espaces de noms

Assurez-vous d’importer les espaces de noms nécessaires dans votre projet :

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Décomposons maintenant le processus de rendu en plusieurs étapes :

## Étape 1 : Définir le répertoire de sortie

Définissez le répertoire dans lequel vous souhaitez que les fichiers rendus soient enregistrés :

```csharp
string outputDirectory = "Your Document Directory";
```

## Étape 2 : Rendre au format HTML

Pour restituer les fichiers CHM en HTML, utilisez l'extrait de code suivant :

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Définir sur vrai pour convertir tout le contenu CHM en une seule page

    viewer.View(options); // Convertir toutes les pages
}
```

## Étape 3 : Rendu au format JPG

Pour convertir des fichiers CHM en images JPG, utilisez l'extrait de code suivant :

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convertir uniquement les pages 1, 2, 3
}
```

## Étape 4 : Rendu au format PNG

Pour restituer des fichiers CHM en images PNG, utilisez l'extrait de code suivant :

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convertir uniquement les pages 1, 2, 3
}
```

## Étape 5 : Rendu au format PDF

Pour restituer des fichiers CHM dans un document PDF, utilisez l'extrait de code suivant :

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Convertir toutes les pages
}
```

## Étape 6 : Vérifier la sortie

Une fois le processus de rendu terminé, vérifiez le répertoire de sortie spécifié pour les fichiers rendus :

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

Le rendu de fichiers CHM avec GroupDocs.Viewer pour .NET est simple. En suivant les étapes décrites dans ce tutoriel, vous pourrez convertir efficacement des documents CHM en différents formats, tels que HTML, images (JPG, PNG) et PDF, dans vos applications .NET.

## FAQ

### Q1 : GroupDocs.Viewer peut-il restituer d’autres formats de documents en dehors de CHM ?

A1 : Oui, GroupDocs.Viewer prend en charge le rendu de plus de 170 formats de documents, notamment PDF, DOCX, XLSX, PPTX, etc.

### Q2 : GroupDocs.Viewer est-il compatible avec .NET Core ?

A2 : Oui, GroupDocs.Viewer prend en charge .NET Core en plus du .NET Framework traditionnel.

### Q3 : Puis-je personnaliser les options de rendu pour différents formats de sortie ?

A3 : Oui, GroupDocs.Viewer fournit diverses options pour personnaliser le processus de rendu, telles que la spécification des numéros de page, la définition de la qualité de l’image et la configuration des chemins de sortie.

### Q4 : GroupDocs.Viewer nécessite-t-il des dépendances externes pour le rendu des documents ?

A4 : Non, GroupDocs.Viewer est une bibliothèque autonome et ne nécessite aucune dépendance externe ni installation de logiciel tiers.

### Q5 : Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer ?

A5 : Oui, vous pouvez bénéficier d’un essai gratuit de GroupDocs.Viewer en visitant le [site web](https://releases.groupdocs.com/).