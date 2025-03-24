---
title: Obtenir Afficher les informations sur le document PDF
linktitle: Obtenir Afficher les informations sur le document PDF
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment extraire des informations d'affichage à partir de documents PDF à l'aide de GroupDocs.Viewer pour .NET dans ce didacticiel complet.
weight: 16
url: /fr/net/pdf-rendering-options/get-view-info-pdf-document/
---

# Obtenir Afficher les informations sur le document PDF

## Introduction
GroupDocs.Viewer pour .NET est un outil puissant conçu pour rationaliser la visualisation de documents dans les applications .NET. Que vous traitiez de PDF, de documents Word, de feuilles de calcul Excel ou de présentations PowerPoint, cette bibliothèque simplifie le processus de rendu et d'interaction avec différents formats de fichiers. Dans ce didacticiel, nous nous concentrerons sur l'exploitation des capacités de GroupDocs.Viewer spécifiquement pour extraire les informations d'affichage des documents PDF.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1.  Installation de GroupDocs.Viewer pour .NET : assurez-vous d'avoir téléchargé et installé la bibliothèque GroupDocs.Viewer. Vous pouvez l'obtenir auprès du[lien de téléchargement](https://releases.groupdocs.com/viewer/net/).   
2. Connaissance de base de C# : La connaissance du langage de programmation C# est essentielle pour comprendre et mettre en œuvre les exemples de code fournis.
3. Accès à un document PDF : préparez un document PDF que vous utiliserez pour extraire les informations d'affichage.

## Importer des espaces de noms
Dans votre projet C#, importez les espaces de noms nécessaires pour utiliser les fonctionnalités de GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Décomposons maintenant le processus de récupération des informations d'affichage à partir d'un document PDF à l'aide de GroupDocs.Viewer pour .NET.
## Étape 1 : initialiser l'objet de visualisation
Créez un objet Viewer et fournissez le chemin d'accès au document PDF en tant que paramètre.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Étape 2 : définir ViewInfoOptions
Spécifiez les options d'affichage, telles que l'affichage HTML, pour récupérer les informations d'affichage.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Étape 3 : Obtenir des informations sur la vue
Appelez la méthode GetViewInfo pour extraire les informations d’affichage du document PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Étape 4 : Afficher les informations de sortie
Affichez les informations d'affichage extraites, telles que le type de document, le nombre de pages et les autorisations d'impression.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Conclusion
Dans ce didacticiel, nous avons expliqué comment utiliser GroupDocs.Viewer pour .NET pour extraire les informations d'affichage des documents PDF. En suivant les étapes fournies, vous pouvez intégrer de manière transparente cette fonctionnalité dans vos applications .NET, améliorant ainsi les capacités de gestion et de visualisation des documents.
## FAQ
### GroupDocs.Viewer est-il compatible avec d'autres formats de fichiers que le PDF ?
Oui, GroupDocs.Viewer prend en charge un large éventail de formats de documents, notamment Word, Excel, PowerPoint, etc.
### Puis-je personnaliser les options d'affichage en fonction des exigences de mon application ?
Absolument, GroupDocs.Viewer propose diverses options pour adapter l'expérience de visualisation en fonction de vos besoins spécifiques.
### GroupDocs.Viewer est-il adapté aux applications de bureau et Web ?
Oui, GroupDocs.Viewer est polyvalent et peut être intégré de manière transparente aux applications .NET de bureau et Web.
### GroupDocs.Viewer fournit-il une assistance et une assistance si je rencontre des problèmes lors de la mise en œuvre ?
Bien entendu, vous pouvez demander de l'aide au forum communautaire GroupDocs.Viewer ou accéder à des services d'assistance professionnels pour une résolution rapide de tout problème.
### Puis-je essayer GroupDocs.Viewer avant de faire un achat ?
 Oui, vous pouvez explorer les fonctionnalités de GroupDocs.Viewer en accédant à la version d'essai gratuite disponible sur le[site web](https://purchase.groupdocs.com/buy).