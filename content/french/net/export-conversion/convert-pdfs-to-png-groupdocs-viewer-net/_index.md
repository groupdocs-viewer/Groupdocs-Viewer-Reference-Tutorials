---
"date": "2025-04-25"
"description": "Découvrez comment convertir des pages PDF en images PNG tout en préservant les dimensions d'origine avec GroupDocs.Viewer pour .NET. Ce guide couvre l'installation, la configuration et les bonnes pratiques."
"title": "Convertir des fichiers PDF en PNG avec leur taille d'origine à l'aide de GroupDocs.Viewer pour .NET"
"url": "/fr/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# Convertir des fichiers PDF en PNG avec leur taille d'origine à l'aide de GroupDocs.Viewer pour .NET

## Introduction

Convertir des fichiers PDF en images PNG tout en conservant la taille d'origine est essentiel pour une numérisation de documents de haute qualité ou la préparation de contenu web. Ce tutoriel vous guidera dans l'utilisation de GroupDocs.Viewer pour .NET afin de restituer des pages PDF au format PNG, en préservant leurs dimensions d'origine.

![Convertissez des fichiers PDF en PNG avec leur taille d'origine avec GroupDocs.Viewer pour .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Ce que vous apprendrez :**
- Comment installer et configurer GroupDocs.Viewer pour .NET dans votre projet
- Processus étape par étape de rendu de fichiers PDF en images PNG tout en conservant les tailles de page
- Options de configuration clés et meilleures pratiques pour des performances optimales

À la fin de ce tutoriel, vous serez capable d'intégrer cette fonctionnalité à vos applications de manière fluide. Commençons par les prérequis nécessaires à la mise en route.

## Prérequis

Avant d'implémenter GroupDocs.Viewer pour .NET dans votre projet, assurez-vous que vous disposez des exigences suivantes :

### Bibliothèques et versions requises
- **GroupDocs.Viewer pour .NET**:Version 25.3.0 ou ultérieure.

### Configuration requise pour l'environnement
- Un environnement de développement compatible tel que Visual Studio.
- Compréhension de base de la programmation C#.

### Prérequis en matière de connaissances
- Familiarité avec la gestion des packages NuGet.
- Une certaine expérience de travail avec des fichiers PDF et de traitement d'images dans des applications .NET.

Une fois ces conditions préalables en place, nous pouvons procéder à la configuration de GroupDocs.Viewer pour .NET.

## Configuration de GroupDocs.Viewer pour .NET

Pour commencer à utiliser GroupDocs.Viewer pour .NET, suivez les étapes d'installation ci-dessous :

### Installation via la console du gestionnaire de packages NuGet
Ouvrez votre projet dans Visual Studio et utilisez la commande suivante :
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Installation via .NET CLI
Alternativement, vous pouvez l'installer en utilisant la CLI .NET avec cette commande :
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Étapes d'acquisition de licence
1. **Essai gratuit**: Téléchargez une version d'essai à partir de [Téléchargements GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **Permis temporaire**: Obtenez une licence temporaire pour explorer toutes les fonctionnalités sur [Page de licence temporaire](https://purchase.groupdocs.com/temporary-license/).
3. **Achat**: Pour une utilisation prolongée, achetez une licence via le [Page d'achat](https://purchase.groupdocs.com/buy).

### Initialisation et configuration de base
Pour initialiser GroupDocs.Viewer pour .NET dans votre projet C#, suivez ces étapes :
1. Importer les espaces de noms nécessaires :
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Configurez les chemins d’accès à votre PDF d’entrée et à votre répertoire de sortie.
3. Initialiser `Viewer` avec le chemin d'accès à votre document source, comme indiqué dans cet extrait :
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Guide de mise en œuvre
Cette section couvre la mise en œuvre du rendu des pages PDF sous forme d'images PNG tout en conservant leur taille d'origine.

### Rendu des pages PDF au format PNG avec la taille de page d'origine
#### Aperçu
Cette fonctionnalité permet de convertir chaque page d'un document PDF en image PNG, en préservant ses dimensions d'origine. Elle est particulièrement utile pour les applications nécessitant une représentation visuelle précise des documents.

##### Étape 1 : Configurer les chemins et initialiser la visionneuse
Créez des variables pour votre chemin d'entrée PDF et votre répertoire de sortie :
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Initialiser le `Viewer` classe avec le chemin de votre document source :
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Le bloc de code continuera à l'étape suivante
}
```
##### Étape 2 : Configurer PngViewOptions
Créer une instance de `PngViewOptions`, en spécifiant un modèle de nommage de fichier pour les images de sortie :
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Configurez les options de la visionneuse pour restituer chaque page à sa taille d'origine :
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Étape 3 : Afficher les pages du document
Appelez le `View` méthode sur votre `Viewer` par exemple, en transmettant les options de vue configurées :
```csharp
viewer.View(viewOptions);
```
### Conseils de dépannage
- Assurez-vous que les chemins sont corrects et que les répertoires existent.
- Vérifiez que vous disposez des autorisations nécessaires pour lire à partir des répertoires d’entrée et écrire dans les répertoires de sortie.

## Applications pratiques
1. **Numérisation de documents**:Convertissez des documents PDF d'archives en images numériques pour un accès et une distribution plus faciles.
2. **Portails Web**: Affichez des aperçus de documents sur des sites Web sans avoir besoin de lecteurs PDF.
3. **Systèmes de gestion de contenu (CMS)**: Intégrez-vous aux plates-formes CMS pour gérer et afficher efficacement de grands volumes de contenu PDF.

## Considérations relatives aux performances
Pour optimiser les performances de votre application à l'aide de GroupDocs.Viewer pour .NET :
- Limitez l'utilisation de la mémoire en traitant les documents par morceaux si vous traitez des fichiers volumineux.
- Utilisez des méthodes asynchrones lorsque cela est possible pour éviter de bloquer les threads pendant le rendu.
- Jeter `Viewer` instances rapidement après utilisation pour libérer des ressources.

## Conclusion
Dans ce tutoriel, vous avez appris à afficher des pages PDF au format PNG tout en conservant leur taille d'origine grâce à GroupDocs.Viewer pour .NET. Nous avons abordé la configuration de votre environnement, les options nécessaires pour des résultats optimaux et exploré les applications pratiques de cette fonctionnalité.

Les prochaines étapes incluent l’expérimentation d’autres options de rendu disponibles dans GroupDocs.Viewer ou son intégration dans des projets plus vastes pour des capacités de gestion de documents améliorées.

## Section FAQ
1. **Quelle est la meilleure façon de gérer des fichiers PDF volumineux avec GroupDocs.Viewer ?**
   - Traitez les documents en morceaux plus petits et utilisez des méthodes asynchrones pour maintenir les performances.
2. **Puis-je personnaliser les noms des fichiers PNG de sortie ?**
   - Oui, en spécifiant un modèle de nommage dans `PngViewOptions`.
3. **Est-il possible de rendre uniquement des pages spécifiques ?**
   - Absolument, vous pouvez configurer `PageNumbers` dans `PngViewOptions` pour spécifier quelles pages rendre.
4. **Comment gérer les licences pour GroupDocs.Viewer ?**
   - Les options incluent un essai gratuit, une licence temporaire ou l’achat d’une licence complète.
5. **Cette configuration peut-elle être utilisée dans des applications Web ?**
   - Oui, il convient au rendu côté serveur de fichiers PDF dans ASP.NET Core et d'autres frameworks Web basés sur .NET.

## Ressources
- [Documentation](https://docs.groupdocs.com/viewer/net/)
- [Référence de l'API](https://reference.groupdocs.com/viewer/net/)
- [Télécharger GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [Licence d'achat](https://purchase.groupdocs.com/buy)
- [Essai gratuit](https://releases.groupdocs.com/viewer/net/)
- [Permis temporaire](https://purchase.groupdocs.com/temporary-license/)
- [Forum d'assistance](https://forum.groupdocs.com/c/viewer/9)