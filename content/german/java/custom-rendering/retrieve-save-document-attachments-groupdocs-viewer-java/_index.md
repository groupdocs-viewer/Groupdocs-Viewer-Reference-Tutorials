---
date: '2026-06-30'
description: Erfahren Sie, wie Sie Dokumentenanhänge in Java-Anwendungen effizient
  mit java file output stream und der leistungsstarken GroupDocs.Viewer API abrufen
  und speichern.
keywords:
- java file output stream
- how to save attachment
- GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  headline: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  name: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  steps:
  - name: '**Create a Viewer Instance**'
    text: '**Create a Viewer Instance**'
  - name: '**Retrieve Attachments**'
    text: '**Retrieve Attachments**'
  - name: '**Understanding Parameters and Methods**'
    text: '**Understanding Parameters and Methods**'
  - name: '**Define the Output Directory**'
    text: '**Define the Output Directory**'
  - name: '**Save Attachments**'
    text: '**Save Attachments**'
  - name: '**Explain Parameters and Methods**'
    text: '**Explain Parameters and Methods**'
  - name: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
    text: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
  - name: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
    text: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
  - name: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
    text: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown earlier; the repository URL and version
      are all you need for a quick start.
    question: How do I install GroupDocs.Viewer in my Java project?
  - answer: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG,
      and many image types—so most common business files are covered.
    question: Can GroupDocs.Viewer handle all document types?
  - answer: Verify that the output path is correct, the directory exists, and your
      process has write permissions. Also ensure you’re using `FileOutputStream` correctly
      as shown.
    question: What if I encounter errors while saving attachments?
  - answer: Yes, a valid GroupDocs.Viewer license is required for production deployments.
      A free trial is available for evaluation.
    question: Is a license required for production use?
  - answer: Using `java file output stream` with buffered I/O efficiently handles
      large binaries; monitor memory usage and consider streaming in chunks for files
      larger than 200 MB.
    question: Does this approach work with large attachment files?
  type: FAQPage
title: Wie man Dokumentenanhänge mit java file output stream und GroupDocs.Viewer
  für Java abruft und speichert
type: docs
url: /de/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# Wie man Dokumentanhänge mit java file output stream und GroupDocs.Viewer für Java abruft und speichert

## Einleitung

Möchten Sie Dokumentanhänge programmgesteuert in Ihren Java‑Anwendungen mit **java file output stream** extrahieren und verwalten? Mit dem Aufkommen des digitalen Dokumentenmanagements ist es entscheidend, Werkzeuge zu haben, die diese Prozesse effizient vereinfachen. Hier kommt GroupDocs.Viewer für Java – Ihre Lösung, um Dokumentanhänge mühelos abzurufen und zu speichern.

![Dokumentanhänge mit GroupDocs.Viewer für Java abrufen und speichern](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[Dokumentanhänge mit GroupDocs.Viewer für Java abrufen und speichern](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

In diesem Tutorial erfahren Sie, wie Sie die Leistungsfähigkeit von GroupDocs.Viewer nutzen können, um Anhänge aus Dokumenten abzurufen und in ein gewünschtes Verzeichnis zu speichern. Wenn Sie den Anweisungen folgen, erwerben Sie praktische Fähigkeiten im effektiven Umgang mit Dokumentdaten in einer Java‑Umgebung und sehen genau **wie man Anhangsdateien** mit dem Standard‑`java file output stream` speichert.

## Schnelle Antworten
- **Was macht java file output stream?** Es schreibt Byte‑Streams direkt in Dateien und ermöglicht das Speichern binärer Daten (wie Anhänge) auf der Festplatte.  
- **Welche API ruft Anhänge ab?** `Viewer.getAttachments()` liefert eine Liste von Anhang‑Metadaten.  
- **Kann ich den Ausgabepfad angeben?** Ja – verwenden Sie `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine kostenpflichtige Lizenz erforderlich.  
- **Ist dieser Ansatz thread‑sicher?** Erstellen Sie pro Thread eine separate `Viewer`‑Instanz oder synchronisieren Sie den Zugriff.

## Was ist java file output stream?
`java.io.FileOutputStream` ist eine Kernklasse von Java, die rohe Bytes in eine Datei schreibt. Sie ist die ideale Wahl, wenn Sie binäre Inhalte wie E‑Mail‑Anhänge, Bilder oder andere Nicht‑Text‑Daten, die aus einem Dokument extrahiert wurden, persistieren müssen. Sie unterstützt das effiziente Schreiben sowohl kleiner als auch großer Dateien und kann mit gepufferten Streams für bessere Leistung kombiniert werden, wodurch eine zuverlässige Speicherung binärer Payloads auf der Festplatte gewährleistet wird.

## Warum java file output stream mit GroupDocs.Viewer verwenden?
Die Kombination von `java.io.FileOutputStream` und GroupDocs.Viewer ermöglicht Entwicklern, Anhang‑Bytes direkt auf die Festplatte zu schreiben, ohne Zwischenschritte der Konvertierung, und bewahrt so die ursprüngliche Dateiintegrität. Dieser Ansatz reduziert den Speicherverbrauch, beschleunigt die Verarbeitung großer Anhänge und vereinfacht den Code, indem er die Standard‑Java‑I/O‑Funktionen mit den leistungsstarken Extraktionsfähigkeiten von GroupDocs.Viewer nutzt.

- **Direkte Binärverarbeitung** – Keine Zwischenkonvertierungen nötig; die Anhang‑Bytes werden exakt so geschrieben, wie sie in der Quelldatei vorkommen.  
- **Performance** – Gestreamte Schreibvorgänge minimieren den Speicher‑Overhead, insbesondere bei großen Anhängen.  
- **Einfachheit** – Die API lässt sich nahtlos in die Standard‑Java‑I/O integrieren, wodurch der Code leicht les‑ und wartbar ist.

## Voraussetzungen
- **Erforderliche Bibliotheken und Abhängigkeiten**: Fügen Sie die GroupDocs.Viewer‑Bibliothek zu Ihrem Projekt hinzu (siehe Maven‑Snippet unten).  
- **Umgebungseinrichtung**: Eine Java‑IDE (IntelliJ IDEA, Eclipse usw.) mit installiertem JDK 8+.  
- **Vorkenntnisse**: Vertrautheit mit Java‑I/O, insbesondere `FileOutputStream`, und Grundkenntnisse in Maven.

## Einrichtung von GroupDocs.Viewer für Java
Um die GroupDocs.Viewer‑API in Ihrem Projekt zu verwenden, müssen Sie sie über Maven installieren. Fügen Sie die folgende Konfiguration zu Ihrer `pom.xml`‑Datei hinzu:

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

**Schritte zum Erwerb einer Lizenz:**
- **Kostenlose Testversion**: Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen zu erkunden.  
- **Temporäre Lizenz**: Holen Sie sich eine temporäre Lizenz für einen erweiterten Evaluierungszeitraum.  
- **Kauf**: Für den Produktionseinsatz benötigen Sie eine gekaufte Lizenz.

### Grundlegende Initialisierung und Einrichtung
Sobald GroupDocs.Viewer als Abhängigkeit in Ihrem Projekt hinzugefügt wurde, initialisieren Sie es in Ihrer Java‑Anwendung. So geht’s:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Diese Grundkonfiguration initialisiert GroupDocs.Viewer und bereitet es auf das Abrufen von Anhängen vor.

## Implementierungsleitfaden

### Dokumentanhänge mit java file output stream abrufen
Lassen Sie uns Schritt für Schritt durchgehen, wie Sie Anhänge mit GroupDocs.Viewer abrufen können. Diese Funktion ermöglicht das Extrahieren von Metadaten zu jedem Anhang, der in Ihrem Dokument enthalten ist.

#### Überblick
Das Abrufen von Anhängen erfolgt über die Methode `getAttachments`, die eine Liste von `Attachment`‑Objekten zurückgibt, die Details wie Dateiname und Größe enthalten. **Attachment** stellt eine in das Quell‑Dokument eingebettete Datei dar, z. B. ein Bild oder eine eingebettete Datei.

#### Implementierungsschritte
1. **Viewer-Instanz erstellen**  
   `Viewer` ist die Hauptklasse von GroupDocs.Viewer, die Dokumente lädt und für Rendering und Extraktion verarbeitet. Initialisieren Sie die `Viewer`‑Klasse mit dem Pfad zu Ihrem Dokument:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Anhänge abrufen**  
   Verwenden Sie die Methode `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Verstehen von Parametern und Methoden**  
   - `Viewer`: Akzeptiert einen Dateipfad oder Stream zum Dokument.  
   - `getAttachments()`: Liefert eine Liste eingebetteter Dateien und stellt Details wie Namen bereit.

### Dokumentanhänge in ein Verzeichnis speichern
Nachdem Sie gelernt haben, wie man Anhänge abruft, speichern wir sie in ein gewünschtes Verzeichnis mithilfe der GroupDocs.Viewer‑API und **java file output stream**.

#### Überblick
Diese Funktion speichert jede abgerufene Anhangsdatei in ein angegebenes Ausgabeverzeichnis.

#### Implementierungsschritte
1. **Ausgabeverzeichnis festlegen**  
   Richten Sie einen `outputDirectory`‑Pfad ein, in dem die Dateien gespeichert werden:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Anhänge speichern**  
   Verwenden Sie eine Schleife, um jeden Anhang mit der Methode `saveAttachment` zu speichern. **saveAttachment** schreibt den binären Inhalt eines `Attachment` in einen bereitgestellten `OutputStream`.

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Parameter und Methoden erklären**  
   - `saveAttachment`: Erwartet ein `Attachment`‑Objekt und einen File‑Output‑Stream, um den Anhang zu speichern.  
   - `FileOutputStream`: Verwaltet das Schreiben von Daten in Dateien nach den **java file output stream**‑Semantiken.

## Wie speichert man Anhänge mit java file output stream?
Laden Sie jedes `Attachment`‑Objekt, öffnen Sie einen `FileOutputStream` für die Zieldatei und streamen Sie die Anhang‑Bytes direkt auf die Festplatte. Dieser Ansatz schreibt das exakte binäre Payload ohne Transformation und garantiert, dass die gespeicherte Datei Byte‑für‑Byte mit dem Originalanhang übereinstimmt. Für große Anhänge sollten Sie den Stream in einen `BufferedOutputStream` einbetten, um den Durchsatz zu erhöhen und I/O‑Aufrufe zu reduzieren. **BufferedOutputStream** puffert Schreibvorgänge, reduziert die Anzahl der I/O‑Operationen und verbessert die Leistung bei großen Dateien.

### Häufige Probleme und Lösungen
- **Fehlende Abhängigkeiten**: Stellen Sie sicher, dass alle Maven‑Abhängigkeiten korrekt hinzugefügt wurden.  
- **Dateipfad‑Fehler**: Überprüfen Sie Pfade sowohl für Dokumente als auch für Ausgabeverzeichnisse sorgfältig.  
- **Zugriffsrechte**: Vergewissern Sie sich, dass Ihre Anwendung über die erforderlichen Lese‑/Schreibrechte verfügt.  

## Praktische Anwendungen
Der Einsatz von GroupDocs.Viewer in Java ist in vielen Szenarien äußerst wertvoll:

1. **E‑Mail‑Clients** – Automatisches Extrahieren von Anhängen aus E‑Mail‑Archiven zur Weiterverarbeitung oder Archivierung.  
2. **Dokumenten‑Management‑Systeme** – DMS durch das Abrufen und Organisieren eingebetteter Dateien erweitern.  
3. **Rechtsabteilungen** – Sicheres Extrahieren von beweisrelevanten Anhängen aus juristischen Dokumenten.  

Integrationsmöglichkeiten mit CRM, ERP oder eigenen Workflow‑Engines können Geschäftsprozesse weiter optimieren und die Anhangs‑Verarbeitung abteilungsübergreifend nahtlos gestalten.

## Leistungsüberlegungen
Um die Performance bei der Nutzung von GroupDocs.Viewer zu optimieren:

- **Dateiverarbeitung optimieren** – Verwenden Sie gepufferte Streams für große Dateien und schließen Sie Ressourcen umgehend.  
- **Speichermanagement** – Geben Sie `Viewer`‑Instanzen zeitnah frei (try‑with‑resources), um Speicherlecks zu vermeiden.  
- **Quantifizierter Nutzen** – GroupDocs.Viewer kann Dokumente bis zu 500 MB verarbeiten und bis zu 200 Anhänge pro Datei handhaben, während der Speicherverbrauch auf einer Standard‑8 GB‑JVM unter 150 MB bleibt.

Die Einhaltung bewährter Java‑Praktiken steigert die Effizienz Ihrer Anhang‑Verarbeitungspipeline erheblich.

## Fazit
Sie haben nun gelernt, wie man Dokumentanhänge mit **java file output stream** und GroupDocs.Viewer für Java abruft und speichert. Diese leistungsstarke API vereinfacht das Management von Dokumentdaten und ist ein unverzichtbares Werkzeug für Entwickler, die mit digitalen Dokumenten arbeiten. Um weitere Funktionen von GroupDocs.Viewer zu erkunden, probieren Sie weitere Features aus – etwa das Rendern von Seiten, das Konvertieren von Formaten oder das Extrahieren von Text. Bei Fragen oder Unterstützungsbedarf wenden Sie sich gerne über die offiziellen Ressourcen an uns.

## Häufig gestellte Fragen

**Q: Wie installiere ich GroupDocs.Viewer in meinem Java‑Projekt?**  
A: Fügen Sie die zuvor gezeigte Maven‑Abhängigkeit hinzu; die Repository‑URL und die Versionsangabe reichen für einen schnellen Start aus.

**Q: Kann GroupDocs.Viewer alle Dokumenttypen verarbeiten?**  
A: Es unterstützt über 50 Eingabe‑ und Ausgabeformate – darunter PDF, DOCX, PPTX, MSG und zahlreiche Bildformate – sodass die meisten gängigen Business‑Dateien abgedeckt sind.

**Q: Was tun, wenn beim Speichern von Anhängen Fehler auftreten?**  
A: Prüfen Sie, ob der Ausgabepfad korrekt ist, das Verzeichnis existiert und Ihr Prozess Schreibrechte besitzt. Stellen Sie außerdem sicher, dass Sie `FileOutputStream` wie gezeigt korrekt verwenden.

**Q: Ist für den Produktionseinsatz eine Lizenz erforderlich?**  
A: Ja, für den produktiven Einsatz ist eine gültige GroupDocs.Viewer‑Lizenz nötig. Eine kostenlose Testversion steht für die Evaluierung zur Verfügung.

**Q: Funktioniert dieser Ansatz bei großen Anhangsdateien?**  
A: Der Einsatz von `java file output stream` zusammen mit gepuffertem I/O verarbeitet große Binärdateien effizient; überwachen Sie den Speicherverbrauch und erwägen Sie das Streamen in Chunks für Dateien größer als 200 MB.

**Letzte Aktualisierung:** 2026-06-30  
**Getestet mit:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs  

## Verwandte Tutorials

- [Wie man Anhänge abruft und Dokumentanhänge mit GroupDocs.Viewer für Java druckt](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Dokumentanhänge in HTML rendern mit GroupDocs.Viewer Java: Eine Schritt‑für‑Schritt‑Anleitung](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [Custom Rendering Handler Java – GroupDocs Viewer Tutorial](/viewer/java/custom-rendering/)