---
date: '2026-03-16'
description: Erfahren Sie, wie Sie DWG mit benutzerdefinierter Größe und Hintergrundfarbe
  in PNG konvertieren können, indem Sie GroupDocs.Viewer für Java verwenden.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Wie man DWG in PNG mit benutzerdefinierter Größe und Hintergrundfarbe mit GroupDocs.Viewer
  für Java konvertiert
type: docs
url: /de/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Wie man DWG in PNG mit benutzerdefinierter Größe und Hintergrundfarbe mit GroupDocs.Viewer für Java konvertiert

Wenn Sie **DWG in PNG** konvertieren möchten und dabei die volle Kontrolle über Bildabmessungen und Hintergrundgestaltung behalten wollen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch das Rendern von CAD‑Dateien als PNG, das Anpassen der Breite und das Ändern der Hintergrundfarbe, sodass das Ergebnis Ihren Bericht-, Präsentations‑ oder Web‑Vorschau‑Anforderungen entspricht.

## Schnelle Antworten
- **Was bedeutet „DWG in PNG konvertieren“?** Es ist der Vorgang, eine DWG‑CAD‑Datei mithilfe von Code in ein PNG‑Bild zu verwandeln.  
- **Kann ich eine benutzerdefinierte Breite festlegen?** Ja – verwenden Sie `CadOptions.forRenderingByWidth(int width)`.  
- **Wie ändere ich die Hintergrundfarbe?** Rufen Sie `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` auf.  
- **Welche Bibliothek wird benötigt?** GroupDocs.Viewer für Java (Version 25.2 oder höher).  
- **Benötige ich eine Lizenz?** Eine temporäre oder gekaufte Lizenz entfernt die Evaluationsbeschränkungen.

![CAD-Zeichnungen als PNG mit benutzerdefinierter Größe und Hintergrundfarbe mit GroupDocs.Viewer für Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Wie man DWG in PNG konvertiert – Überblick
In diesem Abschnitt erweitern wir das Hauptziel: **wie man DWG in PNG konvertiert** und dabei Größe und Hintergrund steuert. Sie sehen die komplette Einrichtung, den genauen Code, den Sie benötigen, und praktische Tipps, um häufige Fallstricke zu vermeiden.

## Was Sie lernen werden
- Einrichtung von GroupDocs.Viewer für Java in einem Maven‑Projekt  
- **DWG in PNG konvertieren** mit benutzerdefinierten Abmessungen  
- **CAD‑Hintergrundfarbe ändern** beim Rendern für ein professionelles Aussehen  
- Praxisbeispiele, bei denen benutzerdefiniertes Rendering Mehrwert schafft  

## Voraussetzungen

### Erforderliche Bibliotheken und Abhängigkeiten
- Java Development Kit (JDK) 8+  
- Maven für das Abhängigkeitsmanagement  

### Anforderungen an die Umgebung
- IDE wie IntelliJ IDEA oder Eclipse  
- Grundkenntnisse in Java  

### Wissensvoraussetzungen
- Vertrautheit mit dem Umgang von Dateien in Java  

## Einrichtung von GroupDocs.Viewer für Java
Fügen Sie das GroupDocs‑Repository und die Abhängigkeit zu Ihrer Maven‑`pom.xml` hinzu:

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
Erstellen Sie eine `Viewer`‑Instanz, die auf Ihre CAD‑Datei verweist:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Feature 1: Rendern von CAD‑Zeichnungen mit benutzerdefinierter Bildgröße und Hintergrundfarbe

### Wie man die CAD‑Hintergrundfarbe ändert
Dieses Feature ermöglicht es Ihnen, **DWG in PNG zu konvertieren**, während Sie eine benutzerdefinierte Breite angeben und einen neuen Hintergrundfarbton anwenden.

#### Schritt‑für‑Schritt‑Implementierung

##### Erforderliche Pakete importieren
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Ausgabe‑Verzeichnis und Dateipfad‑Format einrichten
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
- `setBackgroundColor(Color color)` – **setzt die PNG‑Hintergrundfarbe**, um die visuelle Konsistenz zu verbessern.

#### Tipps zur Fehlersuche
- Stellen Sie sicher, dass das Ausgabeverzeichnis existiert; erstellen Sie es bei Bedarf.  
- Überprüfen Sie den Eingabedateipfad und die Berechtigungen erneut.  

## Feature 2: Hintergrundfarbe in Rendering‑Optionen festlegen

### Wie man die PNG‑Hintergrundfarbe festlegt
Hier konzentrieren wir uns auf die **set background color PNG**‑Option, um sicherzustellen, dass jedes gerenderte Bild zu Ihrer Markenpalette passt.

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
- Verwenden Sie jede `Color`‑Konstante oder ein benutzerdefiniertes `new Color(r,g,b)` für individuelle Hintergründe.  

## Praktische Anwendungen

### 1. Technische Dokumentation
Benutzerdefiniertes Rendering stellt sicher, dass technische Zeichnungen den Unternehmensstilrichtlinien entsprechen.

### 2. Architektonische Visualisierung
Präsentieren Sie Baupläne mit einem sauberen Hintergrund, der zu den Präsentationsfolien passt.

### 3. Fertigungs‑Prototyping
Erzeugen Sie präzise PNGs für schnelle Prototyp‑Workflows.

### Integrationsmöglichkeiten
Kombinieren Sie diese Rendering‑Pipeline mit Dokumenten‑Management‑Systemen, um die automatische Erstellung visueller Assets zu ermöglichen.

## Leistungsüberlegungen

### Leistung optimieren
- **Stapelverarbeitung:** Rendern Sie mehrere CAD‑Dateien in einer Schleife.  
- **Ressourcenverwaltung:** Optimieren Sie die JVM‑Heap‑Größe für große Zeichnungen.

### Richtlinien zur Ressourcennutzung
Überwachen Sie CPU und Speicher; geben Sie `Viewer`‑Instanzen umgehend frei.

### Best Practices für das Java‑Speichermanagement
- Verwenden Sie try‑with‑resources (wie gezeigt), um `Viewer` automatisch zu schließen.  
- Vermeiden Sie es, große `Path`‑Objekte länger als nötig zu halten.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| **Ausgabeverzeichnis nicht gefunden** | Erstellen Sie das Verzeichnis im Voraus oder fügen Sie `Files.createDirectories(outputDirectory);` hinzu. |
| **Leeres Bild** | Stellen Sie sicher, dass `cadOptions.setBackgroundColor` nach `forRenderingByWidth` gesetzt wird. |
| **Out‑of‑Memory‑Fehler** | Erhöhen Sie die JVM‑Option `-Xmx` oder verarbeiten Sie Dateien in kleineren Stapeln. |

## Häufig gestellte Fragen

**Q: Können wir andere CAD‑Formate außer DWG rendern?**  
A: Ja, GroupDocs.Viewer unterstützt DXF, DWF und mehrere andere CAD‑Dateitypen.

**Q: Wie verwenden wir eine benutzerdefinierte RGB‑Farbe anstelle einer vordefinierten Konstante?**  
A: Erstellen Sie eine neue `Color`‑Instanz, z. B. `new Color(123, 45, 67)`, und übergeben Sie sie an `setBackgroundColor`.

**Q: Ist es möglich, nur ein bestimmtes Layout oder eine bestimmte Ebene zu rendern?**  
A: Sie können Layout‑ oder Ebenen‑Optionen über `CadOptions` festlegen, bevor Sie `viewer.view` aufrufen.

**Q: Unterstützt die Bibliothek transparente Hintergründe?**  
A: Setzen Sie die Hintergrundfarbe auf `new Color(0,0,0,0)` für volle Transparenz, falls das Zielformat dies unterstützt.

**Q: Welche Version von GroupDocs.Viewer wird benötigt?**  
A: Das Tutorial verwendet Version 25.2, aber neuere Versionen behalten dieselbe API bei.

---

**Zuletzt aktualisiert:** 2026-03-16  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs