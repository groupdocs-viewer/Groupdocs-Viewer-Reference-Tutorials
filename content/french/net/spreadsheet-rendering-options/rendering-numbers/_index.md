---
"description": "Découvrez la puissance de Groupdocs.Viewer pour .NET pour un rendu fluide des fichiers Numbers. Convertissez facilement vos fichiers en HTML, JPG, PNG et PDF."
"linktitle": "Rendu des nombres"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu des nombres"
"url": "/fr/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# Rendu des nombres

## Introduction
Bienvenue dans ce tutoriel pas à pas sur le rendu de fichiers Numbers avec Groupdocs.Viewer pour .NET. Que vous soyez un développeur expérimenté ou débutant, ce guide vous guidera pas à pas dans la conversion de documents Numbers vers différents formats. Groupdocs.Viewer pour .NET est un outil puissant qui vous permet d'intégrer facilement des fonctionnalités de visualisation de documents à vos applications .NET.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Une connaissance pratique du développement C# et .NET.
- Bibliothèque Groupdocs.Viewer pour .NET installée. Vous pouvez la télécharger. [ici](https://releases.groupdocs.com/viewer/net/).
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
## Étape 1 : Configurer le répertoire de sortie
Avant de commencer le rendu, définissez le répertoire de sortie où seront enregistrés les fichiers convertis. Remplacez « Votre répertoire de documents » par le chemin d'accès réel :
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Rendu en HTML multipages
Utilisez le code suivant pour convertir le fichier Numbers en HTML multipages :
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
Transformez le fichier Numbers au format PNG en utilisant le code suivant :
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Étape 5 : Rendu au format PDF
Enfin, convertissez le fichier Numbers au format PDF en utilisant le code suivant :
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Félicitations ! Vous avez réussi à convertir des fichiers Numbers en différents formats grâce à Groupdocs.Viewer pour .NET.
## Conclusion
Dans ce tutoriel, nous avons abordé les bases du rendu de fichiers Numbers avec Groupdocs.Viewer pour .NET. Cette puissante bibliothèque offre une intégration transparente pour la visualisation et la conversion de documents dans vos applications .NET.
## FAQ
### Puis-je utiliser Groupdocs.Viewer pour .NET avec d’autres types de documents ?
Oui, Groupdocs.Viewer prend en charge une large gamme de formats de documents, notamment Word, Excel, PDF, etc.
### Une licence temporaire est-elle disponible à des fins de test ?
Oui, vous pouvez obtenir un permis temporaire [ici](https://purchase.groupdocs.com/temporary-license/) pour les tests.
### Où puis-je trouver de l'assistance pour Groupdocs.Viewer pour .NET ?
Visitez le [Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pour assistance et discussions.
### Comment acheter la version complète de Groupdocs.Viewer pour .NET ?
Vous pouvez acheter la version complète [ici](https://purchase.groupdocs.com/buy).
### Existe-t-il une version d'essai gratuite disponible ?
Oui, vous pouvez explorer la version d'essai gratuite [ici](https://releases.groupdocs.com/).