---
date: '2026-04-04'
description: Erfahren Sie, wie Sie bestimmte PDF‑Seiten mit GroupDocs.Viewer für Java
  drehen. Diese Schritt‑für‑Schritt‑Anleitung behandelt die Maven‑Einrichtung, das
  Drehen von PDFs um 90 Grad und die Fehlersuche.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: Wie man bestimmte PDF‑Seiten mit GroupDocs.Viewer für Java rotiert
type: docs
url: /de/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Wie man bestimmte PDF-Seiten mit GroupDocs.Viewer für Java rotiert

Das Drehen bestimmter Seiten in einem PDF kann entscheidend sein, um Dokumente auszurichten, gescannte Bilder zu korrigieren oder Präsentationsfolien anzupassen. **In diesem Leitfaden lernen Sie, wie Sie bestimmte PDF-Seiten programmgesteuert mit GroupDocs.Viewer drehen**, egal ob Sie PDF um 90 Grad drehen, einen gesamten Abschnitt umkehren oder mehrere Seiten in einem Aufruf verarbeiten müssen.

![Bestimmte PDF-Seiten mit GroupDocs.Viewer für Java drehen](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Was Sie lernen werden**
- Einrichtung von GroupDocs.Viewer in Ihrem Java‑Projekt (einschließlich Maven‑Konfiguration für GroupDocs Viewer)
- Programmgesteuertes Drehen bestimmter PDF‑Seiten (PDF um 90 Grad, 180 Grad usw. drehen)
- Wichtige Konfigurationen für optimale Nutzung
- Fehlersuche bei häufigen Problemen während der Implementierung

## Schnelle Antworten
- **Welche Bibliothek kann PDF‑Seiten in Java drehen?** GroupDocs.Viewer for Java.  
- **Kann ich eine einzelne Seite um 90 Grad drehen?** Yes, use `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **Benötige ich eine Lizenz für die Entwicklung?** A temporary license is available for free trial.  
- **Ist Maven erforderlich?** Maven is the recommended way to manage GroupDocs dependencies.  
- **Wie rendere ich die gedrehten Seiten?** Use `HtmlViewOptions` and call `viewer.view(...)`.

## Voraussetzungen

### Erforderliche Bibliotheken und Abhängigkeiten
- Java Development Kit (JDK) 8 oder höher.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Maven für das Dependency‑Management.

### Anforderungen an die Umgebungseinrichtung
1. **Maven Configuration** – add GroupDocs.Viewer to your `pom.xml`.  
2. **License Acquisition** – obtain a temporary license from GroupDocs. Visit [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) or apply for a temporary license on the [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Einrichtung von GroupDocs.Viewer für Java

Um GroupDocs.Viewer in Ihr Java‑Projekt mit Maven zu integrieren, aktualisieren Sie Ihre `pom.xml`:

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

### Grundlegende Initialisierung und Einrichtung
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Wie man bestimmte PDF-Seiten mit GroupDocs.Viewer dreht
### Übersicht
Das Drehen bestimmter PDF‑Seiten gibt Ihnen eine feinkörnige Kontrolle über die Dokumentpräsentation, ohne die Originaldatei zu verändern.

### Schritt 1: Seitenrotation konfigurieren
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Schritt 2: Viewer initialisieren und rendern
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parameter und Konfiguration
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` wobei die Rotationsoptionen `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE` sind.  
- **HtmlViewOptions** – Handhabt die PDF‑zu‑HTML‑Konvertierung und bewahrt Layout sowie eingebettete Ressourcen.  
- **pdf to html java** – Die Klasse ist Teil derselben API und sorgt für eine getreue visuelle Darstellung.

## Warum bestimmte PDF-Seiten drehen?
- **Document Alignment** – Correct orientation of scanned contracts or invoices.  
- **Presentation Tweaks** – Adjust slides that were exported as PDF.  
- **Archival Consistency** – Standardize page orientation during bulk digitization.

## Häufige Probleme und Lösungen (pdf‑Rotation)
- **Incorrect Paths** – Verify that `YOUR_DOCUMENT_DIRECTORY` and `YOUR_OUTPUT_DIRECTORY` exist and are accessible.  
- **Missing Dependencies** – Ensure the Maven coordinates match the latest GroupDocs.Viewer version.  
- **License Restrictions** – Apply the temporary license correctly; otherwise, some features may be disabled.  
- **Memory Spikes** – Render large PDFs in smaller batches or increase the JVM heap size.

## Praktische Anwendungen

### Praxisnahe Anwendungsfälle
1. **Document Alignment** – Rotate scanned documents for correct digital orientation.  
2. **Presentation Adjustments** – Modify presentation slides within PDFs before sharing.  
3. **Archival Workflows** – Automatically adjust the orientation of historical documents during digitization.

### Integrationsmöglichkeiten
Kombinieren Sie GroupDocs.Viewer mit Java‑basierten Content‑Management‑Systemen, Unternehmensportalen oder benutzerdefinierten APIs, die eine sofortige Anzeige von PDFs erfordern.

## Leistungsüberlegungen
- **Resource Management** – Always close the `Viewer` instance to release file handles and memory.  
- **Java Memory Management** – Monitor heap usage when processing large PDFs; consider streaming pages instead of loading the whole file.  
- **Best Practices** – Cache rendered HTML for frequently accessed documents to reduce processing time.

## Fazit
Dieses Tutorial behandelte **wie man bestimmte PDF‑Seiten mit GroupDocs.Viewer in Java rotiert**, von der Maven‑Einrichtung bis zum Rendern gedrehter Seiten und der Behandlung gängiger Stolpersteine. Experimentieren Sie mit zusätzlichen Funktionen wie Wasserzeichen, Formatkonvertierung oder Batch‑Verarbeitung, um Ihren Dokumenten‑Workflow weiter zu erweitern.

**Nächste Schritte:** Tauchen Sie ein in weitere GroupDocs.Viewer‑Funktionen wie das Konvertieren von PDFs zu PNG, das Hinzufügen von Wasserzeichen oder die Integration mit Cloud‑Speicher‑Anbietern.

## FAQ-Bereich
- **Troubleshooting Rotation Issues** – Verify page numbers and rotation parameters are correct.  
- **Handling Large PDF Files** – Process pages in batches and monitor memory usage.  
- **Licensing Requirements** – Use a temporary license for development; purchase a full license for production.  
- **Rotating Multiple Pages** – Call `rotatePage` repeatedly with different page numbers and angles.  
- **Integration with Java Libraries** – GroupDocs.Viewer works seamlessly with Spring Boot, Jakarta EE, and other Java frameworks.

## Häufig gestellte Fragen

**F: Kann ich alle Seiten eines PDFs auf einmal drehen?**  
A: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)` for each page.

**F: Beeinflusst die Drehung die originale PDF‑Datei?**  
A: No. Rotation is applied only during the rendering process; the source PDF remains unchanged.

**F: Was ist, wenn ein PDF passwortgeschützt ist?**  
A: Provide the password when creating the `Viewer` instance: `new Viewer(path, password)`.

**F: Wie debugge ich einen „null pointer“-Fehler beim Einrichten von HtmlViewOptions?**  
A: Ensure the output directory exists and that `pageFilePathFormat` resolves correctly.

**F: Gibt es eine Möglichkeit, Seiten beim Konvertieren in andere Formate (z. B. PNG) zu drehen?**  
A: Yes. Use the same `rotatePage` configuration with the appropriate view options for the target format.

## Ressourcen
- **Documentation**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-04-04  
**Getestet mit:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs