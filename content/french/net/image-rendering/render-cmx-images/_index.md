---
"description": "Apprenez à restituer facilement des images CMX dans différents formats grâce à GroupDocs.Viewer pour .NET. Optimisez la gestion de vos documents."
"linktitle": "Rendu des images CMX"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Rendu des images CMX"
"url": "/fr/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# Rendu des images CMX

## Introduction
Dans le domaine de la gestion et de la manipulation de documents, le rendu d'images à partir de différents formats est une tâche cruciale. GroupDocs.Viewer pour .NET simplifie ce processus en offrant des fonctionnalités complètes pour le rendu d'images CMX dans différents formats tels que HTML, JPG, PNG et PDF. Ce tutoriel vous guidera pas à pas dans le rendu d'images CMX avec GroupDocs.Viewer pour .NET.

![Rendu d'images CMX avec GroupDocs.Viewer pour .NET](/viewer/image-rendering/render-cmx-images.png)

## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
1. Bibliothèque GroupDocs.Viewer pour .NET : téléchargez et installez la bibliothèque GroupDocs.Viewer pour .NET à partir de [ici](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : Disposez d'un environnement de développement fonctionnel configuré avec .NET Framework.
3. Fichier image CMX : obtenez un fichier image CMX que vous souhaitez restituer.

## Importation d'espaces de noms
Avant de continuer, assurez-vous d'importer les espaces de noms nécessaires pour accéder aux fonctionnalités de GroupDocs.Viewer dans votre application .NET :
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Rendu en HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Définir le répertoire de sortie : définissez le répertoire dans lequel vous souhaitez stocker les fichiers HTML rendus.
- Spécifier le format du chemin du fichier : définissez le format des fichiers HTML de sortie.
- Instancier l'objet Viewer : créez une instance de la classe Viewer avec le fichier image CMX.
- Options de rendu HTML : configurez les options de rendu HTML, telles que l’intégration de ressources.
- Rendu CMX en HTML : appelez la méthode View de l'objet viewer pour restituer l'image CMX en HTML.
## Rendu au format JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Définir le répertoire de sortie : définissez le répertoire de stockage des fichiers JPG rendus.
- Spécifier le format du chemin d'accès au fichier : définissez le format des fichiers JPG de sortie.
- Instancier l'objet Viewer : créez une instance de la classe Viewer avec le fichier image CMX.
- Options de rendu JPG : configurez les options de rendu JPG.
- Rendu CMX en JPG : appelez la méthode View de l'objet viewer pour rendre l'image CMX en JPG.
## Rendu au format PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Définir le répertoire de sortie : définissez le répertoire de stockage des fichiers PNG rendus.
- Spécifier le format du chemin d'accès au fichier : définissez le format des fichiers PNG de sortie.
- Instancier l'objet Viewer : créez une instance de la classe Viewer avec le fichier image CMX.
- Options de rendu PNG : configurez les options de rendu PNG.
- Rendu CMX en PNG : appelez la méthode View de l'objet viewer pour rendre l'image CMX au format PNG.
## Rendu au format PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Définir le répertoire de sortie : définissez le répertoire de stockage du fichier PDF rendu.
- Spécifier le format du chemin du fichier : définissez le format du fichier PDF de sortie.
- Instancier l'objet Viewer : créez une instance de la classe Viewer avec le fichier image CMX.
- Options de rendu PDF : configurez les options de rendu PDF.
- Rendu CMX en PDF : appelez la méthode View de l'objet viewer pour restituer l'image CMX au format PDF.

## Conclusion
En conclusion, GroupDocs.Viewer pour .NET offre une solution robuste pour le rendu fluide des images CMX dans différents formats. En suivant les étapes décrites dans ce tutoriel, vous pourrez facilement intégrer les fonctionnalités de rendu d'images CMX à vos applications .NET et ainsi améliorer l'efficacité de la gestion de vos documents.
## FAQ
### Puis-je restituer des pages spécifiques d'une image CMX ?
Oui, vous pouvez rendre des pages spécifiques en spécifiant le numéro de page dans les options de rendu.
### GroupDocs.Viewer pour .NET est-il compatible avec tous les frameworks .NET ?
Oui, GroupDocs.Viewer pour .NET est compatible avec plusieurs frameworks .NET, notamment .NET Core et .NET Framework.
### GroupDocs.Viewer prend-il en charge le rendu des images CMX chiffrées ?
Oui, GroupDocs.Viewer prend en charge le rendu des images CMX chiffrées avec des clés de déchiffrement appropriées.
### Puis-je personnaliser les options de rendu pour différents formats de sortie ?
Absolument, GroupDocs.Viewer fournit de nombreuses options pour personnaliser les paramètres de rendu en fonction de vos besoins.
### Existe-t-il un forum communautaire pour le support de GroupDocs.Viewer ?
Oui, vous pouvez demander de l'aide et interagir avec la communauté GroupDocs.Viewer sur le forum d'assistance. [ici](https://forum.groupdocs.com/c/viewer/9).