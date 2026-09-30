---
date: '2026-09-30'
description: Apprenez à faire pivoter une page de 90 degrés en Java avec GroupDocs
  Viewer, y compris la configuration, le code et les conseils de performance.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Faire pivoter une page de 90 degrés en Java avec GroupDocs Viewer.
  Guide pas à pas, conseils de performance et cas d’utilisation réels pour les développeurs.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Faire pivoter la page de 90 degrés avec GroupDocs Viewer pour Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Faire pivoter la page de 90 degrés avec GroupDocs Viewer pour Java
type: docs
url: /fr/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Faire pivoter la page de 90 degrés avec GroupDocs Viewer pour Java

If you need to **rotate page 90 degrees** in a document—whether it’s a PDF, Word file, or spreadsheet—doing it programmatically in Java saves time, removes manual errors, and lets you embed the operation into automated pipelines. In this advanced guide you’ll learn how to rotate the first page of any supported document using **GroupDocs Viewer for Java**, why this capability matters in real‑world projects, and how to keep the process lightweight and memory‑efficient.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Réponses rapides
- **Que signifie « faire pivoter la page de 90 degrés » ?** It turns the selected page clockwise by a quarter turn.  
- **Quelle bibliothèque gère la rotation ?** GroupDocs Viewer for Java provides the `rotatePage` method.  
- **Puis-je faire pivoter des pages PDF avec Java ?** Yes—use the same `rotatePage` call; it works for PDF, DOCX, XLSX, and more.  
- **Ai-je besoin d’une licence ?** A free trial works for development; a paid license is required for production.  
- **L’opération est‑elle gourmande en mémoire ?** Not when you close the `Viewer` instance promptly; see the performance tips below.

## Qu’est‑ce que « faire pivoter la page de 90 degrés » ?
Rotating a page 90 degrees re‑orients the page from portrait to landscape (or vice‑versa) without changing the underlying content. This is handy for presentations, printing landscape‑only graphics, or correcting scanned documents that were captured sideways. The rotation is applied at render time, leaving the original file unchanged.

## Pourquoi faire pivoter les pages programmatiquement avec GroupDocs Viewer pour Java ?
GroupDocs Viewer supports **50+ input and output formats**—including PDF, DOCX, PPTX, XLSX, and many image types—so you can render any document without external converters. The API is fluent, thread‑safe, and runs on any Java 8+ runtime, making it a reliable choice for enterprise‑grade automation that must handle dozens of file types consistently.

## Prérequis

- GroupDocs Viewer for Java (latest version)
- JDK 8 or newer
- Maven (or Gradle) for dependency management
- An IDE such as IntelliJ IDEA or Eclipse
- Basic familiarity with Java I/O

## Configuration de GroupDocs.Viewer pour Java

Add the GroupDocs repository and dependency to your `pom.xml`. This snippet is unchanged from the original tutorial:

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

### Acquisition de licence
- **Free trial** – download from the GroupDocs site.  
- **Temporary license** – request if you need an extended evaluation period.  
- **Full license** – purchase for production deployments.

### Initialisation de base du Viewer
The `Viewer` class is the entry point that loads a document and exposes rendering and transformation methods. Keep the code exactly as shown:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Comment faire pivoter une page PDF en Java avec GroupDocs Viewer
Load the target file with `Viewer`, specify the page number, and call `rotatePage`. The method works for PDF, DOCX, PPTX, XLSX and any other format supported by the library. After rotation, you can render the document to a new PDF or stream it directly to the client, ensuring the original file remains untouched.

## Implémentation étape par étape : faire pivoter la première page de 90 degrés

### 1. Importer les packages requis
`PdfViewOptions` tells the Viewer to output a PDF file, while the `Rotation` enum defines the angle. Both classes belong to the `com.groupdocs.viewer.options` package.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Définir les emplacements de sortie et créer le Viewer
Replace the placeholder paths with your actual directories. The `Viewer` constructor accepts a `File` object that points to the source document.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Configurer les options d’affichage PDF et appliquer la rotation
The `rotatePage(int, Rotation)` method takes a **1‑based** page index and a `Rotation` enum value. In this example we use `Rotation.ON_90_DEGREE` to turn the first page clockwise.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Rendre le document
Calling `view` with the configured options writes the rotated PDF to the output folder.

```java
viewer.view(viewOptions);
```

#### Comment ça fonctionne
- **PdfViewOptions** directs the Viewer to generate a PDF output file.  
- **rotatePage(int, Rotation)** rotates only the specified page, leaving all other pages unchanged.  
- The method supports three rotation constants: `ON_90_DEGREE`, `ON_180_DEGREE`, and `ON_270_DEGREE`.

## Problèmes courants et solutions
| Symptôme | Cause probable | Solution |
|---------|--------------|-----|
| **FileNotFoundException** | Incorrect path or missing folder | Verify `YOUR_OUTPUT_DIRECTORY` and `YOUR_DOCUMENT_DIRECTORY` exist and are readable. |
| **Unsupported file format** | Trying to rotate a format not supported by Viewer | Check the [GroupDocs Viewer supported formats] page. |
| **No rotation visible** | Using the wrong page number (0‑based) | Remember `rotatePage` uses **1‑based** indexing. |
| **Out‑of‑memory errors on large docs** | Rendering many large files in a single thread | Process documents sequentially or use a thread pool with limited concurrency. |

## Applications pratiques

1. **Ajustements de présentation** – Convertir une diapositive en portrait en paysage à la volée pour un meilleur impact visuel.  
2. **Correction massive de documents** – Automatiser la correction de PDF numérisés capturés de travers, économisant des heures de travail manuel.  
3. **Sortie prête à l’impression** – Garantir que les graphiques en paysage s’impriment correctement sur du papier orienté en portrait sans rotation manuelle dans le pilote d’imprimante.

## Conseils de performance

- **Fermer les ressources rapidement** – Le bloc `try‑with‑resources` libère automatiquement le `Viewer`, libérant la mémoire.  
- **Traitement par lots** – Réutiliser une seule instance de `Viewer` par thread pour réduire la surcharge d’initialisation.  
- **Surveiller la mémoire** – Pour les documents de plus de 100 Mo, diffuser la sortie vers le disque au lieu de garder le fichier entier en mémoire ; GroupDocs Viewer peut traiter des fichiers de 200 Mo avec moins de 250 Mo de RAM.

## Questions fréquemment posées

**Q : Puis‑je faire pivoter plusieurs pages à la fois ?**  
**R :** Oui—appelez `rotatePage()` pour chaque numéro de page à faire pivoter, soit dans une boucle, soit en chaînant les appels.

**Q : Existe‑t‑il un moyen d’annuler la rotation après le rendu ?**  
**R :** Pas directement. Vous devez rendre à nouveau le document sans les options de rotation.

**Q : Quels formats de fichiers supportent la rotation de page dans GroupDocs Viewer ?**  
**R :** DOCX, PDF, PPTX, XLSX, et de nombreux autres formats listés dans la documentation officielle.

**Q : Comment puis‑je faire pivoter les pages d’un lot de documents automatiquement ?**  
**R :** Encapsulez la logique de rotation dans une boucle qui parcourt une collection de chemins de fichiers, en appliquant la même configuration `rotatePage` à chaque fichier.

**Q : Quelle est la meilleure pratique pour gérer les erreurs pendant la rotation ?**  
**R :** Enveloppez l’utilisation du Viewer dans un bloc `try‑catch`, consignez les détails de l’exception, et continuez éventuellement le traitement du fichier suivant afin qu’une seule erreur n’arrête pas tout le lot.

## Ressources

- **Documentation** : [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference** : [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download** : [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase** : [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial** : [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license** : [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support** : [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-09-30  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs

## Tutoriels associés

- [Comment faire pivoter des pages PDF spécifiques avec GroupDocs.Viewer pour Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Charger un document depuis une URL en Java – Tutoriel GroupDocs.Viewer](/viewer/java/document-loading/)
- [Vues de documents GroupDocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}