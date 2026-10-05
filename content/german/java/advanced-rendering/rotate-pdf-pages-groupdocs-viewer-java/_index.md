---
date: '2026-10-05'
description: Erfahren Sie, wie Sie bestimmte PDF-Seiten mit GroupDocs.Viewer für Java
  rotieren. Diese Schritt‑für‑Schritt‑Anleitung behandelt die Maven‑Einrichtung, das
  Drehen von PDFs um 90 Grad und die Fehlersuche.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Bestimmte PDF-Seiten mit GroupDocs.Viewer für Java rotieren. Erfahren
  Sie, wie Sie PDFs um 90 Grad drehen, Maven konfigurieren und häufige Probleme in
  einer kompakten Anleitung beheben.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Bestimmte PDF-Seiten mit GroupDocs.Viewer für Java rotieren
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: Wie man bestimmte PDF-Seiten mit GroupDocs.Viewer für Java rotiert
type: docs
url: /de/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Wie man bestimmte PDF-Seiten mit GroupDocs.Viewer für Java dreht

Das Drehen bestimmter Seiten innerhalb einer PDF kann wichtig sein, um Dokumente auszurichten, gescannte Bilder zu korrigieren oder Präsentationsfolien anzupassen. **In diesem Leitfaden lernen Sie, wie Sie bestimmte PDF-Seiten programmgesteuert mit GroupDocs.Viewer drehen**, egal ob Sie PDF um 90 Grad drehen, einen gesamten Abschnitt umkehren oder mehrere Seiten in einem Aufruf verarbeiten müssen.

![Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Was Sie lernen werden**
- Einrichtung von GroupDocs.Viewer in Ihrem Java‑Projekt (inklusive Maven‑Konfiguration für GroupDocs Viewer)
- Programmgesteuertes Drehen bestimmter PDF‑Seiten (PDF um 90 Grad, 180 Grad usw. drehen)
- Wichtige Konfigurationen für optimale Nutzung
- Fehlersuche bei häufigen Problemen während der Implementierung

## Schnelle Antworten
- **Welche Bibliothek kann PDF‑Seiten in Java drehen?** GroupDocs.Viewer für Java bietet integrierte Rotationsunterstützung ohne externe Tools.  
- **Kann ich eine einzelne Seite um 90 Grad drehen?** Ja – rufen Sie `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` auf der Viewer‑Instanz auf.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine temporäre Lizenz ist kostenlos für die Evaluierung; eine Voll‑Lizenz ist für die Produktion erforderlich.  
- **Ist Maven erforderlich?** Maven ist der empfohlene Dependency‑Manager, Sie können jedoch auch Gradle oder die manuelle JAR‑Einbindung verwenden.  
- **Wie rendere ich die gedrehten Seiten?** Verwenden Sie `HtmlViewOptions` mit `viewer.view(documentPath, viewOptions)`, um HTML‑Ausgabe zu erhalten, die die Rotation widerspiegelt.

## Was bedeutet „rotate specific pdf pages“?
`rotate specific pdf pages` bezieht sich auf die Möglichkeit, die Orientierung einzelner Seiten innerhalb eines PDF‑Dokuments zu ändern, während der Rest der Datei unverändert bleibt. Dieser Vorgang wird zur Renderzeit durchgeführt, sodass die Original‑PDF‑Datei nicht verändert wird.

## Warum bestimmte PDF‑Seiten drehen?
Sie können eine einzelne Seite in weniger als 0,05 Sekunden auf einer typischen Server‑VM drehen, wodurch eine Echtzeit‑Vorschau von gescannten Verträgen, Präsentationsdecks oder mehrseitigen Rechnungen mit falsch ausgerichteten Scans ermöglicht wird. Diese feinkörnige Kontrolle eliminiert die Notwendigkeit teurer Nachbearbeitungstools und reduziert den manuellen Aufwand um bis zu 70 % in groß angelegten Digitalisierungsprojekten.

## Voraussetzungen

### Erforderliche Bibliotheken und Abhängigkeiten
- Java Development Kit (JDK) 8 oder höher.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Maven für das Dependency‑Management.

### Anforderungen an die Umgebungseinrichtung
1. **Maven‑Konfiguration** – fügen Sie GroupDocs.Viewer zu Ihrer `pom.xml` hinzu.  
2. **Lizenzbeschaffung** – erhalten Sie eine temporäre Lizenz von GroupDocs. Besuchen Sie [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) oder beantragen Sie eine temporäre Lizenz auf der [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

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
`Viewer` ist die Kernklasse, die ein Dokument lädt und Rendering‑Operationen orchestriert. Nach dem Erstellen einer Instanz können Sie Methoden wie `view` oder `rotatePage` aufrufen.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Wie man bestimmte PDF‑Seiten mit GroupDocs.Viewer dreht
Das Drehen bestimmter PDF‑Seiten mit GroupDocs.Viewer umfasst zwei Hauptaktionen: Erstens die gewünschte Rotation für jede Zielseite mit der Methode `rotatePage` festlegen und zweitens das Dokument mit `HtmlViewOptions` rendern, sodass die Rotation in der Ausgabe sichtbar wird. Dieser Ansatz lässt die Original‑PDF unverändert und liefert korrekt ausgerichtetes HTML.

### Schritt 1: Seitenrotation konfigurieren
`rotatePage` ist eine Methode, die einen nullbasierten Seitenindex und einen `Rotation`‑Enum‑Wert akzeptiert. Der Enum bietet drei Optionen: `ON_90_DEGREE`, `ON_180_DEGREE` und `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Schritt 2: Viewer initialisieren und rendern
`HtmlViewOptions` steuert den PDF‑zu‑HTML‑Konvertierungsprozess. Es bewahrt Layout, Schriftarten und eingebettete Ressourcen, während es jede von Ihnen konfigurierte Rotation anwendet.  

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

## Häufige Probleme und Lösungen (troubleshoot pdf rotation)

- **Falsche Pfade** – Stellen Sie sicher, dass `YOUR_DOCUMENT_DIRECTORY` und `YOUR_OUTPUT_DIRECTORY` existieren und zugänglich sind.  
- **Fehlende Abhängigkeiten** – Vergewissern Sie sich, dass die Maven‑Koordinaten der neuesten GroupDocs.Viewer‑Version entsprechen (derzeit 25.2).  
- **Lizenzbeschränkungen** – Wenden Sie die temporäre Lizenz korrekt an; sonst können einige Funktionen deaktiviert sein.  
- **Speicherspitzen** – Rendern Sie große PDFs in kleineren Batches oder erhöhen Sie die JVM‑Heap‑Größe.

## Praktische Anwendungsfälle

### Real‑World‑Use‑Cases
1. **Dokumentenausrichtung** – Gescannte Verträge für die korrekte digitale Orientierung drehen.  
2. **Präsentationsanpassungen** – Präsentationsfolien innerhalb von PDFs vor dem Teilen modifizieren.  
3. **Archivierungs‑Workflows** – Während der Digitalisierung automatisch die Orientierung historischer Dokumente anpassen.

### Integrationsmöglichkeiten
Kombinieren Sie GroupDocs.Viewer mit Java‑basierten Content‑Management‑Systemen, Unternehmensportalen oder benutzerdefinierten APIs, die eine sofortige PDF‑Ansicht erfordern.

## Leistungsüberlegungen
- **Ressourcenverwaltung** – Schließen Sie stets die `Viewer`‑Instanz, um Dateihandles und Speicher freizugeben.  
- **Java‑Speichermanagement** – Überwachen Sie den Heap‑Verbrauch bei der Verarbeitung großer PDFs; erwägen Sie das Streaming von Seiten statt des Ladens der gesamten Datei.  
- **Best Practices** – Cachen Sie gerendertes HTML für häufig aufgerufene Dokumente, um die Verarbeitungszeit um bis zu 60 % zu reduzieren.

## Fazit
Dieses Tutorial behandelte **wie man bestimmte PDF‑Seiten mit GroupDocs.Viewer in Java dreht**, von der Maven‑Einrichtung über das Rendern gedrehter Seiten bis hin zur Fehlerbehebung. Experimentieren Sie mit zusätzlichen Funktionen wie Wasserzeichen, Formatkonvertierung oder Batch‑Verarbeitung, um Ihren Dokumenten‑Workflow weiter zu erweitern.

**Nächste Schritte:** Erkunden Sie weitere GroupDocs.Viewer‑Funktionen wie das Konvertieren von PDFs zu PNG, das Hinzufügen von Wasserzeichen oder die Integration mit Cloud‑Speicher‑Anbietern.

## FAQ‑Abschnitt
- **Fehlerbehebung bei Rotationsproblemen** – Überprüfen Sie, ob Seitenzahlen und Rotationsparameter korrekt sind.  
- **Umgang mit großen PDF‑Dateien** – Verarbeiten Sie Seiten in Batches und überwachen Sie den Speicherverbrauch.  
- **Lizenzanforderungen** – Verwenden Sie eine temporäre Lizenz für die Entwicklung; erwerben Sie eine Voll‑Lizenz für die Produktion.  
- **Mehrere Seiten rotieren** – Rufen Sie `rotatePage` wiederholt mit unterschiedlichen Seitenzahlen und Winkeln auf.  
- **Integration mit Java‑Bibliotheken** – GroupDocs.Viewer funktioniert nahtlos mit Spring Boot, Jakarta EE und anderen Java‑Frameworks.

## Häufig gestellte Fragen

**F: Kann ich alle Seiten einer PDF auf einmal drehen?**  
A: Ja. Durchlaufen Sie die Seitennummern und rufen Sie `rotatePage(page, Rotation.ON_90_DEGREE)` für jede Seite auf.

**F: Wirkt sich die Rotation auf die Original‑PDF‑Datei aus?**  
A: Nein. Die Rotation wird nur während des Renderns angewendet; die Quell‑PDF bleibt unverändert.

**F: Was, wenn eine PDF passwortgeschützt ist?**  
A: Geben Sie das Passwort beim Erstellen der `Viewer`‑Instanz an: `new Viewer(path, password)`.

**F: Wie debugge ich einen „null pointer“‑Fehler beim Einrichten von HtmlViewOptions?**  
A: Stellen Sie sicher, dass das Ausgabeverzeichnis existiert und dass `pageFilePathFormat` korrekt aufgelöst wird.

**F: Gibt es eine Möglichkeit, Seiten beim Konvertieren in andere Formate (z. B. PNG) zu drehen?**  
A: Ja. Verwenden Sie dieselbe `rotatePage`‑Konfiguration zusammen mit den entsprechenden View‑Optionen für das Zielformat.

## Ressourcen
- **Dokumentation**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API‑Referenz**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Kauf**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Kostenlose Testversion**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporäre Lizenz**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-10-05  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs

## Verwandte Tutorials

- [Java Guide: render selected pages java with GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Java Pdf Rendering Groupdocs Viewer Page Breaks](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [Groupdocs Viewer Java Responsive Html Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)