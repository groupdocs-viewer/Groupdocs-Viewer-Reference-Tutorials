---
title: Rendre une présentation unique dans les dessins CAO
linktitle: Rendre une présentation unique dans les dessins CAO
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment restituer une présentation unique dans des dessins CAO à l'aide de GroupDocs.Viewer pour .NET. Étapes simples pour une intégration transparente dans vos applications .NET.
weight: 14
url: /fr/net/rendering-cad-drawings/render-single-layout-cad/
---

# Rendre une présentation unique dans les dessins CAO

## Introduction
Dans le domaine du développement .NET, la gestion et la visualisation des dessins CAO sont une exigence courante. GroupDocs.Viewer pour .NET simplifie cette tâche en fournissant une solution complète pour le rendu des dessins CAO dans les applications .NET. Dans ce didacticiel, nous aborderons le rendu d'une seule présentation dans des dessins CAO à l'aide de GroupDocs.Viewer pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
- Compréhension de base du langage de programmation C# et du framework .NET.
- Visual Studio installé sur votre système.
-  Bibliothèque GroupDocs.Viewer pour .NET téléchargée et référencée dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).
- Familiarité avec les formats de fichiers CAO et leurs structures.

## Importer des espaces de noms
Tout d'abord, importez les espaces de noms nécessaires dans votre code C# pour accéder aux fonctionnalités de GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Étape 1 : Définir le répertoire de sortie
Spécifiez le répertoire dans lequel vous souhaitez que la sortie rendue soit enregistrée.
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Définir le format du chemin du fichier de page
Définissez le format du chemin de fichier de chaque page rendue.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 3 : Instancier l'objet de visualisation
Créez une instance de la classe Viewer fournie par GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Étape 4 : Configurer les options d'affichage HTML
Configurez les options de rendu de la sortie HTML avec des ressources intégrées.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Étape 5 : Spécifiez le nom de la présentation CAO
Spécifiez le nom de la présentation CAO que vous souhaitez restituer.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Étape 6 : Rendre le dessin CAO
Appelez la méthode View de l'objet Viewer avec les options spécifiées.
```csharp
viewer.View(options);
```
## Étape 7 : Afficher le message de réussite
Informez l'utilisateur du rendu réussi du document source.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Le rendu de dessins CAO, en particulier lorsqu'il s'agit de mises en page, peut être une tâche ardue. Cependant, avec GroupDocs.Viewer pour .NET, le processus devient transparent et efficace. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement restituer une seule présentation dans les dessins CAO au sein de vos applications .NET.
## FAQ
### Puis-je restituer plusieurs mises en page simultanément à l’aide de GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu de plusieurs mises en page à partir de dessins CAO.
### GroupDocs.Viewer est-il compatible avec différents formats de fichiers CAO ?
Absolument, GroupDocs.Viewer prend en charge une large gamme de formats de fichiers CAO, notamment DWG, DXF, DGN, etc.
### Puis-je personnaliser les options de rendu des dessins CAO ?
Oui, GroupDocs.Viewer propose des options étendues pour personnaliser les paramètres de rendu en fonction de vos besoins.
### Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?
 Oui, vous pouvez explorer les fonctionnalités de GroupDocs.Viewer avec un essai gratuit disponible[ici](https://releases.groupdocs.com/).
### Où puis-je obtenir de l’assistance pour GroupDocs.Viewer pour .NET ?
 Pour toute question ou assistance, vous pouvez visiter le forum GroupDocs.Viewer[ici](https://forum.groupdocs.com/c/viewer/9).