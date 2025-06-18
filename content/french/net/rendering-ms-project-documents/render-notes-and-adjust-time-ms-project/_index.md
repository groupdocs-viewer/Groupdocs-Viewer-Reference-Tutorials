---
"description": "Maîtrisez le rendu des documents MS Project avec GroupDocs.Viewer pour .NET. Générez des notes, ajustez les unités de temps et explorez différents formats de sortie en toute simplicité."
"linktitle": "Notes de rendu et ajustement des unités de temps (MS Project)"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Notes de rendu et ajustement des unités de temps (MS Project)"
"url": "/fr/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# Notes de rendu et ajustement des unités de temps (MS Project)

## Introduction
GroupDocs.Viewer pour .NET est une puissante API de rendu de documents qui permet aux développeurs de visualiser et de manipuler différents formats de documents dans leurs applications .NET. Dans ce tutoriel, nous nous concentrerons sur le rendu des notes et l'ajustement des unités de temps, spécifiquement pour les documents MS Project.
## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. GroupDocs.Viewer pour .NET : Assurez-vous d'avoir téléchargé et installé la bibliothèque GroupDocs.Viewer pour .NET. Vous pouvez la télécharger depuis [ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : configurez votre environnement de développement préféré avec prise en charge .NET.
3. Document MS Project : préparez un exemple de document MS Project pour les tests.
## Importer des espaces de noms
Commençons par importer les espaces de noms nécessaires pour commencer à rendre les documents MS Project :
## Étape 1 : Importer les espaces de noms
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Maintenant que nous avons importé les espaces de noms requis, décomposons chaque exemple en plusieurs étapes pour une compréhension complète.
## Rendu d'un document MS Project au format HTML
Pour restituer un document MS Project au format HTML avec des notes incluses, suivez ces étapes :
### Étape 2 : définir le répertoire de sortie et le format de fichier
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Étape 3 : Initialiser l'objet Viewer et définir les options
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Étape 4 : Rendre le document au format HTML
```csharp
viewer.View(options);
```
## Rendu de documents MS Project au format image
Vous pouvez également convertir des documents MS Project en images au format JPG et PNG. Voici comment :
### Étape 5 : Définir le répertoire de sortie et le format de fichier pour JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Étape 6 : Initialiser l'objet Viewer et définir les options JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Étape 7 : Convertir le document en JPG
```csharp
viewer.View(options);
```
Répétez des étapes similaires pour le rendu au format PNG et d’autres formats d’image.
## Conversion d'un document MS Project en PDF
Pour rendre un document MS Project au format PDF, procédez comme suit :
### Étape 8 : Définir le répertoire de sortie et le format de fichier pour le PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Étape 9 : Initialiser l'objet Visionneuse et définir les options PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Étape 10 : Convertir le document au format PDF
```csharp
viewer.View(options);
```

## Conclusion
Félicitations ! Vous avez appris à afficher des documents MS Project et à ajuster les unités de temps avec GroupDocs.Viewer pour .NET. Intégrez ces connaissances à vos projets pour améliorer la visualisation des documents.
## FAQ
### Puis-je restituer des documents MS Project dans d’autres formats que HTML, images et PDF ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu dans divers formats tels que DOCX, XLSX, PPTX, etc.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez obtenir un essai gratuit à partir de [ici](https://releases.groupdocs.com/).
### Comment puis-je obtenir une licence temporaire pour GroupDocs.Viewer pour .NET ?
Visite [ce lien](https://purchase.groupdocs.com/temporary-license/) pour obtenir un permis temporaire.
### Où puis-je trouver la documentation pour GroupDocs.Viewer pour .NET ?
Se référer à la documentation [ici](https://tutorials.groupdocs.com/viewer/net/).
### Où puis-je demander de l'aide ou poser des questions concernant GroupDocs.Viewer pour .NET ?
Vous pouvez visiter le forum d'assistance [ici](https://forum.groupdocs.com/c/viewer/9).