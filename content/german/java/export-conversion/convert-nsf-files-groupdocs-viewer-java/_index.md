---
date: '2026-05-26'
description: Erfahren Sie, wie Sie nsf in pdf und andere Formate (HTML, JPG, PNG)
  mit GroupDocs.Viewer für Java konvertieren. Schritt-für-Schritt-Anleitung mit Best-Practice-Tipps.
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: nsf in pdf konvertieren mit GroupDocs.Viewer für Java
type: docs
url: /de/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# NSF-Dateien in mehrere Formate konvertieren mit GroupDocs.Viewer für Java

In diesem umfassenden Leitfaden erfahren Sie **wie man nsf in pdf konvertiert** und rendern NSF‑Dateien zu HTML, JPG und PNG mit GroupDocs.Viewer für Java. Egal, ob Sie Lotus Notes‑Datenbanken archivieren, sie in einem Browser anzeigen oder Bildvorschauen erzeugen müssen – dieses Tutorial führt Sie durch alles – von der Umgebungseinrichtung bis zu Code‑Details – sodass Sie die Konvertierung in wenigen Minuten implementieren können.

![NSF-Dateien in HTML, JPG, PNG und PDF mit GroupDocs.Viewer für Java konvertieren](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[NSF-Dateien in HTML, JPG, PNG und PDF mit GroupDocs.Viewer für Java konvertieren](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## Schnelle Antworten
- **Was ist der Hauptanwendungsfall?** Rendering von NSF‑Dateien zu PDF, HTML, JPG oder PNG für Web, Archivierung oder Freigabe.  
- **Welche Bibliothek übernimmt die Konvertierung?** GroupDocs.Viewer für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für die Produktion ist eine Volllizenz erforderlich.  
- **Welche Java-Version wird benötigt?** JDK 8 oder höher.  
- **Kann ich mehrere NSF-Dateien stapelweise verarbeiten?** Ja – wickeln Sie die Rendering‑Logik in einer Schleife ein und verwalten Sie Ressourcen mit try‑with‑resources.

## Was bedeutet „convert nsf to pdf“?

Das Konvertieren einer NSF‑Datei (Lotus Notes‑Datenbank) in PDF erzeugt ein statisches, universell lesbares Dokument, das das ursprüngliche Layout, die Schriftarten und Grafiken bewahrt, ohne dass der Notes‑Client benötigt wird. Dieses Format ist ideal für rechtliche Archivierung, sichere Verteilung und langfristige Aufbewahrung, da PDF‑Dateien auf jedem Betriebssystem oder Gerät geöffnet werden können.

## Warum NSF in PDF und andere Formate konvertieren?

Die Umwandlung von NSF‑Dateien in PDF, HTML, JPG oder PNG ermöglicht universellen Zugriff, bewahrt die visuelle Treue und erlaubt nahtlose Integration in moderne Web‑ und Mobile‑Anwendungen. PDF erhält das exakte Seitenlayout, HTML bietet sofortiges Browsing, und JPG/PNG liefern hochauflösende Bildausschnitte für Thumbnails oder Einbettungen.

## Voraussetzungen

- **Java Development Kit (JDK) 8+** – JDK 11 oder neuer wird für bessere Garbage‑Collection‑Leistung empfohlen.  
- **Maven** – für das Abhängigkeitsmanagement.  
- **GroupDocs.Viewer für Java** – Test‑ oder Lizenzversion.  
- Grundlegende Kenntnisse in Java‑Datei‑I/O und Maven‑Projektstruktur.

## Einrichtung von GroupDocs.Viewer für Java

### Maven-Konfiguration

Fügen Sie die GroupDocs.Viewer‑Abhängigkeit zu Ihrer `pom.xml` hinzu. Dadurch werden alle erforderlichen Binärdateien und transitiven Bibliotheken eingebunden.

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

Um die volle Funktionalität freizuschalten, können Sie:

- **Kostenlose Testversion:** Kernfunktionen ohne Lizenzschlüssel evaluieren.  
- **Temporäre Lizenz:** Einen zeitlich begrenzten Schlüssel für Tests anfordern.  
- **Vollkauf:** Eine Produktionslizenz für unbegrenzte Nutzung erhalten.

### Grundlegende Initialisierung

`Viewer` ist die Kernklasse, die Dokumente in das gewünschte Ausgabeformat rendert. Initialisieren Sie sie mit Ihrer Lizenz und dem Dateipfad innerhalb eines try‑with‑resources‑Blocks, um eine ordnungsgemäße Freigabe sicherzustellen.

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## Wie man NSF in PDF konvertiert

Um ein NSF‑Dokument in PDF zu konvertieren, erstellen Sie zunächst eine `Viewer`‑Instanz, die auf die Quelldatei zeigt. Konfigurieren Sie anschließend `PdfViewOptions`, um Ausgabeeigenschaften wie Seitengröße, Komprimierungsgrad und das Einbetten von Schriftarten festzulegen. Rufen Sie schließlich `viewer.view(pdfOptions)` auf, wodurch das gesamte Dokument in eine einzelne PDF‑Datei gerendert wird, die bereit zur Verteilung ist.

`PdfViewOptions` definiert PDF‑spezifische Einstellungen wie Seitengröße und Komprimierung.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## NSF in HTML rendern

### Übersicht

Konvertieren Sie NSF‑Dokumente in eigenständige HTML‑Seiten, die Bilder und CSS einbetten, um eine genaue Bildschirmanzeige zu gewährleisten.

### Schritt‑für‑Schritt‑Anleitung

#### 1. Ausgabeverzeichnis und Dateipfad einrichten

Definieren Sie den Ordner, in dem die HTML‑Dateien gespeichert werden.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. Load‑Optionen konfigurieren

`LoadOptions` ermöglicht das Feintuning des Ressourcen‑Ladens, z. B. das Setzen eines Time‑outs für externe Assets.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. Viewer initialisieren und rendern

`Viewer` verarbeitet das NSF und schreibt HTML‑Dateien in das Zielverzeichnis.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## NSF in JPG rendern

### Übersicht

Erzeugen Sie hochwertige JPG‑Bilder aus jeder Seite eines NSF‑Dokuments, nützlich für Vorschaubilder oder die Einbindung in bildzentrierte Workflows.

#### 1. Ausgabepfad festlegen

Geben Sie ein Namensmuster wie `output_page_{0}.jpg` an, wobei `{0}` die Seitenzahl ist.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. Konfigurieren und rendern

`JpgViewOptions` definiert Einstellungen für die JPEG‑Bildausgabe, einschließlich Auflösung und Qualität. Erstellen Sie `JpgViewOptions`, setzen Sie die gewünschte DPI und rufen Sie `viewer.view(options)` auf.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## NSF in PNG rendern

### Übersicht

Erzeugen Sie verlustfreie PNG‑Bilder, die jedes Detail der ursprünglichen NSF‑Seiten beibehalten.

#### 1. Ausgabepfad festlegen

Verwenden Sie eine Vorlage wie `nsf_page_{0}.png` für die automatische Seitennummerierung.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. Dokument rendern

`PngViewOptions` konfiguriert PNG‑Ausgabeparameter wie Auflösung und Farbtiefe. Konfigurieren Sie `PngViewOptions` (z. B. `setResolution(300)`) und rendern Sie.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## Praktische Anwendungen

1. **Webbasierte Dokumentenfreigabe:** NSF in HTML konvertieren für sofortiges Anzeigen im Browser ohne Installation von Notes.  
2. **Bildarchivierung:** Seitenweise JPG/PNG‑Schnappschüsse für Thumbnail‑Galerien oder OCR‑Pipelines speichern.  
3. **Universeller Zugriff:** PDF‑Konvertierung verwenden, um eine einzelne, sichere Datei bereitzustellen, die auf jedem Gerät geöffnet werden kann und Compliance‑Anforderungen erfüllt.

## Leistungsüberlegungen

- **Ressourcen‑Laden:** `setResourceLoadingTimeout` basierend auf Netzwerk‑Latenz anpassen, um Verzögerungen zu vermeiden.  
- **Speicherverwaltung:** try‑with‑resources für `Viewer`‑Instanzen verwenden; dies gibt native Ressourcen automatisch frei.  
- **Stapelverarbeitung:** Für große Stapel Dateien sequenziell oder in parallelen Streams verarbeiten, den Heap‑Verbrauch überwachen, um unter den Speichergrenzen der JVM zu bleiben.

## FAQ‑Abschnitt

**Was ist das beste Format für die Konvertierung von NSF‑Dokumenten?**  
- Es hängt vom nachgelagerten Verwendungszweck ab: HTML für Webportale, PDF für universelle Verteilung, JPG/PNG für bildbasierte Workflows.

**Wie gehe ich effizient mit großen NSF‑Dateien um?**  
- `LoadOptions` anpassen (z. B. `setResourceLoadingTimeout` erhöhen), Dateien in kleineren Batches verarbeiten und nach Möglichkeit eine einzelne `Viewer`‑Instanz wiederverwenden.

**Kann ich die Ausgabequalität in Bildformaten anpassen?**  
- Ja. DPI, Komprimierungsgrad und Farbtiefe über `JpgViewOptions` bzw. `PngViewOptions` vor dem Rendern festlegen.

**Was tun, wenn die Konvertierung fehlschlägt?**  
- Dateipfade prüfen, sicherstellen, dass die NSF‑Datei nicht beschädigt ist, und die GroupDocs.Viewer‑Logs für detaillierte Fehlermeldungen konsultieren. Ein Update auf die neueste Bibliotheksversion löst häufig Kompatibilitätsprobleme.

**Wird Stapelkonvertierung unterstützt?**  
- Absolut. Wickeln Sie die Rendering‑Logik in eine `for`‑Schleife oder einen Java‑Stream, um mehrere NSF‑Dateien automatisch zu verarbeiten.

## Häufig gestellte Fragen

**Q: Wie konvertiere ich eine NSF‑Datei in PDF, ohne Anmerkungen zu verlieren?**  
A: `PdfViewOptions` bewahrt die meisten Anmerkungen automatisch; rendern Sie das Dokument einfach mit diesen Optionen, und das resultierende PDF spiegelt das ursprüngliche Layout wider.

**Q: Kann ich passwortgeschützte NSF‑Dateien konvertieren?**  
A: Ja. Geben Sie Anmeldeinformationen über `LoadOptions` an, bevor Sie die `Viewer`‑Instanz erstellen.

**Q: Welche Java-Version bietet die beste Leistung?**  
A: JDK 11 oder neuer bietet verbesserte Garbage‑Collection und Parallelität, was Stapelkonvertierungen beschleunigt.

**Q: Ist es möglich, eine benutzerdefinierte DPI für JPG/PNG‑Ausgabe festzulegen?**  
A: Konfigurieren Sie `JpgViewOptions.setResolution(int dpi)` bzw. `PngViewOptions.setResolution(int dpi)` vor dem Aufruf von `viewer.view(options)`.

**Q: Unterstützt GroupDocs.Viewer das direkte Streaming der Ausgabe in eine HTTP‑Antwort?**  
A: Ja. Verwenden Sie die `Stream`‑Überladung der View‑Optionen, um das Ergebnis direkt in `HttpServletResponse.getOutputStream()` zu schreiben.

## Fazit

Sie verfügen nun über eine umfassende Roadmap für **convert nsf to pdf** und das Rendern von NSF‑Dateien zu HTML, JPG und PNG mit GroupDocs.Viewer für Java. Durch Befolgen der obigen Schritte können Sie robuste Dokumentkonvertierung in jede Java‑Anwendung integrieren, Batch‑Jobs automatisieren und Inhalte im Format bereitstellen, das am besten zu den Bedürfnissen Ihrer Nutzer passt. Erkunden Sie weitere Viewer‑Funktionen wie Wasserzeichen, benutzerdefinierte Schriftarten und Mehrseitigkeit, um Ihre Lösung weiter zu bereichern.

---

**Zuletzt aktualisiert:** 2026-05-26  
**Getestet mit:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs

## Verwandte Tutorials

- [groupdocs viewer java: Dokumente in PDF konvertieren – Komplettanleitung](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – ODF in HTML, JPG, PNG, PDF mit GroupDocs.Viewer für Java konvertieren](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [PST in HTML, JPG, PNG, PDF mit GroupDocs.Viewer für Java konvertieren](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)