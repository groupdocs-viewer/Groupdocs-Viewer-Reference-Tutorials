---
title: Obtenir des informations sur les fichiers de données Outlook (PST, OST)
linktitle: Obtenir des informations sur les fichiers de données Outlook (PST, OST)
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment extraire les informations d'affichage des fichiers de données Outlook (PST, OST) à l'aide de GroupDocs.Viewer pour .NET. Améliorez vos capacités de gestion de documents sans effort.
weight: 10
url: /fr/net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---

# Obtenir des informations sur les fichiers de données Outlook (PST, OST)

## Introduction
Dans le domaine de la gestion et de la visualisation de documents, GroupDocs.Viewer pour .NET se présente comme un outil puissant, notamment lorsqu'il s'agit de gérer les fichiers de données Outlook (PST, OST). Dans ce didacticiel, nous aborderons étape par étape le processus d'extraction des informations d'affichage de ces fichiers.
## Conditions préalables
Avant de commencer ce didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
### 1. Installation de GroupDocs.Viewer pour .NET
 Tout d’abord, vous devez avoir GroupDocs.Viewer pour .NET installé dans votre environnement de développement. Vous pouvez télécharger le package nécessaire à partir du[Site Web GroupDocs.Viewer pour .NET](https://releases.groupdocs.com/viewer/net/).
### 2. Familiarité avec le langage de programmation C#
Une connaissance de base du langage de programmation C# est essentielle pour comprendre et mettre en œuvre les exemples de code fournis.
### 3. Fichiers de données Outlook (PST, OST)
Assurez-vous que vous disposez de fichiers de données Outlook (PST, OST) à des fins de test. Vous pouvez obtenir des exemples de fichiers à partir de diverses sources ou utiliser vos propres fichiers de données.

## Importer des espaces de noms
Avant de plonger dans le code, assurons-nous d'importer les espaces de noms nécessaires :
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Maintenant, décomposons l'exemple fourni en plusieurs étapes :
## Étape 1 : instancier l'objet visualiseur
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Ici, nous initialisons un objet Viewer avec le chemin d'accès au fichier de données Outlook (OST) spécifié comme argument.
## Étape 2 : Configurer les options d'affichage des informations
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
Nous configurons les options de récupération des informations de vue. Dans ce cas, nous optons pour la vue HTML.
## Étape 3 : Récupérer les informations d’affichage Outlook
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
Cette ligne récupère les informations d'affichage du fichier de données Outlook.
## Étape 4 : Afficher le type de fichier et le nombre de pages
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
Nous imprimons le type de fichier et le nombre de pages dans le fichier de données Outlook.
## Étape 5 : Parcourir les dossiers
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
Cette boucle parcourt les dossiers contenus dans le fichier de données Outlook et imprime leurs noms.
## Étape 6 : finaliser la récupération
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
Un message indiquant la récupération réussie des informations de vue s'affiche.

## Conclusion
GroupDocs.Viewer pour .NET fournit une solution transparente pour extraire les informations d'affichage des fichiers de données Outlook (PST, OST). En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement obtenir des informations précieuses sur ces fichiers pour une gestion améliorée des documents.
## FAQ
### GroupDocs.Viewer pour .NET est-il compatible avec différentes versions de fichiers de données Outlook ?
Oui, GroupDocs.Viewer pour .NET prend en charge différentes versions de fichiers de données Outlook, garantissant ainsi la compatibilité entre différents environnements.
### Puis-je personnaliser les options d'affichage des fichiers de données Outlook à l'aide de GroupDocs.Viewer pour .NET ?
Absolument! GroupDocs.Viewer pour .NET offre des options de personnalisation étendues, vous permettant d'adapter l'expérience de visualisation en fonction de vos besoins.
### GroupDocs.Viewer pour .NET prend-il en charge d'autres formats de fichiers que les fichiers de données Outlook ?
Oui, GroupDocs.Viewer pour .NET prend en charge un large éventail de formats de fichiers, notamment PDF, DOCX, XLSX, etc.
### Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?
 Oui, vous pouvez accéder à un essai gratuit de GroupDocs.Viewer pour .NET à partir du site Web :[Essai gratuit](https://releases.groupdocs.com/).
### Où puis-je trouver une assistance ou une assistance supplémentaire pour GroupDocs.Viewer pour .NET ?
 Pour toute demande de renseignements ou d'assistance, vous pouvez visiter le forum de support GroupDocs.Viewer pour .NET :[Soutien](https://forum.groupdocs.com/c/viewer/9).