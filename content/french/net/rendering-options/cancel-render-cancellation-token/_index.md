---
title: Annuler le rendu avec le jeton d'annulation
linktitle: Annuler le rendu avec le jeton d'annulation
second_title: API GroupDocs.Viewer .NET
description: Intégrez Groupdocs.Viewer pour .NET de manière transparente dans vos projets .NET pour une visualisation efficace des documents.
weight: 11
url: /fr/net/rendering-options/cancel-render-cancellation-token/
---
## Introduction
Groupdocs.Viewer pour .NET est un outil puissant conçu pour simplifier la visualisation et le traitement des documents dans les applications .NET. Que vous traitiez de PDF, de documents Microsoft Office ou d'autres formats courants, cette bibliothèque offre des fonctionnalités robustes pour intégrer de manière transparente les capacités de visualisation de documents dans vos projets .NET.
## Conditions préalables
Avant de vous lancer dans l'intégration de Groupdocs.Viewer pour .NET, assurez-vous d'avoir les conditions préalables suivantes en place :
1.  Installation : Téléchargez et installez la bibliothèque Groupdocs.Viewer for .NET à partir du[lien de téléchargement](https://releases.groupdocs.com/viewer/net/).
   
2.  Licence : Obtenez une licence auprès de[Documents de groupe](https://purchase.groupdocs.com/buy) pour libérer tout le potentiel de la bibliothèque. Alternativement, vous pouvez commencer par un essai gratuit en utilisant le[permis temporaire](https://purchase.groupdocs.com/temporary-license/).
   
3. Environnement de développement : assurez-vous d'avoir configuré un environnement de développement compatible, y compris Visual Studio ou tout autre IDE .NET de votre choix.

## Importer des espaces de noms
Afin d'utiliser efficacement Groupdocs.Viewer pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet. Suivez ces étapes:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Maintenant, décomposons l'exemple fourni en plusieurs étapes pour une meilleure compréhension et mise en œuvre :
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDirectory = "Your Document Directory";
```
Cette étape définit le répertoire dans lequel les pages du document rendues seront stockées.
## Étape 2 : Définir le format du chemin du fichier de page
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ici, nous définissons le format des chemins de fichiers des pages individuelles du document.
## Étape 3 : initialiser CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource est utilisé pour générer des instances CancellationToken qui peuvent être utilisées pour annuler des opérations asynchrones.
## Étape 4 : Obtenir le jeton d'annulation
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Cette étape récupère le jeton de CancellationTokenSource, qui sera utilisé pour annuler l'opération de rendu.
## Étape 5 : rendre les pages du document
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
Ici, nous lançons le rendu des pages de document de manière asynchrone à l'aide de Task.Run(). L'instance de visionneuse est créée avec le fichier de document spécifié (SAMPLE_DOCX) et les options de rendu sont configurées. Le processus de rendu est ensuite lancé à l'aide de la méthode View de la classe Viewer.
## Étape 6 : Définir le délai d'expiration du rendu
```csharp
cancellationTokenSource.CancelAfter(10);
```
Cette étape définit un délai d'attente de 10 millisecondes pour l'opération de rendu. Si l'opération dépasse ce délai, elle sera automatiquement annulée.
## Étape 7 : Afficher le message de réussite
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Enfin, un message de réussite s'affiche indiquant que le document a été rendu avec succès.

## Conclusion
Dans ce didacticiel, nous avons couvert les bases de l'intégration de Groupdocs.Viewer for .NET dans vos projets. En suivant les étapes décrites ci-dessus, vous pouvez intégrer de manière transparente des fonctionnalités de visualisation de documents dans vos applications .NET, améliorant ainsi l'expérience utilisateur et la productivité.
## FAQ
### Groupdocs.Viewer pour .NET est-il compatible avec tous les formats de documents ?
Groupdocs.Viewer pour .NET prend en charge un large éventail de formats de documents, notamment PDF, documents Microsoft Office, images, etc.
### Puis-je personnaliser l’apparence des pages du document rendues ?
Oui, vous pouvez personnaliser divers aspects du processus de rendu, notamment la taille de la page, la qualité, le filigrane, etc.
### Groupdocs.Viewer pour .NET nécessite-t-il une connectivité Internet ?
Non, Groupdocs.Viewer for .NET fonctionne localement dans votre environnement .NET et ne nécessite pas de connectivité Internet pour l'affichage des documents.
### Un support technique est-il disponible pour Groupdocs.Viewer pour .NET ?
 Oui, l'assistance technique est disponible via le[Forum Groupdocs](https://forum.groupdocs.com/c/viewer/9), où vous pouvez poser des questions, signaler des problèmes et interagir avec la communauté.
### Puis-je essayer Groupdocs.Viewer pour .NET avant d'acheter ?
 Oui, vous pouvez commencer par un essai gratuit en utilisant le[version d'essai](https://releases.groupdocs.com/).