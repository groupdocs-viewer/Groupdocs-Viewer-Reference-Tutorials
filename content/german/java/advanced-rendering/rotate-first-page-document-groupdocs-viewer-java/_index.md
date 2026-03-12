---
date: '2026-01-18'
description: Erfahren Sie, wie Sie mit GroupDocs Viewer eine Seite in Java um 90 Grad
  drehen, inklusive Einrichtung, Code und Leistungstipps.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Seite um 90 Grad drehen mit GroupDocs Viewer für Java
type: docs
url: /de/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Seite um 90 Grad drehen mit GroupDocs Viewer für Java

Wenn Sie eine **Seite um 90 Grad drehen** müssen – egal ob es sich um ein PDF, eine Word-Datei oder eine Tabellenkalkulation handelt – spart das programmatische Vorgehen Zeit und eliminiert manuelle Fehler. In diesem fortgeschrittenen Leitfaden führen wir Sie Schritt für Schritt durch die genauen Schritte, um die erste Seite eines vollständig unterstützten Dokuments mit **GroupDocs Viewer für Java** zu drehen. Am Ende haben Sie ein wiederverwendbares Snippet, das Sie in Ihre eigenen Projekte einbinden können.

![Erste Seite eines Dokuments mit GroupDocs.Viewer für Java drehen](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Schnelle Antworten
- **Was bedeutet „Seite um 90 Grad drehen“?** Es dreht die ausgewählte Seite im Uhrzeigersinn um ein Viertel.
- **Welche Bibliothek führt die Drehung aus?** GroupDocs Viewer für Java stellt die Methode `rotatePage` bereit.
- **Kann ich PDF-Seiten mit Java drehen?** Ja – verwenden Sie denselben `rotatePage`-Aufruf; Er funktioniert für PDF, DOCX, XLSX und weitere Formate.
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; Für den Produktionseinsatz ist eine kostenpflichtige Lizenz erforderlich.
- **Ist der Vorgang speicherintensiv?** Nicht, wenn Sie die `Viewer`-Instanz sofort schließen; siehe die Leistungstipps unten.

## Was ist „Seite um 90 Grad drehen“?
Das Drehen einer Seite um 90 Grad richtet die Seite von Hochformat zu Querformat (oder umgekehrt) neu aus, ohne den zugrunde liegenden Inhalt zu verändern. Das ist besonders praktisch für Präsentationen, den Druck ausschließlich im Querformat vorliegender Grafiken oder das Korrigieren von gescannten Dokumenten, die seitlich aufgenommen wurden.

## Warum Seiten mit GroupDocs Viewer für Java drehen?
GroupDocs Viewer abstrahiert die Komplexität der Verarbeitung von Dutzenden Dateiformaten. Es ermöglicht Ihnen, Seitentransformationen – wie das Drehen – anzuwenden, während die Originaldatei unverändert bleibt. Die API ist flüssig, threadsicher und funktioniert auf jeder Java8+ Laufzeit.

## Voraussetzungen

- **GroupDocs.Viewer für Java** (neueste Version)
- **JDK8** oder neuer
- **Maven** (oder Gradle) für das Abhängigkeitsmanagement
– Eine IDE wie IntelliJ IDEA oder Eclipse
- Grundkenntnisse mit Java I/O

## Einrichten von GroupDocs.Viewer für Java

Fügen Sie das GroupDocs-Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu. Dieser Codeabschnitt bleibt gegenüber dem Original-Tutorial unverändert:

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

### Lizenzerwerb
- **Kostenlose Testversion** – Download von der GroupDocs‑Website.
- **Temporäre Lizenz** – Anfordern, wenn Sie einen verlängerten Evaluierungszeitraum benötigen.
- **Vollständige Lizenz** – Kauf für den Produktionseinsatz.

### Grundlegende Viewer-Initialisierung
Der folgende Code zeigt die minimalste Art, eine „Viewer“-Instanz zu erstellen. Belassen Sie ihn genau wie gezeigt:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Schrittweise Umsetzung: Drehen Sie die erste Seite um 90 Grad

### 1. Importieren Sie die erforderlichen Pakete
Diese Importe geben Ihnen Zugriff auf PDF-Renderoptionen und das Rotations-Enum.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definieren Sie Ausgabeorte und erstellen Sie den Viewer
Ersetzen Sie die Platzhalter-Pfade durch Ihre tatsächlichen Verzeichnisse.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Konfigurieren Sie die PDF-Ansichtsoptionen und wenden Sie die Drehung an
Die Methode `rotatePage` nimmt die Seitennummer (1‑basiert) und einen `Rotation`‑Enum‑Wert.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Rendern Sie das Dokument
Rufen Sie schließlich „view“ auf, um das gedrehte PDF zu erzeugen.

```java
viewer.view(viewOptions);
```

#### Wie es funktioniert
- **PdfViewOptions** teilt dem Viewer mit, eine PDF-Datei auszugeben.
- **rotatePage(int, Rotation)** dreht nur die angegebene Seite und lässt den Rest unverändert.
- Die Methode unterstützt `ON_90_DEGREE`, `ON_180_DEGREE` und `ON_270_DEGREE`.

## Häufige Probleme und Lösungen
| Symptom | Wahrscheinliche Ursache | Fix |
|---------|--------------|-----|
| **FileNotFoundException** | Falscher Pfad oder fehlender Ordner | Stellen Sie sicher, dass „YOUR_OUTPUT_DIRECTORY“ und „YOUR_DOCUMENT_DIRECTORY“ existieren und lesbar sind. |
| **Nicht unterstütztes Dateiformat** | Versuchen Sie, ein Format zu drehen, das vom Viewer nicht unterstützt wird | Überprüfen Sie die Seite [GroupDocs Viewer unterstützte Formate]. |
| **Keine Rotation sichtbar** | Verwendung einer falschen Seitennummer (0‑basiert) | Denken Sie daran, dass `rotatePage` **1‑basiertes** Indexieren verwendet. |
| **Fehler wegen unzureichendem Arbeitsspeicher bei großen Dokumenten** | Viele große Dateien in einem einzelnen Thread rendern | Verarbeiten Sie Dokumente sequenziell oder verwenden Sie einen Thread-Pool mit begrenzter Parallelität. |

## Praktische Anwendungen

1. **Präsentationsanpassungen** – Konvertieren Sie eine Hochformat-Folien sofort in Querformat.
2. **Massenkorrektur von Dokumenten** – Automatisieren Sie das Korrigieren von gescannten PDFs, die seitlich aufgenommen wurden.
3. **Druckfertige Ausgabe** – Stellen Sie sicher, dass Querformat‑Grafiken korrekt auf hochformatigem Papier gedruckt werden.

## Leistungstipps

- **Ressourcen sofort schließen** – Der `try-with-resources`-Block gibt die `Viewer`-Instanz automatisch frei.
- **Batch-Verarbeitung** – Beim Umgang mit vielen Dateien verwenden Sie eine einzelne `Viewer`-Instanz pro Thread, um den Overhead zu reduzieren.
- **Speicher überwachen** – Bei Dokumenten größer als 100 MB sollten Sie in Erwägung ziehen, die Ausgabe auf die Festplatte zu streamen, anstatt sie im Speicher zu behalten.

## Häufig gestellte Fragen

**F: Kann ich mehrere Seiten gleichzeitig drehen?**
A: Ja – rufen Sie „rotatePage()“ für jede Seitennummer auf, die Sie drehen müssen.

**F: Gibt es eine Möglichkeit, die Drehung nach dem Rendern rückgängig zu machen?**
A: Nicht direkt. Sie müssten das Dokument erneut rendern, ohne die Rotationsoptionen zu verwenden.

**F: Welche Dateiformate unterstützen die Seitendrehung im GroupDocs Viewer?**
A: DOCX, PDF, PPTX, XLSX und viele weitere Formate, die in der offiziellen Dokumentation aufgeführt sind.

**F: Wie kann ich Seiten in einem Stapel von Dokumenten automatisch drehen?**
A: Verpacken Sie den Code in einer Schleife, die über eine Sammlung von Dateipfaden iteriert und für jede Datei dieselbe `rotatePage`-Logik anwendet.

**F: Was ist die bewährte Vorgehensweise beim Umgang mit Fehlern während der Drehung?**
A: Umschließen Sie die Nutzung des Viewers mit einem `try-catch`-Block, protokollieren Sie die Ausnahme und fahren Sie optional mit der nächsten Datei fort.

## Ressourcen

- **Dokumentation**: [GroupDocs Viewer Java-Dokumentation](https://docs.groupdocs.com/viewer/java/)
- **API-Referenz**: [GroupDocs API-Referenz](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer für Java herunterladen](https://releases.groupdocs.com/viewer/java/)
- **Lizenz erwerben**: [Lizenz kaufen](https://purchase.groupdocs.com/buy)
- **Kostenlose Testversion**: [Kostenlos testen](https://releases.groupdocs.com/viewer/java/)
- **Temporäre Lizenz**: [Temporäre Lizenz anfordern](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Letzte Aktualisierung:** 18.01.2026
**Getestet mit:** GroupDocs Viewer 25.2 für Java
**Autor:** GroupDocs  

---