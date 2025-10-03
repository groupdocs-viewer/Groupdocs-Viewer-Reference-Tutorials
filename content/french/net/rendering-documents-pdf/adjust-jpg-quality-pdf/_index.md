---
"description": "Découvrez comment ajuster la qualité des images JPG dans les documents PDF rendus avec GroupDocs.Viewer pour .NET. Améliorez votre expérience de visualisation."
"linktitle": "Ajuster la qualité de l'image JPG dans le PDF rendu"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Ajuster la qualité de l'image JPG dans le PDF rendu"
"url": "/fr/net/rendering-documents-pdf/adjust-jpg-quality-pdf/"
"weight": 11
type: docs
---
# Ajuster la qualité de l'image JPG dans le PDF rendu

## Introduction
Dans ce tutoriel, nous apprendrons à ajuster la qualité des images JPG lors du rendu d'un PDF avec GroupDocs.Viewer pour .NET. Cette puissante bibliothèque vous permet de visualiser et de manipuler facilement différents formats de documents dans vos applications .NET.
## Prérequis
Avant de plonger dans ce tutoriel, assurez-vous de disposer des prérequis suivants :
1. Bibliothèque GroupDocs.Viewer pour .NET : Assurez-vous d'avoir téléchargé et installé la bibliothèque GroupDocs.Viewer pour .NET. Vous pouvez la télécharger depuis [ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : disposez d’un environnement de développement fonctionnel configuré avec .NET Framework installé.

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre code C#. Cela permettra à votre application d'accéder aux fonctionnalités de GroupDocs.Viewer pour .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Définir le répertoire de sortie et le chemin du fichier
Définissez le répertoire de sortie dans lequel le PDF rendu sera enregistré et définissez le chemin d'accès au fichier PDF de sortie.
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Étape 2 : Restituer le PDF avec une qualité d'image JPG ajustée
Instanciez la classe Viewer et transmettez le chemin du document contenant les images JPG. Configurez ensuite les options de rendu PDF pour ajuster la qualité de l'image JPG.
```csharp
using (Viewer viewer = new Viewer(TestFiles.JPG_IMAGE_PPTX))
{               
    PdfViewOptions options = new PdfViewOptions(filePath);
    viewer.View(options);
}
```
## Étape 3 : afficher le message de réussite
Une fois le rendu du PDF réussi, affichez un message pour informer l'utilisateur de l'achèvement et de l'emplacement du fichier de sortie.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Dans ce tutoriel, nous avons découvert comment ajuster la qualité des images JPG lors du rendu d'un PDF avec GroupDocs.Viewer pour .NET. En suivant ces étapes, vous pourrez contrôler efficacement la qualité des images de vos documents PDF rendus, garantissant ainsi une représentation visuelle optimale.
## FAQ
### Puis-je ajuster la qualité de l'image pour d'autres formats en plus du JPG ?
Oui, GroupDocs.Viewer pour .NET prend en charge divers formats d’image et vous pouvez également ajuster la qualité pour PNG, TIFF et d’autres formats.
### GroupDocs.Viewer pour .NET est-il compatible avec toutes les versions de .NET Framework ?
GroupDocs.Viewer pour .NET est compatible avec plusieurs versions du framework .NET, notamment .NET Core et .NET Standard.
### Puis-je restituer des documents de manière asynchrone à l’aide de GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer pour .NET fournit des fonctionnalités de rendu asynchrone, vous permettant d’améliorer les performances de vos applications.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez accéder à une version d'essai gratuite de GroupDocs.Viewer pour .NET à partir de [ici](https://releases.groupdocs.com/).
### Comment puis-je obtenir de l'aide ou de l'assistance avec GroupDocs.Viewer pour .NET ?
Vous pouvez visiter le forum GroupDocs.Viewer pour .NET [ici](https://forum.groupdocs.com/c/viewer/9) pour obtenir de l'aide, poser des questions et interagir avec d'autres utilisateurs et développeurs.