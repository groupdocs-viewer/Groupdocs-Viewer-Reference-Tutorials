---
date: '2026-07-19'
description: Erfahren Sie, wie Sie PST mit GroupDocs.Viewer for Java in HTML und weitere
  Formate wie JPG, PNG, PDF konvertieren. Dieser Leitfaden deckt alle erforderlichen
  Schritte und Konfigurationen ab.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Konvertieren Sie PST schnell zu HTML mit GroupDocs.Viewer for Java.
  Erfahren Sie Schritt für Schritt, wie Sie auch in JPG, PNG und PDF exportieren können
  – in einem produktionsreifen Leitfaden.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: PST zu HTML konvertieren mit GroupDocs.Viewer for Java – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: PST zu HTML, JPG, PNG, PDF konvertieren mit GroupDocs.Viewer for Java
type: docs
url: /de/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# PST in HTML, JPG, PNG, PDF konvertieren mit GroupDocs.Viewer für Java

Suchen Sie nach einer Möglichkeit, **pst in html** zu konvertieren oder in andere Formate wie JPG, PNG oder PDF? Mit der leistungsstarken GroupDocs.Viewer for Java-Bibliothek ist diese Aufgabe einfach und effizient. In diesem Tutorial lernen Sie, wie Sie Outlook PST/OST‑Dateien in web‑freundliches HTML, Bilddateien oder ein einzelnes PDF rendern, sodass Ihre E‑Mail‑Archive leicht zu teilen und zu archivieren sind.

![PST/OST in HTML, JPG, PNG, PDF konvertieren mit GroupDocs.Viewer für Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Was Sie lernen werden**
- Wie man GroupDocs.Viewer für Java in einem Maven‑Projekt einrichtet.  
- Schritt‑für‑Schritt‑Anleitungen zum **java convert pst** Dateien in HTML, JPG, PNG und PDF zu konvertieren.  
- Konfigurationstipps für optimale Leistung und häufige Fallstricke.

## Schnelle Antworten
- **Welche Bibliothek übernimmt die PST‑Konvertierung?** GroupDocs.Viewer for Java.  
- **Kann ich PST direkt in PDF konvertieren?** Ja, mit `PdfViewOptions`.  
- **Ist für die Produktion eine Lizenz erforderlich?** Eine gültige GroupDocs‑Lizenz wird benötigt.  
- **Welche Java‑Version wird unterstützt?** JDK 8 oder höher.  
- **Muss ich Anhänge manuell extrahieren?** Nein, der Viewer rendert sie automatisch.

## Was ist GroupDocs.Viewer für Java?
GroupDocs.Viewer für Java ist eine serverseitige API, die über 100 Dokument‑ und E‑Mail‑Formate lädt und sie ohne externe Software in HTML, Bild‑ oder PDF‑Ausgabe rendert. Sie verarbeitet PST‑Dateien bis zu 2 GB, wobei der Speicherverbrauch unter 200 MB bleibt.

## Wie man pst in html mit GroupDocs.Viewer für Java konvertiert?
Laden Sie die PST‑Datei mit `new Viewer("source.pst")`, konfigurieren Sie `HtmlViewOptions`, um auf einen Ausgabepfad zu verweisen, und rufen Sie `viewer.view(htmlOptions)` auf. Die API extrahiert jede E‑Mail, bewahrt Formatierung, Anhänge und Metadaten und schreibt für jede Nachricht eine separate HTML‑Seite – alles in einem einzigen Methodenaufruf.

### Warum GroupDocs.Viewer wählen?
- **High‑fidelity rendering** – 99,9 % des E‑Mail‑Inhalts (einschließlich Rich‑Text‑Körper, Tabellen und eingebetteter Bilder) wird genau wiedergegeben.  
- **Multiple output formats** – Ein API‑Aufruf kann HTML, JPG, PNG oder PDF erzeugen und deckt über 50 Exportoptionen ab.  
- **Zero external dependencies** – Keine Notwendigkeit für Outlook, Exchange Server oder Drittanbieter‑Konverter; alles läuft innerhalb Ihrer Java‑Laufzeit.

## Voraussetzungen

- **GroupDocs.Viewer für Java** – Version 25.2 oder neuer.  
- **Java Development Kit (JDK)** – 8 oder neuer.  
- Maven für die Abhängigkeitsverwaltung.  
- Grundlegende Java‑Kenntnisse und Vertrautheit mit Maven.

## Einrichtung von GroupDocs.Viewer für Java

`Viewer` ist die Kernklasse in GroupDocs.Viewer für Java, die ein Dokument lädt und es in das gewählte Format rendert. Fügen Sie das GroupDocs‑Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu:

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
- **Free trial** – Alle Funktionen kostenlos testen.  
- **Temporary license** – Evaluationszeit bei Bedarf verlängern.  
- **Full license** – Für den Produktionseinsatz erforderlich.

### Grundlegende Initialisierung

`Viewer`‑Instanzen sind leichtgewichtig; Sie können eine einzelne Instanz für viele Dateien wiederverwenden, um den Overhead bei der Objekterstellung zu minimieren.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Implementierungs‑Leitfaden

Die folgenden Abschnitte führen Sie durch das Rendern von PST/OST‑Dateien in jedes unterstützte Format.

### Rendern von PST/OST‑Dokumenten zu HTML

#### Schritt 1: Ausgabeverzeichnis einrichten
Definieren Sie einen Ordner, in dem die HTML‑Seiten geschrieben werden. GroupDocs erstellt für jede E‑Mail einen Unterordner, um die Ressourcen zu organisieren.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Schritt 2: Load‑Optionen konfigurieren
`LoadOptions` ermöglicht die Angabe von Passwortbehandlung, Zeitlimits für das Laden von Ressourcen und selektivem Seiten‑Rendering. Ein Timeout von 30 Sekunden funktioniert in den meisten Serverumgebungen gut.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Schritt 3: HTML‑View‑Optionen definieren
`HtmlViewOptions` legt den Ausgabepfad, die Ressourcenbehandlung und optionale CSS‑Einstellungen für die HTML‑Konvertierung fest.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Schritt 4: Viewer initialisieren und HTML rendern
Erstellen Sie ein `Viewer`‑Objekt, übergeben Sie den PST‑Dateipfad und rufen Sie `view` mit den `HtmlViewOptions` auf. Die API iteriert automatisch durch alle Nachrichten im PST und erzeugt eine übersichtliche HTML‑Hierarchie.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Rendern von PST/OST‑Dokumenten zu JPG

#### Schritt 1: Ausgabeverzeichnis einrichten
Erstellen Sie einen eigenen Ordner für JPG‑Snapshots; jede E‑Mail wird je nach Länge in eine oder mehrere Bilddateien umgewandelt.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Schritt 2: Load‑Optionen konfigurieren
Die gleichen `LoadOptions`, die für HTML verwendet wurden, können hier wiederverwendet werden, um eine konsistente Passwortbehandlung über alle Formate hinweg sicherzustellen.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Schritt 3: JPG‑View‑Optionen definieren
`JpgViewOptions` steuert die Bildauflösung, Qualität und den Ausgabepfad für die JPEG‑Konvertierung.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Schritt 4: Viewer initialisieren und JPG rendern
Verwenden Sie `viewer.view(jpgOptions)`, um hochwertige JPEG‑Dateien für die Web‑Vorschau zu erzeugen.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Rendern von PST/OST‑Dokumenten zu PNG

#### Schritt 1: Ausgabeverzeichnis einrichten
PNG‑Ausgabe ist nützlich, wenn Sie verlustfreie Qualität für Archivierung oder OCR‑Verarbeitung benötigen.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Schritt 2: Load‑Optionen konfigurieren
Keine zusätzlichen Einstellungen sind über die Passwort‑ und Timeout‑Konfiguration hinaus erforderlich.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Schritt 3: PNG‑View‑Optionen definieren
`PngViewOptions` ermöglicht das Festlegen eines transparenten Hintergrunds und eines Ausgabepfads für verlustfreie PNG‑Bilder.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Schritt 4: Viewer initialisieren und PNG rendern
Instanziieren Sie `viewer.view(pngOptions)`, um PNG‑Snapshots jeder E‑Mail zu erzeugen.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendern von PST/OST‑Dokumenten zu PDF

#### Schritt 1: Ausgabeverzeichnis einrichten
Eine einzelne PDF‑Datei pro PST vereinfacht rechtliche Prüfungsabläufe und reduziert den Speicheraufwand.

CODE_BLOCK_PLACEHOLDER_14_END

#### Schritt 2: Load‑Optionen konfigurieren
Beim Konvertieren zu PDF möchten Sie möglicherweise `setEmbedFonts(true)` aktivieren, um visuelle Treue auf jedem Rechner zu gewährleisten.

CODE_BLOCK_PLACEHOLDER_15_END

#### Schritt 3: PDF‑View‑Optionen definieren
`PdfViewOptions` ermöglicht die Auswahl des Kompressionsgrades, das Einbetten von Schriftarten und das Festlegen des Ausgabedateinamens für die PDF‑Konvertierung.

CODE_BLOCK_PLACEHOLDER_16_END

#### Schritt 4: Viewer initialisieren und PDF rendern
Erstellen Sie `PdfViewOptions`, wählen Sie optional einen Kompressionsgrad und rufen Sie `viewer.view(pdfOptions)` auf. Die API fasst alle E‑Mails zu einem durchsuchbaren PDF‑Dokument zusammen.

CODE_BLOCK_PLACEHOLDER_17_END

## Praktische Anwendungen

- **E‑Mail‑Archivierung:** Große PST‑Archive in durchsuchbares HTML oder PDF für die Compliance umwandeln.  
- **Dokumenten‑Management‑Systeme:** Konvertierte Dateien in Systemen speichern, die nur PDF, PNG oder JPG akzeptieren.  
- **Zusammenarbeits‑Plattformen:** Konvertierte E‑Mails als Bilder in Slack oder Teams teilen.  
- **Rechtliche Prüfung:** Gerichten PDF‑Versionen von E‑Mail‑Beweisen bereitstellen.  
- **Backup‑Strategien:** Leichte PNG‑ oder JPG‑Snapshots kritischer Nachrichten behalten.

## Leistungs‑Überlegungen

- **Ressourcen‑Management:** `Viewer`‑Instanzen wiederverwenden, wenn mehrere Dateien verarbeitet werden, um den Overhead zu reduzieren.  
- **Speicher‑Optimierung:** `loadOptions.setResourceLoadingTimeout` basierend auf der Serverkapazität anpassen.  
- **Asynchrones Verarbeiten:** Konvertierung auf Hintergrund‑Threads auslagern für reaktionsfähige UIs.  

## Häufig gestellte Fragen

**Q: Wie konvertiere ich **pst to pdf** mit derselben Codebasis?**  
A: Verwenden Sie `PdfViewOptions` wie im PDF‑Rendering‑Abschnitt gezeigt; der Rest des Codes bleibt unverändert.

**Q: Kann GroupDocs.Viewer verschlüsselte PST‑Dateien verarbeiten?**  
A: Ja, geben Sie das Passwort über `LoadOptions.setPassword("yourPassword")` vor dem Rendering an.

**Q: Was ist der Unterschied zwischen **java convert pst** zu PNG vs JPG?**  
A: PNG bewahrt verlustfreie Qualität, ideal für Screenshots, während JPG kleinere Dateigrößen für E‑Mail‑Vorschauen bietet.

**Q: Gibt es eine Möglichkeit, **how to convert pst** Dateien massenhaft zu konvertieren?**  
A: Verpacken Sie die Rendering‑Logik in einer Schleife, die ein Verzeichnis von PST‑Dateien durchläuft; verwenden Sie dieselbe `Viewer`‑Konfiguration für jede Datei erneut.

**Q: Unterstützt die API die Konvertierung von PST‑Dateien größer als 1 GB?**  
A: Ja, GroupDocs.Viewer streamt Daten und kann Dateien bis zu 2 GB verarbeiten, ohne das gesamte Archiv in den Speicher zu laden.

## Fazit

Sie haben nun eine vollständige, produktionsbereite Anleitung zum **convert pst to html**, JPG, PNG und PDF mit GroupDocs.Viewer für Java. Wenn Sie die obigen Schritte befolgen, können Sie die E‑Mail‑Konvertierung in jeden Java‑basierten Workflow integrieren, die Barrierefreiheit verbessern und Compliance‑Anforderungen erfüllen.

---

**Zuletzt aktualisiert:** 2026-07-19  
**Getestet mit:** GroupDocs.Viewer for Java 25.2  
**Autor:** GroupDocs

## Verwandte Tutorials

- [Convert NSF to PDF, HTML, JPG, PNG using GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Convert ODF to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [How to Convert DOCX to HTML Using GroupDocs.Viewer for Java: A Step‑By‑Step Guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)