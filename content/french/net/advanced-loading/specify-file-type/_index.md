---
title: Spécifier le type de fichier lors du chargement de documents
linktitle: Spécifier le type de fichier lors du chargement de documents
second_title: API GroupDocs.Viewer .NET
description: Découvrez comment spécifier le type de fichier lors du chargement de documents à l'aide de GroupDocs.Viewer pour .NET. Restituez différents formats avec précision dans vos applications .NET.
weight: 10
url: /fr/net/advanced-loading/specify-file-type/
---
## Introduction
GroupDocs.Viewer pour .NET est une API de rendu de documents polyvalente qui prend en charge un large éventail de formats de fichiers, notamment DOCX, PDF, PPTX, etc. En spécifiant le type de fichier lors du chargement des documents, vous pouvez garantir un rendu précis et une expérience de visualisation fluide pour vos utilisateurs.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
- Connaissance de base de C# et du framework .NET.
- Visual Studio installé sur votre système.
- GroupDocs.Viewer pour .NET installé dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).
##
## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre code C#. Ces espaces de noms donnent accès aux classes et méthodes requises pour le rendu du document.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Configurer le répertoire de sortie
Définissez le répertoire dans lequel vous souhaitez enregistrer les pages du document rendues.
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Définir le format du chemin du fichier de page
Spécifiez le format de nom des fichiers HTML de sortie pour chaque page du document.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Étape 3 : Spécifier les options de chargement
 Créez une instance du`LoadOptions` class et définissez le type de fichier souhaité.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Étape 4 : Charger le document et le rendu
 Utilisez le`Viewer` classe pour charger le document et le restituer au format HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Étape 5 : Afficher le message de réussite
Informez l'utilisateur que le document a été rendu avec succès et spécifiez l'emplacement des fichiers de sortie.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser GroupDocs.Viewer pour .NET pour spécifier le type de fichier lors du chargement de documents. En suivant ces étapes simples, vous pouvez garantir un rendu précis de différents formats de documents dans vos applications .NET.
## FAQ
### Puis-je restituer des documents autres que DOCX à l’aide de GroupDocs.Viewer pour .NET ?
Oui, GroupDocs.Viewer prend en charge un large éventail de formats de fichiers, notamment PDF, PPTX, XLSX, etc.
### GroupDocs.Viewer pour .NET est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer pour .NET est compatible avec .NET Framework et .NET Core.
### Puis-je personnaliser les fichiers HTML de sortie générés par GroupDocs.Viewer ?
Oui, vous pouvez personnaliser la sortie HTML à l'aide de diverses options fournies par l'API.
### GroupDocs.Viewer pour .NET nécessite-t-il des dépendances externes ?
Non, GroupDocs.Viewer pour .NET est une bibliothèque autonome et ne nécessite aucune dépendance externe.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.groupdocs.com/viewer/net/).