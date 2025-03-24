---
title: Rendre les pages sélectionnées
linktitle: Rendre les pages sélectionnées
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment afficher des pages sélectionnées à partir de documents à l'aide de Groupdocs.Viewer pour .NET. Tutoriel étape par étape avec des exemples de code inclus.
weight: 17
url: /fr/net/rendering-options/render-selected-pages/
---
## Introduction

Dans ce didacticiel, nous verrons comment utiliser Groupdocs.Viewer pour .NET pour afficher les pages sélectionnées à partir d'un document. Que vous soyez un développeur chevronné ou un débutant, ce guide étape par étape vous guidera facilement tout au long du processus.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

### 1.Installation

 Assurez-vous que Groupdocs.Viewer pour .NET est installé dans votre environnement de développement. Sinon, vous pouvez le télécharger depuis le[Lien de téléchargement](https://releases.groupdocs.com/viewer/net/).

## Importation d'espaces de noms

Dans votre fichier de code C#, importez les espaces de noms nécessaires pour accéder aux classes et méthodes requises. Vous pouvez le faire en utilisant le`using` directif:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Décomposons maintenant l'exemple de code fourni en plusieurs étapes :

## Étape 1 : Définir le répertoire de sortie

 Définissez le répertoire dans lequel vous souhaitez que les pages rendues soient enregistrées. Remplacer`"Your Document Directory"` avec le chemin du répertoire souhaité.

```csharp
string outputDirectory = "Your Document Directory";
```

## Étape 2 : Définir le format du chemin du fichier de page

Spécifiez le format des chemins de fichiers des pages rendues. Ceci sera utilisé pour enregistrer chaque page sous forme de fichier HTML dans le répertoire de sortie.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Étape 3 : Instancier l'objet de visualisation

Créez une instance de la classe Viewer, en passant le chemin du document que vous souhaitez afficher comme argument.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Étape 4 : Configurer les options d'affichage HTML

Configurez les options d'affichage HTML pour le rendu. Dans cet exemple, nous configurons les options pour intégrer des ressources dans la sortie HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Étape 5 : Afficher les pages sélectionnées

Spécifiez les numéros de page que vous souhaitez afficher. Dans ce cas, nous rendons les pages 1 à 3. Ensuite, appelez la méthode View sur l'objet Viewer, en passant les options et les numéros de page comme arguments.

```csharp
viewer.View(options, 1, 3);
```

## Étape 6 : Résultat de sortie

Enfin, affichez un message indiquant le rendu réussi du document et l'emplacement où les fichiers de sortie sont enregistrés.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment restituer les pages sélectionnées à partir d'un document à l'aide de Groupdocs.Viewer pour .NET. Grâce à ces connaissances, vous pouvez désormais intégrer facilement des fonctionnalités de rendu de documents dans vos applications .NET.

## FAQ

### Q : Puis-je restituer des pages à partir de différents types de documents, tels que des PDF ou des images ?

R : Oui, Groupdocs.Viewer pour .NET prend en charge le rendu des pages à partir de divers formats de documents, notamment les PDF, les documents Microsoft Office et les fichiers image.

### Q : Existe-t-il une version d'essai disponible pour tester avant d'acheter ?

 R : Oui, vous pouvez accéder à une version d'essai gratuite de Groupdocs.Viewer pour .NET à partir du[site web](https://releases.groupdocs.com/).

### Q : Puis-je personnaliser le format de sortie autre que HTML ?

R : Absolument, Groupdocs.Viewer pour .NET fournit des options pour afficher les pages sous forme d'images, de PDF, etc., en plus du HTML.

### Q : Comment puis-je obtenir des licences temporaires à des fins de test ?

R : Des licences temporaires peuvent être acquises auprès du[page de licence temporaire](https://purchase.groupdocs.com/temporary-license/) sur le site Groupdocs.

### Q : Où puis-je demander de l'aide ou obtenir de l'aide pour tout problème que je rencontre ?

 R : Vous pouvez visiter le[Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pour le soutien et les conseils de la communauté et des développeurs.