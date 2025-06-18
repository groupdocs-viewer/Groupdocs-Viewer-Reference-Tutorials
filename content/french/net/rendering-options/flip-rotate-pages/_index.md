---
"description": "Découvrez comment intégrer Groupdocs.Viewer pour .NET dans vos applications pour un rendu, un retournement et une rotation de documents transparents."
"linktitle": "Retourner et faire pivoter les pages"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Retourner et faire pivoter les pages"
"url": "/fr/net/rendering-options/flip-rotate-pages/"
"weight": 12
---

# Retourner et faire pivoter les pages

## Introduction
Dans ce tutoriel, nous allons explorer les fonctionnalités de Groupdocs.Viewer pour .NET, en nous concentrant plus particulièrement sur le retournement et la rotation des pages. Groupdocs.Viewer pour .NET est un outil puissant conçu pour afficher des documents dans différents formats au sein d'applications .NET. Que vous développiez un système de gestion documentaire ou que vous ayez besoin d'intégrer des fonctionnalités de visualisation de documents à votre logiciel, Groupdocs.Viewer pour .NET offre une solution efficace.
## Prérequis
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
### Installation de Groupdocs.Viewer pour .NET
Pour utiliser Groupdocs.Viewer pour .NET, vous devez installer le package via le gestionnaire de packages NuGet. Vous trouverez des instructions d'installation détaillées dans le [documentation](https://tutorials.groupdocs.com/viewer/net/).

## Importer des espaces de noms
Assurez-vous que les espaces de noms nécessaires sont importés dans votre projet pour utiliser efficacement Groupdocs.Viewer pour .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Décomposons le processus de retournement et de rotation des pages à l'aide de Groupdocs.Viewer pour .NET en étapes simples :
## Étape 1 : définir le répertoire de sortie et le chemin du fichier
Définissez le répertoire dans lequel vous souhaitez que le fichier de sortie soit enregistré et spécifiez le chemin du fichier de sortie.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Étape 2 : Initialiser l'objet Viewer
Créez une instance de la classe Viewer en passant le chemin vers le document que vous souhaitez afficher.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Étape 3 : Configurer les options d’affichage
Configurez les options d'affichage, telles que la spécification du format du fichier de sortie et tous les paramètres supplémentaires tels que la rotation de la page.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Étape 4 : Rendre le document
Appelez la méthode View de l’objet Viewer et transmettez les options d’affichage.
```csharp
viewer.View(viewOptions);
```
## Étape 5 : Afficher le message de réussite
Informez l'utilisateur que le document a été rendu avec succès et spécifiez le répertoire de sortie pour vérification.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
En conclusion, Groupdocs.Viewer pour .NET offre de puissantes fonctionnalités de rendu de documents, notamment la rotation et la rotation des pages. En suivant les étapes décrites dans ce tutoriel, vous pourrez intégrer facilement ces fonctionnalités à vos applications .NET et améliorer l'expérience de visualisation des documents pour vos utilisateurs.
## FAQ
### Groupdocs.Viewer pour .NET est-il compatible avec tous les formats de documents ?
Oui, Groupdocs.Viewer pour .NET prend en charge une large gamme de formats de documents, notamment DOCX, PDF, PPTX, etc.
### Puis-je personnaliser les options d’affichage au-delà du retournement et de la rotation des pages ?
Absolument, Groupdocs.Viewer pour .NET fournit diverses options de personnalisation pour l'affichage des documents, vous permettant d'adapter l'expérience en fonction de vos besoins.
### Existe-t-il un essai gratuit disponible pour Groupdocs.Viewer pour .NET ?
Oui, vous pouvez bénéficier d'un essai gratuit de Groupdocs.Viewer pour .NET en visitant le [site web](https://releases.groupdocs.com/).
### Comment puis-je obtenir de l'aide pour Groupdocs.Viewer pour .NET ?
Vous pouvez demander de l'aide et vous engager auprès de la communauté via le [Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Où puis-je obtenir une licence temporaire pour Groupdocs.Viewer pour .NET ?
Des licences temporaires pour Groupdocs.Viewer pour .NET peuvent être obtenues auprès du [page d'achat](https://purchase.groupdocs.com/temporary-license/).