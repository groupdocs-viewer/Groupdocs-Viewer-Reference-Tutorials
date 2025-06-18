---
"description": "Découvrez comment ajouter facilement des filigranes à vos documents avec GroupDocs.Viewer pour .NET. Améliorez la sécurité et l'image de marque de vos documents grâce à ce tutoriel facile à suivre."
"linktitle": "Ajouter un filigrane dans le document"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Ajouter un filigrane dans le document"
"url": "/fr/net/rendering-options/add-watermark/"
"weight": 10
---

# Ajouter un filigrane dans le document

## Introduction
À l'ère du numérique, gérer et visualiser facilement divers formats de documents est devenu une nécessité pour de nombreuses entreprises et particuliers. Heureusement, grâce à des outils comme GroupDocs.Viewer pour .NET, la gestion des documents devient un jeu d'enfant. Cette puissante bibliothèque .NET permet aux développeurs d'intégrer facilement des fonctionnalités de visualisation de documents à leurs applications, permettant ainsi aux utilisateurs de consulter des documents sans avoir besoin du logiciel d'origine.
## Prérequis
Avant de vous lancer dans l'utilisation de GroupDocs.Viewer pour .NET pour ajouter des filigranes aux documents, assurez-vous de disposer des éléments suivants :
1. Configuration de l'environnement : disposez d'un environnement de développement configuré avec .NET Framework ou .NET Core installé.
2. GroupDocs.Viewer pour .NET : téléchargez et installez la bibliothèque GroupDocs.Viewer pour .NET à partir du [page de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Fichiers de documents : préparez les fichiers de documents avec lesquels vous souhaitez travailler, tels que DOCX, PDF ou autres.
4. Connaissances de base de C# : une familiarité avec le langage de programmation C# est nécessaire pour implémenter les exemples de code.

## Importer des espaces de noms
Avant de commencer à ajouter des filigranes à vos documents avec GroupDocs.Viewer pour .NET, assurez-vous d'importer les espaces de noms requis dans votre code C#. Cette étape vous permet d'accéder facilement aux classes et méthodes fournies par la bibliothèque.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Voyons maintenant comment ajouter un filigrane à un document avec GroupDocs.Viewer pour .NET. Suivez ces étapes pour intégrer facilement la fonctionnalité de filigrane à votre application.
## Étape 1 : définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Spécifiez le répertoire dans lequel vous souhaitez que les fichiers de sortie soient enregistrés après l'application du filigrane.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Définissez le format des chemins d'accès aux pages affichées. Dans cet exemple, des fichiers HTML avec numéros de page seront générés.
## Étape 3 : instancier l'objet Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Le code continue à l'étape suivante...
}
```
Créez une instance de la classe Viewer en passant le chemin d'accès au fichier document en paramètre. Dans cet exemple, nous utilisons un fichier DOCX.
## Étape 4 : Configurer les options d’affichage HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configurez les options d’affichage HTML, y compris le texte du filigrane que vous souhaitez ajouter au document.
## Étape 5 : Afficher le document avec filigrane
```csharp
viewer.View(options);
```
Appelez la méthode View de l'objet Viewer en lui transmettant les options configurées. Le document sera alors affiché avec le filigrane spécifié.
## Étape 6 : Afficher le chemin du répertoire de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informez l'utilisateur du rendu réussi du document et indiquez le répertoire dans lequel les fichiers de sortie sont enregistrés.

## Conclusion
GroupDocs.Viewer pour .NET offre un moyen pratique d'ajouter des filigranes aux documents par programmation. En suivant les étapes décrites dans ce tutoriel, vous pourrez intégrer facilement la fonctionnalité de filigrane à vos applications .NET, améliorant ainsi la sécurité et l'image de marque de vos documents.
## FAQ
### Puis-je personnaliser l’apparence du filigrane ?
Oui, vous pouvez personnaliser diverses propriétés du filigrane, telles que le texte, la police, la couleur, la taille et la position.
### GroupDocs.Viewer prend-il en charge l’affichage de documents à partir de sources distantes ?
Oui, GroupDocs.Viewer prend en charge l'affichage des documents à partir du stockage local ainsi que des URL distantes.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ici](https://releases.groupdocs.com/).
### Puis-je ajouter des filigranes à plusieurs pages d’un document ?
Absolument, GroupDocs.Viewer permet d'ajouter des filigranes à des pages individuelles ou à toutes les pages d'un document.
### Comment puis-je obtenir de l’aide ou de l’assistance si je rencontre des problèmes ?
Vous pouvez demander de l'aide et du soutien sur les forums de la communauté GroupDocs. [ici](https://forum.groupdocs.com/c/viewer/9).