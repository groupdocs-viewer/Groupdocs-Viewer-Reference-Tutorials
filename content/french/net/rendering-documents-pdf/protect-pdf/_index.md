---
"description": "Protégez facilement vos PDF rendus par des mots de passe grâce à Groupdocs.Viewer pour .NET. Préservez la sécurité et la confidentialité de vos documents."
"linktitle": "Protéger le PDF rendu avec un mot de passe"
"second_title": "API .NET GroupDocs.Viewer"
"title": "Protéger le PDF rendu avec un mot de passe"
"url": "/fr/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
type: docs
---
# Protéger le PDF rendu avec un mot de passe

## Introduction
Dans ce tutoriel, vous apprendrez à utiliser Groupdocs.Viewer pour .NET afin de protéger un PDF rendu par mot de passe. En ajoutant des mesures de sécurité, vous pouvez contrôler l'accès à vos documents PDF, garantissant ainsi leur confidentialité et leur intégrité.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
1. Bibliothèque Groupdocs.Viewer pour .NET : téléchargez et installez la bibliothèque à partir du [site web](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : assurez-vous de disposer d’un environnement de développement fonctionnel configuré pour le développement .NET.

## Importer des espaces de noms
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Étape 1 : Définir le répertoire de sortie et le chemin du fichier
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Étape 2 : Initialiser l'objet Viewer et définir les options de sécurité
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## Étape 3 : définir les options d’affichage PDF
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Étape 4 : Afficher le document avec les options de sécurité
```csharp
    viewer.View(options);
}
```
## Étape 5 : Vérifier le document rendu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
En suivant ces étapes, vous pouvez protéger un PDF rendu par un mot de passe grâce à Groupdocs.Viewer pour .NET. Vos documents restent ainsi sécurisés et accessibles uniquement aux utilisateurs autorisés.

## Conclusion
La sécurisation des documents PDF est essentielle pour préserver la confidentialité et l'intégrité. Avec Groupdocs.Viewer pour .NET, vous pouvez facilement protéger les PDF générés par mot de passe, contrôlant ainsi l'accès aux informations sensibles.

## FAQ
### Puis-je protéger des PDF avec différents niveaux d’autorisations ?
Oui, vous pouvez spécifier différentes autorisations pour l’affichage, l’impression, la copie et bien plus encore tout en protégeant les PDF avec des mots de passe.
### Groupdocs.Viewer est-il compatible avec différents formats de fichiers ?
Absolument ! Groupdocs.Viewer prend en charge le rendu d'une large gamme de formats de fichiers, notamment DOCX, XLSX, PPTX, PDF, etc.
### Puis-je intégrer Groupdocs.Viewer dans mon application .NET existante ?
Certainement ! Groupdocs.Viewer fournit des API pour une intégration transparente dans les applications .NET, offrant des capacités robustes de visualisation de documents.
### Groupdocs.Viewer offre-t-il une prise en charge des services de stockage cloud ?
Oui, Groupdocs.Viewer prend en charge l'intégration avec des services de stockage cloud populaires tels que Dropbox, Google Drive et Amazon S3, vous permettant de restituer des documents stockés dans le cloud.
### Existe-t-il une version d'essai disponible pour Groupdocs.Viewer ?
Oui, vous pouvez commencer à utiliser Groupdocs.Viewer en accédant à la version d'essai gratuite à partir du [site web](https://releases.groupdocs.com/).