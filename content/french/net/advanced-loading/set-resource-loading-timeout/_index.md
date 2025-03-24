---
title: Définir le délai d'expiration du chargement des ressources (avancé)
linktitle: Définir le délai d'expiration du chargement des ressources (avancé)
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment configurer efficacement les délais d’attente de chargement des ressources dans GroupDocs.Viewer pour .NET. Maîtrisez le rendu des documents avec précision et stabilité.
weight: 13
url: /fr/net/advanced-loading/set-resource-loading-timeout/
---
## Introduction
Dans le domaine du développement .NET, GroupDocs.Viewer fournit un ensemble d'outils puissants pour restituer des documents et des images avec précision et efficacité. Pour tirer parti de ses capacités, il faut comprendre ses subtilités, notamment la définition de délais d'attente pour le chargement des ressources. Dans ce didacticiel, nous aborderons le processus de configuration des délais d'attente de chargement des ressources dans GroupDocs.Viewer pour .NET.
## Conditions préalables
Avant de vous lancer dans ce tutoriel, assurez-vous d'avoir les prérequis suivants :
1. Connaissance de base du développement .NET : une connaissance de la programmation C# et des principes fondamentaux du framework .NET est essentielle.
2.  Installation de GroupDocs.Viewer pour .NET : Téléchargez et installez la bibliothèque GroupDocs.Viewer pour .NET à partir du[page de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Environnement de développement intégré (IDE) : installez un IDE tel que Visual Studio sur votre système.

## Importer des espaces de noms
Avant de vous lancer dans le processus de codage, importez les espaces de noms nécessaires :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Étape 1 : Définir le répertoire de sortie
Tout d'abord, définissez le répertoire dans lequel les documents rendus seront enregistrés :
```csharp
string outputDirectory = "Your Document Directory";
```
 Remplacer`"Your Document Directory"`avec le chemin où vous souhaitez enregistrer les documents rendus.
## Étape 2 : Définir le format du chemin du fichier de page
Définissez le format des chemins de fichiers des pages individuelles :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Ce format générera des noms de fichiers comme`page_1.html`, `page_2.html`, etc., dans le répertoire de sortie spécifié.
## Étape 3 : configurer les options de chargement
Configurez les options de chargement, y compris le délai d'expiration du chargement des ressources :
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Dans cet exemple, un délai d'attente de 5 secondes est défini pour le chargement des ressources.
## Étape 4 : initialiser l'objet de visualisation
 Initialisez le`Viewer` objet avec le document à restituer et les options de chargement définies :
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Remplacer`TestFiles.WITH_EXTERNAL_IMAGE_DOC` avec le chemin d'accès au document que vous souhaitez restituer.
## Étape 5 : Configurer les options d'affichage HTML
Configurez les options d'affichage HTML pour les ressources intégrées :
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Cette configuration garantit que les ressources intégrées telles que les images sont incluses dans le code HTML rendu.
## Étape 6 : Rendre le document
Rendre le document en utilisant les options configurées :
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
La maîtrise des délais de chargement des ressources dans GroupDocs.Viewer pour .NET est cruciale pour garantir des processus de rendu de documents fluides. En suivant ce didacticiel, vous avez acquis des connaissances sur la configuration efficace des délais d'attente, améliorant ainsi vos compétences en développement .NET.
## FAQ
### Quelle est l’importance de définir des délais d’expiration de chargement des ressources ?
La définition de délais d'expiration de chargement des ressources garantit que les processus de rendu ne se bloquent pas indéfiniment, améliorant ainsi la stabilité des applications.
### Les délais d'attente de chargement des ressources peuvent-ils être personnalisés en fonction des types de documents ?
Oui, les délais de chargement des ressources peuvent être ajustés en fonction de la complexité et de la taille des documents rendus.
### La définition de délais d'attente plus courts a-t-elle des conséquences sur les performances ?
Des délais d'attente plus courts peuvent conduire à un rendu incomplet de documents complexes si les ressources ne peuvent pas être chargées dans le délai spécifié.
### GroupDocs.Viewer est-il adapté au rendu de différents formats de documents ?
Oui, GroupDocs.Viewer prend en charge le rendu d'un large éventail de formats de documents, notamment PDF, DOCX, XLSX, etc.
### Les délais d'attente de chargement des ressources peuvent-ils être désactivés ?
Bien que cela ne soit pas recommandé, les délais d'attente de chargement des ressources peuvent être définis sur une valeur élevée ou complètement désactivés en fonction des exigences spécifiques.