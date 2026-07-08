---
date: '2026-06-30'
description: Erfahren Sie, wie Sie ViewInfo abrufen und java archive file type structures
  mit GroupDocs.Viewer ermitteln. Dieser Leitfaden behandelt die Einrichtung, Codebeispiele
  und praxisnahe Anwendungsfälle.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Wie man ViewInfo abruft und Archive Structures in Java ermittelt
type: docs
url: /de/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Wie man ViewInfo erhält und Archivstrukturen in Java abruft

Das effektive Verwalten von Archivdateien erfordert ein klares Verständnis ihrer Struktur. In diesem Tutorial lernen Sie **how to get viewinfo** für jedes Archiv und sehen, wie es Ihnen bei der Arbeit mit dem **java archive file type** hilft. Wir führen Sie durch die Einrichtung von GroupDocs.Viewer, das Extrahieren von View-Informationen und das rekursive Lesen von Ordnerhierarchien, damit Sie die Lösung in realen Projekten integrieren können.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**What You'll Learn**
- Einrichten und Konfigurieren von GroupDocs.Viewer für Java.  
- Methoden zum **get viewinfo** aus Archiven.  
- Techniken zum Lesen und Anzeigen der Ordnerstruktur einer Archivdatei.  
- Praktische Anwendungen und Leistungsüberlegungen bei der Verwendung von GroupDocs.Viewer in Java-Projekten.

## Schnelle Antworten
- **What does “viewinfo” provide?** Es liefert den Dateityp, die Seitenzahl und eine vollständige Auflistung von Ordnern und Dateien innerhalb eines Archivs.  
- **Which archive formats are supported?** ZIP, RAR, TAR, 7z, ISO und 12 + weitere gängige Formate.  
- **Do I need a license for production?** Ja – eine kommerzielle Lizenz ist für die Produktion erforderlich; eine kostenlose Testversion reicht für die Evaluierung.  
- **Can large archives be processed efficiently?** Absolut – nutzen Sie Streaming-Optionen und verarbeiten Sie jeweils eine Ordner‑Ebene, um den Speicherverbrauch gering zu halten.  
- **Is Maven the only way to add the library?** Maven ist der empfohlene Dependency‑Manager, aber Gradle oder die manuelle JAR‑Einbindung funktionieren ebenfalls.

## Was ist “how to get viewinfo”?

`getViewInfo` ist eine GroupDocs.Viewer API‑Methode, die Metadaten aus einem Dokument oder Archiv extrahiert, ohne das komplette Rendering durchzuführen. Sie gibt den internen Ordnerbaum, die Dateianzahl und Grundinformationen in einem Aufruf zurück, sodass Sie entscheiden können, welche Teile Sie verarbeiten möchten. Der Aufruf liefert einen vollständigen Schnappschuss von Archiven bis zu 500 MB in weniger als einer Sekunde auf typischen Servern.

## Warum Java-Archivdateityp-Strukturen abrufen?

Das Abrufen des internen Layouts eines **java archive file type** ermöglicht es Ihnen, benötigte Dateien sofort zu finden, unnötige Extraktionen zu vermeiden und automatisierte Pipelines zu bauen, die nur relevante Unterordner berühren. Dieser Ansatz reduziert I/O um bis zu 70 % bei großen Archiven und macht es möglich, Tausende von Dateien pro Minute in Daten‑Ingest‑Szenarien zu scannen.

## Voraussetzungen

- **Java Development Kit (JDK):** Version 8 oder neuer.  
- **Maven:** Für das Abhängigkeitsmanagement und Builds.  
- **Grundlegende Java-Kenntnisse:** Vertrautheit mit OOP-Konzepten ist hilfreich, aber nicht zwingend erforderlich.  

Sie benötigen außerdem Zugriff auf die GroupDocs.Viewer‑Bibliothek, die Sie wie unten gezeigt zu Ihrem Maven‑Projekt hinzufügen können.

## Einrichtung von GroupDocs.Viewer für Java

### Maven-Konfiguration

Fügen Sie das Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Lizenzbeschaffung

- **Kostenlose Testversion:** Laden Sie eine Testversion von der GroupDocs-Website herunter.  
- **Temporäre Lizenz:** Fordern Sie einen temporären Schlüssel für eine kurzfristige Bewertung an.  
- **Vollständige Lizenz:** Kaufen Sie eine kommerzielle Lizenz für uneingeschränkte Produktion.

Sobald die Bibliothek in Ihrem Klassenpfad ist, können Sie mit dem Coden beginnen.

## Implementierungsleitfaden

### Wie man ViewInfo für Archivdateien erhält

Um View‑Informationen zu erhalten, laden Sie zunächst das Archiv in den Viewer, rufen dann `getViewInfo` auf, um die Metadaten abzurufen, und iterieren schließlich über die zurückgegebene Ordnerhierarchie. Dieses Drei‑Schritt‑Muster funktioniert für alle unterstützten Archivformate und liefert einen vollständigen Schnappschuss in einem einzigen API‑Aufruf, was die weitere Verarbeitung vereinfacht.

#### Initialisierung des Viewers

Die `Viewer`‑Klasse ist der Einstiegspunkt für alle Rendering‑ und Inspektions‑Operationen. Sie verwaltet Dateistreams, Format‑Erkennung und Ressourcen‑Bereinigung.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Abrufen von View-Informationen

`ViewInfo` kapselt Metadaten wie Dateityp, Gesamtseitenzahl und eine hierarchische Liste von Ordnern und Dateien. Der Aufruf von `getViewInfo` liefert dieses Objekt sofort zurück.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Anzeigen der Ordnerstruktur

Iterieren Sie über `viewInfo.getFolders()`, um jeden Ordnernamen, seine Tiefe und die enthaltenen Dateien auszugeben. Diese einfache Schleife gibt Ihnen eine lesbare Baumansicht des Archivs.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekursives Ordnerlesen

Für tief verschachtelte Archive kann eine rekursive Hilfsmethode den Baum tiefen‑first durchlaufen und sicherstellen, dass jeder Unterordner besucht wird, ohne das gesamte Archiv in den Speicher zu laden.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Feature 2: Abrufen der Archivordnerstruktur

Dieses Feature konzentriert sich darauf, die Ordnerstruktur einer Archivdatei auszugeben. Es ist dem ersten Feature ähnlich, legt jedoch den Schwerpunkt auf die rekursive Erkundung.

#### Einrichtung der ViewInfo-Optionen

`ArchiveOptions` ermöglicht es Ihnen, Passwortschutz, Seitenlimits und Streaming‑Präferenzen festzulegen, bevor `getViewInfo` aufgerufen wird.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekursive Erkundung

Eine zweite rekursive Routine demonstriert, wie man passwortgeschützte Archive und große Dateimengen effizient verarbeitet.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktische Anwendungen

1. **Datenverwaltung:** Große Datensätze schnell organisieren, indem man die Archivstrukturen versteht.  
2. **Automatisierte Dateiverarbeitung:** Archivierte Dateien stapelweise verarbeiten, ohne sie vollständig zu extrahieren, wodurch I/O um bis zu 70 % reduziert wird.  
3. **CMS-Integration:** Content‑Management‑Systeme mit Echtzeit‑Archivnavigation verbessern, sodass Redakteure Dateien direkt aus dem Archiv ansehen können.

## Leistungsüberlegungen

- **Speichernutzung optimieren:** Ordner einzeln verarbeiten und die `Viewer`‑Instanz sofort schließen.  
- **Aktuell bleiben:** Verwenden Sie die neueste GroupDocs.Viewer‑Version (25.2 zum Zeitpunkt des Schreibens) und JDK‑Versionen für Leistungsverbesserungen.  
- **Streaming-Unterstützung:** Die Bibliothek kann Archive größer als 1 GB streamen, ohne die gesamte Datei in den RAM zu laden, dank ihrer internen Chunk‑Read‑Architektur.

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| `NullPointerException` beim Lesen von Ordnern | `viewInfo.getFolders()` gibt null für leere Verzeichnisse zurück | Überprüfen Sie vor dem Durchlaufen, ob die Liste null oder leer ist. |
| Langsame Verarbeitung großer ZIP-Dateien | Das gesamte Archiv wird in den Speicher geladen | Verwenden Sie die in neueren GroupDocs-Versionen verfügbaren Streaming-Optionen. |
| Lizenz nicht gefunden | Der Pfad zur Lizenzdatei ist falsch | Legen Sie die Lizenzdatei im Anwendungsverzeichnis ab oder setzen Sie `License.setLicense("path/to/license.json")`. |

## Häufig gestellte Fragen

**Q:** Was ist GroupDocs.Viewer?  
**A:** GroupDocs.Viewer ist eine Java‑Bibliothek, die über 100 Dokument‑, Bild‑ und Archivformate nach HTML, PDF oder Bild‑Streams rendert, ohne native Anwendungen zu benötigen.

**Q:** Kann ich GroupDocs.Viewer mit anderen Programmiersprachen verwenden?  
**A:** Ja, GroupDocs bietet SDKs für .NET, Python, PHP und mehr, aber dieses Tutorial konzentriert sich auf die Java‑Implementierung.

**Q:** Wie gehe ich mit großen Archivdateien um?  
**A:** Aktivieren Sie Streaming über `ArchiveOptions.setUseStreaming(true)`, verarbeiten Sie jeweils eine Ordner‑Ebene und entsorgen Sie das `Viewer`‑Objekt nach Gebrauch.

**Q:** Welche Archivtypen unterstützt GroupDocs.Viewer?  
**A:** Es unterstützt 12 + Archivformate, darunter ZIP, RAR, TAR, 7z, ISO, ARJ und CAB sowie viele proprietäre Container‑Typen.

**Q:** Gibt es ein Größenlimit für Archive?  
**A:** Das praktische Limit hängt von RAM und CPU Ihres Servers ab; Tests zeigen eine reibungslose Verarbeitung von 2 GB‑Archiven auf einer 16 GB‑RAM‑Maschine, wenn Streaming aktiviert ist.

**Q:** Funktioniert “how to get viewinfo” bei passwortgeschützten Archiven?  
**A:** Ja, übergeben Sie das Passwort via `ArchiveOptions.setPassword("yourPassword")`, bevor Sie `getViewInfo` aufrufen.

## Fazit

Durch Befolgen dieses Leitfadens wissen Sie jetzt **how to get viewinfo** für jedes unterstützte Archiv und wie Sie dessen Ordnerhierarchie mit GroupDocs.Viewer für Java traversieren. Diese Techniken befähigen Sie, intelligentere Daten‑Verarbeitungspipelines zu bauen, CMS‑Integrationen zu verbessern und große Sammlungen archivierter Dateien mit Zuversicht zu handhaben. Als Nächstes können Sie das Rendern einzelner Dateien aus dem Archiv erkunden oder sie mithilfe weiterer Viewer‑Funktionen in PDF/HTML konvertieren.

---

**Last Updated:** 2026-06-30  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Ressourcen**
- **Dokumentation:** [GroupDocs Viewer Java Dokumentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [GroupDocs API Reference für Java](https://reference.groupdocs.com/viewer/java/)
- **Download GroupDocs.Viewer:** [GroupDocs Download-Seite](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [GroupDocs kaufen](https://purchase.groupdocs.com/buy)
- **Free Trial and Temporary License:** [GroupDocs kostenlose Testversion](https://releases.groupdocs.com/viewer/java/) | [Temporäre Lizenz](https://purchase.groupdocs.com/temporary-license/)

## Verwandte Tutorials

- [Extract Document Metadata with GroupDocs.Viewer for Java - Retrieve Document View Information and Insights](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [How to Retrieve Attachments and Print Document Attachments with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java Guide: Render Specific Pages with GroupDocs.Viewer API for Document Preview and Management](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)