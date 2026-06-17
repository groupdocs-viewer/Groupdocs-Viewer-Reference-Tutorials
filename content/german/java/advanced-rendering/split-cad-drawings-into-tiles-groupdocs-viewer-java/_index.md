---
date: '2026-04-01'
description: Erfahren Sie, wie Sie CAD‑Zeichnungen mit GroupDocs Viewer für Java in
  Kacheln aufteilen, um die Rendering‑Leistung zu steigern und die Handhabung großer
  Dateien zu vereinfachen.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Wie man CAD‑Zeichnungen mit GroupDocs Viewer in Kacheln aufteilt
type: docs
url: /de/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Wie man CAD-Zeichnungen in Kacheln aufteilt mit GroupDocs Viewer

Wenn Sie sich fragen **wie man CAD**-Dateien in kleinere, handlichere Stücke aufteilt, sind Sie hier genau richtig. In diesem Tutorial gehen wir die genauen Schritte durch, die nötig sind, um große CAD‑Zeichnungen in Kacheln zu splitten, und zwar mit **GroupDocs Viewer for Java**. Am Ende haben Sie eine sofort einsetzbare Lösung, die die Rendering‑Geschwindigkeit verbessert, den Speicherverbrauch reduziert und das Anzeigen von Zeichnungen in Web‑ oder Mobile‑Anwendungen erleichtert.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Schnelle Antworten
- **Was bewirkt das „Splitting CAD“?** Es zerlegt eine riesige Zeichnung in kleinere Bilder (Kacheln), die schneller laden und weniger Speicher verbrauchen.  
- **Welches Format wird für die Kacheln verwendet?** Standardmäßig werden PNG‑Dateien erzeugt, aber andere Formate werden über Viewer‑Optionen unterstützt.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testlizenz funktioniert für die Entwicklung; für die Produktion ist eine kostenpflichtige Lizenz erforderlich.  
- **Kann ich die Kachelgröße ändern?** Ja – passen Sie die Berechnungen von `tileWidth` und `tileHeight` an Ihre Bedürfnisse an.  
- **Ist dieser Ansatz thread‑sicher?** Das Rendern jeder Kachel in einer eigenen `Viewer`‑Instanz mit try‑with‑resources ist für parallele Ausführungen sicher.

## Was bedeutet „how to split CAD“?
Das Aufteilen von CAD bezeichnet das Zerlegen einer einzelnen, oft sehr großen CAD‑Zeichnung in mehrere rechteckige Abschnitte (Kacheln). Jede Kachel wird unabhängig gerendert, sodass Sie nur die Teile laden können, die ein Benutzer tatsächlich benötigt – ideal für Web‑Karten, Dokumentenportale und mobile Viewer.

## Warum GroupDocs Viewer für Java verwenden?
GroupDocs Viewer bietet sofortige Unterstützung für über 100 Dateiformate, darunter DWG, DXF und DWF. Seine Kachel‑API ermöglicht es, genaue Koordinaten anzugeben, sodass Sie exakt den Bereich rendern können, der Sie interessiert, ohne die gesamte Datei vorher zu verarbeiten. Das spart CPU‑Zyklen, reduziert den Bandbreitenverbrauch und sorgt für ein flüssigeres Benutzererlebnis.

## Voraussetzungen
- **Libraries**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Any recent Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse oder eine andere Java‑kompatible IDE.  
- **Build Tool**: Maven (andere Build‑Tools funktionieren, solange die Abhängigkeit hinzugefügt wird).  

## Einrichtung von GroupDocs.Viewer für Java
Fügen Sie das GroupDocs‑Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu:

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
GroupDocs Viewer bietet eine kostenlose Testlizenz zur Evaluierung:

- **Kostenlose Testversion**: Besuchen Sie [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/), um die Bibliothek herunterzuladen.  
- **Temporäre Lizenz**: Beantragen Sie sie auf der [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Vollständige Lizenz**: Kaufen Sie eine Produktionslizenz auf der [Purchase Page](https://purchase.groupdocs.com/buy).

### Grundlegende Initialisierung
Erstellen Sie eine einfache `Viewer`‑Instanz, um zu überprüfen, ob die Bibliothek korrekt geladen wird:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Schritt‑für‑Schritt‑Anleitung zum Aufteilen von CAD‑Zeichnungen in Kacheln

### Schritt 1: Definieren des Ausgabeverzeichnisses
Wir speichern jede Kachel als separate PNG‑Datei. Eine Hilfsmethode hält die Pfadlogik sauber und wiederverwendbar.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Schritt 2: Konfigurieren der Ansichtoptionen
Setzen Sie das Render‑Format auf PNG und verhindern Sie, dass der Viewer jede Seite vorab lädt (spart Speicher).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Schritt 3: Berechnen der Kachelabmessungen
Zuerst ermitteln wir die ursprüngliche Breite und Höhe der Zeichnung und teilen sie dann in vier gleich große Quadranten auf.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Schritt 4: Rendern und Speichern der Kacheln
Fügen Sie die berechneten Kacheln zu den Render‑Optionen hinzu und lassen Sie den `Viewer` die PNG‑Dateien erzeugen.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Tipps zur Fehlerbehebung
- **Build‑Pfad** – Stellen Sie sicher, dass die GroupDocs‑JAR‑Dateien im Klassenpfad liegen.  
- **Berechtigungen** – Der Ausgabordner muss vom Java‑Prozess beschreibbar sein.  
- **Ausnahmen** – Wenn Sie `ViewerException` sehen, prüfen Sie, ob die DWG‑Datei beschädigt ist und ob die korrekte Lizenz angewendet wurde.

## Häufige Anwendungsfälle für das Aufteilen von CAD‑Kacheln
1. **Web‑Mapping** – Laden Sie nur den sichtbaren Teil eines Grundrisses, wenn der Benutzer schwenkt/zoomt.  
2. **Dokumentenmanagement** – Speichern Sie jede Kachel separat für schnellere Vorschauregeneration.  
3. **Mobile Ansicht** – Reduzieren Sie die Bandbreite, indem Sie nur die für den aktuellen Bildschirm benötigten Kacheln herunterladen.

## Leistungsüberlegungen
- **Kachelgröße** – Größere Kacheln bedeuten weniger Dateien, aber langsameres Rendering; finden Sie ein Gleichgewicht basierend auf den UI‑Anforderungen.  
- **Speicherüberwachung** – Nutzen Sie Java‑Profiling‑Tools (z. B. VisualVM), um den Heap‑Verbrauch bei der Verarbeitung sehr großer Zeichnungen zu beobachten.  
- **Ressourcen‑Aufräumen** – Das oben gezeigte try‑with‑resources‑Muster gibt native Ressourcen automatisch frei.

## Häufig gestellte Fragen

**Q: Kann ich andere Dateitypen (PDF, Bilder) mit demselben Ansatz in Kacheln aufteilen?**  
A: Ja. GroupDocs Viewer unterstützt viele Formate; Sie müssen lediglich die entsprechende Options‑Klasse verwenden (z. B. `PdfViewOptions`).

**Q: Wie ändere ich die Bildqualität der Ausgabe?**  
A: Passen Sie `viewOptions.setResolution(int dpi)` an oder setzen Sie Kompressionseinstellungen im `PngOptions`‑Objekt.

**Q: Meine Anwendung läuft bei sehr großen DWG‑Dateien out of memory – was kann ich tun?**  
A: Reduzieren Sie die Kachelabmessungen, erhöhen Sie den JVM‑Heap (`-Xmx`) oder rendern Sie Kacheln sequenziell in separaten `Viewer`‑Instanzen.

**Q: Ist es möglich, Kacheln asynchron zu rendern?**  
A: Absolut. Verpacken Sie jeden Render‑Aufruf in ein `CompletableFuture` oder nutzen Sie einen Executor‑Service, um die Arbeit zu parallelisieren.

**Q: Benötige ich für jede Kachel eine separate Lizenz?**  
A: Nein. Eine einzige gültige GroupDocs Viewer‑Lizenz deckt alle Rendering‑Operationen innerhalb Ihrer Anwendung ab.

## Ressourcen
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase a License](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-04-01  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

---