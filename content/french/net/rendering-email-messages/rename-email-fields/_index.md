---
title: Renommer les champs de courrier électronique pendant le rendu
linktitle: Renommer les champs de courrier électronique pendant le rendu
second_title: API GroupDocs.Viewer .NET
description: Améliorez l'expérience de visualisation de documents avec GroupDocs.Viewer pour .NET. Restituez et personnalisez les e-mails en toute transparence.
type: docs
weight: 12
url: /fr/net/rendering-email-messages/rename-email-fields/
---
## Introduction

À l’ère numérique d’aujourd’hui, gérer et visualiser efficacement les documents est primordial pour les entreprises comme pour les particuliers. Qu'il s'agisse de contrats, de rapports ou d'e-mails, la possibilité de naviguer de manière transparente dans ces documents peut grandement améliorer la productivité. C'est là qu'intervient GroupDocs.Viewer pour .NET. Cette puissante bibliothèque permet aux développeurs d'intégrer des fonctionnalités de visualisation de documents directement dans leurs applications .NET, offrant une large gamme de fonctionnalités pour le rendu de divers formats de documents.

## Conditions préalables

Avant de plonger dans le didacticiel sur le renommage des champs de courrier électronique lors du rendu à l'aide de GroupDocs.Viewer pour .NET, assurez-vous de disposer des conditions préalables suivantes :

1.  GroupDocs.Viewer pour la bibliothèque .NET : téléchargez et installez la bibliothèque GroupDocs.Viewer pour .NET à partir de[ici](https://releases.groupdocs.com/viewer/net/).

2. Environnement de développement : assurez-vous de disposer d'un environnement de développement approprié pour le développement .NET, tel que Visual Studio.

3. Compréhension de base de C# : Familiarisez-vous avec les bases du langage de programmation C#, car le didacticiel impliquera des extraits de code C#.

4. Répertoire des documents : préparez un répertoire dans lequel sont stockés les documents à restituer.

## Importer des espaces de noms

Afin d'utiliser les fonctionnalités de GroupDocs.Viewer dans votre application .NET, vous devez importer les espaces de noms nécessaires.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Décomposons maintenant le processus de renommage des champs de courrier électronique lors du rendu à l'aide de GroupDocs.Viewer pour .NET en plusieurs étapes :

## Étape 1 : Définir le répertoire de sortie

Tout d'abord, spécifiez le répertoire dans lequel les pages HTML rendues seront enregistrées.

```csharp
string outputDirectory = "Your Document Directory";
```

## Étape 2 : Définir le format du chemin du fichier de page

Définissez le format des chemins de fichiers des pages HTML rendues. Chaque page sera enregistrée dans un fichier HTML distinct.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Étape 3 : initialiser l'objet de visualisation

Créez une instance de la classe Viewer et transmettez le chemin du document à visualiser en paramètre.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Étape 4 : Configurer les options d'affichage HTML

Configurez les options de l'affichage HTML, notamment en spécifiant le format du fichier de sortie et en configurant les mappages de champs de courrier électronique.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Étape 5 : Rendre le document

Appelez la méthode View de l'objet Viewer, en transmettant les options d'affichage HTML configurées.

```csharp
viewer.View(options);
```

## Étape 6 : Afficher le message de réussite

Informez l'utilisateur que le document a été rendu avec succès.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

En conclusion, GroupDocs.Viewer pour .NET fournit une solution transparente pour le rendu de documents dans les applications .NET. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement renommer les champs de courrier électronique lors du rendu, améliorant ainsi la lisibilité et la convivialité des documents de courrier électronique. Grâce à son API intuitive et à ses fonctionnalités complètes, GroupDocs.Viewer permet aux développeurs de rationaliser efficacement les processus de visualisation de documents.

## FAQ

### Q : Puis-je restituer des documents autres que des e-mails à l'aide de GroupDocs.Viewer pour .NET ?

R : Oui, GroupDocs.Viewer prend en charge le rendu de divers formats de documents, notamment les PDF, les documents Microsoft Office, les images, etc.

### Q : GroupDocs.Viewer est-il compatible avec .NET Core ?

R : Oui, GroupDocs.Viewer prend en charge .NET Core ainsi que le .NET Framework traditionnel.

### Q : Puis-je personnaliser l’apparence des documents rendus ?

R : Absolument, GroupDocs.Viewer offre des options de personnalisation étendues pour contrôler l'apparence et le comportement des documents rendus.

### Q : GroupDocs.Viewer prend-il en charge le streaming de documents ?

R : Oui, GroupDocs.Viewer permet de diffuser des documents directement vers le navigateur du client sans avoir besoin de les stocker sur le serveur.

### Q : GroupDocs.Viewer est-il adapté aux applications de niveau entreprise ?

R : Certes, GroupDocs.Viewer est conçu pour répondre aux exigences des applications d'entreprise grâce à son évolutivité, sa fiabilité et son ensemble de fonctionnalités robustes.
