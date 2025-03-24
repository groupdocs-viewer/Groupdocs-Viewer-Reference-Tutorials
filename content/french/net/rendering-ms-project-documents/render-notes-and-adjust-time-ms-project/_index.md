---
title: Rendre les notes et ajuster les unités de temps (MS Project)
linktitle: Rendre les notes et ajuster les unités de temps (MS Project)
second_title: API GroupDocs.Viewer .NET
description: Maîtrisez le rendu des documents MS Project avec GroupDocs.Viewer pour .NET. Restituez des notes, ajustez les unités de temps et explorez facilement différents formats de sortie.
weight: 11
url: /fr/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Introduction
GroupDocs.Viewer pour .NET est une puissante API de rendu de documents qui permet aux développeurs d'afficher et de manipuler divers formats de documents dans leurs applications .NET. Dans ce didacticiel, nous nous concentrerons sur le rendu des notes et l'ajustement des unités de temps spécifiquement pour les documents MS Project.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. GroupDocs.Viewer pour .NET : assurez-vous d'avoir téléchargé et installé la bibliothèque GroupDocs.Viewer pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : configurez votre environnement de développement préféré avec la prise en charge .NET.
3. Document MS Project : préparez un exemple de document MS Project pour le test.
## Importer des espaces de noms
Tout d'abord, importons les espaces de noms nécessaires pour commencer à rendre les documents MS Project :
## Étape 1 : Importer des espaces de noms
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Maintenant que nous avons importé les espaces de noms requis, décomposons chaque exemple en plusieurs étapes pour une compréhension globale.
## Rendu d'un document MS Project en HTML
Pour afficher un document MS Project au format HTML avec des notes incluses, procédez comme suit :
### Étape 2 : Définir le répertoire de sortie et le format de fichier
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Étape 3 : initialiser l'objet de visualisation et définir les options
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Étape 4 : rendre le document au format HTML
```csharp
viewer.View(options);
```
## Rendu d'un document MS Project aux formats d'image
Vous pouvez également restituer des documents MS Project dans des formats d'image tels que JPG et PNG. Voici comment:
### Étape 5 : Définir le répertoire de sortie et le format de fichier pour JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Étape 6 : initialiser l'objet de visualisation et définir les options JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Étape 7 : rendre le document au format JPG
```csharp
viewer.View(options);
```
Répétez des étapes similaires pour le rendu au format PNG et autres formats d'image.
## Rendu d'un document MS Project au format PDF
Pour restituer un document MS Project au format PDF, procédez comme suit :
### Étape 8 : Définir le répertoire de sortie et le format de fichier pour le PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Étape 9 : initialiser l'objet de visualisation et définir les options PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Étape 10 : Rendre le document au format PDF
```csharp
viewer.View(options);
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment restituer des documents MS Project et ajuster les unités de temps à l'aide de GroupDocs.Viewer pour .NET. Intégrez ces connaissances à vos projets pour améliorer les capacités de visualisation de documents.
## FAQ
### Puis-je restituer des documents MS Project dans d'autres formats que HTML, images et PDF ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu dans divers formats tels que DOCX, XLSX, PPTX, etc.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
 Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.groupdocs.com/).
### Comment puis-je obtenir une licence temporaire pour GroupDocs.Viewer pour .NET ?
 Visite[ce lien](https://purchase.groupdocs.com/temporary-license/) pour obtenir un permis temporaire.
### Où puis-je trouver de la documentation pour GroupDocs.Viewer pour .NET ?
 Se référer à la documentation[ici](https://tutorials.groupdocs.com/viewer/net/).
### Où puis-je demander de l'aide ou poser des questions relatives à GroupDocs.Viewer pour .NET ?
 Vous pouvez visiter le forum d'assistance[ici](https://forum.groupdocs.com/c/viewer/9).