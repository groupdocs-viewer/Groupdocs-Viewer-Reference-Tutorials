---
date: '2026-09-15'
description: Erfahren Sie, wie Sie eml mit GroupDocs.Viewer für Java in html mit einem
  benutzerdefinierten datetime-Format und Zeitzonenoffset konvertieren — ideal für
  E-Mail-Archivierung und Support-Portale.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Konvertieren Sie eml in html mit einem benutzerdefinierten datetime-Format
  und Zeitzonenoffset mithilfe von GroupDocs.Viewer für Java. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung
  für eine präzise E-Mail-Darstellung.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: eml in html mit benutzerdefiniertem datetime in Java mithilfe von GroupDocs.Viewer
  konvertieren
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: eml in html mit benutzerdefiniertem datetime in Java mithilfe von GroupDocs.Viewer
  konvertieren
type: docs
url: /de/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# EML in HTML konvertieren mit benutzerdefiniertem Datum/Zeit in Java mit GroupDocs.Viewer

In modernen Support‑ und Archivierungssystemen ist **EML in HTML konvertieren** schnell und dabei exakte Zeitstempel beizubehalten, eine unverzichtbare Fähigkeit. Dieses Tutorial zeigt Ihnen, wie Sie eine EML‑E‑Mail zu HTML rendern, ein **benutzerdefiniertes Datum/Zeit‑Format** anwenden und einen **Zeitzonen‑Offset** mit GroupDocs.Viewer für Java festlegen. Am Ende haben Sie ein wiederverwendbares Snippet, das genaue, web‑bereite E‑Mail‑Ansichten für jeden **E‑Mail‑zu‑HTML‑Konvertierungs‑Workflow** erzeugt.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Schnelle Antworten
- **Kann GroupDocs.Viewer EML in HTML konvertieren?** Ja – die API rendert EML‑Dateien direkt zu HTML ohne externe Mail‑Clients.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kostenlose Testversion reicht für Tests; für den Produktionseinsatz ist eine kostenpflichtige Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder neuer wird vollständig unterstützt.  
- **Wie ändere ich das angezeigte Datumsformat?** Rufen Sie `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")` auf.  
- **Kann ich die Zeitzone anpassen?** Ja, verwenden Sie `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## Was bedeutet „EML in HTML konvertieren“?
`Convert eml to html` ist der Prozess, eine EML‑E‑Mail‑Datei in ein HTML‑Dokument für die Browserdarstellung zu transformieren. Das Konvertieren einer EML‑Datei zu HTML wandelt die rohe E‑Mail (einschließlich Header, Body und Anhänge) in ein web‑freundliches Format um, das Browser ohne zusätzliche Plugins anzeigen können. Das erleichtert das Einbetten von E‑Mails in Web‑Anwendungen, Archive oder Support‑Dashboards.

## Warum GroupDocs.Viewer für diese Aufgabe verwenden?
GroupDocs.Viewer unterstützt **50+ Eingabe‑ und Ausgabeformate**, darunter EML, MSG, PST und PDF, und kann mehrseitige E‑Mails rendern, ohne die gesamte Datei in den Speicher zu laden. Die Null‑Abhängigkeits‑Engine eliminiert die Notwendigkeit von Outlook oder Drittanbieter‑Parsern und gibt Ihnen volle Kontrolle über **benutzerdefiniertes Datum/Zeit‑Format** und **Zeitzonen‑Offset**, während der Ressourcenverbrauch gering bleibt.

## Voraussetzungen
- GroupDocs.Viewer für Java ≥ 25.2  
- JDK 8+ und eine Java‑IDE (IntelliJ IDEA, Eclipse, VS Code)  
- Maven für die Verwaltung von Abhängigkeiten  

## Einrichtung von GroupDocs.Viewer für Java

### Maven-Konfiguration
Fügen Sie das GroupDocs‑Repository und die Viewer‑Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
Beginnen Sie mit einer kostenlosen Testversion oder beantragen Sie eine temporäre Lizenz für erweiterte Tests. Kaufen Sie eine vollständige Lizenz für den Produktionseinsatz.

### Grundlegende Initialisierung
Erstellen Sie eine `Viewer`‑Instanz, die auf die EML‑Datei zeigt, die Sie konvertieren möchten.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## EML in HTML konvertieren mit benutzerdefiniertem Datum/Zeit in Java

Die folgenden Schritte führen Sie durch das Rendern einer EML‑Datei zu HTML, wobei ein benutzerdefiniertes Datum/Zeit‑Format und ein Zeitzonen‑Offset angewendet werden.

### Schritt 1: Ausgabeverzeichnis und Dateipfad festlegen
Definieren Sie, wo das erzeugte HTML gespeichert werden soll.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Erklärung:* `Path.of()` erstellt eine Referenz auf den Ordner, in dem das HTML gespeichert wird. `resolve()` hängt den Dateinamen an.

### Schritt 2: Viewer mit E‑Mail‑Datei initialisieren
Instanziieren Sie die `Viewer`‑Klasse für die Ziel‑EML‑Datei.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Erklärung:* Die `Viewer`‑Instanz zeigt auf die EML‑Datei, die Sie konvertieren möchten.

### Schritt 3: HtmlViewOptions konfigurieren
Erstellen Sie ein `HtmlViewOptions`‑Objekt, das Bilder und andere Ressourcen direkt in die HTML‑Ausgabe einbettet.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Erklärung:* `forEmbeddedResources()` bettet Bilder und andere Ressourcen direkt in die HTML‑Ausgabe ein.

### Schritt 4: Benutzerdefiniertes Datum/Zeit‑Format festlegen *(custom datetime java)*
`setDateTimeFormat` legt das Datums‑Zeit‑Muster fest, das beim Rendern von E‑Mail‑Zeitstempeln verwendet wird.  
Definieren Sie das Muster, das für alle Zeitstempel im gerenderten HTML verwendet werden soll.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Erklärung:* Dieses Muster zeigt Monat, Tag, Jahr, Stunde, Minute, AM/PM‑Kennzeichen und den Zeitzonen‑Offset (`zzz`) an.

### Schritt 5: Zeitzonen‑Offset festlegen *(timezone offset java)*
`setTimeZoneOffset` gibt die Zeitzone an, die auf alle E‑Mail‑Zeitstempel angewendet wird.  
Passen Sie die Zeitstempel an die gewünschte Zeitzone an.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Erklärung:* Passt die gerenderten Zeitstempel an die gewünschte Zeitzone an. Ersetzen Sie `"GMT+1"` durch einen beliebigen gültigen Zonenkürzel.

### Wie man die E‑Mail‑Zeitzone in Java anpasst
Wenn Sie die **E‑Mail‑Zeitzone** über einfache Offsets hinaus anpassen müssen – etwa bei Sommerzeit‑Umstellungen – können Sie das passende `TimeZone`‑Objekt aus der `java.util.TimeZone`‑API mittels Regions‑IDs wie `"Europe/Paris"` oder `"America/New_York"` abrufen und an `setTimeZoneOffset` übergeben. So stellen Sie sicher, dass die E‑Mail‑Zeitstempel stets die korrekte lokale Zeit anzeigen.

### Schritt 6: Dokument rendern
Führen Sie die Konvertierung aus und erzeugen Sie die finale HTML‑Datei.

```java
viewer.view(options);
```
*Erklärung:* Führt die Konvertierung aus und erzeugt eine HTML‑Datei mit Ihren benutzerdefinierten Datum/Zeit‑Einstellungen.

## Wie wirkt sich das benutzerdefinierte Datum/Zeit‑Format auf das gerenderte HTML aus?
Das benutzerdefinierte Datum/Zeit‑Format bestimmt, wie jeder E‑Mail‑Zeitstempel im erzeugten HTML erscheint, was die Lesbarkeit und die Einhaltung lokaler Vorgaben beeinflusst. Durch Angabe eines Musters wie `"MMM dd, yyyy hh:mm a zzz"` stellen Sie sicher, dass jedes Datum konsistent angezeigt wird, inklusive Monatsabkürzung, Tag, Jahr, Stunde, Minute, AM/PM‑Kennzeichen und explizitem Zeitzonen‑Offset – ein entscheidender Faktor für globale Support‑Teams.

## Welche Dateiformate unterstützt GroupDocs.Viewer für die E‑Mail‑Darstellung?
GroupDocs.Viewer kann **EML, MSG, PST, MBOX und EMLX** Dateien zu HTML, PDF, PNG und JPEG rendern. Insgesamt unterstützt es über 50 Dokument‑ und Bildformate, sodass Sie E‑Mails in jedes gängige web‑freundliche Ausgabeformat konvertieren können, ohne zusätzliche Konverter zu benötigen.

## Wie kann ich mehrere EML‑Dateien stapelweise konvertieren?
Legen Sie alle EML‑Dateien in ein einzelnes Verzeichnis, iterieren Sie mit einer `for`‑ oder `foreach`‑Schleife über jede Datei, verwenden Sie dieselbe `HtmlViewOptions`‑Instanz und rufen Sie `viewer.view` für jede Datei auf. Dieser Ansatz minimiert den Objekt‑Erstellungs‑Overhead und beschleunigt Massenkonvertierungen.

## Tipps zur Fehlersuche
- **FileNotFoundException:** Überprüfen Sie die in `Viewer` und `Path.of()` verwendeten Pfade.  
- **Falsche Zeitstempel:** Stellen Sie sicher, dass die `TimeZone`‑ID Ihrer Zielregion entspricht.  
- **Fehlende Bilder:** Vergewissern Sie sich, dass Sie `HtmlViewOptions.forEmbeddedResources()` verwendet haben; andernfalls können externe Ressourcen ausgelassen werden.  

## Praktische Anwendungen
1. **E‑Mail‑Archivierung:** Speichern Sie durchsuchbare HTML‑Schnappschüsse von E‑Mails für Compliance‑Prüfungen.  
2. **Kunden‑Support‑Portale:** Zeigen Sie eingehende Tickets mit genauen lokalen Zeiten für Agenten weltweit an.  
3. **Rechtliche Dokumentation:** Erstellen Sie gerichtsreife E‑Mail‑Aufzeichnungen mit standardisierten Zeitstempeln.  

## Leistungsüberlegungen
- Setzen Sie die Anwendung auf einem dedizierten Server für Massenkonvertierungen ein.  
- Überwachen Sie den Java‑Heap‑Verbrauch; erhöhen Sie `-Xmx`, falls Sie `OutOfMemoryError` erhalten.  
- Cachen Sie gerendertes HTML, wenn dieselbe E‑Mail wiederholt angefordert wird, um die CPU‑Last zu reduzieren.  

## Fazit
Sie verfügen nun über eine vollständige, produktionsreife Methode, **EML in HTML zu konvertieren** mit einem benutzerdefinierten Datum/Zeit‑Format und Zeitzonen‑Offset mittels GroupDocs.Viewer für Java. Diese Lösung verbessert die Lesbarkeit, garantiert Zeitstempel‑Genauigkeit und lässt sich nahtlos in Archivierungs-, Support‑ oder Rechts‑Workflows integrieren.

**Nächste Schritte:** Erkunden Sie weitere Viewer‑Optionen wie das Einfügen benutzerdefinierten CSS, Paginierung oder PDF‑Konvertierung, um die Ausgabe weiter an die Bedürfnisse Ihrer Anwendung anzupassen.

## Häufig gestellte Fragen

**Q: Wie gehe ich mit EML‑Dateien mit Anhängen um?**  
A: Anhänge werden automatisch eingebettet, wenn Sie `HtmlViewOptions.forEmbeddedResources()` verwenden. Sie können sie auch über die Viewer‑API extrahieren, falls Sie separate Dateien benötigen.

**Q: Kann ich die HTML‑Vorlage ändern oder benutzerdefiniertes CSS hinzufügen?**  
A: Ja, nach dem Rendern können Sie die erzeugte HTML‑Datei bearbeiten oder CSS programmgesteuert vor dem Speichern injizieren.

**Q: Ist es möglich, mehrere EML‑Dateien stapelweise zu rendern?**  
A: Verpacken Sie die Render‑Logik in einer Schleife und verwenden Sie dieselbe `HtmlViewOptions`‑Instanz für jede Datei.

**Q: Was ist, wenn ich andere E‑Mail‑Formate wie MSG unterstützen muss?**  
A: GroupDocs.Viewer unterstützt ebenfalls MSG, PST und weitere E‑Mail‑Container – ändern Sie einfach die Dateierweiterung im `Viewer`‑Konstruktor.

**Q: Benötige ich für jeden Server eine separate Lizenz?**  
A: Die Lizenzierung erfolgt pro Bereitstellung; konsultieren Sie den GroupDocs‑Lizenz‑Leitfaden für Multi‑Server‑Szenarien.

## Ressourcen

- [Dokumentation](https://docs.groupdocs.com/viewer/java/)
- [API‑Referenz](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Kauf](https://purchase.groupdocs.com/buy)
- [Kostenlose Testversion](https://releases.groupdocs.com/viewer/java/)
- [Temporäre Lizenz](https://purchase.groupdocs.com/temporary-license/)
- [Support‑Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-09-15  
**Getestet mit:** GroupDocs.Viewer 25.2 (Java)  
**Autor:** GroupDocs

## Verwandte Tutorials

- [E‑Mail in HTML konvertieren & Felder umbenennen – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – Optimieren der E‑Mail‑zu‑PDF‑Darstellung mit GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [GroupDocs Viewer Java Responsive HTML‑Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
