---
title: Charger des documents à partir du disque local
linktitle: Charger des documents à partir du disque local
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer de manière transparente des documents à partir de votre disque local à l'aide de Groupdocs.Viewer for .NET. Améliorez vos applications .NET avec un document efficace.
weight: 10
url: /fr/net/loading-documents/loading-document-local-disk/
---

# Charger des documents à partir du disque local

## Introduction
À l’ère numérique d’aujourd’hui, un rendu efficace des documents est essentiel pour diverses applications. Groupdocs.Viewer for .NET offre une solution puissante pour restituer des documents directement à partir de votre disque local. Dans ce didacticiel, nous vous guiderons tout au long du processus de chargement de documents à partir de votre disque local à l'aide de Groupdocs.Viewer pour .NET. Que vous soyez un développeur chevronné ou débutant, ce guide étape par étape vous aidera à intégrer de manière transparente le rendu de documents dans vos applications .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1.  Groupdocs.Viewer pour .NET : téléchargez et installez la dernière version à partir de[ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement .NET : assurez-vous de disposer d'un environnement de développement .NET fonctionnel configuré sur votre système.
3. Documents locaux : stockez les documents que vous souhaitez restituer localement sur votre disque.

## Importer des espaces de noms
Tout d'abord, importons les espaces de noms nécessaires pour accéder aux fonctionnalités de Groupdocs.Viewer pour .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Charger des documents à partir du disque local
Commencez par configurer le répertoire de sortie dans lequel les pages HTML rendues seront enregistrées.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 2 : initialiser la visionneuse et restituer les documents
Initialisez l'objet Viewer avec le chemin du document et restituez-le à l'aide des options d'affichage HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Étape 3 : Afficher la sortie
Une fois le rendu terminé, affichez un message indiquant le rendu réussi du document source et l'emplacement des fichiers de sortie.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment charger des documents à partir de votre disque local à l'aide de Groupdocs.Viewer pour .NET. Cet outil puissant ouvre un monde de possibilités pour le rendu de documents au sein de vos applications .NET.
## FAQ
### Puis-je restituer des documents de différents formats à l’aide de Groupdocs.Viewer pour .NET ?
Oui, Groupdocs.Viewer pour .NET prend en charge un large éventail de formats de documents, notamment DOCX, PDF, XLSX, PPTX, etc.
### Groupdocs.Viewer pour .NET est-il compatible avec tous les frameworks .NET ?
Groupdocs.Viewer pour .NET est compatible avec la plupart des frameworks .NET, notamment .NET Core, .NET Framework et .NET Standard.
### Puis-je personnaliser les options de rendu de mes documents ?
Absolument! Groupdocs.Viewer pour .NET fournit des options de personnalisation étendues vous permettant d'adapter le processus de rendu à vos besoins spécifiques.
### Existe-t-il une version d'essai disponible pour Groupdocs.Viewer pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.groupdocs.com/).
### Où puis-je trouver une assistance ou des ressources supplémentaires pour Groupdocs.Viewer pour .NET ?
 Pour obtenir de l'aide et des ressources supplémentaires, visitez le Groupdocs.Viewer for .NET[forum](https://forum.groupdocs.com/c/viewer/9).