---
title: Obtenir les noms des feuilles de calcul
linktitle: Obtenir les noms des feuilles de calcul
second_title: API GroupDocs.Viewer .NET
description: Explorez la magie de GroupDocs.Viewer pour .NET – intégrez de manière transparente la visualisation de documents dans vos applications. Essayez l'essai gratuit maintenant !
weight: 11
url: /fr/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Introduction
Bienvenue dans le monde fascinant de GroupDocs.Viewer pour .NET ! Si vous êtes un développeur ou un passionné désireux d'explorer de puissantes fonctionnalités de visualisation de documents au sein de vos applications .NET, vous allez vous régaler. Dans ce guide complet, nous aborderons les subtilités de la récupération des noms de feuilles de calcul à l'aide de GroupDocs.Viewer. Alors attachez votre ceinture et embarquons pour ce voyage passionnant !
## Conditions préalables
Avant de plonger dans la magie du codage, assurons-nous que tout est configuré :
1.  Installez GroupDocs.Viewer pour .NET : rendez-vous sur le[lien de téléchargement](https://releases.groupdocs.com/viewer/net/)pour récupérer la dernière version de GroupDocs.Viewer pour .NET. Suivez les instructions d'installation pour l'intégrer de manière transparente dans votre environnement de développement.
2. Préparez votre document : assurez-vous d'avoir un document cible, disons un fichier Excel nommé "file.xlsx", dans votre répertoire de documents désigné.
## Importer des espaces de noms
Maintenant que vous avez les prérequis en place, commençons par importer les espaces de noms nécessaires. Cela garantit que votre application reconnaît et peut utiliser les fonctionnalités fournies par GroupDocs.Viewer pour .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Configuration du répertoire de documents
```csharp
string outputDirectory = "Your Document Directory";
```
Remplacez « Votre répertoire de documents » par le chemin d'accès au répertoire où se trouve votre document cible.
## 2. Initialisation de la visionneuse
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Dans cette étape, nous créons une instance de la classe Viewer, fournissant le chemin d'accès à votre fichier Excel.
## 3. Configuration des options d'affichage des informations
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Ici, nous configurons ViewInfoOptions pour générer des vues HTML et définir des options supplémentaires pour le rendu des feuilles de calcul.
## 4. Récupération des informations de vue
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Utilisez l'instance Viewer pour récupérer les informations d'affichage en fonction des options configurées.
## 5. Affichage des noms des feuilles de calcul
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Parcourez les pages récupérées et imprimez le nom de chaque feuille de calcul sur la console.
## Conclusion
Toutes nos félicitations! Vous avez réussi à parcourir le processus de récupération des noms de feuilles de calcul à l’aide de GroupDocs.Viewer pour .NET. Cela ouvre une myriade de possibilités pour améliorer les fonctionnalités de visualisation de documents au sein de vos applications.
## FAQ
### Puis-je utiliser GroupDocs.Viewer pour .NET avec d’autres formats de document ?
Absolument! GroupDocs.Viewer prend en charge un large éventail de formats de documents, notamment PDF, Microsoft Office, etc.
### Existe-t-il un essai gratuit disponible ?
 Oui, vous pouvez explorer GroupDocs.Viewer pour .NET avec notre[essai gratuit](https://releases.groupdocs.com/).
### Où puis-je trouver une assistance supplémentaire ?
 Dirigez-vous vers le[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pour le soutien et les discussions de la communauté.
### Puis-je obtenir un permis temporaire ?
 Certainement! Visite[ce lien](https://purchase.groupdocs.com/temporary-license/) pour obtenir votre permis temporaire.
### Existe-t-il des ressources de documentation détaillées disponibles ?
 Absolument! Vérifiez[documentation officielle](https://tutorials.groupdocs.com/viewer/net/) pour des informations détaillées et des guides.