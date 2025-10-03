---
"description": "Apprenez à optimiser la taille et la qualité des images au format JPEG avec Groupdocs.Viewer pour .NET. Améliorez votre expérience de visualisation de documents."
"linktitle": "Ajuster la taille et la qualité de l'image (JPG)"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Ajuster la taille et la qualité de l'image (JPG)"
"url": "/fr/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
type: docs
---
# Ajuster la taille et la qualité de l'image (JPG)

## Introduction
Groupdocs.Viewer pour .NET est une bibliothèque puissante qui permet aux développeurs d'intégrer facilement des fonctionnalités de visualisation de documents à leurs applications .NET. L'une des exigences courantes des applications de visualisation de documents est la possibilité d'ajuster la taille et la qualité des images, notamment celles au format JPEG (JPG). Dans ce tutoriel, nous vous expliquerons comment ajuster la taille et la qualité des images avec Groupdocs.Viewer pour .NET.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
1. Compréhension de base du langage de programmation C#.
2. Visual Studio installé sur votre système.
3. Bibliothèque Groupdocs.Viewer pour .NET installée. Vous pouvez la télécharger ici. [ici](https://releases.groupdocs.com/viewer/net/).

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre code C#. Ces espaces de noms donnent accès aux classes et méthodes nécessaires à l'utilisation de Groupdocs.Viewer.
## Étape 1 : Importer les espaces de noms
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Maintenant, décomposons l’exemple de code fourni en plusieurs étapes pour une meilleure compréhension.
## Étape 2 : Définir le répertoire de sortie et le format du chemin d'accès au fichier d'échange
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Dans cette étape, nous spécifions le répertoire de sortie dans lequel les images rendues seront enregistrées et définissons le format du chemin de fichier de chaque image de page.
## Étape 3 : Initialiser la visionneuse et configurer les options d’affichage JPG
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
Dans ce tutoriel, nous avons appris à ajuster la taille et la qualité des images JPEG avec Groupdocs.Viewer pour .NET. En suivant les étapes décrites ci-dessus, vous pourrez facilement intégrer cette fonctionnalité à vos applications .NET et ainsi offrir aux utilisateurs une expérience de visualisation d'images optimisée.
## FAQ
### Puis-je également régler la qualité de l’image ?
Oui, vous pouvez ajuster la qualité de l'image en définissant la propriété Qualité dans JpgViewOptions.
### Quels formats de documents sont pris en charge par Groupdocs.Viewer pour .NET ?
Groupdocs.Viewer pour .NET prend en charge une large gamme de formats de documents, notamment DOCX, PDF, PPTX, XLSX, etc.
### Groupdocs.Viewer pour .NET est-il compatible avec .NET Core ?
Oui, Groupdocs.Viewer pour .NET est compatible avec .NET Core ainsi qu'avec le .NET Framework traditionnel.
### Puis-je personnaliser le format de dénomination du fichier de sortie ?
Oui, vous pouvez personnaliser le format de nommage du fichier de sortie en modifiant la variable pageFilePathFormat dans le code.
### Groupdocs.Viewer pour .NET prend-il en charge les annotations de documents ?
Oui, Groupdocs.Viewer pour .NET fournit une prise en charge complète des annotations de documents, notamment la mise en évidence, le soulignement et les commentaires du texte.