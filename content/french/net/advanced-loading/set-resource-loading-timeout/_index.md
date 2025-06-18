---
"description": "Apprenez à configurer efficacement les délais de chargement des ressources dans GroupDocs.Viewer pour .NET. Maîtrisez le rendu des documents avec précision et stabilité."
"linktitle": "Définir le délai d'expiration du chargement des ressources (avancé)"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Définir le délai d'expiration du chargement des ressources (avancé)"
"url": "/fr/net/advanced-loading/set-resource-loading-timeout/"
"weight": 13
---

# Définir le délai d'expiration du chargement des ressources (avancé)

## Introduction
Dans le domaine du développement .NET, GroupDocs.Viewer offre un ensemble d'outils puissants pour le rendu précis et efficace des documents et des images. Exploiter pleinement ses fonctionnalités nécessite de comprendre ses subtilités, notamment la définition des délais d'expiration de chargement des ressources. Dans ce tutoriel, nous allons explorer le processus de configuration des délais d'expiration de chargement des ressources dans GroupDocs.Viewer pour .NET.

![Définir le délai d'expiration du chargement des ressources (avancé) dans GroupDocs.Viewer pour .NET](/viewer/advanced-loading/set-resource-loading-timeout-img.png)

## Prérequis
Avant de vous lancer dans ce tutoriel, assurez-vous de disposer des prérequis suivants :
1. Connaissances de base du développement .NET : une connaissance de la programmation C# et des fondamentaux du framework .NET est essentielle.
2. Installation de GroupDocs.Viewer pour .NET : Téléchargez et installez la bibliothèque GroupDocs.Viewer pour .NET à partir du [page de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Environnement de développement intégré (IDE) : disposez d’un IDE tel que Visual Studio installé sur votre système.

## Importer des espaces de noms
Avant de plonger dans le processus de codage, importez les espaces de noms nécessaires :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Étape 1 : Définir le répertoire de sortie
Tout d’abord, définissez le répertoire où les documents rendus seront enregistrés :
```csharp
string outputDirectory = "Your Document Directory";
```
Remplacer `"Your Document Directory"` avec le chemin où vous souhaitez enregistrer les documents rendus.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
Définir le format des chemins d'accès aux fichiers des pages individuelles :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ce format générera des noms de fichiers tels que `page_1.html`, `page_2.html`, etc., dans le répertoire de sortie spécifié.
## Étape 3 : Configurer les options de chargement
Configurez les options de chargement, y compris le délai d'expiration du chargement des ressources :
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Dans cet exemple, un délai d’expiration de 5 secondes est défini pour le chargement des ressources.
## Étape 4 : Initialiser l'objet Viewer
Initialiser le `Viewer` objet avec le document à restituer et les options de chargement définies :
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
Remplacer `TestFiles.WITH_EXTERNAL_IMAGE_DOC` avec le chemin vers le document que vous souhaitez rendre.
## Étape 5 : Configurer les options d’affichage HTML
Configurer les options d’affichage HTML pour les ressources intégrées :
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Cette configuration garantit que les ressources intégrées telles que les images sont incluses dans le HTML rendu.
## Étape 6 : Rendre le document
Affichez le document en utilisant les options configurées :
```csharp
viewer.View(options);
```
Cette étape lance le processus de rendu.
## Étape 7 : Afficher le répertoire de sortie
Afficher un message indiquant le rendu réussi et l'emplacement du répertoire de sortie :
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Maîtriser les délais d'expiration de chargement des ressources dans GroupDocs.Viewer pour .NET est essentiel pour garantir un rendu fluide des documents. En suivant ce tutoriel, vous aurez appris à configurer efficacement les délais d'expiration et à améliorer vos compétences en développement .NET.
## FAQ
### Quelle est l’importance de définir des délais d’expiration de chargement des ressources ?
La définition des délais d'expiration de chargement des ressources garantit que les processus de rendu ne se bloquent pas indéfiniment, améliorant ainsi la stabilité de l'application.
### Les délais d’expiration du chargement des ressources peuvent-ils être personnalisés en fonction des types de documents ?
Oui, les délais de chargement des ressources peuvent être ajustés en fonction de la complexité et de la taille des documents rendus.
### La définition de délais d’expiration plus courts a-t-elle des conséquences sur les performances ?
Des délais d'expiration plus courts peuvent entraîner un rendu incomplet de documents complexes si les ressources ne peuvent pas être chargées dans le délai spécifié.
### GroupDocs.Viewer est-il adapté au rendu de différents formats de documents ?
Oui, GroupDocs.Viewer prend en charge le rendu d'une large gamme de formats de documents, notamment PDF, DOCX, XLSX, etc.
### Les délais d’expiration du chargement des ressources peuvent-ils être désactivés ?
Bien que cela ne soit pas recommandé, les délais d'expiration de chargement des ressources peuvent être définis sur une valeur élevée ou complètement désactivés en fonction des exigences spécifiques.