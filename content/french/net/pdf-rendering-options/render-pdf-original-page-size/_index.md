---
title: Rendre un PDF avec la taille de page d'origine
linktitle: Rendre un PDF avec la taille de page d'origine
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer des PDF avec les tailles de page d'origine à l'aide de GroupDocs.Viewer pour .NET. Suivez notre guide étape par étape et intégrez cette fonctionnalité de manière transparente.
type: docs
weight: 17
url: /fr/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Introduction
Dans le domaine du développement .NET, GroupDocs.Viewer se distingue comme un outil puissant pour le rendu de divers formats de documents, y compris les PDF. Une exigence courante dans la gestion des documents est de restituer les PDF tout en préservant leur taille de page d'origine. Réaliser cette tâche de manière transparente nécessite une compréhension complète de GroupDocs.Viewer pour .NET et de ses fonctionnalités.
## Conditions préalables
Avant de vous lancer dans le rendu de PDF avec les formats de page d'origine à l'aide de GroupDocs.Viewer pour .NET, assurez-vous d'avoir les conditions préalables suivantes en place :
### 1. Installez GroupDocs.Viewer pour .NET
 Commencez par télécharger la bibliothèque GroupDocs.Viewer depuis le site Web. Vous pouvez obtenir la bibliothèque à partir du[lien de téléchargement](https://releases.groupdocs.com/viewer/net/). Suivez les instructions d'installation fournies dans la documentation pour l'intégrer efficacement dans votre projet .NET.
### 2. Configurer l'environnement de développement
Assurez-vous de disposer d'un environnement de développement configuré pour le développement .NET. Cela inclut l'installation d'un IDE compatible, tel que Visual Studio, et une compréhension de base de la programmation C#.
### 3. Obtenez un document PDF
Vous aurez besoin d'un exemple de document PDF à restituer avec GroupDocs.Viewer. Vous pouvez utiliser n'importe quel document PDF à des fins de test. Si vous n'en avez pas, vous pouvez télécharger un exemple de PDF à partir de diverses sources en ligne.

## Importer des espaces de noms
Avant de procéder au rendu des PDF, il est essentiel d'importer les espaces de noms nécessaires dans votre projet C#. Cette étape vous permet d'accéder aux classes et méthodes requises depuis la bibliothèque GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Maintenant que vous avez les conditions préalables en place et les espaces de noms nécessaires importés, décomposons le processus de rendu des PDF avec les tailles de page d'origine à l'aide de GroupDocs.Viewer pour .NET en étapes simples :
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
 Assurez-vous de spécifier le répertoire dans lequel vous souhaitez que les pages rendues soient enregistrées. Remplacer`"Your Document Directory"` avec le chemin du répertoire souhaité.
## Étape 2 : Définir le format du chemin du fichier de page
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Configurez le format de nom des fichiers de page rendus. Dans cet exemple, les pages seront enregistrées sous forme d'images PNG avec des noms de fichiers au format`"page_1.png"`, `"page_2.png"`, et ainsi de suite.
## Étape 3 : Rendre le PDF avec la taille de page d'origine
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Instancier un`Viewer` objet avec le chemin d’accès à votre fichier PDF. Ensuite, créez`PngViewOptions` avec le format de chemin de fichier d'échange spécifié. Ensemble`RenderOriginalPageSize` propriété à`true` pour conserver les tailles de page d'origine lors du rendu.
## Étape 4 : Afficher l'emplacement du document rendu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprimez un message indiquant un rendu réussi et fournissez le répertoire dans lequel les pages rendues sont enregistrées.

## Conclusion
Le rendu de PDF avec les tailles de page d'origine à l'aide de GroupDocs.Viewer pour .NET est un processus simple lorsque vous suivez les étapes décrites dans ce didacticiel. En important les espaces de noms nécessaires et en suivant le guide étape par étape, vous pouvez intégrer de manière transparente cette fonctionnalité dans vos applications .NET.
## FAQ
### GroupDocs.Viewer peut-il restituer d'autres formats de documents que le PDF ?
Oui, GroupDocs.Viewer prend en charge le rendu de divers formats de documents, notamment Word, Excel, PowerPoint, etc.
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer est compatible avec les environnements .NET Framework et .NET Core.
### Puis-je personnaliser le format de sortie des pages rendues ?
Oui, vous pouvez personnaliser le format de sortie en ajustant les options fournies par GroupDocs.Viewer, telles que la définition de différents formats d'image ou la spécification d'options de rendu personnalisées.
### GroupDocs.Viewer offre-t-il une prise en charge du rendu de documents basé sur le cloud ?
Oui, GroupDocs.Viewer fournit des API pour le rendu de documents basé sur le cloud, vous permettant de restituer des documents directement à partir de fournisseurs de stockage cloud.
### Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer ?
 Oui, vous pouvez explorer GroupDocs.Viewer avec un essai gratuit en visitant le site fourni[lien](https://releases.groupdocs.com/).