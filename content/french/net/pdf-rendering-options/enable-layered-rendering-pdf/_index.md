---
"description": "Découvrez comment activer le rendu par calques dans les documents PDF avec GroupDocs.Viewer pour .NET. Améliorez facilement la visualisation de vos documents."
"linktitle": "Activer le rendu en couches dans PDF"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Activer le rendu en couches dans PDF"
"url": "/fr/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
type: docs
---
# Activer le rendu en couches dans PDF

## Introduction
Dans ce tutoriel, nous allons explorer le processus d'activation du rendu par calques dans les documents PDF à l'aide de GroupDocs.Viewer pour .NET. Le rendu par calques améliore l'affichage et la manipulation des documents, offrant ainsi aux utilisateurs une expérience de visualisation plus interactive.

![Activer le rendu en couches dans PDF avec GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. GroupDocs.Viewer pour .NET : assurez-vous d’avoir installé le package ou la bibliothèque nécessaire pour utiliser GroupDocs.Viewer pour .NET dans votre projet.
2. Visual Studio : vous devez avoir Visual Studio installé sur votre système pour coder et exécuter les exemples fournis.
3. Compréhension de base de C# : ce didacticiel suppose une familiarité avec la syntaxe et les concepts du langage de programmation C#.

## Importer des espaces de noms
Commencez par importer les espaces de noms requis dans votre projet :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Assurez-vous de spécifier le chemin du répertoire dans lequel vous souhaitez que la sortie rendue soit enregistrée.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Cette étape définit le format des chemins de fichiers des pages individuelles dans la sortie rendue. `{0}` est un espace réservé pour le numéro de page.
## Étape 3 : Activer le rendu en couches
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Ici, nous créons un `Viewer` et spécifier le document PDF à traiter. Nous configurons ensuite `HtmlViewOptions` avec le format de chemin d'accès au fichier d'échange défini. En définissant `EnableLayeredRendering` propriété à `true` dans `PdfOptions`, nous activons le rendu en couches pour le document PDF.
## Étape 4 : afficher le répertoire de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Enfin, nous imprimons un message indiquant le rendu réussi du document source et invitons l'utilisateur à vérifier la sortie dans le répertoire spécifié.

## Conclusion
L'activation du rendu par calques dans les documents PDF avec GroupDocs.Viewer pour .NET améliore les capacités de visualisation des documents, offrant aux utilisateurs une expérience plus riche et plus interactive. En suivant les étapes décrites dans ce tutoriel, vous pourrez intégrer facilement cette fonctionnalité à vos applications .NET.
## FAQ
### Qu'est-ce que le rendu en couches dans les documents PDF ?
Le rendu en couches permet la séparation et la manipulation de différents composants au sein d'un document PDF, permettant une visualisation interactive et une expérience utilisateur améliorée.
### Puis-je personnaliser le répertoire de sortie pour les documents rendus ?
Oui, vous pouvez spécifier n’importe quel chemin de répertoire pour la sortie selon vos besoins.
### GroupDocs.Viewer prend-il en charge d’autres formats de fichiers en plus du PDF ?
Oui, GroupDocs.Viewer prend en charge une large gamme de formats de documents, notamment Word, Excel, PowerPoint, etc.
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer est compatible avec les environnements .NET Framework et .NET Core.
### Où puis-je trouver un soutien ou une assistance supplémentaire ?
Vous pouvez visiter le forum GroupDocs.Viewer pour toute question ou assistance concernant la bibliothèque de visualisation.