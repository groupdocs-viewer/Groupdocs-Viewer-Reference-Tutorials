---
"description": "Découvrez comment afficher facilement des documents depuis votre disque local grâce à Groupdocs.Viewer pour .NET. Améliorez vos applications .NET grâce à une gestion efficace des documents."
"linktitle": "Charger des documents à partir du disque local"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Charger des documents à partir du disque local"
"url": "/fr/net/loading-documents/loading-document-local-disk/"
"weight": 10
type: docs
---
# Charger des documents à partir du disque local

## Introduction
À l'ère du numérique, un rendu de documents efficace est essentiel pour diverses applications. Groupdocs.Viewer pour .NET offre une solution puissante pour le rendu de documents directement depuis votre disque local. Dans ce tutoriel, nous vous guiderons dans le processus de chargement de documents depuis votre disque local avec Groupdocs.Viewer pour .NET. Que vous soyez un développeur expérimenté ou débutant, ce guide étape par étape vous aidera à intégrer facilement le rendu de documents à vos applications .NET.

![Charger des documents à partir du disque local avec GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-local-disk.png)

## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
1. Groupdocs.Viewer pour .NET : téléchargez et installez la dernière version à partir de [ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement .NET : assurez-vous qu’un environnement de développement .NET fonctionnel est configuré sur votre système.
3. Documents locaux : stockez les documents que vous souhaitez restituer localement sur votre disque.

## Importer des espaces de noms
Tout d’abord, importons les espaces de noms nécessaires pour accéder aux fonctionnalités de Groupdocs.Viewer pour .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Charger les documents à partir du disque local
Commencez par configurer le répertoire de sortie dans lequel les pages HTML rendues seront enregistrées.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 2 : Initialiser la visionneuse et afficher les documents
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
Félicitations ! Vous avez appris à charger des documents depuis votre disque local avec Groupdocs.Viewer pour .NET. Cet outil puissant ouvre un monde de possibilités pour le rendu de documents dans vos applications .NET.
## FAQ
### Puis-je restituer des documents de différents formats à l’aide de Groupdocs.Viewer pour .NET ?
Oui, Groupdocs.Viewer pour .NET prend en charge une large gamme de formats de documents, notamment DOCX, PDF, XLSX, PPTX, etc.
### Groupdocs.Viewer pour .NET est-il compatible avec tous les frameworks .NET ?
Groupdocs.Viewer pour .NET est compatible avec la plupart des frameworks .NET, notamment .NET Core, .NET Framework et .NET Standard.
### Puis-je personnaliser les options de rendu de mes documents ?
Absolument ! Groupdocs.Viewer pour .NET offre de nombreuses options de personnalisation vous permettant d'adapter le rendu à vos besoins spécifiques.
### Existe-t-il une version d'essai disponible pour Groupdocs.Viewer pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ici](https://releases.groupdocs.com/).
### Où puis-je trouver de l'aide ou des ressources supplémentaires pour Groupdocs.Viewer pour .NET ?
Pour obtenir de l'aide et des ressources supplémentaires, visitez Groupdocs.Viewer pour .NET [forum](https://forum.groupdocs.com/c/viewer/9).