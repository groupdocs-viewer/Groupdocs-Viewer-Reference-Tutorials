---
date: '2026-02-23'
description: Erfahren Sie, wie Sie IGS mit GroupDocs.Viewer für Java in PDF, HTML,
  JPG und PNG konvertieren. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung mit sofort
  einsatzbereiten Codebeispielen.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: IGS in PDF, HTML, JPG & PNG mit GroupDocs.Viewer Java konvertieren
type: docs
url: /de/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# IGS in PDF, HTML, JPG & PNG konvertieren mit GroupDocs.Viewer Java

Wenn Sie **IGS in PDF** (oder in HTML, JPG, PNG) direkt aus einer Java-Anwendung konvertieren müssen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch alles, was Sie benötigen – von der Einrichtung der Bibliothek bis zur Darstellung des 3‑D‑Modells im für Ihr Projekt passenden Format. Sie werden sehen, warum GroupDocs.Viewer eine solide Wahl für schnelle, zuverlässige Konvertierungen ist, und erhalten praxisnahen Code, den Sie in Ihre eigene Lösung einbinden können.

![IGS-Dateien mit GroupDocs.Viewer für Java in HTML, JPG, PNG und PDF konvertieren](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Schnelle Antworten
- **Kann ich IGS mit Java in PDF konvertieren?** Ja, mit `PdfViewOptions` von GroupDocs.Viewer.  
- **Welche Ausgabeformate werden unterstützt?** HTML, JPG, PNG und PDF.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist erforderlich; ein kostenloser Testzeitraum ist zum Testen verfügbar.  
- **Welche Java-Version wird benötigt?** JDK 8 oder höher.  
- **Ist Maven die einzige Möglichkeit, die Bibliothek hinzuzufügen?** Nein, Sie können auch Gradle oder die manuelle JAR‑Einbindung verwenden.

## Was bedeutet „IGS in PDF konvertieren“?
Das Konvertieren von IGS (ein neutrales Dateiformat für 3‑D‑CAD‑Daten) in PDF bedeutet, ein komplexes 3‑D‑Modell in ein statisches, breit anzeigbares Dokument zu verwandeln. Das ist nützlich, um Entwürfe mit Stakeholdern zu teilen, die keine CAD‑Werkzeuge besitzen.

## Warum GroupDocs.Viewer für IGS-Konvertierungen verwenden?
- **Zero‑Code CAD‑Rendering** – die Bibliothek übernimmt das aufwändige Parsen des IGS‑Formats.  
- **Mehrere Ausgabeoptionen** – ein API‑Aufruf kann HTML, JPG, PNG oder PDF erzeugen.  
- **Plattformübergreifend** – funktioniert auf jedem Betriebssystem, das Java unterstützt.  
- **Leistungsorientiert** – schnelle Darstellung selbst bei großen Baugruppen.

## Voraussetzungen
- **GroupDocs.Viewer für Java** ≥ 25.2  
- **JDK 8+** installiert und in Ihrer IDE (IntelliJ IDEA, Eclipse, NetBeans usw.) konfiguriert  
- Grundkenntnisse in Maven (optional, aber empfohlen)

## Einrichtung von GroupDocs.Viewer für Java

### Maven-Abhängigkeit
Fügen Sie das GroupDocs-Repository und die Viewer-Abhängigkeit zu Ihrer `pom.xml` hinzu:

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
GroupDocs.Viewer offers:
- **Kostenlose Testversion** – begrenzte Nutzung, ideal für schnelle Tests.  
- **Temporäre Lizenz** – voller Funktionsumfang für einen kurzen Evaluationszeitraum.  
- **Kommerzielle Lizenz** – uneingeschränkter Produktionseinsatz.

### Grundlegende Viewer-Initialisierung
Das nachstehende Snippet zeigt, wie Sie eine `Viewer`‑Instanz erstellen, die auf Ihre IGS‑Datei verweist:

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

## Rendering von IGS nach HTML

### Wie konvertiere ich IGS nach HTML?
HTML‑Ausgabe liefert Ihnen eine interaktive, browserfreundliche Ansicht des 3‑D‑Modells.

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

**Wichtiger Hinweis:** `HtmlViewOptions.forEmbeddedResources()` bettet alle erforderlichen Ressourcen (CSS, Bilder) direkt in die HTML‑Datei ein, wodurch sie portabel wird.

## Rendering von IGS nach JPG

### Wie konvertiere ich IGS nach JPG?
JPG‑Bilder eignen sich perfekt für Thumbnails oder schnelle Vorschauen.

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

Sie können `JpgViewOptions` anpassen, um Auflösung und Kompressionsqualität zu steuern.

## Rendering von IGS nach PNG

### Wie konvertiere ich IGS nach PNG?
PNG unterstützt Transparenz, was praktisch ist, um das Modell auf verschiedenen Hintergründen zu überlagern.

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

Experimentieren Sie mit den `PngViewOptions`, um das beste Gleichgewicht zwischen Dateigröße und visueller Treue zu erzielen.

## Rendering von IGS nach PDF

### Wie konvertiere ich IGS nach PDF?
PDF ist das bevorzugte Format zum Teilen detaillierter Designdokumentation. Dieser Abschnitt behandelt direkt das Hauptkeyword **convert IGS to PDF**.

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

`PdfViewOptions` ermöglicht es Ihnen, das Seitenlayout, die Bildqualität und das Einbetten von Schriftarten zu steuern.

## Praktische Anwendungsfälle
- **Webportale** – HTML‑gerenderte Modelle direkt in Produktkonfiguratoren einbetten.  
- **Marketing‑Materialien** – hochauflösende JPG/PNG‑Bilder für Broschüren erzeugen.  
- **Technische Dokumentation** – PDF‑Renderings von CAD‑Modellen in Benutzerhandbüchern einbinden.  
- **Qualitätssicherung** – automatisierte Thumbnail‑Erstellung für große Stapel von IGS‑Dateien.

## Häufige Probleme & Lösungen

| Problem | Lösung |
|-------|----------|
| **Ausgabeordner nicht gefunden** | Überprüfen Sie den an `Path outputDirectory` übergebenen Pfad und stellen Sie sicher, dass der Java‑Prozess Schreibrechte hat. |
| **Leerseiten im PDF** | Stellen Sie sicher, dass die IGS‑Datei nicht beschädigt ist; versuchen Sie zunächst, sie in einem CAD‑Viewer zu öffnen. |
| **Langsames Rendering bei großen Baugruppen** | Erhöhen Sie den JVM‑Heap (`-Xmx2g` oder mehr) und erwägen Sie, bei Bedarf seitenweise mit `viewer.getPageCount()` zu rendern. |
| **Fehlende Schriftarten im PDF** | Verwenden Sie `PdfViewOptions`, um erforderliche Schriftarten einzubetten, oder installieren Sie die fehlenden Schriftarten auf dem Server. |

## Häufig gestellte Fragen

**Q: Kann ich mehrere IGS‑Dateien in einem Durchlauf konvertieren?**  
A: Ja. Durchlaufen Sie eine Liste von Dateipfaden und rufen Sie für jede die entsprechende `view`‑Methode auf.

**Q: Ist es möglich, die PDF‑Seitengröße anzupassen?**  
A: Absolut. `PdfViewOptions` bietet `setPageSize(PageSize.A4)` und ähnliche Methoden.

**Q: Benötige ich für jedes Ausgabeformat eine separate Lizenz?**  
A: Nein. Eine einzelne GroupDocs.Viewer‑Lizenz deckt alle unterstützten Formate ab.

**Q: Wie groß kann eine IGS‑Datei sein, bevor die Leistung nachlässt?**  
A: Die Bibliothek verarbeitet Dateien bis zu mehreren hundert Megabyte, aber für sehr große Modelle müssen Sie möglicherweise mehr JVM‑Speicher zuweisen.

**Q: Kann ich nur eine bestimmte Ansicht oder Orientierung rendern?**  
A: GroupDocs.Viewer rendert die Standardansicht. Für benutzerdefinierte Orientierungen sollten Sie die IGS‑Datei vor der Konvertierung mit einem CAD‑Tool vorverarbeiten.

---

**Zuletzt aktualisiert:** 2026-02-23  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs