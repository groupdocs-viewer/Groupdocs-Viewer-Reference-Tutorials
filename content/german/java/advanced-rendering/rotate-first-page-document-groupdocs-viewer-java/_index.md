---
date: '2026-09-30'
description: Erfahren Sie, wie Sie eine Seite in Java mit GroupDocs Viewer um 90 Grad
  drehen, einschließlich Einrichtung, Code und Performance‑Tipps.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Drehen Sie eine Seite in Java mit GroupDocs Viewer um 90 Grad. Schritt‑für‑Schritt‑Anleitung,
  Performance‑Tipps und praxisnahe Anwendungsbeispiele für Entwickler.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Seite um 90 Grad drehen mit GroupDocs Viewer für Java
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
title: Seite um 90 Grad drehen mit GroupDocs Viewer für Java
type: docs
url: /de/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Seite um 90 Grad drehen mit GroupDocs Viewer für Java

If you need to **rotate page 90 degrees** in a document—whether it’s a PDF, Word file, or spreadsheet—doing it programmatically in Java saves time, removes manual errors, and lets you embed the operation into automated pipelines. In this advanced guide you’ll learn how to rotate the first page of any supported document using **GroupDocs Viewer for Java**, why this capability matters in real‑world projects, and how to keep the process lightweight and memory‑efficient.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Schnelle Antworten
- **Was bedeutet „rotate page 90 degrees“?** It turns the selected page clockwise by a quarter turn.  
- **Welche Bibliothek führt die Drehung aus?** GroupDocs Viewer for Java provides the `rotatePage` method.  
- **Kann ich PDF‑Seiten mit Java drehen?** Yes—use the same `rotatePage` call; it works for PDF, DOCX, XLSX, and more.  
- **Brauche ich eine Lizenz?** A free trial works for development; a paid license is required for production.  
- **Ist der Vorgang speicherintensiv?** Not when you close the `Viewer` instance promptly; see the performance tips below.

## Was bedeutet „rotate page 90 degrees“?
Rotating a page 90 degrees re‑orients the page from portrait to landscape (or vice‑versa) without changing the underlying content. This is handy for presentations, printing landscape‑only graphics, or correcting scanned documents that were captured sideways. The rotation is applied at render time, leaving the original file unchanged.

## Warum Seiten programmgesteuert mit GroupDocs Viewer für Java drehen?
GroupDocs Viewer supports **50+ input and output formats**—including PDF, DOCX, PPTX, XLSX, and many image types—so you can render any document without external converters. The API is fluent, thread‑safe, and runs on any Java 8+ runtime, making it a reliable choice for enterprise‑grade automation that must handle dozens of file types consistently.

## Voraussetzungen

- GroupDocs Viewer für Java (neueste Version)
- JDK 8 oder neuer
- Maven (oder Gradle) für die Abhängigkeitsverwaltung
- Eine IDE wie IntelliJ IDEA oder Eclipse
- Grundlegende Kenntnisse von Java I/O

## Einrichtung von GroupDocs.Viewer für Java

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

### Lizenzbeschaffung
- **Kostenlose Testversion** – download from the GroupDocs site.  
- **Temporäre Lizenz** – request if you need an extended evaluation period.  
- **Vollständige Lizenz** – purchase for production deployments.

### Grundlegende Viewer-Initialisierung
The `Viewer` class is the entry point that loads a document and exposes rendering and transformation methods. Keep the code exactly as shown:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Wie man PDF‑Seite in Java mit GroupDocs Viewer rotiert
Load the target file with `Viewer`, specify the page number, and call `rotatePage`. The method works for PDF, DOCX, PPTX, XLSX and any other format supported by the library. After rotation, you can render the document to a new PDF or stream it directly to the client, ensuring the original file remains untouched.

## Schritt‑für‑Schritt‑Implementierung: Erste Seite um 90 Grad drehen

### 1. Erforderliche Pakete importieren
`PdfViewOptions` tells the Viewer to output a PDF file, while the `Rotation` enum defines the angle. Both classes belong to the `com.groupdocs.viewer.options` package.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Ausgabepfade definieren und den Viewer erstellen
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

### 3. PDF‑Ansichtsoptionen konfigurieren und die Drehung anwenden
The `rotatePage(int, Rotation)` method takes a **1‑based** page index and a `Rotation` enum value. In this example we use `Rotation.ON_90_DEGREE` to turn the first page clockwise.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Dokument rendern
Calling `view` with the configured options writes the rotated PDF to the output folder.

```java
viewer.view(viewOptions);
```

#### Wie es funktioniert
- **PdfViewOptions** directs the Viewer to generate a PDF output file.  
- **rotatePage(int, Rotation)** rotates only the specified page, leaving all other pages unchanged.  
- The method supports three rotation constants: `ON_90_DEGREE`, `ON_180_DEGREE`, and `ON_270_DEGREE`.

## Häufige Probleme und Lösungen
| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| **FileNotFoundException** | Incorrect path or missing folder | Verify `YOUR_OUTPUT_DIRECTORY` and `YOUR_DOCUMENT_DIRECTORY` exist and are readable. |
| **Unsupported file format** | Trying to rotate a format not supported by Viewer | Check the [GroupDocs Viewer supported formats] page. |
| **No rotation visible** | Using the wrong page number (0‑based) | Remember `rotatePage` uses **1‑based** indexing. |
| **Out‑of‑memory errors on large docs** | Rendering many large files in a single thread | Process documents sequentially or use a thread pool with limited concurrency. |

## Praktische Anwendungen

1. **Präsentationsanpassungen** – Convert a portrait slide to landscape on the fly for better visual impact.  
2. **Massenkorrektur von Dokumenten** – Automate fixing of scanned PDFs that were captured sideways, saving hours of manual work.  
3. **Druckfertige Ausgabe** – Ensure landscape graphics print correctly on portrait‑oriented paper without manual rotation in the printer driver.

## Leistungstipps

- **Ressourcen sofort schließen** – The `try‑with‑resources` block automatically disposes of the `Viewer`, freeing memory.  
- **Stapelverarbeitung** – Reuse a single `Viewer` instance per thread to reduce initialization overhead.  
- **Speicher überwachen** – For documents larger than 100 MB, stream the output to disk instead of keeping the whole file in memory; GroupDocs Viewer can process 200 MB files using under 250 MB of RAM.

## Häufig gestellte Fragen

**Q: Kann ich mehrere Seiten gleichzeitig drehen?**  
A: Yes—invoke `rotatePage()` for each page number you need to rotate, either in a loop or by chaining calls.

**Q: Gibt es eine Möglichkeit, die Drehung nach dem Rendern rückgängig zu machen?**  
A: Not directly. You would need to render the document again without the rotation options.

**Q: Welche Dateiformate unterstützen die Seitendrehung in GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.

**Q: Wie kann ich Seiten in einem Stapel von Dokumenten automatisch drehen?**  
A: Wrap the rotation logic in a loop that iterates over a collection of file paths, applying the same `rotatePage` configuration to each file.

**Q: Was ist die beste Praxis für den Umgang mit Fehlern während der Drehung?**  
A: Enclose the Viewer usage in a `try‑catch` block, log the exception details, and optionally continue processing the next file to avoid a single failure stopping the whole batch.

## Ressourcen

- **Dokumentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API‑Referenz**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Kauf**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Kostenlose Testversion**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporäre Lizenz**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-09-30  
**Getestet mit:** GroupDocs Viewer 25.2 für Java  
**Autor:** GroupDocs

## Verwandte Tutorials

- [Wie man bestimmte PDF‑Seiten mit GroupDocs.Viewer für Java dreht](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Dokument aus URL in Java laden – GroupDocs.Viewer Tutorial](/viewer/java/document-loading/)
- [GroupDocs Viewer Java Dokumentansichten](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}