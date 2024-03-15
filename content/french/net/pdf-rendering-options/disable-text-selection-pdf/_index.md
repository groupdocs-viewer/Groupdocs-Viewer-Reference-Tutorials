---
title: Désactiver la sélection de texte dans PDF
linktitle: Désactiver la sélection de texte dans PDF
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment désactiver la sélection de texte dans un PDF à l'aide de GroupDocs.Viewer pour .NET. Suivez notre guide étape par étape pour une intégration transparente.
type: docs
weight: 13
url: /fr/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Introduction
GroupDocs.Viewer pour .NET est une puissante API de rendu de documents qui permet aux développeurs d'intégrer sans effort des fonctionnalités de visualisation de documents dans leurs applications .NET. L'une des fonctionnalités clés fournies par GroupDocs.Viewer est la possibilité de désactiver la sélection de texte dans les documents PDF. Cette fonctionnalité est particulièrement utile dans les scénarios où vous devez empêcher les utilisateurs de copier du texte à partir de documents sensibles, garantissant ainsi la sécurité et l'intégrité des documents.
## Conditions préalables
Avant de plonger dans le guide étape par étape sur la façon de désactiver la sélection de texte dans un PDF à l'aide de GroupDocs.Viewer pour .NET, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Installation de GroupDocs.Viewer pour .NET : assurez-vous d'avoir téléchargé et installé GroupDocs.Viewer pour .NET à partir du[lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
2. Répertoire de documents : préparez un répertoire dans lequel vos documents seront stockés. Vous devrez spécifier ce répertoire dans l'extrait de code pour afficher le document PDF.

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par GroupDocs.Viewer pour .NET. Voici comment procéder :

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Maintenant, décomposons le processus de désactivation de la sélection de texte dans un document PDF à l'aide de GroupDocs.Viewer pour .NET en plusieurs étapes :
## Étape 1 : Spécifier le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
 Dans cette étape, remplacez`"Your Document Directory"` avec le chemin du répertoire où se trouve votre document PDF.
## Étape 2 : Définir le format du chemin du fichier de page
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Cette étape définit le format des chemins de fichiers des pages HTML rendues. Chaque page du document PDF sera convertie en fichier HTML avec un numéro de page séquentiel.
## Étape 3 : Rendre le document PDF avec la sélection de texte désactivée
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Remplacer`"Path to Your PDF Document"` avec le chemin réel vers votre fichier PDF. Cet extrait de code initialise un`Viewer` objet, configure les options d'affichage HTML pour intégrer des ressources et désactive la sélection de texte en définissant`RenderTextAsImage` propriété à`true`.
## Étape 4 : Afficher le message de réussite
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Après le rendu du document PDF, cette étape affiche un message de réussite ainsi que le répertoire dans lequel les pages HTML rendues sont stockées.

## Conclusion
Dans ce didacticiel, nous avons appris comment désactiver la sélection de texte dans les documents PDF à l'aide de GroupDocs.Viewer pour .NET. En suivant le guide étape par étape, vous pouvez intégrer de manière transparente cette fonctionnalité dans vos applications .NET, garantissant ainsi la sécurité des documents et améliorant l'expérience utilisateur.
## FAQ
### Puis-je personnaliser le répertoire de sortie pour les pages HTML rendues ?
Oui, vous pouvez spécifier n'importe quel chemin de répertoire dans lequel vous souhaitez que les pages HTML rendues soient stockées.
### GroupDocs.Viewer pour .NET est-il compatible avec différentes versions du framework .NET ?
Oui, GroupDocs.Viewer pour .NET est compatible avec différentes versions du framework .NET, notamment .NET Core et .NET Framework.
### La désactivation de la sélection de texte affecte-t-elle d'autres fonctionnalités du document PDF ?
Non, la désactivation de la sélection de texte empêche uniquement les utilisateurs de sélectionner et de copier du texte à partir du document. Les autres fonctionnalités restent intactes.
### Puis-je réactiver la sélection de texte après le rendu du document ?
 Oui, vous pouvez activer la sélection de texte en définissant simplement le`RenderTextAsImage` propriété à`false` dans les options d'affichage HTML.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
 Oui, vous pouvez accéder à un essai gratuit de GroupDocs.Viewer pour .NET à partir du[site web](https://releases.groupdocs.com/).