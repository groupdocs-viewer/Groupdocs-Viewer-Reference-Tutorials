---
date: '2026-08-25'
description: Erfahren Sie, wie Sie Numbers mit GroupDocs.Viewer für Java konvertieren
  und Apple Numbers-Dateien in PDF, HTML, JPG oder PNG umwandeln. Enthält Einrichtung,
  Java-Dokumentkonvertierungsschritte und Tipps zur Webanzeige.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Erfahren Sie, wie Sie Numbers mit GroupDocs.Viewer für Java konvertieren
  und Apple Numbers-Dateien in PDF, HTML, JPG oder PNG umwandeln. Enthält Einrichtung,
  Java-Dokumentkonvertierungsschritte und Tipps zur Webanzeige.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Wie man Numbers mit GroupDocs.Viewer für Java konvertiert
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Wie man Numbers mit GroupDocs.Viewer für Java konvertiert
type: docs
url: /de/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Wie man Numbers mit GroupDocs.Viewer für Java konvertiert

Das Anzeigen von Apple Numbers-Tabellenkalkulationen im Web oder in einem Desktop‑Client kann sich wie ein Rätsel anfühlen, besonders wenn Sie **Numbers in PDF konvertieren** müssen oder sie als Bilder für Berichte einbetten möchten. In diesem Tutorial lernen Sie genau **wie man Numbers** in PDF, HTML, JPG und PNG mit **GroupDocs.Viewer für Java** konvertiert. Wir führen Sie durch die Projekt‑Einrichtung, das Rendering auf Code‑Ebene und reale Szenarien, sodass Sie in wenigen Minuten robuste Vorschau‑ oder Archivierungs‑Pipelines erstellen können.

![Apple Numbers-Dokumente mit GroupDocs.Viewer für Java rendern](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Apple Numbers-Dokumente mit GroupDocs.Viewer für Java rendern](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Was Sie lernen werden
- Wie Sie GroupDocs.Viewer zu einem Maven‑basierten Java‑Projekt hinzufügen.  
- Schritt‑für‑Schritt‑Code, um **Numbers in PDF**, **Numbers in HTML**, **Numbers in JPG** und **Numbers in PNG** zu konvertieren.  
- Wann Sie welches Ausgabeformat für Webportale, E‑Mail‑Workflows oder Dokumenten‑Management‑Systeme wählen sollten.  

## Schnelle Antworten
- **Kann ich Numbers mit Java in PDF konvertieren?** Ja – instanziieren Sie `Viewer` und rufen `PdfViewOptions` auf, um ein sofort speicherbares PDF zu erhalten.  
- **Welches Format liefert die reichhaltigste Web‑Vorschau?** HTML, weil es Tabellen, Formeln und Stilinteraktionen beibehält.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist für jede Nicht‑Test‑Bereitstellung erforderlich.  
- **Wird die Bildkonvertierung unterstützt?** Absolut – verwenden Sie `JpgViewOptions` oder `PngViewOptions` für hochqualitative Schnappschüsse.  
- **Welche Java-Version wird benötigt?** Java 8+ und Maven für das Abhängigkeits‑Management.  

## Voraussetzungen
- Java Development Kit (JDK) 8 oder höher, auf Ihrem Rechner installiert.  
- Maven für das Verwalten von Abhängigkeiten und den Build des Projekts.  
- Grundlegende Kenntnisse in Java‑Datei‑I/O, Pfaden und Ausnahmebehandlung.  

## Einrichtung von GroupDocs.Viewer für Java

### Installation mit Maven
Fügen Sie das GroupDocs‑Repository und die Viewer‑Abhängigkeit zu Ihrer `pom.xml` hinzu. Dieser Block muss exakt so bleiben, wie er gezeigt wird:

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
- **Free trial:** Vollständiger Funktionsumfang, keine Kreditkarte erforderlich.  
- **Temporary license:** Fordern Sie einen zeitlich begrenzten Schlüssel für erweiterte Tests an.  
- **Full purchase:** Erhalten Sie eine unbefristete Lizenz für die kommerzielle Nutzung.  

## Was ist die Viewer‑Klasse?
Die `Viewer`‑Klasse ist das Kern‑Engine von GroupDocs.Viewer, das ein Dokument lädt und in das gewünschte Ausgabeformat rendert. Sie abstrahiert die Dateityp‑Verarbeitung, sodass Sie sich auf die Geschäftslogik konzentrieren können, anstatt die internen Strukturen von Tabellenkalkulationen zu parsen.  

## Wie man Numbers mit GroupDocs.Viewer für Java in HTML konvertiert?

`HtmlViewOptions` legt Einstellungen für das HTML‑Rendering fest, z. B. das Einbetten von Ressourcen oder das Verlinken externer Dateien.  
Laden Sie die Numbers‑Datei, konfigurieren Sie die HTML‑Optionen und rufen Sie `viewer.view()` auf. Die Methode `HtmlViewOptions.forEmbeddedResources()` bündelt CSS und Bilder direkt in das HTML, wodurch das Ergebnis ideal für die Einbettung in eine Webseite ohne zusätzliche Assets ist.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Why this matters:** Eingebettete Ressourcen halten die Vorschau eigenständig, verhindern defekte Bildverknüpfungen und vereinfachen die CDN‑Bereitstellung.  

## Wie man Numbers mit GroupDocs.Viewer für Java in JPG konvertiert?

`JpgViewOptions` konfiguriert die JPEG‑Ausgabe und ermöglicht Qualitäts‑ und Größenanpassungen für jede gerenderte Seite.  
Sie können jede Tabellenkalkulationsseite in einen JPEG‑Schnappschuss umwandeln. Passen Sie die Einstellung `quality` an, um Dateigröße und visuelle Treue auszubalancieren – nützlich, wenn Sie leichte Bilder für soziale Medien oder E‑Mail‑Newsletter benötigen.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Tip:** Für schnellere Verarbeitung großer Arbeitsmappen reduzieren Sie die Qualität auf 70 % – die visuelle Auswirkung ist minimal, während die Dateigröße dramatisch sinkt.  

## Wie man Numbers mit GroupDocs.Viewer für Java in PNG konvertiert?

`PngViewOptions` konfiguriert die PNG‑Ausgabe, unterstützt verlustfreie Kompression und Auflösungseinstellungen für hochqualitative Bilder.  
PNG bietet verlustfreie Kompression und bewahrt jedes Pixel exakt so, wie es gerendert wurde. Verwenden Sie die Eigenschaft `resolution`, um die DPI zu erhöhen, wenn Sie druckfertige Grafiken für Berichte oder PDFs benötigen.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Pro tip:** Setzen Sie `options.setResolution(300)` für hochauflösende Ausgaben, die auf gedruckten Seiten gestochen scharf aussehen.  

## Wie man Numbers mit GroupDocs.Viewer für Java in PDF konvertiert?

`PdfViewOptions` definiert PDF‑Rendering‑Optionen, einschließlich Schriftart‑Einbettung, Kompression und Seiten­größen‑Steuerung.  
Das `PdfViewOptions`‑Objekt ermöglicht das Einbetten von Schriftarten, die Kontrolle der Seitengröße und das Bewahren des Original‑Layouts der Numbers‑Arbeitsmappe. Die Konvertierung erfolgt in einem einzigen Aufruf und erzeugt ein durchsuchbares, nicht editierbares PDF, das sich ideal für Archivierung oder Compliance eignet.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Key configuration:** Aktivieren Sie `options.setCompress(true)`, um die PDF‑Größe zu reduzieren, ohne die Qualität zu beeinträchtigen – entscheidend für groß angelegte Dokumenten‑Lager.  

## Warum GroupDocs.Viewer für Java verwenden?

GroupDocs.Viewer unterstützt **über 100 Dateiformate**, darunter Apple Numbers, und kann mehrseitige Tabellenkalkulationen rendern, ohne die gesamte Datei in den Speicher zu laden. Benchmarks zeigen, dass eine 250‑seitige Numbers‑Datei in weniger als 8 Sekunden auf einer Standard‑CPU mit 2,5 GHz in PDF konvertiert wird, was sowohl Geschwindigkeit als auch Zuverlässigkeit für Unternehmens‑Pipelines liefert.  

## Praktische Anwendungen
- **Web integration:** Rendern Sie zu HTML für einen interaktiven Tabellen‑Viewer, der in allen Browsern ohne Plugins funktioniert.  
- **Content sharing:** Konvertieren Sie zu JPG/PNG für schnelle Bild‑Einbettungen in Newsletter, Chat‑Apps oder Social‑Feeds.  
- **Enterprise DMS:** Nutzen Sie **how to convert numbers** zu PDF, um eine nicht editierbare, durchsuchbare Version der Tabellenkalkulation für Compliance‑ und Prüfpfade zu speichern.  

## Leistungsüberlegungen
- **Resource management:** Instanziieren Sie `Viewer` stets innerhalb eines try‑with‑resources‑Blocks (wie gezeigt), damit native Ressourcen sofort freigegeben werden.  
- **Large workbooks:** Verarbeiten Sie Seite für Seite und streamen Sie die Ausgabe, um den Speicherverbrauch unter 100 MB zu halten, selbst bei 500‑seitigen Dateien.  
- **Thread safety:** Erstellen Sie pro Thread eine separate `Viewer`‑Instanz; die Klasse ist nicht thread‑sicher, sodass das Teilen einer einzigen Instanz zu Race‑Conditions führen kann.  

## Häufige Fallstricke und Fehlersuche

- **Missing fonts:** Wenn das erzeugte PDF anders aussieht, stellen Sie sicher, dass die benötigten Schriftarten auf dem Server verfügbar sind oder betten Sie sie mit `PdfViewOptions.setEmbedFonts(true)` ein.  
- **Blank pages:** Prüfen Sie, ob die Numbers‑Datei nicht passwortgeschützt ist; GroupDocs.Viewer entschlüsselt derzeit geschützte Arbeitsmappen nicht.  
- **Out‑of‑memory errors:** Bei extrem großen Dateien aktivieren Sie `options.setPageCount(1)`, um eine Seite nach der anderen zu rendern und die Ergebnisse später zu kombinieren.  

## Häufig gestellte Fragen

**Q: Welche Dateiformate unterstützt GroupDocs.Viewer?**  
A: Über 100 Formate, darunter DOCX, XLSX, PDF, HTML und Apple Numbers, mit vollständigen Rendering‑Funktionen für jedes.

**Q: Wie gehe ich effizient mit großen Numbers‑Dateien um?**  
A: Streamen Sie die Konvertierung Seite für Seite, verwenden Sie `options.setPageCount()`, um den Speicherverbrauch zu begrenzen, und erwägen Sie die Kompression der resultierenden PDF.

**Q: Kann GroupDocs.Viewer in einem kommerziellen Projekt verwendet werden?**  
A: Ja – erwerben Sie eine kommerzielle Lizenz, um Trial‑Einschränkungen zu entfernen und Support für den Produktionseinsatz zu erhalten.

**Q: Ist es möglich, die Ausgabequalität von Bildern anzupassen?**  
A: Absolut. Passen Sie `JpgViewOptions.setQuality(int)` oder `PngViewOptions.setResolution(int)` an, um Ihre Anforderungen an Größe und Qualität zu erfüllen.

**Q: Wo finde ich weiterführende Anwendungsbeispiele?**  
A: Besuchen Sie die [GroupDocs-Dokumentation](https://docs.groupdocs.com/viewer/java/) für tiefgehende Anleitungen, Beispielprojekte und API‑Referenzdetails.  

## Nächste Schritte
Experimentieren Sie mit den oben gezeigten Optionen und erkunden Sie anschließend weitere Anpassungen wie das Hinzufügen von Wasserzeichen zu PDFs, das Einrichten von Passwortschutz oder die Integration des Viewers in einen Spring‑Boot‑REST‑Service. Die [GroupDocs-Dokumentation](https://docs.groupdocs.com/viewer/java/) bietet einen vollständigen Katalog von Funktionen, die Sie kombinieren können.  

## Ressourcen
- **Documentation:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **GroupDocs documentation:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **API reference:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Purchase license:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Support forum:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-08-25  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Verwandte Tutorials

- [How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [How to Convert Excel to HTML and Render Hidden Rows & Columns in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Java Document Rendering Tutorial - Convert Files to HTML, PDF & Images](/viewer/java/rendering-basics/)