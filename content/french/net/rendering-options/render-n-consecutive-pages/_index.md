---
"description": "Découvrez comment intégrer GroupDocs.Viewer pour .NET dans vos applications pour restituer sans effort des documents avec N pages consécutives."
"linktitle": "Afficher N pages consécutives"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Afficher N pages consécutives"
"url": "/fr/net/rendering-options/render-n-consecutive-pages/"
"weight": 16
type: docs
---
# Afficher N pages consécutives

## Introduction
Dans le domaine du développement .NET, l'intégration de fonctionnalités de visualisation de documents à vos applications peut considérablement améliorer l'expérience utilisateur et les fonctionnalités. GroupDocs.Viewer pour .NET est un outil qui facilite le rendu fluide des documents. Cette puissante bibliothèque permet aux développeurs d'afficher facilement divers formats de documents dans leurs applications.
## Prérequis
Avant de vous plonger dans l'implémentation de GroupDocs.Viewer pour .NET, assurez-vous que les conditions préalables suivantes sont en place :
1. Environnement de développement .NET : assurez-vous qu’un environnement de développement .NET fonctionnel est configuré sur votre machine.
  
2. GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET à partir du fichier fourni. [lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
3. Fichiers de documents : préparez les fichiers de documents que vous souhaitez restituer à l’aide de GroupDocs.Viewer pour .NET.
#
## Importer des espaces de noms
Pour commencer à intégrer GroupDocs.Viewer pour .NET à votre projet, vous devez importer les espaces de noms nécessaires. Cette étape est cruciale pour accéder aux fonctionnalités de la bibliothèque dans votre base de code.
## Étape 1 : Importer l'espace de noms GroupDocs.Viewer
```csharp
using System;
using System.IO;
using System.Linq;
using GroupDocs.Viewer.Options;
```
## Étape 2 : Importer l'espace de noms System.IO
```csharp
using System.IO;
```

Maintenant que vous avez configuré les conditions préalables et importé les espaces de noms requis, passons au rendu d'un nombre spécifié de pages consécutives à partir d'un document à l'aide de GroupDocs.Viewer pour .NET.
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Spécifiez le répertoire dans lequel vous souhaitez que les pages rendues soient enregistrées.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Définissez le format des chemins d'accès aux pages affichées. Dans cet exemple, les pages seront enregistrées au format HTML avec des noms tels que « page_1.html », « page_2.html », etc.
## Étape 3 : Définir la plage de pages
```csharp
int[] range = Enumerable.Range(1, 3).ToArray();
```
Spécifiez la plage de pages consécutives à afficher. Dans ce cas, nous affichons les pages 1 à 3.
## Étape 4 : Rendre les pages du document
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options, range);
}
```
Créer une instance de `Viewer` en passant le chemin d'accès au fichier document en paramètre. Configurez ensuite les options d'affichage HTML et appelez la classe `View` méthode, spécifiant la plage de pages à restituer.
## Étape 5 : Afficher la sortie rendue
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Enfin, affichez un message de réussite indiquant que le document a été rendu avec succès et informez l'utilisateur du répertoire de sortie dans lequel les pages rendues sont enregistrées.

## Conclusion
L'intégration de GroupDocs.Viewer pour .NET à vos applications .NET ouvre un monde de possibilités pour un rendu fluide des documents. En suivant les étapes décrites dans ce tutoriel, vous pouvez facilement afficher N pages consécutives à partir de différents formats de documents, améliorant ainsi les fonctionnalités de votre application et l'expérience utilisateur.
## FAQ
### Puis-je restituer des pages à partir de documents autres que des fichiers DOCX ?
Oui, GroupDocs.Viewer pour .NET prend en charge une large gamme de formats de documents, notamment PDF, PPT, XLS, etc.
### GroupDocs.Viewer pour .NET est-il adapté aux applications Web ?
Absolument ! GroupDocs.Viewer pour .NET s'intègre parfaitement aux applications de bureau et Web.
### GroupDocs.Viewer pour .NET nécessite-t-il une licence pour une utilisation commerciale ?
Oui, vous pouvez obtenir une licence commerciale à partir du lien d’achat fourni pour utiliser GroupDocs.Viewer pour .NET dans des projets commerciaux.
### Puis-je personnaliser l'apparence des pages rendues ?
Oui, GroupDocs.Viewer pour .NET fournit diverses options pour personnaliser l’apparence et le comportement des documents rendus.
### Existe-t-il un forum communautaire pour rechercher de l’aide et partager des expériences ?
Oui, vous pouvez visiter le forum GroupDocs.Viewer via le lien d'assistance fourni pour interagir avec la communauté et obtenir l'aide d'experts.