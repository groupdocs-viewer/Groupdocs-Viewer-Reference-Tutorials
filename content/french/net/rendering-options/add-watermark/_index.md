---
title: Ajouter un filigrane dans le document
linktitle: Ajouter un filigrane dans le document
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment ajouter de manière transparente des filigranes aux documents à l'aide de GroupDocs.Viewer pour .NET. Améliorez la sécurité des documents et l'image de marque avec ce didacticiel facile à suivre.
weight: 10
url: /fr/net/rendering-options/add-watermark/
---

# Ajouter un filigrane dans le document

## Introduction
À l’ère numérique d’aujourd’hui, gérer et visualiser de manière transparente différents formats de documents est une nécessité pour de nombreuses entreprises et particuliers. Heureusement, avec des outils comme GroupDocs.Viewer pour .NET, la gestion des documents devient un jeu d'enfant. Cette puissante bibliothèque .NET permet aux développeurs d'intégrer sans effort la fonctionnalité de visualisation de documents dans leurs applications, permettant ainsi aux utilisateurs de visualiser des documents sans avoir besoin du logiciel d'origine qui les a créés.
## Conditions préalables
Avant de vous lancer dans l'utilisation de GroupDocs.Viewer pour .NET pour ajouter des filigranes aux documents, assurez-vous de disposer des éléments suivants :
1. Configuration de l'environnement : disposez d'un environnement de développement configuré avec .NET Framework ou .NET Core installé.
2.  GroupDocs.Viewer pour .NET : téléchargez et installez la bibliothèque GroupDocs.Viewer pour .NET à partir du[page de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Fichiers de documents : préparez les fichiers de documents avec lesquels vous souhaitez travailler, tels que DOCX, PDF ou autres.
4. Connaissance de base de C# : Une connaissance du langage de programmation C# est nécessaire pour implémenter les exemples de code.

## Importer des espaces de noms
Avant de commencer à ajouter des filigranes aux documents à l'aide de GroupDocs.Viewer pour .NET, assurez-vous d'importer les espaces de noms requis dans votre code C#. Cette étape vous permet d'accéder aux classes et méthodes fournies par la bibliothèque de manière transparente.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Passons maintenant au processus d'ajout d'un filigrane à un document à l'aide de GroupDocs.Viewer pour .NET. Suivez ces étapes pour intégrer de manière transparente la fonctionnalité de filigrane dans votre application.
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Spécifiez le répertoire dans lequel vous souhaitez que les fichiers de sortie soient enregistrés après avoir appliqué le filigrane.
## Étape 2 : Définir le format du chemin du fichier de page
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Définissez le format des chemins de fichiers des pages rendues. Dans cet exemple, des fichiers HTML avec des numéros de page seront générés.
## Étape 3 : Instancier l'objet de visualisation
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Le code continue à l'étape suivante...
}
```
Créez une instance de la classe Viewer, en passant le chemin d'accès au fichier de document en tant que paramètre. Dans cet exemple, nous utilisons un exemple de fichier DOCX.
## Étape 4 : Configurer les options d'affichage HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configurez les options d'affichage HTML, y compris le texte en filigrane que vous souhaitez ajouter au document.
## Étape 5 : Afficher le document avec filigrane
```csharp
viewer.View(options);
```
Appelez la méthode View de l'objet Viewer, en transmettant les options configurées. Cela rendra le document avec le filigrane spécifié.
## Étape 6 : Afficher le chemin du répertoire de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informez l'utilisateur du rendu réussi du document et indiquez le répertoire dans lequel les fichiers de sortie sont enregistrés.

## Conclusion
GroupDocs.Viewer pour .NET fournit un moyen pratique d'ajouter des filigranes aux documents par programmation. En suivant les étapes décrites dans ce didacticiel, vous pouvez intégrer de manière transparente la fonctionnalité de filigrane dans vos applications .NET, améliorant ainsi la sécurité des documents et l'image de marque.
## FAQ
### Puis-je personnaliser l’apparence du filigrane ?
Oui, vous pouvez personnaliser diverses propriétés du filigrane, telles que le texte, la police, la couleur, la taille et la position.
### GroupDocs.Viewer prend-il en charge l'affichage de documents à partir de sources distantes ?
Oui, GroupDocs.Viewer prend en charge l'affichage de documents à partir du stockage local ainsi que des URL distantes.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.groupdocs.com/).
### Puis-je ajouter des filigranes à plusieurs pages d'un document ?
Absolument, GroupDocs.Viewer permet d'ajouter des filigranes à des pages individuelles ou à toutes les pages d'un document.
### Comment puis-je obtenir de l'aide ou de l'aide si je rencontre des problèmes ?
 Vous pouvez demander de l'aide et du soutien sur les forums de la communauté GroupDocs.[ici](https://forum.groupdocs.com/c/viewer/9).