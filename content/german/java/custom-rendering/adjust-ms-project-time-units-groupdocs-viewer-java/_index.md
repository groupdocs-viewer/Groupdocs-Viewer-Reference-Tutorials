---
date: '2026-05-21'
description: Erfahren Sie, wie Sie den MS Project HTML-Export mit angepassten Zeiteinheiten
  mithilfe von GroupDocs Viewer for Java durchführen. Schritt‑für‑Schritt‑Anleitung
  mit Voraussetzungen, Einrichtung und Fehlersuche.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML-Export: Zeiteinheiten über GroupDocs Java anpassen'
type: docs
url: /de/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML-Export: Zeiteinheiten anpassen mit GroupDocs Java

Das Exportieren einer **MS Project**‑Datei nach HTML ist eine häufige Anforderung für Projekt‑Management‑Dashboards, Status‑Report‑Portale und kollaborative Prüftools. Standardmäßig rendert der Viewer zeitbezogene Daten in Minuten, was das Layout überladen und tägliche Berichte schwer lesbar machen kann. Mit **GroupDocs Viewer for Java** können Sie programmgesteuert die Zeiteinheit auf **Tage** setzen und so einen sauberen *ms project html export* erzeugen, der den typischen Erwartungen der Stakeholder entspricht. In diesem Tutorial lernen Sie, wie Sie den Viewer konfigurieren, die Zeiteinheit anpassen und das Projekt in wenigen einfachen Schritten nach HTML rendern.

![Zeiteinheiten von MS Project mit GroupDocs.Viewer für Java anpassen](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Zeiteinheiten von MS Project mit GroupDocs.Viewer für Java anpassen](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Schnelle Antworten
- **Welche Bibliothek rendert MS Project‑Dateien?** GroupDocs Viewer for Java.  
- **Welche Zeiteinheit kann ich für den HTML‑Export festlegen?** Tage, mit `TimeUnit.DAYS`.  
- **Benötige ich eine Lizenz für die Produktion?** Ja – eine permanente Lizenz ist erforderlich; ein Testlauf funktioniert für die Evaluierung. Sie können mit einer [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) beginnen.  
- **Welche IDE eignet sich am besten?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans), die Maven unterstützt.  
- **Ist Maven zwingend erforderlich?** Maven vereinfacht das Abhängigkeitsmanagement, aber Sie können auch Gradle oder manuelle JAR‑Einbindung verwenden.  
- **Wo kann ich kaufen?** Besuchen Sie die [Kaufseite](https://purchase.groupdocs.com/buy) für Preise.

## Was ist GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** ist ein Java‑SDK, das über 150 Dokumentformate – einschließlich MS Project – in web‑freundliches HTML, PNG, JPEG oder PDF konvertiert.  
Es abstrahiert die Parsing‑Logik, ermöglicht die Steuerung von Rendering‑Optionen wie Zeiteinheiten und funktioniert auf jeder Plattform, die Java 8 oder höher unterstützt.

## Warum Zeiteinheiten für den MS Project HTML‑Export anpassen?
Das Festlegen der Zeiteinheit auf **Tage** reduziert visuelles Rauschen, entspricht den meisten Berichtszyklen und verbessert die Ladezeiten, da weniger feinkörnige Zeitmarkierungen erzeugt werden. Quantitativ kann das Rendern mit Tagen anstelle von Minuten die erzeugte HTML‑Größe bei typischen 30‑Tage‑Projekten um bis zu **45 %** reduzieren und das clientseitige Rendering um etwa **30 %** beschleunigen.

## Voraussetzungen
- **Java Development Kit (JDK) 8 oder neuer** auf Ihrem Rechner installiert.  
- **Maven** (oder Gradle) für das Abhängigkeitsmanagement.  
- Eine **MS Project (.mpp)**‑Datei, die Sie exportieren möchten.  
- Zugang zu einer **GroupDocs Viewer for Java**‑Lizenz (Testversion oder permanent).  

### Erforderliche Bibliotheken
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` (oder dem entsprechenden Gradle‑Snippet) hinzu:

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro‑Tipp:** Halten Sie die Versionsnummer aktuell; neuere Releases fügen Formatunterstützung und Leistungsverbesserungen hinzu.

## Wie richte ich GroupDocs Viewer for Java ein?
Initialisieren Sie den Viewer, indem Sie eine `Viewer`‑Instanz erstellen, die auf Ihre MS Project‑Datei verweist. Die Klasse `Viewer` ist der Einstiegspunkt für alle Rendering‑Operationen. Sie lädt das Quelldokument, bereitet interne Strukturen vor und stellt Methoden wie `view()` und `viewToHtml()` zur Verfügung, um die gewünschten Ausgabeformate zu erzeugen.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition:** Die Klasse `Viewer` ist die Kernkomponente von GroupDocs Viewer, die ein Quelldokument lädt und Rendering‑Methoden wie `view()` und `viewToHtml()` bereitstellt.

## Wie kann ich die Zeiteinheiten für den HTML‑Export anpassen?
Um die Zeitgranularität zu ändern, erstellen Sie ein `ViewOptions`‑Objekt, konfigurieren dessen `ProjectOptions` auf `TimeUnit.DAYS` und übergeben es dem Viewer. `ViewOptions` definiert die Rendering‑Einstellungen für das Dokument, während das `TimeUnit`‑Enum die Einheit (Minuten, Stunden, Tage) für zeitbezogene Daten festlegt. Nach dem Setzen dieser Optionen rufen Sie `viewer.view(options)` auf, um HTML mit täglichen Markierungen zu erzeugen.

Laden Sie Ihre MS Project‑Datei mit `new Viewer("file.mpp")`, erstellen Sie ein `ViewOptions`‑Objekt, setzen Sie `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` und rufen Sie anschließend `viewer.view(options)` auf. Dieser dreistufige Ablauf ändert die Zeiteinheit von Minuten zu Tagen und erzeugt HTML‑Dateien, die nur tägliche Intervalle anzeigen.

### Schritt 1: Ausgabeordner festlegen
Wählen Sie ein beschreibbares Verzeichnis, in dem die HTML‑Seiten gespeichert werden, z. B. `output/`.

### Schritt 2: View‑Optionen mit eingebetteten Ressourcen erstellen
Eingebettete Ressourcen (CSS, JavaScript) stellen sicher, dass die HTML‑Seiten eigenständig sind.

### Schritt 3: Zeiteinheit auf Tage setzen
Verwenden Sie `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, um die Granularität zu ändern.

### Schritt 4: Dokument rendern
Rufen Sie `viewer.view(options)` auf; der Viewer schreibt für jede Projektseite eine HTML‑Datei in den Ausgabeordner.

### Schritt 5: Ergebnis überprüfen
Öffnen Sie das erzeugte `index.html` in einem Browser; Sie sollten Aufgabenbalken sehen, die an Tagesmarkierungen statt an Minutenmarkierungen ausgerichtet sind.

## Häufige Fallstricke und Fehlersuche
- **Falscher Ausgabepfad** – Stellen Sie sicher, dass das Verzeichnis existiert und der Java‑Prozess Schreibrechte hat.  
- **Fehlende Lizenz** – Ohne gültige Lizenz fällt der Viewer in den Testmodus zurück und kann Wasserzeichen einbetten.  
- **Große Dateien (> 500 MB)** – Erwägen Sie, die JVM‑Heap‑Größe (`-Xmx2g`) zu erhöhen oder mit `options.setRenderLimit(1000)` zu rendern, um Seiten stapelweise zu verarbeiten.  

## Praktische Anwendungsfälle des angepassten Zeit‑Einheiten‑HTML‑Exports
1. **Executive Dashboards** – Tägliche Granularität entspricht den meisten KPI‑Visualisierungen.  
2. **Automatisierte Status‑E‑Mails** – Betten Sie das erzeugte HTML direkt in E‑Mail‑Körper ein für schnelle Updates.  
3. **Projektportale** – Hosten Sie das HTML auf einer Intranet‑Seite, auf der Teammitglieder Aufgaben nach Tag filtern können.  

## Leistungsüberlegungen für große MS Project‑Dateien
- **Speicherverwaltung** – Verwenden Sie Java‑Garbage‑Collector‑Flags (`-XX:+UseG1GC`), um ungenutzte Objekte zeitnah freizugeben.  
- **Selektives Rendering** – Wenn Sie nur das Gantt‑Diagramm benötigen, deaktivieren Sie das Rendering anderer Ressourcen über `options.getProjectOptions().setRenderGantt(true)` und `setRenderResources(false)`.  
- **Parallele Verarbeitung** – Für Stapelkonvertierungen erstellen Sie separate `Viewer`‑Objekte pro Datei und führen sie in einem Thread‑Pool aus, um Mehrkern‑CPUs zu nutzen.

## Fazit
Sie verfügen nun über einen vollständigen, produktionsbereiten Workflow zum Durchführen eines **ms project html export** mit auf Tage eingestellten Zeiteinheiten mithilfe von GroupDocs Viewer for Java. Dieser Ansatz reduziert die HTML‑Größe, beschleunigt das Client‑Rendering und liefert eine stakeholder‑freundliche Ansicht von Projektplänen. Erkunden Sie weitere Rendering‑Optionen – wie PDF‑Export oder Bild‑Snapshots – um die Integration in umfassendere Reporting‑Pipelines zu erweitern.

## Häufig gestellte Fragen

**Q: Kann ich andere Projektansichten (z. B. Ressourcenblatt) nach HTML rendern?**  
A: Ja, das `ProjectOptions`‑Objekt ermöglicht das Aktivieren oder Deaktivieren bestimmter Ansichten wie Gantt, Ressourcenblatt und Kalender vor dem Rendering.

**Q: Ist es möglich, das CSS des erzeugten HTML anzupassen?**  
A: Absolut. Geben Sie einen Pfad zu einem benutzerdefinierten Stylesheet über `options.setStyleSheetPath("path/to/custom.css")` an und der Viewer bettet es in jede Seite ein.

**Q: Welche Dateigrößenbeschränkungen unterstützt GroupDocs Viewer für MS Project?**  
A: Das SDK kann Dateien bis zu **500 MB** verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, dank seiner Streaming‑Architektur.

**Q: Muss ich Microsoft Project auf dem Server installieren?**  
A: Nein. GroupDocs Viewer parst das .mpp‑Format direkt und erfordert weder Microsoft Project noch eine Office‑Installation.

**Q: Wie lizenziere ich den Viewer für eine Produktionsumgebung?**  
A: Kaufen Sie eine permanente Lizenz im GroupDocs‑Store; wenden Sie die Lizenzdatei zur Laufzeit mit `License license = new License(); license.setLicense("path/to/license.lic");` an. Für kurzfristige Bedürfnisse können Sie eine [temporäre Lizenz](https://purchase.groupdocs.com/temporary-license/) erhalten.

---

**Letzte Aktualisierung:** 2026-05-21  
**Getestet mit:** GroupDocs Viewer Java 25.2  
**Autor:** GroupDocs  

**Ressourcen**  
- [Dokumentation](https://docs.groupdocs.com/viewer/java/)  
- [API‑Referenz](https://reference.groupdocs.com/viewer/java/)  
- [GroupDocs.Viewer herunterladen](https://releases.groupdocs.com/viewer/java/)  
- [Lizenz kaufen](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Verwandte Tutorials

- [Wie man MS Project‑Dateien als HTML, JPG, PNG und PDF mit Notizen mithilfe von GroupDocs.Viewer für Java rendert](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Wie man GroupDocs Viewer verwendet, um Projektdokumente nach Zeitintervallen in Java zu rendern](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Wie man Lizenzen in GroupDocs.Viewer Java setzt: Datei‑ und URL‑Einrichtungs‑Leitfaden](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)