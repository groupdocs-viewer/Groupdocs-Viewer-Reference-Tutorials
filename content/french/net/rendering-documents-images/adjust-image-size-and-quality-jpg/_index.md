---
title: Ajuster la taille et la qualité de l'image (JPG)
linktitle: Ajuster la taille et la qualité de l'image (JPG)
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment optimiser la taille et la qualité des images au format JPEG à l'aide de Groupdocs.Viewer pour .NET. Améliorez votre expérience de visualisation de documents.
weight: 11
url: /fr/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---

# Ajuster la taille et la qualité de l'image (JPG)

## Introduction
Groupdocs.Viewer for .NET est une bibliothèque puissante qui permet aux développeurs d'intégrer de manière transparente la fonctionnalité de visualisation de documents dans leurs applications .NET. Une exigence courante dans les applications de visualisation de documents est la possibilité d'ajuster la taille et la qualité des images, en particulier lorsqu'il s'agit d'images JPEG (JPG). Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajustement de la taille et de la qualité de l'image à l'aide de Groupdocs.Viewer pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Compréhension de base du langage de programmation C#.
2. Visual Studio installé sur votre système.
3.  Groupdocs.Viewer pour la bibliothèque .NET installée. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).

## Importer des espaces de noms
Tout d’abord, vous devez importer les espaces de noms nécessaires dans votre code C#. Ces espaces de noms donnent accès aux classes et méthodes requises pour travailler avec Groupdocs.Viewer.
## Étape 1 : Importer des espaces de noms
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Maintenant, décomposons l'exemple de code fourni en plusieurs étapes pour une meilleure compréhension.
## Étape 2 : Définir le répertoire de sortie et le format du chemin du fichier d'échange
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Dans cette étape, nous spécifions le répertoire de sortie dans lequel les images rendues seront enregistrées et définissons le format du chemin de fichier de chaque image de page.
## Étape 3 : initialiser la visionneuse et configurer les options d'affichage JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Ici, nous initialisons l'objet Viewer avec le chemin d'accès au document à visualiser. Ensuite, nous créons une instance de JpgViewOptions et définissons la largeur et la hauteur souhaitées pour les images JPEG.
## Étape 4 : Rendre le document source
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Enfin, nous imprimons un message indiquant le rendu réussi du document source et l'emplacement où les images de sortie sont enregistrées.

## Conclusion
Dans ce didacticiel, nous avons appris à ajuster la taille et la qualité des images JPEG à l'aide de Groupdocs.Viewer pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez facilement intégrer cette fonctionnalité dans vos applications .NET, offrant ainsi aux utilisateurs une expérience de visualisation d'images optimisée.
## FAQ
### Puis-je également ajuster la qualité de l’image ?
Oui, vous pouvez ajuster la qualité de l'image en définissant la propriété Quality dans JpgViewOptions.
### Quels formats de documents sont pris en charge par Groupdocs.Viewer pour .NET ?
Groupdocs.Viewer pour .NET prend en charge un large éventail de formats de documents, notamment DOCX, PDF, PPTX, XLSX, etc.
### Groupdocs.Viewer pour .NET est-il compatible avec .NET Core ?
Oui, Groupdocs.Viewer pour .NET est compatible avec .NET Core ainsi qu'avec le .NET Framework traditionnel.
### Puis-je personnaliser le format de nom du fichier de sortie ?
Oui, vous pouvez personnaliser le format de dénomination du fichier de sortie en modifiant la variable pageFilePathFormat dans le code.
### Groupdocs.Viewer pour .NET prend-il en charge les annotations de documents ?
Oui, Groupdocs.Viewer pour .NET offre une prise en charge complète des annotations de documents, notamment la mise en surbrillance, le soulignement et les commentaires de texte.