---
title: Exclure les polices du HTML rendu
linktitle: Exclure les polices du HTML rendu
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment exclure des polices du HTML rendu à l’aide de GroupDocs.Viewer pour .NET. Suivez ce guide étape par étape pour un affichage transparent des documents.
weight: 10
url: /fr/net/rendering-documents-html/exclude-fonts-html/
---
## Introduction
GroupDocs.Viewer for .NET est une puissante bibliothèque de rendu de documents qui permet aux développeurs d'afficher plus de 50 formats de documents dans leurs applications .NET sans avoir besoin de dépendances externes. Dans ce didacticiel, nous nous concentrerons sur une fonctionnalité spécifique de GroupDocs.Viewer : l'exclusion des polices de la sortie HTML rendue. 
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Compréhension de base du développement C# et .NET.
2.  GroupDocs.Viewer pour .NET installé. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio ou tout autre IDE pour le développement C#.

## Importer des espaces de noms
Dans votre code C#, assurez-vous d'inclure les espaces de noms nécessaires :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Étape 1 : Définir le répertoire de sortie
Configurez le répertoire dans lequel vous souhaitez que les fichiers HTML rendus soient enregistrés.
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Définir le format du chemin du fichier de page
Spécifiez le format des chemins de fichiers des pages individuelles du document rendu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 3 : initialiser l'objet de visualisation
Instanciez l'objet Viewer avec le document que vous souhaitez restituer.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Votre code va ici
}
```
## Étape 4 : Définir les options d'affichage HTML
Définissez les options de rendu HTML, y compris le format des ressources intégrées et les polices à exclure.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Étape 5 : Rendre le document
Transmettez les options d'affichage HTML à l'objet Viewer pour afficher le document.
```csharp
viewer.View(options);
```
## Étape 6 : Emplacement du document rendu en sortie
Informez l'utilisateur de l'emplacement où les fichiers HTML rendus sont enregistrés.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser GroupDocs.Viewer pour .NET pour exclure les polices de la sortie HTML rendue. En suivant les étapes décrites ci-dessus, vous pouvez personnaliser le processus de rendu pour répondre à vos besoins spécifiques, garantissant ainsi un affichage optimal des documents dans vos applications.
## FAQ
### Puis-je exclure plusieurs polices du HTML rendu ?
 Oui, vous pouvez ajouter plusieurs noms de polices au`FontsToExclude` liste dans les options d’affichage HTML.
### GroupDocs.Viewer est-il compatible avec tous les frameworks .NET ?
Oui, GroupDocs.Viewer prend en charge .NET Framework 4.6.1 et versions ultérieures.
### Puis-je restituer des documents à partir d’emplacements de stockage distants ?
Oui, GroupDocs.Viewer prend en charge le rendu des documents à partir du stockage local ainsi que des emplacements et flux de stockage distants.
### GroupDocs.Viewer prend-il en charge la conception réactive pour la sortie HTML ?
Oui, vous pouvez activer le rendu réactif en ajustant les options d'affichage HTML en conséquence.
### Un support technique est-il disponible pour GroupDocs.Viewer ?
 Oui, vous pouvez demander de l'aide et participer aux discussions sur le[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).