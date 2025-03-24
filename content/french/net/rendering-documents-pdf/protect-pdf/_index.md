---
title: Protéger le PDF rendu avec un mot de passe
linktitle: Protéger le PDF rendu avec un mot de passe
second_title: API GroupDocs.Viewer .NET
description: Protégez facilement vos PDF rendus avec des mots de passe à l'aide de Groupdocs.Viewer pour .NET. Gardez vos documents sécurisés et confidentiels.
weight: 12
url: /fr/net/rendering-documents-pdf/protect-pdf/
---

# Protéger le PDF rendu avec un mot de passe

## Introduction
Dans ce didacticiel, vous apprendrez à utiliser Groupdocs.Viewer for .NET pour protéger un PDF rendu avec un mot de passe. En ajoutant des mesures de sécurité, vous pouvez contrôler l'accès à vos documents PDF, garantissant ainsi la confidentialité et l'intégrité.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Groupdocs.Viewer pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir du[site web](https://releases.groupdocs.com/viewer/net/).
2. Environnement de développement : assurez-vous de disposer d'un environnement de développement fonctionnel configuré pour le développement .NET.

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
## Étape 2 : initialiser l'objet de visualisation et définir les options de sécurité
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
## Étape 3 : Définir les options d'affichage PDF
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Étape 4 : Rendre le document avec les options de sécurité
```csharp
    viewer.View(options);
}
```
## Étape 5 : Vérifier le document rendu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
En suivant ces étapes, vous pouvez protéger un PDF rendu avec un mot de passe à l'aide de Groupdocs.Viewer for .NET. Cela garantit que vos documents restent sécurisés et accessibles uniquement aux utilisateurs autorisés.

## Conclusion
La sécurisation des documents PDF est essentielle pour maintenir la confidentialité et l’intégrité. Avec Groupdocs.Viewer pour .NET, vous pouvez facilement protéger les PDF rendus avec des mots de passe, contrôlant ainsi l'accès aux informations sensibles.

## FAQ
### Puis-je protéger les PDF avec différents niveaux d’autorisations ?
Oui, vous pouvez spécifier différentes autorisations pour afficher, imprimer, copier et bien plus encore tout en protégeant les PDF avec des mots de passe.
### Groupdocs.Viewer est-il compatible avec différents formats de fichiers ?
Absolument! Groupdocs.Viewer prend en charge le rendu d'un large éventail de formats de fichiers, notamment DOCX, XLSX, PPTX, PDF, etc.
### Puis-je intégrer Groupdocs.Viewer dans mon application .NET existante ?
Certainement! Groupdocs.Viewer fournit des API pour une intégration transparente dans les applications .NET, offrant de solides capacités de visualisation de documents.
### Groupdocs.Viewer offre-t-il une prise en charge des services de stockage cloud ?
Oui, Groupdocs.Viewer prend en charge l'intégration avec des services de stockage cloud populaires tels que Dropbox, Google Drive et Amazon S3, vous permettant de restituer des documents stockés dans le cloud.
### Existe-t-il une version d'essai disponible pour Groupdocs.Viewer ?
 Oui, vous pouvez démarrer avec Groupdocs.Viewer en accédant à la version d'essai gratuite à partir du[site web](https://releases.groupdocs.com/).