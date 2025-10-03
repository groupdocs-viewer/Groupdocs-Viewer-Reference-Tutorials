---
"description": "Découvrez comment restituer des PDF avec leurs tailles de page d'origine grâce à GroupDocs.Viewer pour .NET. Suivez notre guide étape par étape et intégrez cette fonctionnalité en toute simplicité."
"linktitle": "Rendre le PDF avec la taille de page d'origine"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendre le PDF avec la taille de page d'origine"
"url": "/fr/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
type: docs
---
# Rendre le PDF avec la taille de page d'origine

## Introduction
Dans le domaine du développement .NET, GroupDocs.Viewer se distingue par sa puissance pour le rendu de divers formats de documents, dont les PDF. L'une des exigences courantes en matière de gestion de documents est de restituer les PDF tout en préservant leur taille de page d'origine. Réaliser cette tâche en toute fluidité nécessite une compréhension approfondie de GroupDocs.Viewer pour .NET et de ses fonctionnalités.

![Afficher un PDF avec la taille de page d'origine avec GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Prérequis
Avant de vous lancer dans le rendu de PDF avec les tailles de page d'origine à l'aide de GroupDocs.Viewer pour .NET, assurez-vous de disposer des conditions préalables suivantes :
### 1. Installer GroupDocs.Viewer pour .NET
Commencez par télécharger la bibliothèque GroupDocs.Viewer depuis le site web. Vous pouvez l'obtenir à partir du lien fourni. [lien de téléchargement](https://releases.groupdocs.com/viewer/net/)Suivez les instructions d’installation fournies dans la documentation pour l’intégrer efficacement dans votre projet .NET.
### 2. Configurer l'environnement de développement
Assurez-vous de disposer d'un environnement de développement adapté au développement .NET. Cela implique l'installation d'un IDE compatible, tel que Visual Studio, et une compréhension de base de la programmation C#.
### 3. Obtenir un document PDF
Vous aurez besoin d'un exemple de document PDF à afficher avec GroupDocs.Viewer. Vous pouvez utiliser n'importe quel document PDF à des fins de test. Si vous n'en avez pas, vous pouvez télécharger un exemple de PDF depuis différentes sources en ligne.

## Importer des espaces de noms
Avant de procéder au rendu des PDF, il est essentiel d'importer les espaces de noms nécessaires dans votre projet C#. Cette étape vous permet d'accéder aux classes et méthodes requises depuis la bibliothèque GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Maintenant que vous avez mis en place les prérequis et importé les espaces de noms nécessaires, décomposons le processus de rendu de PDF avec les tailles de page d'origine à l'aide de GroupDocs.Viewer pour .NET en étapes simples :
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Assurez-vous de spécifier le répertoire dans lequel vous souhaitez enregistrer les pages rendues. Remplacer `"Your Document Directory"` avec le chemin de votre répertoire souhaité.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Définissez le format de nommage des fichiers de page générés. Dans cet exemple, les pages seront enregistrées au format PNG avec des noms de fichiers au format `"page_1.png"`, `"page_2.png"`, et ainsi de suite.
## Étape 3 : Rendre le PDF avec la taille de page d'origine
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Instancier un `Viewer` objet avec le chemin d'accès à votre fichier PDF. Créez ensuite `PngViewOptions` avec le format de chemin d'accès au fichier d'échange spécifié. Définir `RenderOriginalPageSize` propriété à `true` pour conserver les tailles de page d'origine lors du rendu.
## Étape 4 : Afficher l'emplacement du document rendu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprimez un message indiquant le rendu réussi et indiquez le répertoire dans lequel les pages rendues sont enregistrées.

## Conclusion
Le rendu de PDF avec leurs tailles de page d'origine avec GroupDocs.Viewer pour .NET est simple à réaliser en suivant les étapes décrites dans ce tutoriel. En important les espaces de noms nécessaires et en suivant le guide étape par étape, vous pouvez intégrer facilement cette fonctionnalité à vos applications .NET.
## FAQ
### GroupDocs.Viewer peut-il restituer d'autres formats de documents en plus du PDF ?
Oui, GroupDocs.Viewer prend en charge le rendu de divers formats de documents, notamment Word, Excel, PowerPoint, etc.
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer est compatible avec les environnements .NET Framework et .NET Core.
### Puis-je personnaliser le format de sortie des pages rendues ?
Oui, vous pouvez personnaliser le format de sortie en ajustant les options fournies par GroupDocs.Viewer, comme la définition de différents formats d'image ou la spécification d'options de rendu personnalisées.
### GroupDocs.Viewer offre-t-il une prise en charge du rendu de documents basé sur le cloud ?
Oui, GroupDocs.Viewer fournit des API pour le rendu de documents basé sur le cloud, vous permettant de restituer des documents directement à partir de fournisseurs de stockage cloud.
### Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer ?
Oui, vous pouvez explorer GroupDocs.Viewer avec un essai gratuit en visitant le site fourni [lien](https://releases.groupdocs.com/).