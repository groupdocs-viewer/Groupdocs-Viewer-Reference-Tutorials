---
"description": "Découvrez comment restituer de manière transparente des documents au format JPG/PNG dans .NET à l'aide de GroupDocs.Viewer pour une expérience utilisateur et une productivité améliorées."
"linktitle": "Rendre le document au format JPG"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendre le document au format JPG"
"url": "/fr/net/rendering-documents-images/render-jpg-png/"
"weight": 10
type: docs
---
# Rendre le document au format JPG

## Introduction

Dans le monde du développement .NET, la gestion efficace des documents est essentielle pour diverses applications. Que vous développiez un système de gestion de documents, une plateforme de commerce électronique ou une application riche en contenu, la visualisation fluide des documents est cruciale. C'est là qu'intervient GroupDocs.Viewer pour .NET, une solution complète pour le rendu de documents dans différents formats tels que JPG et PNG.

## Prérequis

Avant de vous lancer dans l'utilisation de GroupDocs.Viewer pour .NET, vous devez vous assurer de quelques prérequis :

1. Environnement de développement .NET : Assurez-vous de disposer d'un environnement de développement .NET fonctionnel sur votre machine. Cela inclut l'installation du SDK .NET.

2. Licence GroupDocs.Viewer : Obtenez une licence valide pour GroupDocs.Viewer. Vous pouvez acheter une licence ou utiliser une licence temporaire à des fins d'évaluation.

3. Installation : Téléchargez et installez GroupDocs.Viewer pour .NET à partir du fichier fourni [lien de téléchargement](https://releases.groupdocs.com/viewer/net/).

4. Fichiers de documents : Préparez les fichiers de documents que vous souhaitez afficher. GroupDocs.Viewer prend en charge divers formats, notamment DOCX, PDF, PPT, etc.

## Importer des espaces de noms

Pour commencer à générer des documents avec GroupDocs.Viewer pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet. Cela vous permettra d'accéder aux fonctionnalités de la bibliothèque.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Convertir un document au format JPG ou PNG est un processus simple avec GroupDocs.Viewer pour .NET. Voici un guide étape par étape pour vous aider à y parvenir :

## Étape 1 : Définir le répertoire de sortie

Tout d'abord, définissez le répertoire où vous souhaitez enregistrer les pages rendues. Ce répertoire doit exister et être accessible par l'application.

```csharp
string outputDirectory = "Your Document Directory";
```

## Étape 2 : Définir le format du chemin d'accès au fichier d'échange

Spécifiez le format des chemins d'accès aux fichiers de chaque page affichée. GroupDocs.Viewer remplacera `{0}` avec le numéro de page lors de l'enregistrement des fichiers.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Étape 3 : instancier l'objet Viewer

Créer une instance de `Viewer` classe en fournissant le chemin vers le fichier de document que vous souhaitez restituer.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Le code pour le rendu va ici
}
```

## Étape 4 : Définir les options de rendu

Spécifiez les options de rendu selon vos besoins. Pour le rendu JPG/PNG, utilisez `JpgViewOptions` ou `PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Étape 5 : Rendre le document

Invoquer le `View` méthode de la `Viewer` objet et passez les options de rendu créées précédemment.

```csharp
viewer.View(options);
```

## Étape 6 : Résultats de sortie

Une fois le processus de rendu terminé, vous pouvez informer l'utilisateur du rendu réussi et fournir le répertoire dans lequel les pages rendues sont enregistrées.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

En conclusion, GroupDocs.Viewer pour .NET offre une solution puissante pour le rendu de documents dans différents formats, notamment JPG et PNG. En suivant les étapes décrites dans ce tutoriel, vous pourrez intégrer facilement la fonctionnalité de rendu de documents à vos applications .NET, améliorant ainsi l'expérience utilisateur et la productivité.

## FAQ

### Q : Puis-je restituer des documents autres que DOCX à l’aide de GroupDocs.Viewer pour .NET ?

R : Oui, GroupDocs.Viewer prend en charge une large gamme de formats de documents, notamment PDF, PPT, XLS, etc.

### Q : Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?

R : Oui, vous pouvez télécharger une version d’essai gratuite à partir de [ici](https://releases.groupdocs.com/).

### Q : Comment puis-je obtenir une licence temporaire à des fins d’évaluation ?

R : Vous pouvez demander une licence temporaire auprès de [ici](https://purchase.groupdocs.com/temporary-license/).

### Q : Où puis-je trouver la documentation pour GroupDocs.Viewer pour .NET ?

A : Une documentation détaillée est disponible [ici](https://tutorials.groupdocs.com/viewer/net/).

### Q : Où puis-je obtenir de l’aide ou poser des questions concernant GroupDocs.Viewer pour .NET ?

R : Vous pouvez visiter le forum d'assistance [ici](https://forum.groupdocs.com/c/viewer/9) pour obtenir de l'aide.