---
"description": "Apprenez à remplacer facilement les polices manquantes dans vos documents .NET grâce à GroupDocs.Viewer. Assurez un rendu précis en quelques étapes simples."
"linktitle": "Remplacer la police manquante"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Remplacer la police manquante"
"url": "/fr/net/rendering-options/replace-missing-font/"
"weight": 20
---

# Remplacer la police manquante

## Introduction
Dans le monde du développement .NET, une gestion efficace des documents est cruciale. GroupDocs.Viewer pour .NET offre une solution puissante pour visualiser différents formats de documents dans vos applications .NET. Dans ce tutoriel, nous découvrirons comment utiliser GroupDocs.Viewer pour .NET pour remplacer les polices manquantes dans vos documents. Que vous travailliez avec des PDF, des présentations PowerPoint ou des documents Word, GroupDocs.Viewer simplifie le processus et garantit un rendu précis de vos documents, même en cas d'absence de polices.
## Prérequis
Avant de vous lancer dans ce tutoriel, assurez-vous de disposer des éléments suivants :
1. GroupDocs.Viewer pour .NET : téléchargez et installez la bibliothèque GroupDocs.Viewer à partir du site Web](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : configurez un environnement de développement .NET, tel que Visual Studio.
3. Connaissances de base en C# : Familiarité avec le langage de programmation C# et le framework .NET.

## Importer des espaces de noms
Dans votre code C#, importez les espaces de noms nécessaires pour accéder aux fonctionnalités de GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Maintenant, parcourons le processus de remplacement des polices manquantes dans les documents à l’aide de GroupDocs.Viewer pour .NET.
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Définissez le répertoire dans lequel les pages du document rendues seront enregistrées.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Spécifiez le format de nommage des fichiers HTML de sortie. Dans cet exemple, chaque page sera enregistrée au format HTML avec la convention de nommage « page_{numéro_page}.html ».
## Étape 3 : Initialiser l'objet Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Initialisez une nouvelle instance de la classe Viewer, en passant le chemin d'accès au fichier de document (dans ce cas, une présentation PowerPoint avec des polices manquantes) en tant que paramètre.
## Étape 4 : définir les options d’affichage HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Créez une instance de HtmlViewOptions et configurez-la pour intégrer des ressources dans la sortie HTML. Spécifiez un nom de police par défaut à utiliser en remplacement des polices manquantes.
## Étape 5 : Rendre le document
```csharp
viewer.View(options);
```
Appelez la méthode View de l'objet Viewer en lui transmettant les options d'affichage HTML. Les pages du document seront alors affichées selon les options spécifiées.
## Étape 6 : Afficher le chemin de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprimez un message indiquant le rendu réussi du document et indiquez le chemin où les fichiers HTML de sortie sont enregistrés.

## Conclusion
Dans ce tutoriel, nous avons appris à utiliser GroupDocs.Viewer pour .NET afin de remplacer les polices manquantes dans vos documents. En suivant ces étapes, vous garantissez un rendu précis de vos documents, même lorsque certaines polices sont indisponibles. GroupDocs.Viewer simplifie le processus et vous permet de vous concentrer sur la création d'applications .NET robustes sans vous soucier des problèmes de compatibilité des polices.
## FAQ
### GroupDocs.Viewer peut-il gérer d’autres types de problèmes liés aux polices ?
Oui, GroupDocs.Viewer fournit diverses fonctionnalités liées aux polices, notamment la substitution et la détection de polices.
### GroupDocs.Viewer est-il compatible avec tous les frameworks .NET ?
GroupDocs.Viewer prend en charge une large gamme de frameworks .NET, notamment .NET Core et .NET Standard.
### Puis-je personnaliser le remplacement de police par défaut dans GroupDocs.Viewer ?
Absolument, vous pouvez spécifier n'importe quelle police de votre choix comme remplacement par défaut des polices manquantes.
### GroupDocs.Viewer prend-il en charge le traitement par lots de documents ?
Oui, GroupDocs.Viewer vous permet de traiter plusieurs documents simultanément, ce qui le rend idéal pour les scénarios de traitement par lots.
### Où puis-je trouver une assistance ou un support supplémentaire pour GroupDocs.Viewer ?
Vous pouvez visiter le forum GroupDocs.Viewer [ici](https://forum.groupdocs.com/c/viewer/9) pour toute question d'assistance ou de support.