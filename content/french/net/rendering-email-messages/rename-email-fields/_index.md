---
"description": "Améliorez la visualisation de vos documents avec GroupDocs.Viewer pour .NET. Affichez et personnalisez vos e-mails en toute simplicité."
"linktitle": "Renommer les champs de courrier électronique pendant le rendu"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Renommer les champs de courrier électronique pendant le rendu"
"url": "/fr/net/rendering-email-messages/rename-email-fields/"
"weight": 12
type: docs
---
# Renommer les champs de courrier électronique pendant le rendu

## Introduction

À l'ère du numérique, gérer et consulter efficacement les documents est primordial pour les entreprises comme pour les particuliers. Qu'il s'agisse de contrats, de rapports ou d'e-mails, naviguer facilement dans ces documents peut considérablement améliorer la productivité. C'est là qu'intervient GroupDocs.Viewer pour .NET. Cette puissante bibliothèque permet aux développeurs d'intégrer des fonctionnalités de visualisation de documents directement dans leurs applications .NET, offrant ainsi un large éventail de fonctionnalités pour le rendu de différents formats de documents.

## Prérequis

Avant de plonger dans le didacticiel sur le changement de nom des champs de courrier électronique lors du rendu à l'aide de GroupDocs.Viewer pour .NET, assurez-vous de disposer des prérequis suivants :

1. Bibliothèque GroupDocs.Viewer pour .NET : téléchargez et installez la bibliothèque GroupDocs.Viewer pour .NET à partir de [ici](https://releases.groupdocs.com/viewer/net/).

2. Environnement de développement : assurez-vous de disposer d’un environnement de développement adapté au développement .NET, tel que Visual Studio.

3. Compréhension de base de C# : familiarisez-vous avec les bases du langage de programmation C#, car le didacticiel impliquera des extraits de code C#.

4. Répertoire de documents : Préparez un répertoire où sont stockés les documents à restituer.

## Importer des espaces de noms

Afin d'utiliser les fonctionnalités de GroupDocs.Viewer dans votre application .NET, vous devez importer les espaces de noms nécessaires.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Décomposons maintenant le processus de changement de nom des champs de courrier électronique lors du rendu à l'aide de GroupDocs.Viewer pour .NET en plusieurs étapes :

## Étape 1 : Définir le répertoire de sortie

Tout d’abord, spécifiez le répertoire dans lequel les pages HTML rendues seront enregistrées.

```csharp
string outputDirectory = "Your Document Directory";
```

## Étape 2 : Définir le format du chemin d'accès au fichier d'échange

Définissez le format des chemins d'accès aux pages HTML affichées. Chaque page sera enregistrée dans un fichier HTML distinct.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Étape 3 : Initialiser l'objet Viewer

Créez une instance de la classe Viewer et transmettez le chemin du document à visualiser en tant que paramètre.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Étape 4 : Configurer les options d’affichage HTML

Configurez les options de la vue HTML, notamment en spécifiant le format du fichier de sortie et en configurant les mappages de champs de courrier électronique.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Étape 5 : Rendre le document

Appelez la méthode View de l’objet Viewer, en transmettant les options d’affichage HTML configurées.

```csharp
viewer.View(options);
```

## Étape 6 : Afficher le message de réussite

Informer l'utilisateur que le document a été rendu avec succès.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

En conclusion, GroupDocs.Viewer pour .NET offre une solution transparente pour l'affichage de documents dans les applications .NET. En suivant les étapes décrites dans ce tutoriel, vous pouvez facilement renommer les champs d'e-mail lors de l'affichage, améliorant ainsi la lisibilité et l'ergonomie des documents. Grâce à son API intuitive et à ses fonctionnalités complètes, GroupDocs.Viewer permet aux développeurs de rationaliser efficacement la visualisation des documents.

## FAQ

### Q : Puis-je restituer d’autres documents que des e-mails à l’aide de GroupDocs.Viewer pour .NET ?

: Oui, GroupDocs.Viewer prend en charge le rendu de divers formats de documents, notamment PDF, documents Microsoft Office, images, etc.

### Q : GroupDocs.Viewer est-il compatible avec .NET Core ?

R : Oui, GroupDocs.Viewer prend en charge .NET Core ainsi que le .NET Framework traditionnel.

### Q : Puis-je personnaliser l’apparence des documents rendus ?

R : Absolument, GroupDocs.Viewer offre de nombreuses options de personnalisation pour contrôler l’apparence et le comportement des documents rendus.

### Q : GroupDocs.Viewer prend-il en charge la diffusion de documents ?

R : Oui, GroupDocs.Viewer permet de diffuser des documents directement vers le navigateur du client sans avoir besoin de les stocker sur le serveur.

### Q : GroupDocs.Viewer est-il adapté aux applications de niveau entreprise ?

R : Certainement, GroupDocs.Viewer est conçu pour répondre aux exigences des applications de niveau entreprise grâce à son évolutivité, sa fiabilité et son ensemble de fonctionnalités robustes.