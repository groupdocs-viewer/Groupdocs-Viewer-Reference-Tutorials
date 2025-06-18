---
"description": "Intégrez Groupdocs.Viewer pour .NET de manière transparente dans vos projets .NET pour une visualisation efficace des documents."
"linktitle": "Annuler le rendu avec le jeton d'annulation"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Annuler le rendu avec le jeton d'annulation"
"url": "/fr/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# Annuler le rendu avec le jeton d'annulation

## Introduction
Groupdocs.Viewer pour .NET est un outil puissant conçu pour simplifier la visualisation et le traitement des documents dans les applications .NET. Que vous utilisiez des PDF, des documents Microsoft Office ou d'autres formats courants, cette bibliothèque offre des fonctionnalités robustes pour intégrer facilement la visualisation de documents à vos projets .NET.
## Prérequis
Avant de vous lancer dans l'intégration de Groupdocs.Viewer pour .NET, assurez-vous de disposer des prérequis suivants :
1. Installation : Téléchargez et installez la bibliothèque Groupdocs.Viewer pour .NET à partir du fichier fourni. [lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
   
2. Licence : Obtenir une licence auprès de [Groupdocs](https://purchase.groupdocs.com/buy) pour exploiter tout le potentiel de la bibliothèque. Vous pouvez également commencer par un essai gratuit en utilisant le [permis temporaire](https://purchase.groupdocs.com/temporary-license/).
   
3. Environnement de développement : assurez-vous d’avoir configuré un environnement de développement compatible, notamment Visual Studio ou tout autre IDE .NET de votre choix.

## Importer des espaces de noms
Pour utiliser efficacement Groupdocs.Viewer pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet. Suivez ces étapes :

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Décomposons maintenant l’exemple fourni en plusieurs étapes pour une meilleure compréhension et une meilleure mise en œuvre :
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Cette étape définit le répertoire dans lequel les pages du document rendues seront stockées.
## Étape 2 : Définir le format du chemin d'accès au fichier d'échange
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ici, nous définissons le format des chemins d'accès aux fichiers des pages de documents individuelles.
## Étape 3 : Initialiser CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource est utilisé pour générer des instances CancellationToken qui peuvent être utilisées pour annuler des opérations asynchrones.
## Étape 4 : Obtenir un jeton d'annulation
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Cette étape récupère le jeton de CancellationTokenSource, qui sera utilisé pour annuler l'opération de rendu.
## Étape 5 : Afficher les pages du document
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Ici, nous lançons le rendu des pages du document de manière asynchrone à l'aide de Task.Run(). L'instance Viewer est créée avec le fichier de document spécifié (SAMPLE_DOCX) et les options de rendu sont configurées. Le processus de rendu est ensuite lancé via la méthode View de la classe Viewer.
## Étape 6 : définir le délai d'expiration du rendu
```csharp
cancellationTokenSource.CancelAfter(10);
```
Cette étape définit un délai d'expiration de 10 millisecondes pour l'opération de rendu. Si l'opération dépasse ce délai, elle sera automatiquement annulée.
## Étape 7 : Afficher le message de réussite
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Enfin, un message de réussite s'affiche indiquant que le document a été rendu avec succès.

## Conclusion
Dans ce tutoriel, nous avons abordé les bases de l'intégration de Groupdocs.Viewer pour .NET à vos projets. En suivant les étapes décrites ci-dessus, vous pourrez intégrer facilement des fonctionnalités de visualisation de documents à vos applications .NET, améliorant ainsi l'expérience utilisateur et la productivité.
## FAQ
### Groupdocs.Viewer pour .NET est-il compatible avec tous les formats de documents ?
Groupdocs.Viewer pour .NET prend en charge une large gamme de formats de documents, notamment les documents PDF, Microsoft Office, les images, etc.
### Puis-je personnaliser l’apparence des pages du document rendues ?
Oui, vous pouvez personnaliser divers aspects du processus de rendu, notamment la taille de la page, la qualité, le filigrane, etc.
### Groupdocs.Viewer pour .NET nécessite-t-il une connexion Internet ?
Non, Groupdocs.Viewer pour .NET fonctionne localement dans votre environnement .NET et ne nécessite pas de connexion Internet pour la visualisation des documents.
### Un support technique est-il disponible pour Groupdocs.Viewer pour .NET ?
Oui, le support technique est disponible via le [Forum Groupdocs](https://forum.groupdocs.com/c/viewer/9), où vous pouvez poser des questions, signaler des problèmes et interagir avec la communauté.
### Puis-je essayer Groupdocs.Viewer pour .NET avant de l'acheter ?
Oui, vous pouvez commencer avec un essai gratuit en utilisant le [version d'essai](https://releases.groupdocs.com/).