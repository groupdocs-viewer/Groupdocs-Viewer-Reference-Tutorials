---
"description": "Apprenez à restituer des images EMZ et EMF dans différents formats avec GroupDocs.Viewer pour .NET. Tutoriel facile à suivre pour les développeurs."
"linktitle": "Rendu des images EMZ et EMF"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu des images EMZ et EMF"
"url": "/fr/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# Rendu des images EMZ et EMF

## Introduction

GroupDocs.Viewer pour .NET est une puissante API de rendu de documents qui permet aux développeurs d'afficher différents types de documents, notamment des images EMZ (Enhanced Windows Metafile) et EMF (Enhanced Metafile), dans leurs applications .NET. Dans ce tutoriel, nous découvrirons comment afficher des images EMZ et EMF dans différents formats tels que HTML, JPG, PNG et PDF avec GroupDocs.Viewer pour .NET.

![Rendu d'images EMZ et EMF avec GroupDocs.Viewer pour .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. GroupDocs.Viewer pour .NET : vous pouvez télécharger la bibliothèque à partir de [ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : assurez-vous d’avoir un environnement de développement compatible configuré pour le développement .NET.
3. Exemples d'images EMZ/EMF : disposez d'exemples d'images EMZ et EMF pour le rendu.

## Importer des espaces de noms

Avant de plonger dans le code, importons les espaces de noms nécessaires :

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Maintenant, décomposons chaque exemple en plusieurs étapes dans un format de guide étape par étape :

## Rendu d'images EMZ/EMF au format HTML

### Étape 1 : définir le répertoire de sortie :
```csharp
string outputDirectory = "Your Document Directory";
```
Remplacer `"Your Document Directory"` avec le chemin où vous souhaitez enregistrer le fichier HTML rendu.

### Étape 2 : Définir le format du chemin d’accès au fichier d’échange :
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Cela spécifiera le format du chemin d'accès au fichier HTML rendu.

### Étape 3 : Rendu au format HTML :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Ce code initialise le `Viewer` objet avec l'exemple d'image EMZ et le restitue au format HTML à l'aide des options spécifiées.

## Rendu d'images EMZ/EMF au format JPG, PNG et PDF

Répétez les étapes suivantes pour le rendu aux formats JPG, PNG et PDF :

### Étape 1 : Définir le format du chemin d’accès au fichier d’échange :
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Ajustez le nom et l'extension du fichier en fonction du format de sortie souhaité (`jpg`, `png`, ou `pdf`).

### Étape 2 : Rendu au format respectif :
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Ajustez les options en fonction du format de sortie (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Remplacer `JpgViewOptions` avec `PngViewOptions` ou `PdfViewOptions` en fonction du format de sortie souhaité.

## Conclusion

En conclusion, GroupDocs.Viewer pour .NET offre une solution transparente pour le rendu d'images EMZ et EMF dans différents formats dans les applications .NET. En suivant les étapes décrites dans ce tutoriel, les développeurs peuvent facilement intégrer les fonctionnalités de rendu de documents à leurs applications.

## FAQ

### Q : GroupDocs.Viewer peut-il restituer d’autres formats de documents en dehors des images EMZ et EMF ?
R : Oui, GroupDocs.Viewer prend en charge une large gamme de formats de documents, notamment PDF, DOCX, PPTX, XLSX, etc.

### Q : Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?
R : Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.groupdocs.com/).

### Q : GroupDocs.Viewer offre-t-il un support aux développeurs ?
R : Oui, GroupDocs fournit une assistance via son [forum](https://forum.groupdocs.com/c/viewer/9) où les développeurs peuvent poser des questions et demander de l'aide.

### Q : Puis-je acheter une licence temporaire pour GroupDocs.Viewer pour .NET ?
R : Oui, des licences temporaires sont disponibles à l’achat [ici](https://purchase.groupdocs.com/temporary-license/).

### Q : Où puis-je trouver une documentation détaillée sur GroupDocs.Viewer pour .NET ?
R : Vous pouvez vous référer à la documentation [ici](https://tutorials.groupdocs.com/viewer/net/) pour des conseils complets sur l'utilisation de l'API.