---
title: Rendre les colonnes et les lignes masquées
linktitle: Rendre les colonnes et les lignes masquées
second_title: API GroupDocs.Viewer .NET
description: Déverrouillez facilement les données cachées dans les feuilles de calcul à l'aide de GroupDocs.Viewer pour .NET. Suivez notre guide étape par étape pour révéler les colonnes et les lignes masquées.
weight: 13
url: /fr/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---

# Rendre les colonnes et les lignes masquées

## Introduction
Dans le domaine de la visualisation de documents, GroupDocs.Viewer pour .NET se présente comme un outil robuste qui facilite le rendu transparent de divers formats de documents. Une fonctionnalité intéressante est la possibilité de révéler des colonnes et des lignes cachées dans des feuilles de calcul. Dans ce didacticiel, nous aborderons les étapes permettant de débloquer cette fonctionnalité et de libérer le potentiel de vos données.
## Conditions préalables
Avant de vous lancer dans ce voyage, assurez-vous d'avoir les conditions préalables suivantes en place :
- GroupDocs.Viewer pour .NET : assurez-vous que la dernière version est installée. Sinon, vous pouvez le télécharger depuis le[site officiel](https://releases.groupdocs.com/viewer/net/).
- Fichier de document : préparez un exemple de document dans un format de feuille de calcul (par exemple, SAMPLE.XLSX) pour expérimenter les colonnes et les lignes masquées.
- Environnement de développement : configurez un environnement de travail, de préférence en utilisant Visual Studio ou tout autre IDE approprié pour le développement .NET.
## Importer des espaces de noms
Dans votre projet .NET, importez les espaces de noms nécessaires pour exploiter efficacement les fonctionnalités de GroupDocs.Viewer :
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Configurer le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Définissez le répertoire de sortie dans lequel les pages HTML rendues seront stockées. Ajustez le format du chemin de fichier en conséquence.
## Étape 2 : initialiser la visionneuse et configurer les options
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Créez une instance de Viewer en fournissant le chemin d'accès à votre feuille de calcul. Configurez les options d'affichage HTML pour intégrer des ressources et activer le rendu des colonnes et des lignes masquées.
## Étape 3 : Exécuter le processus de rendu
```csharp
    viewer.View(options);
}
```
Appelez la méthode View sur l'objet visualiseur, en transmettant les options configurées. Cela lance le processus de rendu.
## Étape 4 : Vérifiez la sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Vérifiez le rendu réussi du document source et localisez la sortie dans le répertoire spécifié.
## Conclusion
Déverrouiller les colonnes et les lignes masquées dans vos feuilles de calcul devient un jeu d'enfant avec GroupDocs.Viewer pour .NET. Ce didacticiel vous a fourni les étapes essentielles pour révéler les données masquées, offrant ainsi une vue plus complète de vos documents.
## Questions fréquemment posées
### Puis-je afficher les colonnes et les lignes masquées dans d'autres formats de document que les feuilles de calcul ?
Oui, GroupDocs.Viewer prend en charge divers formats de documents, notamment Word, PDF et PowerPoint, en plus des feuilles de calcul.
### Y a-t-il une limite au nombre de colonnes et de lignes masquées pouvant être affichées ?
GroupDocs.Viewer gère efficacement le rendu d'un large éventail de colonnes et de lignes masquées. Toutefois, les cas extrêmes comportant une grande quantité de données cachées peuvent avoir un impact sur les performances.
### Puis-je personnaliser le format de sortie des données rendues ?
Absolument! GroupDocs.Viewer fournit des options flexibles pour personnaliser la sortie, vous permettant d'adapter les données rendues à vos besoins spécifiques.
### Existe-t-il des considérations en matière de licence pour l’utilisation de GroupDocs.Viewer ?
 Oui, assurez-vous de disposer de la licence appropriée pour votre utilisation. Explorez les options de licence sur[Achat de GroupDocs](https://purchase.groupdocs.com/buy) ou obtenir un[permis temporaire](https://purchase.groupdocs.com/temporary-license/) pour tester.
### Où puis-je demander de l'aide ou contacter la communauté GroupDocs pour obtenir de l'aide ?
 Visiter le[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pour le soutien, les discussions et l’interaction communautaire.