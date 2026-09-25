---
date: '2026-09-25'
description: Erfahren Sie, wie Sie mit GroupDocs Viewer for Java eine HTML-Ansicht
  für MPP erstellen und Projektdokumente nach Zeitintervallen rendern, mit Schritt‑für‑Schritt‑Code.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Erstellen Sie mit GroupDocs Viewer for Java eine HTML-Ansicht für
  MPP, um Microsoft Project‑Dateien nach bestimmten Zeitintervallen zu rendern. Befolgen
  Sie die Schritt‑für‑Schritt‑Einrichtung, Lizenzierung und Code‑Beispiele für eine
  präzise Zeitstrahl‑Visualisierung.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: HTML-Ansicht für MPP mit GroupDocs Viewer for Java erstellen
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: HTML-Ansicht für MPP mit GroupDocs Viewer (Java) erstellen
type: docs
url: /de/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Wie man GroupDocs Viewer verwendet, um Projektdokumente nach Zeitintervallen in Java zu rendern

In diesem Tutorial lernen Sie, wie Sie **create html view mpp** mit GroupDocs Viewer für Java erstellen, sodass Sie nur die Teile einer Microsoft Project‑Datei rendern können, die in einen bestimmten Start‑ und End‑Datumsbereich fallen. Wir führen Sie durch die Maven‑Einrichtung, Lizenzierung und die genauen API‑Aufrufe, die Sie benötigen, um präzise Zeitstrahl‑Ansichten direkt in Ihre Anwendungen einzubetten.

![Projektdokumente nach Zeitintervallen mit GroupDocs.Viewer für Java rendern](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Für eine Vorschau siehe den [Projektdokumente nach Zeitintervallen mit GroupDocs.Viewer für Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Schnelle Antworten
- **Was macht die Funktion?** Sie rendert nur den Teil einer Microsoft Project‑Datei, der zwischen einem Start‑ und Enddatum liegt.  
- **Welches Ausgabeformat wird verwendet?** HTML mit eingebetteten Ressourcen, ideal für die Web‑Integration.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich den Datumsbereich zur Laufzeit ändern?** Ja – passen Sie die Werte `setStartDate` und `setEndDate` in den Rendering‑Optionen an.  
- **Wird dies von allen Java‑Versionen unterstützt?** Funktioniert mit Java 8+ solange Sie GroupDocs.Viewer 25.2 oder neuer verwenden.

## Was ist create html view mpp?
`create html view mpp` ist der Prozess, eine Microsoft Project‑Datei (`.mpp` oder `.mpt`) in eine Reihe von HTML‑Seiten zu konvertieren, die den Zeitplan darstellen. GroupDocs Viewer führt die Konvertierung serverseitig aus, sodass Sie den Zeitstrahl in jedem Browser anzeigen können, ohne Microsoft Project zu installieren.

## Warum Projektdokumente mit Zeitintervallen rendern?
Das Rendern nur des benötigten Zeitintervalls reduziert die Größe des erzeugten HTML, beschleunigt das Laden der Seite und ermöglicht es Ihnen, sich auf die spezifische Projektphase zu konzentrieren, die Sie analysieren möchten. Diese gezielte Ansicht ist ideal für Dashboards, Statusberichte oder die Einbettung in benutzerdefinierte PM‑Tools, bei denen vollständige Projektdaten überwältigend wären.

## Voraussetzungen

- **GroupDocs.Viewer für Java** Version 25.2 oder höher.  
- Java Development Kit (JDK) 8 oder neuer.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Grundkenntnisse in Maven.  

## Einrichtung von GroupDocs.Viewer für Java

### Maven‑Abhängigkeit

Fügen Sie das Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu:

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

### Schritte zum Erwerb einer Lizenz

1. **Kostenlose Testversion** – Laden Sie eine Testversion von der [GroupDocs-Downloadseite](https://releases.groupdocs.com/viewer/java/) herunter.  
2. **Temporäre Lizenz** – Erhalten Sie eine temporäre Lizenz für erweiterte Tests über die [temporäre‑Lizenz‑Seite](https://purchase.groupdocs.com/temporary-license/).  
3. **Kauf** – Für uneingeschränkte Produktion kaufen Sie eine Lizenz auf der [GroupDocs-Kaufseite](https://purchase.groupdocs.com/buy).

## Grundlegende Viewer‑Initialisierung

`Viewer` ist die Hauptklasse in GroupDocs.Viewer für Java, die ein Dokument lädt und Rendering‑Funktionen bereitstellt.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Abrufen von View‑Informationen für Projektdateien

`ProjectManagementViewInfo` liefert Metadaten zu einer Microsoft Project‑Datei, einschließlich des Gesamtschedule‑Start‑ und Enddatums.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## HTML‑Rendering‑Optionen konfigurieren (HTML aus Projekt generieren)

`HtmlViewOptions` konfiguriert, wie GroupDocs HTML rendert, sodass Sie den Datumsbereich festlegen, Ressourcen einbetten und das Erscheinungsbild anpassen können.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Ausführen des Rendering‑Prozesses

`viewer.render` führt die Konvertierung basierend auf den angegebenen Optionen aus und schreibt die resultierenden HTML‑Dateien in das Zielverzeichnis.

```java
viewer.view(viewOptions);
```

## Häufige Fallstricke & Fehlersuche

- **Falsche Dateipfade** – Überprüfen Sie, dass sowohl die Quell‑`.mpp`‑Datei als auch das Ausgabeverzeichnis existieren.  
- **Nicht unterstützter Dateityp** – Stellen Sie sicher, dass das Dokument ein unterstütztes Project‑Format ist (z. B. `.mpp`, `.mpt`).  
- **Lizenzfehler** – Eine Testlizenz kann Rendering‑Grenzen setzen; wechseln Sie zu einer Voll‑Lizenz für uneingeschränkte Nutzung.  

## Praktische Anwendungen

1. **Analyse des Projektzeitstrahls** – Zeigen Sie Stakeholdern nur die aktuelle Phase.  
2. **Automatisierte Berichterstellung** – Generieren Sie zeitlich begrenzte HTML‑Berichte für wöchentliche Status‑Updates.  
3. **Integration in Dashboards** – Betten Sie die gerenderten Seiten in BI‑Tools oder benutzerdefinierte Portale ein.  
4. **Archivierung** – Speichern Sie einen web‑freundlichen Schnappschuss des Projektzeitplans für zukünftige Referenz.  

## Leistungstipps

- Verwenden Sie die Option *eingebettete Ressourcen*, um jede HTML‑Seite eigenständig zu halten und HTTP‑Anfragen zu reduzieren.  
- Bei sehr großen Projekten sollten Sie das Rendering in kleineren Datumsabschnitten durchführen, um den Speicherverbrauch gering zu halten. Das Rendern eines ein‑jährigen Abschnitts kann die HTML‑Größe im Vergleich zum vollständigen Projekt‑Export um bis zu 80 % reduzieren und die Ladezeit von mehreren Sekunden auf unter eine Sekunde auf typischen Servern senken.  
- Bereinigen Sie temporäre Dateien nach dem Bereitstellen, um Speicherplatzverschwendung zu vermeiden.  

## Fazit

Sie wissen jetzt, **wie man GroupDocs** Viewer verwendet, um Projektdokumente innerhalb eines bestimmten Zeitintervalls zu rendern und **HTML aus Projektdaten** in Java zu erzeugen. Diese Fähigkeit vereinfacht Zeitstrahl‑Visualisierungen, verbessert die Reporting‑Effizienz und lässt sich nahtlos in moderne Web‑Anwendungen integrieren.

### Nächste Schritte
- Entdecken Sie weitere Viewer‑Funktionen wie Wasserzeichen, Passwortschutz oder benutzerdefiniertes CSS‑Styling.  
- Kombinieren Sie diese Rendering‑Pipeline mit einer REST‑API, um zeitgesteuerte Ansichten auf Abruf bereitzustellen.  

## Häufig gestellte Fragen

**F: Welche Dateiformate unterstützt GroupDocs.Viewer?**  
GroupDocs.Viewer unterstützt über 100 Eingabeformate, darunter PDF, DOCX, XLSX, PPTX und Microsoft Project‑Dateien, wodurch eine universelle Dokumentenvisualisierung ermöglicht wird.

**F: Wie beginne ich mit einer kostenlosen Testversion von GroupDocs.Viewer?**  
Sie können die Testversion von der [GroupDocs Viewer Java‑Downloadseite](https://releases.groupdocs.com/viewer/java/) herunterladen.

**F: Kann ich Dokumente rendern, ohne Ressourcen einzubetten?**  
Ja, Sie können eine andere HTML‑View‑Option wählen, die externe Ressourcen referenziert, anstatt sie einzubetten.

**F: Was, wenn mein Dokument zu groß zum Rendern ist?**  
Erwägen Sie, das Dokument in kleinere Abschnitte zu teilen oder nur den erforderlichen Datumsbereich zu rendern, wie oben gezeigt.

**F: Wie gehe ich mit Rendering‑Fehlern um?**  
Überprüfen Sie alle Konfigurationseinstellungen, stellen Sie sicher, dass Sie eine gültige Lizenz besitzen, und konsultieren Sie die GroupDocs‑Dokumentation für detaillierte Fehlercodes.

## Ressourcen
- **Dokumentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API‑Referenz**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Lizenz kaufen**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Kostenlose Version testen**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Temporäre Lizenz erhalten**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-09-25  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Verwandte Tutorials

- [Wie man MS Project‑Dateien als HTML, JPG, PNG und PDF mit Notizen mit GroupDocs.Viewer für Java rendert](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [MS Project HTML‑Export: Zeit‑Einheiten über GroupDocs Java anpassen](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [GroupDocs Viewer Java Responsive HTML‑Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)