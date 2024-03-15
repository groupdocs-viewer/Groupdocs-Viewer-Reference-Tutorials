---
title: Récupérer et enregistrer les pièces jointes de documents
linktitle: Récupérer et enregistrer les pièces jointes de documents
second_title: API GroupDocs.Viewer .NET
description: Gérez efficacement les pièces jointes aux documents dans les applications .NET à l’aide de GroupDocs.Viewer. Récupérez et enregistrez les pièces jointes sans tracas.
type: docs
weight: 12
url: /fr/net/processing-document-attachments/retrieve-and-save-attachments/
---
## Introduction
À l’ère du numérique, une gestion efficace des documents est cruciale pour les entreprises comme pour les particuliers. Qu'il s'agisse de gérer des e-mails, de consulter des contrats ou d'accéder à des rapports, disposer d'un outil fiable de visualisation de documents est essentiel. GroupDocs.Viewer pour .NET apparaît comme une solution robuste, permettant aux utilisateurs de visualiser et d'interagir sans effort avec divers formats de documents directement dans leurs applications .NET.
## Conditions préalables
Avant de vous lancer dans l'utilisation de GroupDocs.Viewer pour .NET pour la récupération et l'enregistrement de pièces jointes, assurez-vous que vous disposez des conditions préalables suivantes :
1. Environnement d'exploitation : Un environnement de travail mis en place avec le framework .NET.
2.  Installation : bibliothèque GroupDocs.Viewer pour .NET téléchargée et installée. Vous pouvez accéder à la bibliothèque depuis le[lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Compréhension de base : Familiarité avec le langage de programmation C#.
4. Source du document : accès à un exemple de document avec pièces jointes à des fins de démonstration.

## Importer des espaces de noms
Pour commencer à utiliser GroupDocs.Viewer pour .NET pour la récupération et l'enregistrement des pièces jointes, importez les espaces de noms nécessaires :
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Définissez le répertoire dans lequel vous souhaitez enregistrer les pièces jointes récupérées du document.
## Étape 2 : Instancier l'objet de visualisation
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instanciez l'objet Viewer avec le chemin d'accès au document contenant les pièces jointes.
## Étape 3 : Récupérer les pièces jointes
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Récupérer une liste des pièces jointes présentes dans le document.
## Étape 4 : Enregistrer les pièces jointes
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Parcourez chaque pièce jointe, définissez le chemin du fichier et enregistrez la pièce jointe dans le répertoire spécifié.
## Étape 5 : Afficher le message de réussite
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Afficher un message de réussite indiquant l'enregistrement réussi des pièces jointes ainsi que le chemin du répertoire.

## Conclusion
L'intégration de GroupDocs.Viewer pour .NET dans vos flux de travail de gestion de documents rationalise le processus de gestion des pièces jointes, offrant efficacité et commodité. En suivant le guide étape par étape décrit ci-dessus, les utilisateurs peuvent facilement récupérer et enregistrer les pièces jointes des documents dans leurs applications .NET.
## FAQ
### GroupDocs.Viewer pour .NET peut-il gérer différents formats de documents ?
Oui, GroupDocs.Viewer prend en charge un large éventail de formats de documents, notamment les PDF, les documents Microsoft Office, les images, etc.
### Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?
 Oui, vous pouvez accéder à l'essai gratuit à partir de[ici](https://releases.groupdocs.com/).
### Comment puis-je obtenir des licences temporaires pour GroupDocs.Viewer pour .NET ?
 Des licences temporaires peuvent être acquises auprès de[ce lien](https://purchase.groupdocs.com/temporary-license/).
### Où puis-je trouver de la documentation pour GroupDocs.Viewer pour .NET ?
 Une documentation complète est disponible[ici](https://reference.groupdocs.com/viewer/net/).
### Quelles options de support sont disponibles pour GroupDocs.Viewer pour .NET ?
 Vous pouvez demander de l'aide sur le forum communautaire[ici](https://forum.groupdocs.com/c/viewer/9).