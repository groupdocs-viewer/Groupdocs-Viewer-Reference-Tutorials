---
date: '2026-08-08'
description: Apprenez à convertir IGS en PDF, HTML, JPG et PNG en utilisant GroupDocs.Viewer
  pour Java. Guide étape par étape, prérequis et dépannage pour les développeurs Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Convertissez IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer pour
  Java. Configuration détaillée, extraits de code et dépannage pour les développeurs
  Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Convertir IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Convertir IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer Java
type: docs
url: /fr/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convertir IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer Java

Si vous devez **convertir IGS en PDF** (ou en HTML, JPG, PNG) directement depuis une application Java, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue tout ce dont vous avez besoin — de l'installation de la bibliothèque au rendu du modèle 3 D dans le format qui convient à votre projet. Vous comprendrez pourquoi GroupDocs.Viewer est un choix solide pour des conversions rapides et fiables et vous obtiendrez des extraits de code prêts à l'emploi que vous pourrez intégrer à votre propre solution.

![Convertir des fichiers IGS en HTML, JPG, PNG et PDF avec GroupDocs.Viewer pour Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Réponses rapides
- **Puis-je convertir IGS en PDF avec Java ?** Oui, utilisez `PdfViewOptions` avec l'API `Viewer`.  
- **Quels formats de sortie sont pris en charge ?** HTML, JPG, PNG et PDF sont tous gérés nativement.  
- **Ai-je besoin d'une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit vous permet de tester les fonctionnalités principales.  
- **Quelle version de Java est requise ?** JDK 8 ou supérieur ; la bibliothèque fonctionne également avec Java 11, 17 et les versions ultérieures.  
- **Maven est-il le seul moyen d'ajouter la bibliothèque ?** Non, vous pouvez également utiliser Gradle ou ajouter manuellement les fichiers JAR à votre classpath.

## Qu'est-ce que la conversion d'IGS en PDF ?
Convertir IGS en PDF signifie transformer un fichier CAO 3 D neutre en un document statique, universellement visualisable. Cela vous permet de partager les visuels de conception avec des parties prenantes qui ne disposent pas d'outils CAO, d'intégrer le rendu dans des rapports ou d'archiver le modèle à des fins de conformité.

## Pourquoi utiliser GroupDocs.Viewer pour les conversions IGS ?
GroupDocs.Viewer traite les fichiers IGS sans nécessiter de logiciel CAO externe. Il prend en charge **plus de 50 formats d'entrée et de sortie**, peut rendre des assemblages contenant **des centaines de pièces** tout en maintenant l'utilisation de la mémoire en dessous de **200 Mo**, et fournit des résultats en moins de **2 secondes** pour des modèles typiques sur un serveur standard. Ces avantages quantifiés en font un choix haute performance et rentable pour les pipelines d'entreprise.

## Prérequis
- **GroupDocs.Viewer for Java** ≥ 25.2 (la dernière version stable).  
- **JDK 8+** installé et configuré dans votre IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  
- Connaissances de base en Maven (optionnel mais recommandé pour la gestion des dépendances).  

## Configuration de GroupDocs.Viewer pour Java

### Dépendance Maven
Ajoutez le dépôt GroupDocs et la dépendance Viewer à votre `pom.xml` :

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Obtention de licence
GroupDocs.Viewer propose trois options de licence :
- **Essai gratuit** – utilisation limitée, parfait pour des tests rapides de preuve de concept.  
- **Licence temporaire** – ensemble complet de fonctionnalités pour une courte période d'évaluation, idéal pour les projets pilotes.  
- **Licence commerciale** – utilisation en production sans restriction, inclut le support prioritaire et les mises à jour.

### Initialisation de base du visualiseur
La classe `Viewer` est le point d'entrée pour toutes les opérations de rendu. Elle charge le fichier source, analyse le format et expose des méthodes pour produire la sortie souhaitée.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendu d'IGS en HTML

### Comment convertir IGS en HTML ?
Chargez le fichier IGS avec une instance `Viewer` et transmettez un objet `HtmlViewOptions` qui intègre tous les actifs requis. L'appel renvoie un fichier HTML unique contenant la vue 3 D complète, ce qui facilite l'intégration dans les pages web. Vous pouvez également personnaliser le rendu en définissant des options telles que la taille de la page, la couleur d'arrière-plan et l'inclusion de contrôles interactifs.  
`HtmlViewOptions` configure la génération de la sortie HTML, y compris l'intégration des ressources et la mise en page.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendu d'IGS en JPG

### Comment convertir IGS en JPG ?
Créez un objet `JpgViewOptions`, configurez la résolution souhaitée et la qualité de compression, puis laissez le `Viewer` générer des images raster pour chaque page du modèle. Les fichiers JPG générés peuvent être enregistrés dans un répertoire spécifié, et vous pouvez ajuster le paramètre de qualité pour équilibrer la taille du fichier et la fidélité visuelle, ce qui est utile pour les miniatures ou les impressions haute résolution.  
`JpgViewOptions` spécifie les paramètres de génération d'images JPG tels que la résolution, la qualité et le répertoire de sortie.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendu d'IGS en PNG

### Comment convertir IGS en PNG ?
La classe `PngViewOptions` vous permet de produire des images sans perte avec transparence optionnelle. Ce format est idéal pour superposer le modèle sur des arrière-plans colorés dans le matériel marketing. Vous pouvez également définir la résolution et la couleur d'arrière-plan pour correspondre aux directives de votre marque, assurant une apparence cohérente sur tous les actifs générés.  
`PngViewOptions` définit les paramètres du rendu PNG, incluant la résolution, la transparence et la couleur d'arrière-plan.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendu d'IGS en PDF

### Comment convertir IGS en PDF ?
Utilisez `PdfViewOptions` pour produire un PDF paginé qui préserve la mise en page visuelle du modèle 3 D. Vous pouvez également intégrer des polices et contrôler la taille des pages pour respecter les directives de la marque de l'entreprise. Des paramètres supplémentaires vous permettent de spécifier la qualité d'image, le niveau de compression et l'inclusion d'une table des matières pour les assemblages multi‑pages.  
`PdfViewOptions` contrôle la création du PDF, permettant la configuration de la taille des pages, de la qualité d'image et de l'intégration des polices.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Applications pratiques
- **Portails web** – intégrez des modèles rendus en HTML directement dans les configurateurs de produits, permettant aux clients de faire pivoter et zoomer sans installer de plugins.  
- **Supports marketing** – générez des images JPG/PNG haute résolution pour les brochures, présentations et publications sur les réseaux sociaux.  
- **Documentation technique** – incluez les rendus PDF des modèles CAO dans les manuels utilisateurs, garantissant que les ingénieurs puissent visualiser les conceptions hors ligne.  
- **Assurance qualité** – automatisez la création de miniatures pour des milliers de fichiers IGS, accélérant les flux de travail d'inspection visuelle.

## Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| **Dossier de sortie introuvable** | Vérifiez le chemin passé à `Path outputDirectory` et assurez-vous que le processus Java dispose des permissions d'écriture sur le répertoire cible. |
| **Pages blanches dans le PDF** | Confirmez que le fichier IGS source n'est pas corrompu ; ouvrez-le d'abord dans un visualiseur CAO natif. |
| **Rendu lent pour les grands assemblages** | Augmentez le tas JVM (`-Xmx2g` ou plus) et envisagez de rendre page par page en utilisant `viewer.getPageCount()` pour traiter les morceaux. |
| **Polices manquantes dans le PDF** | Utilisez `PdfViewOptions` pour intégrer les polices requises ou installez les polices manquantes sur le serveur hébergeant le service de conversion. |

## Questions fréquemment posées

**Q : Puis-je convertir plusieurs fichiers IGS en une seule exécution ?**  
R : Oui. Parcourez une collection de chemins de fichiers et invoquez la méthode `view` appropriée pour chaque fichier au sein de la même instance `Viewer`.

**Q : Est-il possible de personnaliser la taille de la page PDF ?**  
R : Absolument. `PdfViewOptions` propose `setPageSize(PageSize.A4)`, `PageSize.Letter` et des dimensions personnalisées via `setCustomSize(width, height)`.

**Q : Ai-je besoin d'une licence distincte pour chaque format de sortie ?**  
R : Non. Une seule licence GroupDocs.Viewer couvre tous les formats pris en charge, y compris HTML, JPG, PNG et PDF.

**Q : Quelle taille maximale peut atteindre un fichier IGS avant que les performances ne se dégradent ?**  
R : La bibliothèque traite de manière fiable les fichiers jusqu'à **500 Mo** ; pour les modèles supérieurs à 200 Mo, allouez davantage de mémoire JVM et envisagez de rendre par lots.

**Q : Puis-je rendre uniquement une vue ou une orientation spécifique ?**  
R : GroupDocs.Viewer rend l'orientation par défaut définie dans le fichier IGS. Pour des vues personnalisées, prétraitez le fichier avec un outil CAO ou ajustez le modèle avant la conversion.

---

**Dernière mise à jour :** 2026-08-08  
**Testé avec :** GroupDocs.Viewer 25.2 pour Java  
**Auteur :** GroupDocs

## Tutoriels associés

- [convertir cdr en html, jpg, png, pdf avec GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Comment convertir pdf en html et optimiser la qualité d'image en Java avec GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)