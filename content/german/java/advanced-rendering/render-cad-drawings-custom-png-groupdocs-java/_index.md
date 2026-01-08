---
date: '2026-01-08'
description: Erfahren Sie, wie Sie CAD‑Zeichnungen mit benutzerdefinierten Abmessungen
  und Hintergrundfarben in hochwertige PNG‑Bilder rendern können, mit GroupDocs.Viewer
  für Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Wie man CAD‑Zeichnungen als PNG mit benutzerdefinierter Größe und Hintergrundfarbe
  mit GroupDocs.Viewer für Java rendert
type: docs
url: /de/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Wie man CAD‑Zeichnungen als PNG mit benutzerdefinierter Größe und Hintergrundfarbe mit GroupDocs.Viewer für Java rendert

Haben Sie Schwierigkeiten, Ihre CAD‑Zeichnungen in hochqualitative Bilder zu konvertieren und dabei bestimmte Abmessungen und Ästhetik beizubehalten? In diesem Tutorial zeigen wir **wie man CAD**‑Dateien als PNGs mit benutzerdefinierter Größe und Hintergrundfarbe rendert, sodass Sie genau das gewünschte Aussehen für Berichte, Präsentationen oder Web‑Vorschauen erhalten.

## Schnelle Antworten
- **Was bedeutet „how to render CAD“?** Es bezieht sich auf das Konvertieren von CAD‑Dateien (z. B. DWG) in Bildformate wie PNG mittels Code.  
- **Kann ich eine benutzerdefinierte Breite festlegen?** Ja – verwenden Sie `CadOptions.forRenderingByWidth(int width)`.  
- **Wie ändere ich den Hintergrund?** Rufen Sie `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` auf.  
- **Welche Bibliothek wird benötigt?** GroupDocs.Viewer für Java (Version 25.2 oder neuer).  
- **Benötige ich eine Lizenz?** Eine temporäre oder gekaufte Lizenz entfernt die Evaluationsbeschränkungen.

![CAD-Zeichnungen als PNG mit benutzerdefinierter Größe und Hintergrundfarbe mit GroupDocs.Viewer für Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Wie man CAD‑Zeichnungen rendert – Überblick
Dieser Abschnitt erweitert das Hauptziel: **wie man CAD**‑Zeichnungen in PNG‑Dateien rendert, während Größe und Hintergrund gesteuert werden. Wir führen Sie durch die komplette Einrichtung, Code‑Snippets und praktische Tipps.

## Was Sie lernen werden
- Einrichtung von GroupDocs.Viewer für Java in Ihrem Projekt  
- **DWG zu PNG konvertieren** mit benutzerdefinierten Abmessungen  
- **Hintergrundfarbe für PNG setzen** während des Renderns für ein professionelles Aussehen  
- Praxisbeispiele, bei denen benutzerdefiniertes Rendering Mehrwert schafft

## Voraussetzungen

### Erforderliche Bibliotheken und Abhängigkeiten
- Java Development Kit (JDK) 8+  
- Maven für das Abhängigkeitsmanagement  

### Anforderungen an die Umgebungseinrichtung
- IDE wie IntelliJ IDEA oder Eclipse  
- Grundkenntnisse in Java  

### Wissensvoraussetzungen
- Vertrautheit mit dem Umgang mit Dateien in Java  

## Einrichtung von GroupDocs.Viewer für Java
Add the GroupDocs repository and dependency to your Maven `pom.xml`:

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
Erhalten Sie eine temporäre oder vollständige Lizenz, um Evaluationsbeschränkungen zu entfernen.

### Grundlegende Initialisierung und Einrichtung
Create a `Viewer` instance that points to your CAD file:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Implementierungs‑Leitfaden

### Feature 1: Rendern von CAD‑Zeichnungen mit benutzerdefinierter Bildgröße und Hintergrundfarbe
#### Überblick
Dieses Feature ermöglicht es Ihnen, **DWG zu PNG** zu konvertieren, während Sie Bildbreite und Hintergrundfarbton angeben.

#### Schritt‑für‑Schritt‑Implementierung

##### Erforderliche Pakete importieren
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Einrichten des Ausgabeverzeichnisses und des Dateipfadformats
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
- `PngViewOptions` – definiert das Ausgabeformat und die Benennung.  
- `forRenderingByWidth(int width)` – legt die benutzerdefinierte Bildbreite fest.  
- `setBackgroundColor(Color color)` – **wendet Hintergrundfarbrendering** auf das PNG an.

#### Tipps zur Fehlersuche
- Stellen Sie sicher, dass das Ausgabeverzeichnis existiert; erstellen Sie es bei Bedarf.  
- Überprüfen Sie den Eingabedateipfad und die Berechtigungen erneut.

### Feature 2: Hintergrundfarbe in Rendering‑Optionen festlegen
#### Überblick
Hier konzentrieren wir uns auf **Hintergrundfarbe für PNG setzen**, um die visuelle Konsistenz zu verbessern.

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
- Passen Sie `forRenderingByWidth(int width)` für verschiedene Abmessungen an.  
- Verwenden Sie jede `Color`‑Konstante oder ein benutzerdefiniertes `new Color(r,g,b)` für maßgeschneiderte Hintergründe.

## Praktische Anwendungen

### 1. Technische Dokumentation
Benutzerdefiniertes Rendering stellt sicher, dass technische Zeichnungen den Unternehmensstilrichtlinien entsprechen.

### 2. Architektonische Visualisierung
Präsentieren Sie Baupläne mit einem sauberen Hintergrund, der zu den Präsentationsfolien passt.

### 3. Fertigungs‑Prototyping
Erzeugen Sie präzise PNGs für Workflows des schnellen Prototypings.

### Integrationsmöglichkeiten
Kombinieren Sie diese Rendering‑Pipeline mit Dokumentenmanagementsystemen, um die automatische Erstellung visueller Assets zu ermöglichen.

## Leistungs‑Überlegungen

### Leistung optimieren
- **Batch‑Verarbeitung:** Rendern Sie mehrere CAD‑Dateien in einer Schleife.  
- **Ressourcenverwaltung:** Passen Sie die JVM‑Heap‑Größe für große Zeichnungen an.

### Richtlinien zur Ressourcennutzung
Überwachen Sie CPU und Speicher; geben Sie `Viewer`‑Instanzen umgehend frei.

### Best Practices für das Java‑Speichermanagement
- Verwenden Sie try‑with‑resources (wie gezeigt), um `Viewer` automatisch zu schließen.  
- Vermeiden Sie das längerfristige Halten großer `Path`‑Objekte.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Ausgabeverzeichnis nicht gefunden** | Erstellen Sie das Verzeichnis im Voraus oder fügen Sie `Files.createDirectories(outputDirectory);` hinzu. |
| **Leeres Bild** | Stellen Sie sicher, dass `cadOptions.setBackgroundColor` nach `forRenderingByWidth` gesetzt wird. |
| **Out‑of‑Memory‑Fehler** | Erhöhen Sie die JVM‑Option `-Xmx` oder verarbeiten Sie Dateien in kleineren Stapeln. |

## Häufig gestellte Fragen

**F: Kann ich andere CAD‑Formate außer DWG rendern?**  
A: Ja, GroupDocs.Viewer unterstützt DXF, DWF und mehrere andere CAD‑Dateitypen.

**F: Wie verwende ich eine benutzerdefinierte RGB‑Farbe anstelle einer vordefinierten Konstante?**  
A: Erstellen Sie eine neue `Color`‑Instanz, z. B. `new Color(123, 45, 67)` und übergeben Sie sie an `setBackgroundColor`.

**F: Ist es möglich, nur ein bestimmtes Layout oder eine Ebene zu rendern?**  
A: Sie können Layout‑ oder Ebenen‑Optionen über `CadOptions` festlegen, bevor Sie `viewer.view` aufrufen.

**F: Unterstützt die Bibliothek transparente Hintergründe?**  
A: Setzen Sie die Hintergrundfarbe auf `new Color(0,0,0,0)` für volle Transparenz, falls das Zielformat dies unterstützt.

**F: Welche Version von GroupDocs.Viewer wird benötigt?**  
A: Das Tutorial verwendet Version 25.2, aber neuere Versionen behalten dieselbe API bei.

## Fazit
Sie wissen jetzt **wie man CAD**‑Zeichnungen in PNG‑Dateien mit benutzerdefinierten Abmessungen und Hintergrundfarben mithilfe von GroupDocs.Viewer für Java rendert. Wenden Sie diese Techniken an, um professionell aussehende visuelle Assets für Ingenieur‑, Architektur‑ oder Fertigungs‑Workflows zu erstellen.

### Nächste Schritte
- Experimentieren Sie mit verschiedenen Bildbreiten und Farben.  
- Integrieren Sie den Rendering‑Code in einen Batch‑Verarbeitungs‑Service.  
- Erkunden Sie weitere Viewer‑Optionen wie PDF‑Konvertierung oder Mehrseiten‑Rendering.

---

**Zuletzt aktualisiert:** 2026-01-08  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs