---
date: '2026-08-08'
description: Erfahren Sie, wie Sie IGS mit GroupDocs.Viewer für Java in PDF, HTML,
  JPG und PNG konvertieren. Schritt‑für‑Schritt‑Anleitung, Voraussetzungen und Fehlerbehebung
  für Java‑Entwickler.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Konvertieren Sie IGS mit GroupDocs.Viewer für Java in PDF, HTML, JPG
  und PNG. Detaillierte Einrichtung, Code‑Beispiele und Fehlerbehebung für Java‑Entwickler.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: IGS in PDF, HTML, JPG & PNG konvertieren mit GroupDocs.Viewer Java
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
title: IGS in PDF, HTML, JPG & PNG konvertieren mit GroupDocs.Viewer Java
type: docs
url: /de/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# IGS in PDF, HTML, JPG & PNG mit GroupDocs.Viewer Java konvertieren

Wenn Sie **IGS in PDF konvertieren** (oder in HTML, JPG, PNG) direkt aus einer Java-Anwendung benötigen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch alles, was Sie benötigen – von der Installation der Bibliothek bis zur Darstellung des 3‑D‑Modells im Format, das zu Ihrem Projekt passt. Sie werden verstehen, warum GroupDocs.Viewer eine solide Wahl für schnelle, zuverlässige Konvertierungen ist, und Sie erhalten sofort einsatzbereite Code‑Snippets, die Sie in Ihre eigene Lösung einbinden können.

![IGS-Dateien in HTML, JPG, PNG und PDF mit GroupDocs.Viewer für Java konvertieren](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Schnelle Antworten
- **Kann ich IGS mit Java in PDF konvertieren?** Ja, verwenden Sie `PdfViewOptions` zusammen mit der `Viewer`‑API.  
- **Welche Ausgabeformate werden unterstützt?** HTML, JPG, PNG und PDF werden alle nativ verarbeitet.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist erforderlich; ein kostenloser Test ermöglicht es Ihnen, die Kernfunktionen zu testen.  
- **Welche Java-Version wird benötigt?** JDK 8 oder höher; die Bibliothek läuft auch auf Java 11, 17 und später.  
- **Ist Maven die einzige Möglichkeit, die Bibliothek hinzuzufügen?** Nein, Sie können auch Gradle verwenden oder die JAR‑Dateien manuell zu Ihrem Klassenpfad hinzufügen.

## Was ist die Konvertierung von IGS zu PDF?
Die Konvertierung von IGS zu PDF bedeutet, eine neutrale 3‑D‑CAD‑Datei in ein statisches, universell anzeigbares Dokument zu verwandeln. Dies ermöglicht es Ihnen, Design‑Visualisierungen mit Stakeholdern zu teilen, die keine CAD‑Tools besitzen, die Darstellung in Berichte einzubetten oder das Modell zu Compliance‑Zwecken zu archivieren.

## Warum GroupDocs.Viewer für IGS-Konvertierungen verwenden?
GroupDocs.Viewer verarbeitet IGS‑Dateien, ohne dass externe CAD‑Software erforderlich ist. Es unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate**, kann Baugruppen mit **Hunderten von Bauteilen** rendern, während der Speicherverbrauch unter **200 MB** bleibt, und liefert Ergebnisse in weniger als **2 Sekunden** für typische Modelle auf einem Standard‑Server. Diese quantifizierten Vorteile machen es zu einer leistungsstarken, kosteneffizienten Wahl für Unternehmens‑Pipelines.

## Voraussetzungen
- **GroupDocs.Viewer für Java** ≥ 25.2 (die neueste stabile Version).  
- **JDK 8+** installiert und in Ihrer IDE (IntelliJ IDEA, Eclipse, NetBeans usw.) konfiguriert.  
- Grundkenntnisse in Maven (optional, aber empfohlen für das Dependency‑Management).  

## Einrichtung von GroupDocs.Viewer für Java

### Maven‑Abhängigkeit
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer offers three licensing options:
- **Kostenlose Testversion** – begrenzte Nutzung, ideal für schnelle Proof‑of‑Concept‑Tests.  
- **Temporäre Lizenz** – vollständiger Funktionsumfang für einen kurzen Evaluationszeitraum, ideal für Pilotprojekte.  
- **Kommerzielle Lizenz** – uneingeschränkter Produktionseinsatz, beinhaltet Prioritäts‑Support und Updates.

### Grundlegende Viewer‑Initialisierung
Die Klasse `Viewer` ist der Einstiegspunkt für alle Rendering‑Operationen. Sie lädt die Quelldatei, analysiert das Format und stellt Methoden bereit, um die gewünschte Ausgabe zu erzeugen.

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

## Rendering von IGS zu HTML

### Wie konvertiere ich IGS zu HTML?
Laden Sie die IGS‑Datei mit einer `Viewer`‑Instanz und übergeben Sie ein `HtmlViewOptions`‑Objekt, das alle erforderlichen Ressourcen einbettet. Der Aufruf liefert eine einzelne HTML‑Datei, die die vollständige 3‑D‑Ansicht enthält und das Einbetten in Webseiten erleichtert. Sie können das Rendering auch anpassen, indem Sie Optionen wie Seitengröße, Hintergrundfarbe und die Einbindung interaktiver Steuerelemente festlegen.  
`HtmlViewOptions` konfiguriert, wie die HTML‑Ausgabe erzeugt wird, einschließlich Ressourcen‑Einbettung und Seitenlayout.

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

## Rendering von IGS zu JPG

### Wie konvertiere ich IGS zu JPG?
Erstellen Sie ein `JpgViewOptions`‑Objekt, konfigurieren Sie die gewünschte Auflösung und Kompressionsqualität und lassen Sie den `Viewer` Rasterbilder für jede Seite des Modells erzeugen. Die erzeugten JPG‑Dateien können in ein angegebenes Verzeichnis gespeichert werden, und Sie können den Qualitätsparameter anpassen, um Dateigröße und visuelle Treue auszubalancieren, was für Thumbnails oder hochauflösende Drucke nützlich ist.  
`JpgViewOptions` legt Einstellungen für die JPG‑Bildgenerierung fest, wie Auflösung, Qualität und Ausgabeverzeichnis.

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

## Rendering von IGS zu PNG

### Wie konvertiere ich IGS zu PNG?
Die Klasse `PngViewOptions` ermöglicht die Erstellung verlustfreier Bilder mit optionaler Transparenz. Dieses Format ist ideal, um das Modell in Marketing‑Materialien auf farbigen Hintergründen zu überlagern. Sie können zudem Auflösung und Hintergrundfarbe festlegen, um Ihren Markenrichtlinien zu entsprechen und ein konsistentes Erscheinungsbild aller erzeugten Assets zu gewährleisten.  
`PngViewOptions` definiert Parameter für das PNG‑Rendering, einschließlich Auflösung, Transparenz und Hintergrundfarbe.

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

## Rendering von IGS zu PDF

### Wie konvertiere ich IGS zu PDF?
Verwenden Sie `PdfViewOptions`, um ein paginiertes PDF zu erzeugen, das das visuelle Layout des 3‑D‑Modells beibehält. Sie können auch Schriftarten einbetten und die Seitengröße steuern, um Unternehmens‑Branding‑Richtlinien zu entsprechen. Weitere Einstellungen ermöglichen die Angabe von Bildqualität, Kompressionsgrad und ob ein Inhaltsverzeichnis für mehrseitige Baugruppen enthalten sein soll.  
`PdfViewOptions` steuert die PDF‑Erstellung und ermöglicht Konfiguration von Seitengröße, Bildqualität und Schriftart‑Einbettung.

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

## Praktische Anwendungsfälle
- **Webportale** – HTML‑gerenderte Modelle direkt in Produktkonfiguratoren einbetten, sodass Kunden das Modell drehen und zoomen können, ohne Plugins zu installieren.  
- **Marketing‑Assets** – hochauflösende JPG/PNG‑Bilder für Broschüren, Präsentationen und Social‑Media‑Beiträge erzeugen.  
- **Technische Dokumentation** – PDF‑Renderings von CAD‑Modellen in Benutzerhandbüchern einbinden, sodass Ingenieure Designs offline ansehen können.  
- **Qualitätssicherung** – automatisierte Erstellung von Thumbnails für tausende IGS‑Dateien, um visuelle Prüfabläufe zu beschleunigen.

## Häufige Probleme & Lösungen

| Problem | Lösung |
|-------|----------|
| **Ausgabeordner nicht gefunden** | Überprüfen Sie den an `Path outputDirectory` übergebenen Pfad und stellen Sie sicher, dass der Java‑Prozess Schreibrechte für das Zielverzeichnis hat. |
| **Leere Seiten im PDF** | Stellen Sie sicher, dass die Quell‑IGS‑Datei nicht beschädigt ist; öffnen Sie sie zunächst in einem nativen CAD‑Viewer. |
| **Langsames Rendering bei großen Baugruppen** | Erhöhen Sie den JVM‑Heap (`-Xmx2g` oder mehr) und erwägen Sie, das Rendering seitenweise mit `viewer.getPageCount()` zu verarbeiten. |
| **Fehlende Schriftarten im PDF** | Verwenden Sie `PdfViewOptions`, um erforderliche Schriftarten einzubetten, oder installieren Sie die fehlenden Schriftarten auf dem Server, der den Konvertierungsdienst hostet. |

## Häufig gestellte Fragen

**Q: Kann ich mehrere IGS‑Dateien in einem Durchlauf konvertieren?**  
A: Ja. Durchlaufen Sie eine Sammlung von Dateipfaden und rufen Sie die entsprechende `view`‑Methode für jede Datei innerhalb derselben `Viewer`‑Instanz auf.

**Q: Ist es möglich, die PDF‑Seitengröße anzupassen?**  
A: Absolut. `PdfViewOptions` bietet `setPageSize(PageSize.A4)`, `PageSize.Letter` und benutzerdefinierte Abmessungen über `setCustomSize(width, height)`.

**Q: Benötige ich eine separate Lizenz für jedes Ausgabeformat?**  
A: Nein. Eine einzelne GroupDocs.Viewer‑Lizenz deckt alle unterstützten Formate ab, einschließlich HTML, JPG, PNG und PDF.

**Q: Wie groß kann eine IGS‑Datei sein, bevor die Leistung nachlässt?**  
A: Die Bibliothek verarbeitet zuverlässig Dateien bis zu **500 MB**; bei Modellen größer als 200 MB sollten Sie zusätzlichen JVM‑Speicher zuweisen und ein Batch‑Rendering in Betracht ziehen.

**Q: Kann ich nur eine bestimmte Ansicht oder Orientierung rendern?**  
A: GroupDocs.Viewer rendert die im IGS‑Datei definierte Standard‑Orientierung. Für benutzerdefinierte Ansichten sollten Sie die Datei mit einem CAD‑Tool vorverarbeiten oder das Modell vor der Konvertierung anpassen.

**Zuletzt aktualisiert:** 2026-08-08  
**Getestet mit:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Verwandte Tutorials

- [cdr zu html, jpg, png, pdf mit GroupDocs.Viewer Java konvertieren](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Wie man pdf zu html konvertiert und die Bildqualität in Java mit GroupDocs.Viewer optimiert](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)