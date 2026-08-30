---
date: '2026-08-30'
description: Erfahren Sie, wie Sie DWG in PNG konvertieren, die Hintergrundfarbe in
  Java festlegen und die Bildgröße mit GroupDocs.Viewer for Java anpassen.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Konvertieren Sie DWG in PNG mit GroupDocs.Viewer for Java, während
  Sie eine benutzerdefinierte Bildbreite und Hintergrundfarbe festlegen. Dieser Leitfaden
  bietet Schritt‑für‑Schritt‑Anleitung, Code‑Beispiele und Fehlerbehebungstipps.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: DWG in PNG mit benutzerdefinierter Größe und Hintergrundfarbe in Java konvertieren
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Wie man DWG mit benutzerdefinierter Größe und Hintergrundfarbe in PNG konvertiert
  mit GroupDocs.Viewer for Java
type: docs
url: /de/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Wie man DWG in PNG mit benutzerdefinierter Größe & Hintergrundfarbe mit GroupDocs.Viewer für Java konvertiert

In diesem Tutorial lernen Sie **wie man DWG in PNG** konvertiert, während Sie die Ausgabedimensionen und die Hintergrundfarbe steuern, mithilfe von GroupDocs.Viewer für Java. Egal, ob Sie CAD‑Zeichnungen in einen Bericht einbetten, Thumbnails für ein Web‑Portal erzeugen oder die Batch‑Renderung automatisieren müssen – die nachfolgenden Schritte geben Ihnen die volle Kontrolle über das visuelle Erscheinungsbild jeder PNG‑Datei.

## Schnelle Antworten
- **Was bedeutet „DWG in PNG konvertieren“?** Es ist der Prozess, eine DWG‑CAD‑Datei per Code in ein PNG‑Bild zu verwandeln und dabei Vektordetails als Rasterpixel zu erhalten.  
- **Kann ich eine benutzerdefinierte Breite festlegen?** Ja – rufen Sie `CadOptions.forRenderingByWidth(int width)` auf, um die exakt benötigte Pixelbreite zu definieren.  
- **Wie ändere ich die Hintergrundfarbe?** Verwenden Sie `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` vor dem Rendern.  
- **Welche Bibliothek wird benötigt?** GroupDocs.Viewer für Java (Version 25.2 oder neuer).  
- **Benötige ich eine Lizenz?** Eine temporäre oder vollständige Lizenz entfernt Evaluationsbeschränkungen und ermöglicht unbegrenztes Rendern.

![CAD-Zeichnungen als PNG mit benutzerdefinierter Größe & Hintergrundfarbe mit GroupDocs.Viewer für Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Was ist GroupDocs.Viewer für Java?
GroupDocs.Viewer für Java ist eine serverseitige API, die über 150 Dateiformate – einschließlich CAD‑Dateien – in Bilder, PDFs oder HTML rendert. Sie funktioniert, ohne dass Drittanbieter‑Software wie AutoCAD erforderlich ist, und eignet sich daher ideal für automatisierte Pipelines.

## Wie man DWG in PNG mit benutzerdefinierter Größe und Hintergrundfarbe konvertiert?
Laden Sie die DWG‑Datei mit einer `Viewer`‑Instanz, konfigurieren Sie `CadOptions` für die gewünschte Breite und den Hintergrund und rufen Sie schließlich `viewer.view` mit `PngViewOptions` auf. Dieser dreistufige Ablauf übernimmt Datei‑I/O, Rendering und Ausgabe‑Benennung in einem einzigen, speichereffizienten Vorgang.

Viewer ist die Hauptklasse, die ein Dokument lädt und das Rendering ausführt.  
CadOptions konfiguriert CAD‑spezifische Einstellungen wie Bildbreite und Hintergrundfarbe.  
PngViewOptions definiert das PNG‑Ausgabeformat und das Namensmuster für die gerenderten Seiten.

Sie können nun jede DWG‑Zeichnung in ein PNG mit exakt der von Ihnen angegebenen Breite rendern und jede beliebige Vollfarbe (oder Transparenz) als Hintergrund wählen, um Ihrer Marke oder UI‑Thematik zu entsprechen.

## Warum eine benutzerdefinierte Hintergrundfarbe festlegen?
Das Festlegen einer Hintergrundfarbe sorgt dafür, dass das gerenderte PNG nahtlos mit umgebenden UI‑Elementen verschmilzt, unerwünschte weiße Ränder vermeidet und Zeichnungsdetails hervorheben kann, die bei einem Standard‑Weiß‑Canvas verloren gehen würden. GroupDocs.Viewer unterstützt jedes `java.awt.Color`, einschließlich benutzerdefinierter RGB‑Werte, und gibt Ihnen pixelgenaue Kontrolle.

java.awt.Color stellt einen Farbwert dar, der für das Rendern von Hintergründen verwendet wird.

## Voraussetzungen
- **Java Development Kit (JDK) 8+** – die API zielt auf Java 8 und neuer ab.  
- **Maven** – zur Verwaltung von Abhängigkeiten.  
- **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  
- **Grundlegende Java‑Dateiverarbeitungskenntnisse** – zum Lesen von DWG‑Quelldateien und Schreiben von PNG‑Ausgaben.

## Einrichtung von GroupDocs.Viewer für Java
Fügen Sie das GroupDocs‑Repository und die Viewer‑Abhängigkeit zu Ihrer Maven `pom.xml` hinzu:

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
Holen Sie sich einen temporären oder vollständigen Lizenzschlüssel vom GroupDocs‑Portal und platzieren Sie die Datei `license.lic` im Ressourcenordner Ihres Projekts. Dadurch wird das 20‑Seiten‑Evaluationslimit entfernt und das Rendering in voller Auflösung freigeschaltet.

### Grundlegende Initialisierung und Einrichtung
Erstellen Sie eine `Viewer`‑Instanz, die auf den Ordner mit Ihren DWG‑Dateien zeigt:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Feature 1: Rendering von CAD-Zeichnungen mit benutzerdefinierter Bildgröße und Hintergrundfarbe

### Wie man die CAD-Hintergrundfarbe ändert
Um die CAD‑Hintergrundfarbe zu ändern, konfigurieren Sie das CadOptions‑Objekt vor dem Rendern. Setzen Sie die gewünschte Breite mit `forRenderingByWidth` und wenden Sie den neuen Hintergrund mit `setBackgroundColor` an. Der Viewer erzeugt dann PNG‑Bilder, die die angegebene Farbe widerspiegeln und über alle Ausgabedateien hinweg einen konsistenten visuellen Stil sicherstellen.

#### Schritt‑für‑Schritt‑Implementierung

##### Erforderliche Pakete importieren
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Ausgabeverzeichnis und Dateipfadmuster einrichten
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Viewer mit benutzerdefinierten Rendering‑Optionen initialisieren
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Erklärung der Parameter**  
- `PngViewOptions` – definiert das PNG‑Ausgabeformat und das Namensmuster.  
- `forRenderingByWidth(int width)` – zwingt den Renderer, ein Bild zu erzeugen, dessen Breite dem angegebenen Pixelwert entspricht; die Höhe wird proportional skaliert.  
- `setBackgroundColor(Color color)` – überschreibt das standardmäßige weiße Canvas mit der von Ihnen gewählten Farbe und verbessert die visuelle Konsistenz der erzeugten Assets.

#### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass das Ausgabeverzeichnis existiert; verwenden Sie `Files.createDirectories(outputDir)`, falls es nicht vorhanden ist.  
- Vergewissern Sie sich, dass der Eingabepfad korrekt ist und die Anwendung Leseberechtigungen hat.

## Feature 2: Hintergrundfarbe in Rendering‑Optionen festlegen

### Wie man die PNG‑Hintergrundfarbe festlegt
Das Festlegen der PNG‑Hintergrundfarbe beinhaltet das Erzeugen einer Color‑Instanz und deren Zuweisung zu den CadOptions vor dem Rendern. So wird sichergestellt, dass jedes erzeugte PNG den angegebenen Hintergrund verwendet und damit Ihren Markenrichtlinien oder UI‑Themen entspricht. Sie können vordefinierte Konstanten nutzen oder benutzerdefinierte RGB‑Werte für präzise Kontrolle definieren.

java.awt.Color stellt einen Farbwert dar, der für das Rendern von Hintergründen verwendet wird.

#### Schritt‑für‑Schritt‑Implementierung

##### Erforderliche Pakete importieren
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Rendering‑Optionen mit Hintergrundfarbe konfigurieren
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Wichtige Konfigurationsoptionen**  
- Passen Sie `forRenderingByWidth(int width)` für verschiedene Dimensionen an, z. B. 800 px für Web‑Thumbnails oder 1920 px für hochauflösende Drucke.  
- Verwenden Sie jede vordefinierte `Color`‑Konstante (z. B. `Color.LIGHT_GRAY`) oder erstellen Sie eine benutzerdefinierte Instanz mit `new Color(r, g, b)` für präzises Branding.

## Praktische Anwendungen

### 1. Technische Dokumentation
Benutzerdefiniertes Rendering stellt sicher, dass jede Zeichnung den Unternehmens‑Styleguide einhält und nach dem Export keine manuelle Bildbearbeitung mehr nötig ist.

### 2. Architektonische Visualisierung
Präsentieren Sie Baupläne mit einem Hintergrund, der zu Präsentationsfolien oder Kunden‑Portalen passt, und verbessern Sie so die visuelle Kohärenz.

### 3. Fertigungsprototyping
Generieren Sie PNGs für Rapid‑Prototype‑Workflows, bei denen nachgelagerte Tools eine bestimmte Bildgröße und Hintergrundfarbe erwarten.

### Integrationsmöglichkeiten
Koppeln Sie diese Rendering‑Pipeline mit einem Dokumenten‑Management‑System (z. B. SharePoint), um automatisch Vorschaubilder zu erzeugen, sobald eine DWG‑Datei hochgeladen wird.

## Leistungsüberlegungen

### Leistung optimieren
- **Batch‑Verarbeitung:** Durchlaufen Sie ein Verzeichnis mit DWG‑Dateien und rendern Sie jede nacheinander, um die JVM‑Warm‑up‑Kosten zu amortisieren.  
- **Ressourcenmanagement:** Bei großen Zeichnungen (500 + Seiten) erhöhen Sie den JVM‑Heap (`-Xmx2g`) oder verarbeiten Sie Dateien in kleineren Batches, um Out‑of‑Memory‑Fehler zu vermeiden.

### Richtlinien zur Ressourcennutzung
Überwachen Sie CPU‑ und Speicherverbrauch mit Tools wie VisualVM; geben Sie `Viewer`‑Instanzen umgehend über try‑with‑resources frei.

### Best Practices für das Java‑Speichermanagement
- Verwenden Sie try‑with‑resources (wie gezeigt), um `Viewer` automatisch zu schließen.  
- Vermeiden Sie das Behalten großer `Path`‑Objekte über deren unmittelbare Nutzung hinaus.

## Häufige Probleme und Lösungen

| Problem | Lösung |
|---------|--------|
| Ausgabeverzeichnis nicht gefunden | Erstellen Sie das Verzeichnis im Voraus oder fügen Sie `Files.createDirectories(outputDirectory);` hinzu |
| Leeres Bild | Stellen Sie sicher, dass `cadOptions.setBackgroundColor` nach `forRenderingByWidth` aufgerufen wird. |
| Out‑of‑Memory‑Fehler | Erhöhen Sie die JVM‑Option `-Xmx` oder verarbeiten Sie Dateien in kleineren Batches. |

## Häufig gestellte Fragen

**Q: Kann ich neben DWG auch andere CAD‑Formate rendern?**  
A: Ja, GroupDocs.Viewer unterstützt DXF, DWF und mehrere weitere CAD‑Formate.

**Q: Wie verwende ich eine benutzerdefinierte RGB‑Farbe statt einer vordefinierten Konstante?**  
A: Instanziieren Sie ein neues `Color` mit `new Color(123, 45, 67)` und übergeben Sie es an `setBackgroundColor`.

**Q: Ist es möglich, nur ein bestimmtes Layout oder eine Ebene zu rendern?**  
A: Sie können Layout‑ oder Ebenen‑Optionen über `CadOptions` festlegen, bevor Sie `viewer.view` aufrufen.

**Q: Unterstützt die Bibliothek transparente Hintergründe?**  
A: Setzen Sie die Hintergrundfarbe auf `new Color(0,0,0,0)` für vollständige Transparenz, sofern das Ausgabeformat dies unterstützt.

**Q: Welche Version von GroupDocs.Viewer wird benötigt?**  
A: Das Tutorial verwendet Version 25.2, neuere Releases behalten jedoch dieselbe API‑Oberfläche bei.

---

**Zuletzt aktualisiert:** 2026-08-30  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs

## Verwandte Tutorials

- [groupdocs viewer dwg – Wie man bestimmte CAD-Zeichnungen in Java mit GroupDocs.Viewer rendert](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [CAD-Layer in Java mit GroupDocs.Viewer rendern – Ein vollständiger Leitfaden](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Wie man PDF in HTML konvertiert und die Bildqualität in Java mit GroupDocs.Viewer optimiert](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)