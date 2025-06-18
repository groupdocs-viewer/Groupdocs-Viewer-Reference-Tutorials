---
"description": "Apprenez à convertir des archives RAR aux formats HTML, JPG, PNG ou PDF avec GroupDocs.Viewer pour .NET. Visualisez et partagez facilement le contenu des archives RAR."
"linktitle": "Rendre les archives RAR"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendre les archives RAR"
"url": "/fr/net/rendering-archive-files/render-rar/"
"weight": 13
---

# Rendre les archives RAR

## Introduction
Les archives RAR sont un format courant pour compresser et stocker plusieurs fichiers et dossiers dans un seul conteneur. Le rendu des archives RAR dans différents formats tels que HTML, JPG, PNG ou PDF peut être essentiel pour visualiser ou partager leur contenu. Dans ce tutoriel, nous allons découvrir comment rendre des archives RAR avec GroupDocs.Viewer pour .NET.
## Prérequis
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
1. GroupDocs.Viewer pour .NET : installez la bibliothèque GroupDocs.Viewer pour .NET à partir du [lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
2. Exemple d'archive RAR : préparez un exemple d'archive RAR pour le rendu.

## Importer des espaces de noms
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
## Étape 2 : Rendre au format HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Étape 3 : Rendu au format JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Étape 4 : Rendu au format PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Étape 5 : Rendu au format PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Conclusion
GroupDocs.Viewer pour .NET simplifie le rendu des archives RAR dans différents formats. En suivant les étapes décrites dans ce tutoriel, vous pouvez facilement convertir des archives RAR aux formats HTML, JPG, PNG ou PDF, facilitant ainsi la visualisation et le partage de leur contenu.
## FAQ
### GroupDocs.Viewer pour .NET peut-il gérer les archives RAR chiffrées ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu des archives RAR chiffrées à condition que les mots de passe nécessaires soient fournis pendant le processus de rendu.
### Est-il possible de personnaliser l’apparence de sortie des documents rendus ?
Absolument ! GroupDocs.Viewer pour .NET offre de nombreuses options de personnalisation permettant aux utilisateurs d'adapter l'apparence des documents rendus en fonction de leurs tutoriels.
### GroupDocs.Viewer pour .NET prend-il en charge le rendu d’autres formats d’archive en dehors de RAR ?
Oui, GroupDocs.Viewer pour .NET prend en charge le rendu de divers formats d’archives, notamment ZIP, TAR, 7z, etc.
### Puis-je intégrer GroupDocs.Viewer pour .NET dans mon application Web ?
Certainement ! GroupDocs.Viewer pour .NET fournit des API adaptées à l'intégration dans des applications de bureau et Web.
### Existe-t-il une version d'essai disponible pour GroupDocs.Viewer pour .NET ?
Oui, vous pouvez bénéficier d'un essai gratuit de GroupDocs.Viewer pour .NET à partir du [site web](https://releases.groupdocs.com/).