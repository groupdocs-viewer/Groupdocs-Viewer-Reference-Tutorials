---
"description": "Apprenez à générer une mise en page unique dans vos dessins CAO avec GroupDocs.Viewer pour .NET. Étapes simples pour une intégration transparente dans vos applications .NET."
"linktitle": "Rendu d'une disposition unique dans les dessins CAO"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu d'une disposition unique dans les dessins CAO"
"url": "/fr/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# Rendu d'une disposition unique dans les dessins CAO

## Introduction
Dans le domaine du développement .NET, la gestion et la visualisation des dessins CAO sont courantes. GroupDocs.Viewer pour .NET simplifie cette tâche en fournissant une solution complète pour le rendu des dessins CAO dans les applications .NET. Dans ce tutoriel, nous allons explorer le rendu d'une mise en page unique dans des dessins CAO avec GroupDocs.Viewer pour .NET.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Compréhension de base du langage de programmation C# et du framework .NET.
- Visual Studio installé sur votre système.
- Téléchargez la bibliothèque GroupDocs.Viewer pour .NET et ajoutez des tutoriels à votre projet. Vous pouvez la télécharger depuis [ici](https://releases.groupdocs.com/viewer/net/).
- Connaissance des formats de fichiers CAO et de leurs structures.

## Importer des espaces de noms
Tout d’abord, importez les espaces de noms nécessaires dans votre code C# pour accéder aux fonctionnalités de GroupDocs.Viewer.

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
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
Définissez le format du chemin de fichier de chaque page rendue.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 3 : instancier l'objet Viewer
Créez une instance de la classe Viewer fournie par GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Étape 4 : Configurer les options d’affichage HTML
Configurez les options de rendu de sortie HTML avec des ressources intégrées.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Étape 5 : Spécifier le nom de la disposition CAO
Spécifiez le nom de la mise en page CAO que vous souhaitez restituer.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Étape 6 : Rendu du dessin CAO
Appelez la méthode View de l’objet Viewer avec les options spécifiées.
```csharp
viewer.View(options);
```
## Étape 7 : Afficher le message de réussite
Informer l'utilisateur du rendu réussi du document source.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Le rendu de dessins CAO, notamment de mises en page, peut s'avérer complexe. Cependant, avec GroupDocs.Viewer pour .NET, le processus devient fluide et efficace. En suivant les étapes décrites dans ce tutoriel, vous pouvez facilement générer une mise en page unique dans vos dessins CAO au sein de vos applications .NET.
## FAQ
### Puis-je restituer plusieurs mises en page simultanément à l’aide de GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu de plusieurs mises en page à partir de dessins CAO.
### GroupDocs.Viewer est-il compatible avec différents formats de fichiers CAO ?
Absolument, GroupDocs.Viewer prend en charge une large gamme de formats de fichiers CAO, notamment DWG, DXF, DGN, etc.
### Puis-je personnaliser les options de rendu pour les dessins CAO ?
Oui, GroupDocs.Viewer fournit de nombreuses options pour personnaliser les paramètres de rendu en fonction de vos besoins.
### Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez explorer les fonctionnalités de GroupDocs.Viewer avec un essai gratuit disponible [ici](https://releases.groupdocs.com/).
### Où puis-je obtenir de l'aide pour GroupDocs.Viewer pour .NET ?
Pour toute question ou assistance, vous pouvez visiter le forum GroupDocs.Viewer [ici](https://forum.groupdocs.com/c/viewer/9).