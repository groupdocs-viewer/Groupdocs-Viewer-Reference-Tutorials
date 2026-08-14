---
date: '2026-06-15'
description: Erfahren Sie, wie Sie Excel mit Java in PDF konvertieren und Excel-Tabellenblätter
  nach Zeilen und Spalten mit GroupDocs Viewer aufteilen. Enthält Einrichtung, Code
  und bewährte Methoden.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Excel in PDF konvertieren mit Java & Tabellenblätter nach Zeilen und Spalten
  aufteilen
type: docs
url: /de/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel in PDF konvertieren mit Java & Tabellenblätter nach Zeilen und Spalten aufteilen (Java)

Große Excel‑Arbeitsmappen enthalten oft mehr Daten, als bequem auf einem einzigen Bildschirm oder einer Druckseite angezeigt werden können. **convert excel to pdf java** ist eine häufige Anforderung, wenn Sie ein statisches, teilbares Format benötigen, während **splitting Excel sheets by rows and columns** die Daten in Web‑ oder Drucklayouts leichter konsumierbar macht. In diesem Leitfaden gehen wir beide Aufgaben mit **GroupDocs Viewer for Java** durch, zeigen Ihnen, wie Sie die Seitennummerierung konfigurieren, und erklären bewährte Tipps für Leistung und Fehlersuche.

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** GroupDocs Viewer for Java.  
- **Kann ich sowohl nach Zeilen als auch nach Spalten aufteilen?** Ja – Sie können rows‑per‑page und columns‑per‑page zusammen definieren.  
- **Brauche ich eine Lizenz?** Eine Test‑ oder temporäre Lizenz funktioniert für die Entwicklung; eine Voll‑Lizenz ist für die Produktion erforderlich.  
- **Welche Ausgabeformate werden unterstützt?** HTML (eingebettete Ressourcen) wird gezeigt; PDF kann mit denselben Optionen erzeugt werden.  
- **Ist Maven erforderlich?** Maven ist der empfohlene Weg, um Abhängigkeiten zu verwalten.  
- **Kann ich auch Excel in PDF konvertieren?** Absolut – einfach `HtmlViewOptions` durch `PdfViewOptions` ersetzen und dieselben Paginierungseinstellungen wiederverwenden.

## Was ist „How to Split Excel“?
Das Aufteilen eines Excel‑Blatts bedeutet, ein einzelnes Arbeitsblatt in mehrere Seiten oder Dateien zu unterteilen, basierend auf einer festen Anzahl von Zeilen, Spalten oder beidem. Diese Technik ist praktisch, wenn Sie paginierte Berichte erstellen, Daten in Webseiten einbetten oder druckbare Abschnitte generieren möchten, ohne die gesamte Arbeitsmappe auf einmal zu laden.

## Warum GroupDocs Viewer für Java verwenden?
GroupDocs Viewer verarbeitet Tabellenkalkulationen in einem einzigen Durchlauf und paginiert sie automatisch, wodurch manuelle Berechnungen entfallen. **Schnelles Rendering verarbeitet eine 250‑seitige XLSX‑Arbeitsmappe in unter 2 Sekunden auf einem typischen 2‑Kern‑Server**, und **die Bibliothek unterstützt 50+ Eingabe‑ und Ausgabeformate**, darunter XLS, XLSX, CSV, PDF und HTML. Sie läuft auf jeder JVM‑kompatiblen Plattform — Windows, Linux, macOS, Docker‑Container oder cloud‑basierte serverlose Laufzeiten — so dass Sie sie überall dort integrieren können, wo Ihre Java‑Anwendung lebt.

## Voraussetzungen
- Java 17 oder neuer installiert.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Maven für das Abhängigkeitsmanagement.  
- Grundkenntnisse in Java und Vertrautheit mit der Handhabung von Excel‑Dateien.

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
Fügen Sie das GroupDocs‑Repository und die Viewer‑Abhängigkeit zu Ihrer `pom.xml` hinzu:

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
Erwerben Sie eine kostenlose Test‑, temporäre Lizenz oder kaufen Sie eine Voll‑Lizenz bei [GroupDocs](https://purchase.groupdocs.com/buy).

## Wie Excel in PDF mit Java konvertieren?

Die Klasse `Viewer` ist die Kernkomponente von GroupDocs Viewer, die ein Dokument lädt und Rendering‑Methoden für verschiedene Ausgabeformate bereitstellt. `SpreadsheetOptions` ermöglicht die Steuerung von Paginierungseinstellungen wie rows‑per‑page und columns‑per‑page für das Rendering von Tabellenkalkulationen.

Laden Sie Ihre Excel‑Datei mit `new Viewer("source.xlsx")`, konfigurieren Sie `SpreadsheetOptions` für die Paginierung und rufen Sie `viewer.view(pdfOptions, stream)` auf — dieser einzelne Aufruf konvertiert die Arbeitsmappe in ein PDF und berücksichtigt dabei die von Ihnen festgelegten Zeilen‑/Spalten‑Grenzen. Die Konvertierung bewahrt Formeln, Bilder und Zellstile und liefert ein getreues PDF‑Duplikat, das bereit zur Verteilung ist.

## Wie man Excel‑Tabellenblätter nach Zeilen aufteilt

Das Aufteilen nach Zeilen erzeugt eine Reihe von HTML‑Seiten, von denen jede eine feste Anzahl von Zeilen (z. B. 15) enthält. Dieser Ansatz ist ideal für Dashboards, die eine begrenzte Anzahl von Datensätzen pro Ansicht anzeigen. Der Viewer erzeugt separate HTML‑Dateien wie `page_0.html`, `page_1.html` usw., die jeweils die angegebene Zeilenzahl enthalten. Das ermöglicht das Laden nur des benötigten Abschnitts in einer Web‑Oberfläche, wodurch Bandbreite und Renderzeit reduziert werden.

### Definitionsanker
`Viewer` ist die Kernklasse von GroupDocs Viewer, die ein Dokument lädt und das Rendering in das gewählte Ausgabeformat orchestriert.

### Schritt‑für‑Schritt‑Implementierung

#### Schritt 1: Pfade einrichten und den Viewer initialisieren
Zuerst definieren Sie, wo die aufgeteilten Seiten gespeichert werden sollen, und erstellen eine `Viewer`‑Instanz für die Quell‑Arbeitsmappe.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Schritt 2: Zeilen pro Seite konfigurieren
Teilen Sie dem Viewer mit, wie viele Zeilen jede Seite enthalten soll.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Schritt 3: Dokument rendern
Zum Schluss rendern Sie die Arbeitsmappe mit den definierten Optionen.

```java
viewer.view(viewOptions);
```

## Wie man Excel‑Tabellenblätter nach Zeilen und Spalten aufteilt

Manchmal muss eine einzelne Seite ein Raster aus Zeilen **und** Spalten zeigen (z. B. 15 Zeilen × 7 Spalten). Das gibt Ihnen volle Kontrolle über das Layout jeder HTML‑Seite. Die resultierenden Seiten zeigen einen rechteckigen Zellblock, zum Beispiel Zeilen 1‑15 und Spalten A‑G auf der ersten Seite, Zeilen 16‑30 und Spalten H‑N auf der nächsten. Diese rasterbasierte Paginierung ist nützlich für druckbare Berichte, die auf Standard‑Papiergrößen passen.

### Definitionsanker
`SpreadsheetOptions` konfiguriert, wie viele Zeilen und Spalten auf jeder erzeugten Seite erscheinen.

### Schritt‑für‑Schritt‑Implementierung

#### Schritt 1: Pfade einrichten und den Viewer initialisieren
Der Aufbau entspricht dem Beispiel nur für Zeilen, der Dateiname ändert sich jedoch.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Schritt 2: Zeilen und Spalten pro Seite konfigurieren
Geben Sie beide Dimensionen an, um ein rasterbasiertes Aufteilen zu erzeugen.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Schritt 3: Dokument rendern
Rendern Sie mit demselben `view`‑Aufruf.

```java
viewer.view(options);
```

## Praktische Anwendungen
- **Excel‑Bericht mit Java generieren**: Große Finanzmodelle in eine Reihe paginierter HTML‑Berichte umwandeln.  
- **GroupDocs Viewer Excel**: Aufgeteilte Seiten direkt in ein Web‑Portal einbetten für interaktive Datenexploration.  
- **Render Excel HTML Java**: Die erzeugten HTML‑Seiten über ein Servlet oder einen Spring‑Controller bereitstellen für schnelles clientseitiges Rendering.  

## Leistungsüberlegungen
- **Speichernutzung** – Große Arbeitsmappen können erheblichen Heap verbrauchen; erwägen Sie, die JVM‑Einstellung `-Xmx` zu erhöhen.  
- **Chunk‑Größe** – Wählen Sie Zeilen‑/Spaltenzahlen, die Seiten‑größe und Rendering‑Geschwindigkeit ausbalancieren.  
- **Versions‑Updates** – Halten Sie GroupDocs Viewer aktuell, um von Leistungsverbesserungen zu profitieren; das neueste Release 25.2 steigert die Rendering‑Geschwindigkeit um bis zu 30 % gegenüber 24.x.

## Häufige Probleme & Fehlersuche
| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| `OutOfMemoryError` | Rendering einer sehr großen Tabelle mit zu vielen Zeilen pro Seite | `countRowsPerPage` reduzieren oder JVM‑Heap erhöhen |
| Leere Ausgabedateien | Falscher Dateipfad oder fehlende Schreibrechte | Sicherstellen, dass `outputDirectory` existiert und beschreibbar ist |
| HTML‑Ressourcen laden nicht | Verwendung von `forEmbeddedResources`, aber Dateien werden von einer anderen Basis‑URL serviert | Den gesamten Ausgabordner bereitstellen oder zu `forExternalResources` wechseln |

## Häufig gestellte Fragen

**Q: Kann ich auch ein PDF statt HTML erzeugen?**  
A: Ja. Ersetzen Sie `HtmlViewOptions` durch `PdfViewOptions` und behalten Sie die gleiche `SpreadsheetOptions`‑Konfiguration bei.

**Q: Ist es möglich, basierend auf Zellinhalt statt fester Zeilen/Spalten aufzuteilen?**  
A: Ein direktes, inhaltbasiertes Aufteilen ist nicht in GroupDocs Viewer integriert, Sie können jedoch die Arbeitsmappe mit Apache POI vorverarbeiten, um separate Blätter zu erstellen, bevor Sie rendern.

**Q: Unterstützt GroupDocs Viewer ältere Excel‑Formate (XLS)?**  
A: Absolut. Der Viewer verarbeitet XLS, XLSX, CSV und weitere Tabellenformate.

**Q: Wie bette ich das erzeugte HTML in eine Spring‑MVC‑Ansicht ein?**  
A: Stellen Sie den Ausgabordner als statische Ressource bereit und referenzieren Sie die erzeugten `page_0.html`, `page_1.html` usw. aus Ihren Thymeleaf‑ oder JSP‑Templates.

**Q: Welche Lizenz benötige ich für den kommerziellen Einsatz?**  
A: Eine Voll‑Produktionslizenz von GroupDocs ist erforderlich; Testlizenzen dienen nur zur Evaluierung.

## Ressourcen
- **Dokumentation**: [GroupDocs Viewer Java Dokumentation](https://docs.groupdocs.com/viewer/java/)
- **API‑Referenz**: [GroupDocs API Referenz](https://reference.groupdocs.com/viewer/java/)
- **Downloads**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Lizenz kaufen**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Kostenlose Testversion**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporäre Lizenz erhalten**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support‑Forum**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

**Zuletzt aktualisiert:** 2026-06-15  
**Getestet mit:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs  

## Verwandte Tutorials

- [Versteckte Zeilen & Spalten in Java‑Tabellen mit GroupDocs.Viewer rendern](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Leere Zeilen beim Rendern in Java mit GroupDocs.Viewer überspringen: Ein Performance‑Leitfaden](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Umfassender Leitfaden: Excel 2003 XML in HTML/JPG/PNG/PDF mit GroupDocs.Viewer Java konvertieren](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)