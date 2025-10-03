---
"description": "Apprenez à afficher des pages sélectionnées à partir de documents avec Groupdocs.Viewer pour .NET. Tutoriel pas à pas avec exemples de code inclus."
"linktitle": "Rendre les pages sélectionnées"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendre les pages sélectionnées"
"url": "/fr/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# Rendre les pages sélectionnées

## Introduction

Dans ce tutoriel, nous allons découvrir comment utiliser Groupdocs.Viewer pour .NET pour afficher les pages sélectionnées d'un document. Que vous soyez un développeur expérimenté ou débutant, ce guide étape par étape vous guidera tout au long du processus.

## Prérequis

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

### 1. Installation

Assurez-vous que Groupdocs.Viewer pour .NET est installé dans votre environnement de développement. Sinon, vous pouvez le télécharger depuis le [Lien de téléchargement](https://releases.groupdocs.com/viewer/net/).

## Importation d'espaces de noms

Dans votre fichier de code C#, importez les espaces de noms nécessaires pour accéder aux classes et méthodes requises. Pour ce faire, utilisez l'outil `using` directif:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Décomposons maintenant l’exemple de code fourni en plusieurs étapes :

## Étape 1 : définir le répertoire de sortie

Définissez le répertoire où vous souhaitez enregistrer les pages rendues. Remplacez `"Your Document Directory"` avec le chemin du répertoire souhaité.

```csharp
string outputDirectory = "Your Document Directory";
```

## Étape 2 : Définir le format du chemin d'accès au fichier d'échange

Spécifiez le format des chemins d'accès aux pages affichées. Ce format sera utilisé pour enregistrer chaque page au format HTML dans le répertoire de sortie.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Étape 3 : instancier l'objet Viewer

Créez une instance de la classe Viewer, en passant le chemin du document que vous souhaitez restituer comme argument.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Étape 4 : Configurer les options d’affichage HTML

Configurez les options d'affichage HTML pour le rendu. Dans cet exemple, nous configurons les options d'intégration des ressources dans la sortie HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Étape 5 : Afficher les pages sélectionnées

Spécifiez les numéros de page à afficher. Dans ce cas, nous affichons les pages 1 à 3. Appelez ensuite la méthode View sur l'objet Viewer en passant les options et les numéros de page comme arguments.

```csharp
viewer.View(options, 1, 3);
```

## Étape 6 : Résultat de sortie

Enfin, affichez un message indiquant le rendu réussi du document et l'emplacement où les fichiers de sortie sont enregistrés.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

Félicitations ! Vous avez appris à afficher les pages sélectionnées d'un document avec Groupdocs.Viewer pour .NET. Grâce à ces connaissances, vous pouvez désormais intégrer facilement les fonctionnalités de rendu de documents à vos applications .NET.

## FAQ

### Q : Puis-je restituer des pages à partir de différents types de documents, tels que des PDF ou des images ?

R : Oui, Groupdocs.Viewer pour .NET prend en charge le rendu de pages à partir de divers formats de documents, notamment les fichiers PDF, les documents Microsoft Office et les fichiers image.

### Q : Existe-t-il une version d’essai disponible pour tester avant l’achat ?

R : Oui, vous pouvez accéder à une version d’essai gratuite de Groupdocs.Viewer pour .NET à partir du [site web](https://releases.groupdocs.com/).

### Q : Puis-je personnaliser le format de sortie autre que HTML ?

R : Absolument, Groupdocs.Viewer pour .NET fournit des options pour restituer des pages sous forme d’images, de PDF et plus encore, en plus du HTML.

### Q : Comment puis-je obtenir des licences temporaires à des fins de test ?

R : Des licences temporaires peuvent être acquises auprès du [page de licence temporaire](https://purchase.groupdocs.com/temporary-license/) sur le site Groupdocs.

### Q : Où puis-je demander de l’aide ou obtenir de l’aide en cas de problème que je rencontre ?

A : Vous pouvez visiter le [Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pour le soutien et les conseils de la communauté et des développeurs.