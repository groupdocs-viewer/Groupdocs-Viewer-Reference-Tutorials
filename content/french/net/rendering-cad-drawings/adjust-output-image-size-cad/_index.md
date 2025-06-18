---
"description": "Découvrez comment ajuster la taille de l'image de sortie pour les dessins CAO avec GroupDocs.Viewer pour .NET. Améliorez la visibilité et la convivialité sans effort."
"linktitle": "Ajuster la taille de l'image de sortie pour les dessins CAO"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Ajuster la taille de l'image de sortie pour les dessins CAO"
"url": "/fr/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Ajuster la taille de l'image de sortie pour les dessins CAO

## Introduction
Les dessins CAO nécessitent souvent des ajustements spécifiques pour une visualisation et une présentation optimales. GroupDocs.Viewer pour .NET offre un ensemble d'outils puissants pour gérer et personnaliser la sortie des dessins CAO. Dans ce tutoriel, nous vous guiderons pas à pas dans le processus d'ajustement de la taille de l'image de sortie des dessins CAO.
## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET depuis [ici](https://releases.groupdocs.com/viewer/net/).
2. Répertoire de documents : Préparez le répertoire dans lequel se trouve votre document.
3. Compréhension de base : Familiarisez-vous avec les concepts de base de la programmation .NET.

## Importer des espaces de noms
Tout d’abord, assurez-vous d’importer les espaces de noms nécessaires pour accéder aux fonctionnalités de GroupDocs.Viewer :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : définir le répertoire de sortie
Définissez le répertoire dans lequel vous souhaitez stocker les images de sortie des dessins CAO :
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
Définissez le format des chemins d'accès aux fichiers d'échange. Ce format sera utilisé pour nommer et enregistrer les pages individuelles au format HTML :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 3 : Ajuster la taille de l’image
À l'intérieur d'un bloc d'utilisation pour l'objet Viewer, ajustez la taille de l'image pour les dessins CAO en définissant les options appropriées :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Étape 4 : afficher le répertoire de sortie
Après le rendu du document, affichez un message indiquant le rendu réussi et indiquez l'emplacement du répertoire de sortie :
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Ajuster la taille de l'image de sortie des dessins CAO est essentiel pour améliorer leur visibilité et leur convivialité. Avec GroupDocs.Viewer pour .NET, ce processus est simplifié et efficace, vous permettant de personnaliser la sortie selon vos besoins spécifiques.
## FAQ
### Puis-je ajuster la taille de l'image de sortie pour d'autres types de documents en plus des dessins CAO ?
Oui, GroupDocs.Viewer pour .NET prend en charge différents types de documents et vous pouvez ajuster la taille de l’image de sortie pour la plupart des formats de documents.
### GroupDocs.Viewer pour .NET est-il compatible avec différentes versions du framework .NET ?
Oui, GroupDocs.Viewer pour .NET est compatible avec plusieurs versions du framework .NET, garantissant flexibilité et convivialité dans différents environnements.
### Existe-t-il des options de licence disponibles pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez explorer différentes options de licence, y compris les licences temporaires et les licences commerciales, en fonction de vos besoins.
### Puis-je personnaliser le format de sortie des documents rendus ?
Absolument, GroupDocs.Viewer pour .NET propose diverses options de personnalisation, vous permettant d'adapter le format de sortie en fonction de vos tutoriels.
### Où puis-je trouver une assistance ou un support supplémentaire avec GroupDocs.Viewer pour .NET ?
Vous pouvez visiter le forum GroupDocs.Viewer [ici](https://forum.groupdocs.com/c/viewer/9) pour obtenir de l'aide, poser des questions et interagir avec la communauté.