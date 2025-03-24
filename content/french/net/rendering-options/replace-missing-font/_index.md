---
title: Remplacer la police manquante
linktitle: Remplacer la police manquante
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment remplacer facilement les polices manquantes dans les documents .NET à l'aide de GroupDocs.Viewer. Garantissez un rendu précis en quelques étapes simples.
weight: 20
url: /fr/net/rendering-options/replace-missing-font/
---
## Introduction
Dans le monde du développement .NET, une gestion efficace des documents est cruciale. GroupDocs.Viewer pour .NET fournit une solution puissante pour afficher différents formats de documents dans vos applications .NET. Dans ce didacticiel, nous verrons comment utiliser GroupDocs.Viewer pour .NET pour remplacer les polices manquantes dans les documents. Que vous traitiez de PDF, de présentations PowerPoint ou de documents Word, GroupDocs.Viewer simplifie le processus, garantissant que vos documents sont rendus avec précision, même lorsque des polices sont manquantes.
## Conditions préalables
Avant de plonger dans ce didacticiel, assurez-vous d'avoir les éléments suivants :
1. GroupDocs.Viewer pour .NET : Téléchargez et installez la bibliothèque GroupDocs.Viewer à partir du site Web](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : configurez un environnement de développement .NET, tel que Visual Studio.
3. Connaissances de base en C# : Familiarité avec le langage de programmation C# et le framework .NET.

## Importer des espaces de noms
Dans votre code C#, importez les espaces de noms nécessaires pour accéder aux fonctionnalités GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Passons maintenant au processus de remplacement des polices manquantes dans les documents à l'aide de GroupDocs.Viewer pour .NET.
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Définissez le répertoire dans lequel les pages du document rendues seront enregistrées.
## Étape 2 : Définir le format du chemin du fichier de page
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Spécifiez le format de nom des fichiers HTML de sortie. Dans cet exemple, chaque page sera enregistrée sous forme de fichier HTML avec la convention de dénomination « page_{page_number}.html".
## Étape 3 : initialiser l'objet de visualisation
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Initialisez une nouvelle instance de la classe Viewer, en passant le chemin d'accès au fichier du document (dans ce cas, une présentation PowerPoint avec des polices manquantes) comme paramètre.
## Étape 4 : Définir les options d'affichage HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Créez une instance de HtmlViewOptions et configurez-la pour intégrer des ressources dans la sortie HTML. Spécifiez un nom de police par défaut à utiliser pour remplacer les polices manquantes.
## Étape 5 : Rendre le document
```csharp
viewer.View(options);
```
Invoquez la méthode View de l'objet Viewer, en transmettant les options d'affichage HTML. Cela rendra les pages du document en utilisant les options spécifiées.
## Étape 6 : Afficher le chemin de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprimez un message indiquant le rendu réussi du document et indiquez le chemin où les fichiers HTML de sortie sont enregistrés.

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser GroupDocs.Viewer pour .NET pour remplacer les polices manquantes dans les documents. En suivant ces étapes, vous pouvez vous assurer que vos documents sont rendus avec précision, même lorsque certaines polices ne sont pas disponibles. GroupDocs.Viewer simplifie le processus, vous permettant de vous concentrer sur la création d'applications .NET robustes sans vous soucier des problèmes de compatibilité des polices.
## FAQ
### GroupDocs.Viewer peut-il gérer d’autres types de problèmes liés aux polices ?
Oui, GroupDocs.Viewer fournit diverses fonctionnalités liées aux polices, notamment la substitution de polices et la détection de polices.
### GroupDocs.Viewer est-il compatible avec tous les frameworks .NET ?
GroupDocs.Viewer prend en charge un large éventail de frameworks .NET, notamment .NET Core et .NET Standard.
### Puis-je personnaliser le remplacement de la police par défaut dans GroupDocs.Viewer ?
Absolument, vous pouvez spécifier n'importe quelle police de votre choix comme remplacement par défaut des polices manquantes.
### GroupDocs.Viewer prend-il en charge le traitement par lots de documents ?
Oui, GroupDocs.Viewer vous permet de traiter plusieurs documents simultanément, ce qui le rend idéal pour les scénarios de traitement par lots.
### Où puis-je trouver une assistance ou un support supplémentaire pour GroupDocs.Viewer ?
 Vous pouvez visiter le forum GroupDocs.Viewer[ici](https://forum.groupdocs.com/c/viewer/9) pour toute demande d'assistance ou de support.