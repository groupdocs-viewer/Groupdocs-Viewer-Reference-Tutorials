---
"description": "Intégrez GroupDocs.Viewer pour .NET en toute transparence à vos applications pour bénéficier de puissantes fonctionnalités de visualisation de documents. Améliorez l'expérience utilisateur grâce à des options personnalisables."
"linktitle": "Définir le format de date et d'heure et le décalage horaire (e-mail)"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Définir le format de date et d'heure et le décalage horaire (e-mail)"
"url": "/fr/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
---

# Définir le format de date et d'heure et le décalage horaire (e-mail)


## Introduction
GroupDocs.Viewer pour .NET est un outil puissant qui permet aux développeurs d'intégrer facilement des fonctionnalités de visualisation de documents à leurs applications .NET. Avec GroupDocs.Viewer, vous pouvez afficher une large gamme de formats de documents, tels que des PDF, des documents Microsoft Office, des images et bien plus encore, directement dans votre application, sans plug-ins ni visualiseurs externes. Dans ce tutoriel complet, nous vous guiderons dans la configuration de GroupDocs.Viewer pour .NET, en explorant ses fonctionnalités et en vous montrant comment l'utiliser efficacement pour améliorer les capacités de visualisation de documents de votre application.
## Prérequis
Avant de vous lancer dans ce didacticiel, assurez-vous que les prérequis suivants sont définis :
1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système. GroupDocs.Viewer pour .NET est entièrement compatible avec Visual Studio, permettant une intégration transparente à vos projets .NET.
2. GroupDocs.Viewer pour .NET : téléchargez et installez GroupDocs.Viewer pour .NET à partir du [lien de téléchargement](https://releases.groupdocs.com/viewer/net/)Suivez les instructions d’installation fournies pour configurer la bibliothèque dans votre environnement de développement.
3. .NET Framework : assurez-vous d'avoir installé la version appropriée de .NET Framework. GroupDocs.Viewer pour .NET prend en charge différentes versions de .NET Framework, notamment .NET Core et .NET Standard.

## Importer des espaces de noms
Pour utiliser efficacement GroupDocs.Viewer pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet. Suivez ces étapes :

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Décomposons l’exemple fourni en plusieurs étapes pour comprendre chaque composant et ses fonctionnalités.
## Étape 1 : définir le répertoire de sortie et le chemin du fichier
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Dans cette étape, nous définissons le répertoire de sortie dans lequel le document rendu sera enregistré et spécifions le chemin d'accès au fichier HTML de sortie.
## Étape 2 : instancier l'objet Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Ici, nous créons une nouvelle instance du `Viewer` classe, en passant le chemin du document à visualiser (dans ce cas, un exemple de fichier EML) en paramètre.
## Étape 3 : Définir les options d’affichage HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Dans cette étape, nous configurons les options d’affichage HTML pour le rendu du document, en spécifiant le chemin du fichier de sortie pour le document HTML rendu.
## Étape 4 : Définir le format de date et d'heure et le décalage du fuseau horaire
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Ici, nous personnalisons le format de date et d'heure des messages électroniques et définissons le décalage horaire en fonction du fuseau horaire souhaité.
## Étape 5 : Rendre le document
```csharp
viewer.View(options);
```
Enfin, nous appelons le `View` méthode de la `Viewer` objet, en passant les options d'affichage HTML configurées pour rendre le document au format HTML.
## Étape 6 : Afficher le répertoire de sortie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cette étape affiche simplement un message indiquant le rendu réussi du document et fournit le chemin d'accès au répertoire de sortie où se trouve le document HTML rendu.

## Conclusion
GroupDocs.Viewer pour .NET offre une solution robuste pour intégrer des fonctionnalités de visualisation de documents à vos applications .NET. En suivant les étapes décrites dans ce tutoriel, vous pouvez facilement configurer GroupDocs.Viewer, importer les espaces de noms nécessaires et utiliser ses fonctionnalités pour afficher des documents avec des options personnalisables. Que vous travailliez avec des PDF, des documents Microsoft Office ou d'autres formats, GroupDocs.Viewer simplifie la visualisation des documents et améliore l'expérience utilisateur de vos applications.
## FAQ
### GroupDocs.Viewer est-il compatible avec .NET Core ?
Oui, GroupDocs.Viewer pour .NET prend en charge .NET Core, permettant une compatibilité multiplateforme pour vos applications.
### Puis-je personnaliser l'apparence des documents rendus ?
Absolument ! GroupDocs.Viewer propose diverses options de personnalisation, notamment des niveaux de zoom, la rotation des pages et bien plus encore, pour adapter l'expérience de visualisation à vos tutoriels.
### Existe-t-il une version d'essai disponible à des fins de test ?
Oui, vous pouvez télécharger une version d'essai gratuite de GroupDocs.Viewer pour .NET à partir du [lien vers le site Web](https://releases.groupdocs.com/viewer/net/) pour évaluer ses caractéristiques avant de procéder à un achat.
### GroupDocs.Viewer prend-il en charge le rendu de documents protégés par mot de passe ?
Oui, GroupDocs.Viewer dispose d'une prise en charge intégrée pour le rendu de documents protégés par mot de passe, garantissant ainsi une visualisation sécurisée des documents dans vos applications.
### Où puis-je trouver une assistance ou un support supplémentaire avec GroupDocs.Viewer ?
Pour toute question technique ou assistance, vous pouvez visiter GroupDocs.Viewer [forum](https://forum.groupdocs.com/c/viewer/9) ou contactez leur équipe d'assistance pour obtenir une aide et des conseils rapides.