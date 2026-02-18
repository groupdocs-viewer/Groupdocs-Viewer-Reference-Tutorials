---
date: '2026-02-18'
description: Erfahren Sie, wie Sie WMZ- und WMF-Dateien mit GroupDocs Viewer für Java
  in PDF, HTML, JPG und PNG konvertieren. Dieser Leitfaden behandelt GroupDocs Viewer
  Java und die Java-Konvertierung von Vektorgrafiken.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Wie man WMZ mit GroupDocs Viewer für Java in PDF und andere Formate konvertiert
type: docs
url: /de/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 lines? They appear as separate lines. Keep them unchanged.

Also there is a blockquote with license tip: keep formatting.

Now produce final.# Wie man WMZ in PDF und andere Formate mit GroupDocs Viewer für Java konvertiert

Das Konvertieren von WMZ (Web Metafile) und WMF (Windows Metafile) Dateien in zugänglichere Formate – insbesondere **convert WMZ to PDF** – kann knifflig sein, da diese Vektorgrafik‑Formate Zeichenanweisungen statt Pixeldaten speichern. Mit **GroupDocs Viewer for Java** können Sie WMZ/WMF‑Dokumente in HTML, JPG, PNG, **PDF** und andere gängige Formate in nur wenigen Code‑Zeilen rendern.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

In diesem Tutorial lernen Sie, wie Sie die Bibliothek einrichten, WMZ/WMF‑Dateien in das gewünschte Ausgabeformat rendern und gängige Fallstricke behandeln. Am Ende können Sie **groupdocs viewer java** in Ihre Java‑Anwendungen integrieren, um **java convert vector graphics** schnell und zuverlässig durchzuführen.

## Schnelle Antworten
- **In welche Formate können WMZ/WMF konvertiert werden?** HTML, JPG, PNG und PDF werden vollständig unterstützt.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; eine kommerzielle Lizenz entfernt Evaluationsbeschränkungen.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher wird empfohlen.  
- **Kann ich nur bestimmte Seiten rendern?** Ja, Sie können Seitenbereiche in den View‑Optionen angeben.  
- **Ist der Speicherverbrauch bei großen Dateien ein Problem?** Verwenden Sie try‑with‑resources und rendern Sie nur benötigte Seiten, um den Speicherverbrauch gering zu halten.

## Was bedeutet „convert WMZ to PDF“?
Das Konvertieren von WMZ zu PDF bedeutet, die vektorbasierte WMZ‑Datei zu rasterisieren (oder ihre Vektordaten) in einem PDF‑Container zu speichern. PDF ist universell anzeigbar, durchsuchbar und druckbar, was es ideal für die Archivierung und Weitergabe von WMZ‑Grafiken macht.

## Warum GroupDocs Viewer für Java zum Konvertieren von Vektorgrafiken verwenden?
- **Hohe Treue**: Die Bibliothek bewahrt die ursprüngliche Zeichenqualität, egal ob Sie nach PDF oder PNG ausgeben.  
- **Keine externen Abhängigkeiten**: Keine nativen Windows‑Bibliotheken nötig; alles läuft auf jeder Plattform mit einem JDK.  
- **Einfache API**: Eine `Viewer`‑Instanz und ein einzelner `view`‑Aufruf erledigen die gesamte Konvertierung.  
- **Skalierbar**: Funktioniert gleichermaßen gut für einseitige Icons und mehrseitige technische Zeichnungen.

## Voraussetzungen

### Erforderliche Bibliotheken
- **GroupDocs.Viewer for Java** – die Kern‑Rendering‑Engine.  
- Java Development Kit (JDK) 8+.

### Umgebung einrichten
- IDE wie IntelliJ IDEA oder Eclipse.  
- Maven für das Abhängigkeits‑Management (oder Gradle, falls bevorzugt).

### Wissensvoraussetzungen
- Vertrautheit mit Java‑Datei‑I/O (`java.nio.file.Path`).  
- Grundlegendes Verständnis davon, wie Dokumenten‑Viewer Inhalte rendern.

## Einrichtung von GroupDocs.Viewer für Java

Fügen Sie das Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu:

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

> **Lizenz‑Hinweis:** Verwenden Sie eine kostenlose Testversion für die Evaluierung und wenden Sie anschließend eine temporäre oder gekaufte Lizenz an, um die volle Funktionalität freizuschalten.

Sobald die Abhängigkeit aufgelöst ist, können Sie eine `Viewer`‑Instanz erstellen, die für jeden Konvertierungsschritt wiederverwendet wird.

## Implementierungsleitfaden

Wir gehen vier Konvertierungsszenarien durch: HTML, JPG, PNG und PDF. Jeder Beispielcode folgt demselben Muster – definieren Sie einen Ausgabepfad, instanziieren Sie `Viewer` mit der Quell‑WMZ‑Datei, konfigurieren Sie die passenden View‑Optionen und rufen Sie `view` auf.

### Rendern von WMZ/WMF zu HTML

#### Übersicht
HTML‑Ausgabe ermöglicht das direkte Einbetten der Grafik in Webseiten, wobei alle Ressourcen (Bilder, CSS) in einer einzigen Datei enthalten sind.

**Schritt 1: Ausgabeverzeichnis-Pfad festlegen**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Schritt 2: Viewer initialisieren und nach HTML rendern**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendern von WMZ/WMF zu JPG

#### Übersicht
JPG ist ein weit verbreitetes Rasterformat, ideal für schnelle Vorschauen oder E‑Mail‑Anhänge.

**Schritt 1: Ausgabeverzeichnis-Pfad festlegen**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Schritt 2: Viewer initialisieren und nach JPG rendern**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendern von WMZ/WMF zu PNG

#### Übersicht
PNG unterstützt Transparenz und ist damit ideal für Grafiken, die sich in unterschiedliche Hintergründe einfügen sollen.

**Schritt 1: Ausgabeverzeichnis-Pfad festlegen**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Schritt 2: Viewer initialisieren und nach PNG rendern**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendern von WMZ/WMF zu PDF

#### Übersicht
PDF liefert ein plattformunabhängiges, durchsuchbares Dokument, das das ursprüngliche Layout beibehält.

**Schritt 1: Ausgabeverzeichnis-Pfad festlegen**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Schritt 2: Viewer initialisieren und nach PDF rendern**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|----------|
| **OutOfMemoryError** bei großen WMZ‑Dateien | Viewer lädt das gesamte Dokument in den Speicher | Rendern Sie Seite für Seite mit `PageStreamViewOptions` oder erhöhen Sie den JVM‑Heap (`-Xmx`). |
| **Fehlende Schriftarten** im PDF | Schriftart nicht im Quell‑WMZ eingebettet | Installieren Sie die benötigten Schriftarten auf dem Host‑System oder verwenden Sie `FontSettings`, um benutzerdefinierte Schriftarten bereitzustellen. |
| **Leere PNG‑Ausgabe** | Falscher Ausgabepfad oder unzureichende Schreibrechte | Stellen Sie sicher, dass `outputDirectory` existiert und die Anwendung Schreibzugriff hat. |
| **HTML‑Ressourcen werden nicht geladen** | Verwendung von `forExternalResources` ohne Kopieren der Dateien | Verwenden Sie `forEmbeddedResources` für eine eigenständige HTML‑Datei. |

## Häufig gestellte Fragen

**F: Kann ich WMF zu PNG mit demselben Code konvertieren?**  
A: Ja. Das PNG‑Beispiel funktioniert für sowohl WMZ‑ als auch WMF‑Dateien; ersetzen Sie einfach `TestFiles.SAMPLE_WMZ` durch Ihre WMF‑Quelle.

**F: Ist es möglich, nur einen Teil der Seiten zu konvertieren?**  
A: Absolut. Nutzen Sie `PdfViewOptions` (bzw. die entsprechenden Optionen für andere Formate) und rufen Sie `setPageNumbers(List<Integer>)` vor dem Rendern auf.

**F: Benötige ich für jedes Ausgabeformat eine separate Lizenz?**  
A: Nein. Eine einzelne GroupDocs Viewer‑Lizenz deckt alle unterstützten Formate ab, einschließlich HTML, JPG, PNG und PDF.

**F: Wie wirkt sich „java convert vector graphics“ auf die Performance aus?**  
A: Die Vektor‑zu‑Raster‑Konvertierung ist CPU‑intensiv. Für große Stapel sollten Sie Multithreading in Betracht ziehen und eine einzige `Viewer`‑Instanz über mehrere Dateien hinweg wiederverwenden.

**F: Behält das PDF die Vektor‑Qualität bei oder wird es gerastert?**  
A: Beim Konvertieren von WMZ/WMF zu PDF bewahrt GroupDocs Viewer nach Möglichkeit die Vektor‑Anweisungen, sodass ein skalierbares PDF entsteht.

## Fazit

Sie haben nun eine vollständige, produktionsreife Anleitung, um **WMZ in PDF** und andere gängige Formate mit **GroupDocs Viewer für Java** zu konvertieren. Egal, ob Sie einen Web‑Service bauen, der Grafiken on‑the‑fly bereitstellt, oder ein Archivierungs‑Tool, das Dokumente als PDFs speichert – die obigen Schritte helfen Ihnen, schnell ans Ziel zu kommen.

---

**Zuletzt aktualisiert:** 2026-02-18  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs  

---