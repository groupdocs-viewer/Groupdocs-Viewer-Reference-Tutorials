---
"description": "Gérez efficacement les pièces jointes de vos applications .NET grâce à GroupDocs.Viewer. Récupérez et enregistrez vos pièces jointes en toute simplicité."
"linktitle": "Récupérer et enregistrer les pièces jointes des documents"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Récupérer et enregistrer les pièces jointes des documents"
"url": "/fr/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
---

# Récupérer et enregistrer les pièces jointes des documents

## Introduction
À l'ère du numérique, une gestion efficace des documents est essentielle pour les entreprises comme pour les particuliers. Qu'il s'agisse de gérer ses e-mails, de consulter ses contrats ou d'accéder à ses rapports, disposer d'un outil fiable de visualisation de documents est essentiel. GroupDocs.Viewer pour .NET s'impose comme une solution robuste, permettant aux utilisateurs de visualiser et d'interagir facilement avec différents formats de documents directement dans leurs applications .NET.

![Récupérer et enregistrer les pièces jointes des documents avec GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Prérequis
Avant de vous lancer dans l'utilisation de GroupDocs.Viewer pour .NET pour la récupération et l'enregistrement des pièces jointes de documents, assurez-vous de disposer des prérequis suivants :
1. Environnement d'exploitation : Un environnement de travail configuré avec le framework .NET.
2. Installation : Bibliothèque GroupDocs.Viewer pour .NET téléchargée et installée. Vous pouvez y accéder depuis le [lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Compréhension de base : Familiarité avec le langage de programmation C#.
4. Source du document : Accès à un exemple de document avec pièces jointes à des fins de démonstration.

## Importer des espaces de noms
Pour commencer à utiliser GroupDocs.Viewer pour .NET pour la récupération et l'enregistrement des pièces jointes de documents, importez les espaces de noms nécessaires :
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
## Étape 2 : instancier l'objet Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instanciez l’objet Viewer avec le chemin d’accès au document contenant les pièces jointes.
## Étape 3 : Récupérer les pièces jointes
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Récupérer une liste des pièces jointes présentes dans le document.
## Étape 4 : Enregistrer les pièces jointes
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
Affiche un message de réussite indiquant la réussite de l'enregistrement des pièces jointes ainsi que le chemin du répertoire.

## Conclusion
L'intégration de GroupDocs.Viewer pour .NET à vos workflows de gestion de documents simplifie la gestion des pièces jointes, offrant efficacité et praticité. En suivant le guide étape par étape décrit ci-dessus, les utilisateurs peuvent récupérer et enregistrer facilement les pièces jointes dans leurs applications .NET.
## FAQ
### GroupDocs.Viewer pour .NET peut-il gérer différents formats de documents ?
Oui, GroupDocs.Viewer prend en charge une large gamme de formats de documents, notamment les documents PDF, Microsoft Office, les images, etc.
### Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez accéder à l'essai gratuit à partir de [ici](https://releases.groupdocs.com/).
### Comment puis-je obtenir des licences temporaires pour GroupDocs.Viewer pour .NET ?
Les licences temporaires peuvent être acquises auprès de [ce lien](https://purchase.groupdocs.com/temporary-license/).
### Où puis-je trouver la documentation pour GroupDocs.Viewer pour .NET ?
Une documentation complète est disponible [ici](https://tutorials.groupdocs.com/viewer/net/).
### Quelles options de support sont disponibles pour GroupDocs.Viewer pour .NET ?
Vous pouvez demander de l'aide sur le forum communautaire [ici](https://forum.groupdocs.com/c/viewer/9).