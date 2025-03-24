---
title: Définir le format DateHeure et le décalage horaire (e-mail)
linktitle: Définir le format DateHeure et le décalage horaire (e-mail)
second_title: API GroupDocs.Viewer .NET
description: Intégrez GroupDocs.Viewer pour .NET de manière transparente dans vos applications pour bénéficier de puissantes fonctionnalités de visualisation de documents. Améliorez l'expérience utilisateur avec des options personnalisables.
weight: 11
url: /fr/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Introduction
GroupDocs.Viewer for .NET est un outil puissant qui permet aux développeurs d'intégrer de manière transparente des fonctionnalités de visualisation de documents dans leurs applications .NET. Avec GroupDocs.Viewer, vous pouvez afficher un large éventail de formats de documents, notamment des PDF, des documents Microsoft Office, des images et bien plus encore, directement dans votre application, sans avoir besoin de plugins ou de visionneuses externes. Dans ce didacticiel complet, nous vous guiderons tout au long du processus de configuration de GroupDocs.Viewer pour .NET, en explorant ses fonctionnalités et en démontrant comment l'utiliser efficacement pour améliorer les capacités d'affichage de documents de votre application.
## Conditions préalables
Avant de plonger dans ce didacticiel, assurez-vous que les conditions préalables suivantes sont définies :
1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système. GroupDocs.Viewer pour .NET est entièrement compatible avec Visual Studio, permettant une intégration transparente dans vos projets .NET.
2.  GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET à partir du[lien de téléchargement](https://releases.groupdocs.com/viewer/net/). Suivez les instructions d'installation fournies pour configurer la bibliothèque dans votre environnement de développement.
3. .NET Framework : assurez-vous que la version appropriée de .NET Framework est installée. GroupDocs.Viewer pour .NET prend en charge différentes versions de .NET Framework, notamment .NET Core et .NET Standard.

## Importer des espaces de noms
Afin d'utiliser efficacement GroupDocs.Viewer pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet. Suivez ces étapes pour importer les espaces de noms requis :

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Décomposons l'exemple fourni en plusieurs étapes pour comprendre chaque composant et ses fonctionnalités.
## Étape 1 : Définir le répertoire de sortie et le chemin du fichier
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Dans cette étape, nous définissons le répertoire de sortie dans lequel le document rendu sera enregistré et spécifions le chemin du fichier HTML de sortie.
## Étape 2 : Instancier l'objet de visualisation
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Ici, nous créons une nouvelle instance du`Viewer` classe, en passant le chemin du document à visualiser (dans ce cas, un exemple de fichier EML) en paramètre.
## Étape 3 : Définir les options d'affichage HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Dans cette étape, nous configurons les options d'affichage HTML pour le rendu du document, en spécifiant le chemin du fichier de sortie pour le document HTML rendu.
## Étape 4 : Définir le format DateHeure et le décalage horaire
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Ici, nous personnalisons le format de date et d'heure des messages électroniques et définissons le décalage horaire en fonction du fuseau horaire souhaité.
## Étape 5 : Rendre le document
```csharp
viewer.View(options);
```
 Enfin, nous appelons le`View` méthode du`Viewer` objet, en transmettant les options d'affichage HTML configurées pour restituer le document au format HTML.
## Étape 6 : Afficher le répertoire de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cette étape affiche simplement un message indiquant le rendu réussi du document et fournit le chemin d'accès au répertoire de sortie où se trouve le document HTML rendu.

## Conclusion
GroupDocs.Viewer pour .NET offre une solution robuste pour intégrer des fonctionnalités de visualisation de documents dans vos applications .NET. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement configurer GroupDocs.Viewer, importer les espaces de noms nécessaires et utiliser ses fonctionnalités pour restituer des documents avec des options personnalisables. Que vous travailliez avec des PDF, des documents Microsoft Office ou d'autres formats, GroupDocs.Viewer simplifie le processus de visualisation des documents, améliorant ainsi l'expérience utilisateur de vos applications.
## FAQ
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer pour .NET prend en charge .NET Core, permettant une compatibilité multiplateforme pour vos applications.
### Puis-je personnaliser l’apparence des documents rendus ?
Absolument! GroupDocs.Viewer propose diverses options de personnalisation, notamment les niveaux de zoom, la rotation des pages, etc. pour adapter l'expérience de visualisation en fonction de vos préférences.
### Existe-t-il une version d'essai disponible à des fins de test ?
 Oui, vous pouvez télécharger une version d'essai gratuite de GroupDocs.Viewer pour .NET à partir du[lien de site Web](https://releases.groupdocs.com/viewer/net/) pour évaluer ses fonctionnalités avant de faire un achat.
### GroupDocs.Viewer prend-il en charge le rendu des documents protégés par mot de passe ?
Oui, GroupDocs.Viewer prend en charge de manière intégrée le rendu des documents protégés par mot de passe, garantissant ainsi une visualisation sécurisée des documents dans vos applications.
### Où puis-je trouver une assistance ou une assistance supplémentaire avec GroupDocs.Viewer ?
 Pour toute question technique ou assistance, vous pouvez visiter le GroupDocs.Viewer[forum](https://forum.groupdocs.com/c/viewer/9) ou contactez leur équipe d’assistance pour obtenir une aide et des conseils rapides.