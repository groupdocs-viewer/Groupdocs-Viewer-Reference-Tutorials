---
date: '2026-03-05'
description: Erfahren Sie, wie Sie Zahlen mit GroupDocs.Viewer für Java in PDF und
  andere Formate wie HTML, JPG, PNG konvertieren. Dieser Leitfaden behandelt die Einrichtung,
  Rendering‑Techniken und praktische Anwendungen.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: Numbers in PDF konvertieren mit GroupDocs.Viewer für Java
type: docs
url: /de/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Numbers in PDF (und andere Formate) konvertieren mit GroupDocs.Viewer für Java

Apple Numbers-Dokumente im Web oder in Desktop-Anwendungen anzuzeigen kann knifflig sein, besonders wenn Sie **Numbers in PDF konvertieren** oder sie als Bilder einbetten müssen. In diesem Tutorial zeigen wir, wie Sie **GroupDocs.Viewer für Java** verwenden, um Numbers-Dateien in HTML, JPG, PNG und **PDF** zu rendern – und Ihnen flexible Optionen zum Teilen, Vorschauen oder Archivieren Ihrer Tabellenkalkulationen bieten.

![Apple Numbers-Dokumente mit GroupDocs.Viewer für Java rendern](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Was Sie lernen werden
- Wie man GroupDocs.Viewer in einem Maven‑basierten Java-Projekt einrichtet  
- Schritt‑für‑Schritt‑Code, um **Numbers in PDF konvertieren**, **Numbers in HTML konvertieren** und **Numbers in JPG konvertieren**  
- Praxisnahe Szenarien, in denen die Dokumentkonvertierung Webportalen, E‑Mail‑Workflows und DMS‑Integrationen Mehrwert verleiht  

## Schnelle Antworten
- **Kann ich Numbers mit Java in PDF konvertieren?** Ja, mit `PdfViewOptions` in GroupDocs.Viewer.  
- **Welches Format ist am besten für die Webvorschau?** HTML bietet das interaktivste Erlebnis.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine kommerzielle Lizenz ist für Nicht‑Test‑Einsätze erforderlich.  
- **Wird die Bildkonvertierung unterstützt?** Absolut – verwenden Sie `JpgViewOptions` oder `PngViewOptions`, um hochwertige Bilder zu erhalten.  
- **Welche Java-Version wird benötigt?** Java 8+ und Maven für das Abhängigkeitsmanagement.  

## Voraussetzungen
- Java Development Kit (JDK) 8 oder höher installiert.  
- Maven zur Verwaltung der Abhängigkeiten.  
- Grundlegende Kenntnisse von Java-Datei‑I/O und Pfaden.  

## GroupDocs.Viewer für Java einrichten

### Installation mit Maven
Fügen Sie das Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu. Dieser Block muss exakt wie gezeigt bleiben:

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
- **Free Trial:** Alle Funktionen kostenlos testen.  
- **Temporary License:** Einen zeitlich begrenzten Schlüssel für erweitertes Testen anfordern.  
- **Purchase:** Eine Voll‑Lizenz für kommerzielle Projekte erwerben.  

## Numbers-Dokument in HTML rendern  
*Anwendungsfall: Eine Tabelle direkt in eine Webseite einbetten.*

### Schritt 1: Viewer initialisieren und HTML-Optionen konfigurieren
Unten finden Sie den genauen Code, den Sie ausführen. Die Kommentare erklären jede Zeile, aber **ändern Sie den Codeblock nicht**.

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

- **Warum das wichtig ist:** `HtmlViewOptions.forEmbeddedResources()` bündelt CSS und Bilder in das HTML, was es perfekt für schnelle Webvorschauen macht.

## Numbers-Dokument zu JPG rendern  
*Ideal zum Teilen eines Schnappschusses einer Tabelle in sozialen Medien oder per E‑Mail.*

### Schritt 1: Viewer einrichten und JPG-Optionen konfigurieren
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

- **Tipp:** Passen Sie die Bildqualität über `options.setQuality(int)` an, wenn Sie kleinere Dateien benötigen.

## Numbers-Dokument zu PNG rendern  
*Ideal, wenn Sie ein verlustfreies, hochauflösendes Bild für Berichte benötigen.*

### Schritt 1: PNG-Optionen initialisieren und konfigurieren
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

- **Pro‑Tipp:** Verwenden Sie `options.setResolution(int)`, um die DPI für druckfertige Bilder zu steuern.

## Numbers-Dokument zu PDF rendern  
*Das Hauptziel vieler Entwickler: **Numbers in PDF konvertieren** zum Archivieren oder Verteilen.*

### Schritt 1: Viewer für PDF-Konvertierung einrichten
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

- **Wichtige Konfiguration:** `PdfViewOptions` ermöglicht das Einbetten von Schriftarten und die Steuerung der Seitengröße, sodass die Ausgabe Ihren Markenanforderungen entspricht.

## Praktische Anwendungen
- **Web‑Integration:** In HTML rendern für einen interaktiven Tabellenkalkulations‑Viewer auf Ihrer Seite.  
- **Content Sharing:** In JPG/PNG konvertieren für schnelle Bildeinbettungen in Newslettern oder Chats.  
- **Enterprise DMS:** **Numbers in PDF konvertieren**, um eine nicht editierbare, durchsuchbare Version der Tabelle zu speichern.  

## Leistungsüberlegungen
- **Ressourcenverwaltung:** Schließen Sie den `Viewer` immer in einem try‑with‑resources‑Block (wie gezeigt), um native Ressourcen sofort freizugeben.  
- **Große Dateien:** Bei sehr großen Numbers‑Dateien sollten Sie die Verarbeitung seitenweise durchführen und Ergebnisse streamen, um hohen Speicherverbrauch zu vermeiden.  
- **Thread‑Sicherheit:** Erstellen Sie für jeden Thread eine separate `Viewer`‑Instanz; die Klasse ist nicht thread‑sicher.

## Fazit
Sie verfügen jetzt über ein vollständiges Werkzeugset für **Numbers in PDF konvertieren**, sowie für HTML, JPG und PNG, mit GroupDocs.Viewer für Java. Diese Möglichkeiten ermöglichen den Aufbau flexibler Dokumenten‑Pipelines – egal, ob Sie ein Web‑Portal versorgen, Berichte erstellen oder Tabellenkalkulationen archivieren.

### Nächste Schritte
Erkunden Sie weitere Anpassungsoptionen in der [GroupDocs-Dokumentation](https://docs.groupdocs.com/viewer/java/) und experimentieren Sie mit der Integration dieser Funktionen in Ihre eigenen Anwendungen.

## FAQ-Bereich

**Q1: Welche Dateiformate unterstützt GroupDocs.Viewer?**  
A1: Es unterstützt eine breite Palette von Dokumentformaten, darunter DOCX, XLSX, PDF und weitere.

**Q2: Wie gehe ich effizient mit großen Numbers‑Dateien um?**  
A2: Nutzen Sie Java‑Speicherverwaltungstechniken und optimieren Sie Ihren Code, um große Dateigrößen effektiv zu verarbeiten.

**Q3: Kann GroupDocs.Viewer in einem kommerziellen Projekt verwendet werden?**  
A4: Ja, Sie müssen jedoch eine Lizenz für die kommerzielle Nutzung erwerben.

**Q4: Ist es möglich, die Ausgabequalität von Bildern anzupassen?**  
A5: Absolut. Sie können die Einstellungen in `JpgViewOptions` und `PngViewOptions` anpassen.

**Q5: Wo finde ich weiterführende Anwendungsbeispiele?**  
A5: Besuchen Sie die [API‑Referenz](https://reference.groupdocs.com/viewer/java/) für ausführliche Dokumentation.

## Häufig gestellte Fragen

**Q: Wie konvertiere ich eine Numbers‑Datei in PDF, ohne das Layout zu verlieren?**  
A: Verwenden Sie `PdfViewOptions` wie oben gezeigt; der Viewer bewahrt Layout, Schriftarten und Zellstile automatisch.

**Q: Kann ich eine Tabellenkalkulation in einem einzigen Aufruf in ein Bild konvertieren?**  
A: Ja, `JpgViewOptions` oder `PngViewOptions` erledigen die Konvertierung in einem Schritt und ermöglichen die Angabe von Auflösung und Qualität.

**Q: Gibt es eine Möglichkeit, mehrere Numbers‑Dateien stapelweise zu verarbeiten?**  
A: Verpacken Sie die Viewer‑Logik in einer Schleife, initialisieren Sie `Viewer` für jede Datei neu und schreiben Sie jede Ausgabe in einen separaten Ordner.

**Q: Benötige ich für jedes Ausgabeformat eine separate Lizenz?**  
A: Nein, eine einzelne GroupDocs.Viewer‑Lizenz deckt alle unterstützten Formate ab.

**Q: Welche Version von GroupDocs.Viewer wird für diese Funktionen benötigt?**  
A: Die Beispiele zielen auf Version 25.2 ab, die die vollständige Unterstützung für Numbers‑zu‑PDF/HTML/Image‑Konvertierung bietet.

## Ressourcen
- **Dokumentation:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **API‑Referenz:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Lizenz kaufen:** [Buy a License](https://purchase.groupdocs.com/buy)
- **Kostenlose Testversion:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporäre Lizenz:** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **Support‑Forum:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-03-05  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs