---
"date": "2025-04-25"
"description": "Apprenez à convertir des fichiers TXT en plusieurs formats tels que HTML, JPG, PNG et PDF à l'aide de GroupDocs.Viewer pour .NET avec ce guide complet."
"title": "Convertir du TXT en HTML, JPG, PNG, PDF à l'aide de GroupDocs.Viewer .NET - Guide complet"
"url": "/fr/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# Convertir du TXT en plusieurs formats avec GroupDocs.Viewer .NET

## Introduction

Vous souhaitez convertir facilement des documents texte en différents formats tels que HTML, JPG, PNG ou PDF ? Gérer la conversion de documents peut s'avérer complexe, surtout lorsqu'il s'agit de plusieurs pages ou de formats spécifiques. **GroupDocs.Viewer pour .NET** simplifie le processus de rendu des fichiers TXT dans divers formats de sortie, garantissant que vos données sont accessibles et visuellement attrayantes.

![Convertissez du TXT en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

Dans ce guide, nous découvrirons comment utiliser GroupDocs.Viewer pour .NET pour transformer des documents TXT en HTML multipages, HTML monopages, JPG, PNG et PDF. À la fin de ce guide, vous maîtriserez :
- Conversion de fichiers TXT en C# avec GroupDocs.Viewer
- Mise en œuvre de différentes options de rendu selon vos besoins
- Optimiser les performances lors des conversions

Plongeons-nous dans la résolution de vos problèmes de conversion de documents.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants à portée de main :
- **Environnement de développement**: Visual Studio 2019 ou version ultérieure.
- **.NET Framework**:Version 4.6.1 ou supérieure.
- **Bibliothèque GroupDocs.Viewer pour .NET**:
  - Via la console du gestionnaire de packages NuGet : `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Utilisation de .NET CLI : `dotnet add package GroupDocs.Viewer --version 25.3.0`

Une connaissance de la programmation C# et des opérations de fichiers de base dans .NET est recommandée pour suivre facilement.

## Configuration de GroupDocs.Viewer pour .NET

### Installation

Pour commencer, installez le **GroupDocs.Viewer** bibliothèque en utilisant votre gestionnaire de paquets préféré :

#### Console du gestionnaire de packages NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Licences

Vous pouvez commencer avec un **essai gratuit** ou obtenir un **permis temporaire** pour explorer toutes les fonctionnalités de GroupDocs.Viewer pour .NET sans limitations d'évaluation :
- Essai gratuit : [Télécharger ici](https://releases.groupdocs.com/viewer/net/)
- Licence temporaire : [Demandez ici](https://purchase.groupdocs.com/temporary-license/)

Pour une utilisation continue, pensez à acheter une licence directement auprès de [Documents de groupe](https://purchase.groupdocs.com/buy).

### Initialisation de base

Pour configurer GroupDocs.Viewer dans votre projet :

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Initialisez l'objet Viewer avec un chemin de fichier TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Votre code de rendu ira ici.
}
```

## Guide de mise en œuvre

Examinons maintenant chaque fonctionnalité et voyons comment vous pouvez les mettre en œuvre.

### Convertir un document TXT en HTML multipage

#### Aperçu
Cette fonctionnalité illustre la conversion d'un document TXT au format HTML multipage. Chaque page du fichier texte est rendue sous forme de fichier HTML individuel avec des ressources intégrées.

#### Étape 1 : Configurer la visionneuse

Créer un `Viewer` objet pour votre fichier TXT source :

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Initialisez la visionneuse avec un exemple de fichier texte.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Passez à l'étape 2...
```

#### Étape 2 : Configurer les options d’affichage HTML

Installation `HtmlViewOptions` pour rendre chaque page séparément :

```csharp
// Configurer les options d’affichage HTML pour le rendu multipage.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Rendre le document sous forme de HTML multipage.
viewer.View(options);
}
```

**Explication**: Le `ForEmbeddedResources()` Cette méthode garantit que les ressources telles que les images et les styles sont intégrées directement dans le fichier HTML, facilitant ainsi le partage.

### Convertir un document TXT en HTML sur une seule page

#### Aperçu
Convertissez un document TXT en une seule page HTML, idéal pour les documents qui doivent être affichés sous la forme d'une seule page Web continue.

#### Étape 1 : Configurer la visionneuse

Initialiser le `Viewer` objet:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Initialiser une nouvelle instance de Viewer pour un fichier texte différent.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Passez à l'étape 2...
```

#### Étape 2 : Configurer les options HTML d'une seule page

Configure `HtmlViewOptions` avec le paramètre de page unique activé :

```csharp
// Configurez les options de rendu dans une seule page HTML.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Rendu sous forme d'une seule page HTML.
viewer.View(options);
}
```

**Explication**: Le `RenderToSinglePage` la propriété garantit que l'intégralité du contenu est rendue sur une seule page.

### Convertir un document TXT en JPG

#### Aperçu
Cette fonctionnalité vous permet de convertir un document texte en image JPEG, utile pour les présentations visuelles ou à des fins d'archivage.

#### Étape 1 : Configurer la visionneuse

Préparez votre `Viewer` objet:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Initialisez la visionneuse avec un fichier d’exemple.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Passez à l'étape 2...
```

#### Étape 2 : Configurer les options d’affichage JPG

Installation `JpgViewOptions` pour le rendu d'image :

```csharp
// Configurez les options de rendu sous forme d'image JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Rendre le document sous forme de fichier JPEG.
viewer.View(options);
}
```

**Explication**: Le `JpgViewOptions` la classe spécifie comment rendre et enregistrer chaque page de votre document au format JPEG.

### Rendre un document TXT au format PNG

#### Aperçu
Convertissez un document texte au format PNG, offrant une sortie d'image de haute qualité avec prise en charge de la transparence.

#### Étape 1 : Configurer la visionneuse

Initialiser le `Viewer` objet:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Créez une instance de visionneuse pour votre fichier TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Passez à l'étape 2...
```

#### Étape 2 : Configurer les options d’affichage PNG

Installation `PngViewOptions`:

```csharp
// Configurez les options d'affichage pour le rendu sous forme d'image PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Rendre le document au format PNG.
viewer.View(options);
}
```

**Explication**: Le `PngViewOptions` la classe permet à chaque page d'être rendue avec transparence, ce qui la rend adaptée aux graphiques en couches.

### Convertir un document TXT en PDF

#### Aperçu
Cette fonctionnalité est parfaite pour convertir des documents texte en un format PDF universellement accessible.

#### Étape 1 : Configurer la visionneuse

Préparez votre `Viewer` objet:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Initialisez une instance de visionneuse pour votre exemple de fichier texte.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Passez à l'étape 2...
```

#### Étape 2 : Configurer les options d’affichage PDF

Installation `PdfViewOptions`:

```csharp
// Configurer les options d'affichage pour le rendu sous forme de document PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Convertissez le document en fichier PDF.
viewer.View(options);
}
```

**Explication**: Le `PdfViewOptions` la classe spécifie comment convertir et enregistrer vos fichiers TXT en documents PDF.

## Conclusion

Avec GroupDocs.Viewer pour .NET, convertir des documents texte en différents formats est simple. Ce guide explique comment transformer des fichiers TXT en HTML multipages, HTML monopages, JPG, PNG et PDF avec C#. Que vous cherchiez à améliorer l'accessibilité ou la compatibilité de vos documents, ces méthodes offrent des solutions robustes.

Pour obtenir une assistance supplémentaire ou des fonctionnalités plus avancées, reportez-vous à la [documentation officielle de GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/)Bon codage !