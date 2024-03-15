---
title: Ajuster la taille de l'image de sortie pour les dessins CAO
linktitle: Ajuster la taille de l'image de sortie pour les dessins CAO
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment ajuster la taille de l'image de sortie pour les dessins CAO à l'aide de GroupDocs.Viewer for .NET. Améliorez la visibilité et la convivialité sans effort.
type: docs
weight: 15
url: /fr/net/rendering-cad-drawings/adjust-output-image-size-cad/
---
## Introduction
Les dessins CAO nécessitent souvent des ajustements spécifiques pour une visualisation et une présentation optimales. GroupDocs.Viewer pour .NET fournit un ensemble d'outils puissants pour gérer et personnaliser la sortie des dessins CAO. Dans ce didacticiel, nous vous guiderons étape par étape dans le processus d'ajustement de la taille de l'image de sortie pour les dessins CAO.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des conditions préalables suivantes :
1.  GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET à partir de[ici](https://releases.groupdocs.com/viewer/net/).
2. Répertoire des documents : préparez le répertoire dans lequel se trouve votre document.
3. Compréhension de base : Familiarisez-vous avec les concepts de base de la programmation .NET.

## Importer des espaces de noms
Tout d'abord, assurez-vous d'importer les espaces de noms nécessaires pour accéder aux fonctionnalités de GroupDocs.Viewer :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Définir le répertoire de sortie
Définissez le répertoire dans lequel vous souhaitez stocker les images de sortie des dessins CAO :
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Définir le format du chemin du fichier de page
Définissez le format des chemins de fichiers d'échange. Ce format sera utilisé pour nommer et enregistrer des pages individuelles sous forme de fichiers HTML :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 3 : Ajuster la taille de l'image
Dans un bloc using pour l'objet Viewer, ajustez la taille de l'image pour les dessins CAO en définissant les options appropriées :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Étape 4 : Afficher le répertoire de sortie
Après le rendu du document, affichez un message indiquant le rendu réussi et indiquez l'emplacement du répertoire de sortie :
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
L'ajustement de la taille de l'image de sortie des dessins CAO est crucial pour améliorer leur visibilité et leur convivialité. Avec GroupDocs.Viewer pour .NET, ce processus devient rationalisé et efficace, vous permettant de personnaliser la sortie en fonction de vos besoins spécifiques.
## FAQ
### Puis-je ajuster la taille de l'image de sortie pour d'autres types de documents que les dessins CAO ?
Oui, GroupDocs.Viewer pour .NET prend en charge différents types de documents et vous pouvez ajuster la taille de l'image de sortie pour la plupart des formats de document.
### GroupDocs.Viewer pour .NET est-il compatible avec différentes versions du framework .NET ?
Oui, GroupDocs.Viewer pour .NET est compatible avec plusieurs versions du framework .NET, garantissant flexibilité et convivialité dans différents environnements.
### Existe-t-il des options de licence disponibles pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez explorer différentes options de licence, notamment des licences temporaires et des licences commerciales, pour répondre à vos besoins.
### Puis-je personnaliser le format de sortie des documents rendus ?
Absolument, GroupDocs.Viewer pour .NET propose diverses options de personnalisation, vous permettant d'adapter le format de sortie en fonction de vos préférences.
### Où puis-je trouver une assistance ou une assistance supplémentaire concernant GroupDocs.Viewer pour .NET ?
 Vous pouvez visiter le forum GroupDocs.Viewer[ici](https://forum.groupdocs.com/c/viewer/9) pour obtenir du soutien, poser des questions et interagir avec la communauté.