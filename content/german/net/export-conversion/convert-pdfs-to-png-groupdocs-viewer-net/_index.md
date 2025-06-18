---
"date": "2025-04-25"
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET PDF-Seiten in PNG-Bilder konvertieren und dabei die Originalabmessungen beibehalten. Diese Anleitung behandelt Einrichtung, Konfiguration und bewährte Methoden."
"title": "Konvertieren Sie PDFs mit GroupDocs.Viewer für .NET in PNG mit Originalgröße"
"url": "/de/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
---

# Konvertieren Sie PDFs mit GroupDocs.Viewer für .NET in PNG mit Originalgröße

## Einführung

Die Konvertierung von PDF-Dateien in PNG-Bilder unter Beibehaltung der ursprünglichen Seitengröße ist für die hochwertige Digitalisierung von Dokumenten oder die Erstellung von Webinhalten unerlässlich. Dieses Tutorial führt Sie durch die Verwendung von GroupDocs.Viewer für .NET zum Rendern von PDF-Seiten als PNG-Dateien unter Beibehaltung ihrer ursprünglichen Abmessungen.

![Konvertieren Sie PDFs mit GroupDocs.Viewer für .NET in PNG mit Originalgröße](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Was Sie lernen werden:**
- So richten Sie GroupDocs.Viewer für .NET in Ihrem Projekt ein und konfigurieren es
- Schrittweiser Prozess zum Rendern von PDFs in PNG-Bilder unter Beibehaltung der Seitengröße
- Wichtige Konfigurationsoptionen und Best Practices für optimale Leistung

Nach Abschluss dieses Tutorials können Sie diese Funktionalität nahtlos in Ihre Anwendungen integrieren. Beginnen wir mit den Voraussetzungen für den Einstieg.

## Voraussetzungen

Bevor Sie GroupDocs.Viewer für .NET in Ihrem Projekt implementieren, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

### Erforderliche Bibliotheken und Versionen
- **GroupDocs.Viewer für .NET**: Version 25.3.0 oder höher.

### Anforderungen für die Umgebungseinrichtung
- Eine kompatible Entwicklungsumgebung wie Visual Studio.
- Grundlegende Kenntnisse der C#-Programmierung.

### Voraussetzungen
- Vertrautheit mit der NuGet-Paketverwaltung.
- Einige Erfahrung in der Arbeit mit PDFs und der Bildverarbeitung in .NET-Anwendungen.

Sobald diese Voraussetzungen erfüllt sind, können wir mit der Einrichtung von GroupDocs.Viewer für .NET fortfahren.

## Einrichten von GroupDocs.Viewer für .NET

Um GroupDocs.Viewer für .NET zu verwenden, befolgen Sie die folgenden Installationsschritte:

### Installation über die NuGet Package Manager-Konsole
Öffnen Sie Ihr Projekt in Visual Studio und verwenden Sie den folgenden Befehl:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Installation über .NET CLI
Alternativ können Sie es mithilfe der .NET-CLI mit diesem Befehl installieren:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Schritte zum Lizenzerwerb
1. **Kostenlose Testversion**: Laden Sie eine Testversion herunter von [GroupDocs-Downloads](https://releases.groupdocs.com/viewer/net/).
2. **Temporäre Lizenz**: Erwerben Sie eine temporäre Lizenz, um alle Funktionen zu nutzen unter [Seite „Temporäre Lizenz“](https://purchase.groupdocs.com/temporary-license/).
3. **Kaufen**: Für eine erweiterte Nutzung erwerben Sie eine Lizenz über die [Seite kaufen](https://purchase.groupdocs.com/buy).

### Grundlegende Initialisierung und Einrichtung
Um GroupDocs.Viewer für .NET in Ihrem C#-Projekt zu initialisieren, führen Sie die folgenden Schritte aus:
1. Importieren Sie die erforderlichen Namespaces:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Richten Sie die Pfade für Ihr Eingabe-PDF und Ihr Ausgabeverzeichnis ein.
3. Initialisieren `Viewer` durch den Pfad zu Ihrem Quelldokument, wie in diesem Ausschnitt gezeigt:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Implementierungshandbuch
In diesem Abschnitt wird die Implementierung der Darstellung von PDF-Seiten als PNG-Bilder unter Beibehaltung ihrer Originalgröße behandelt.

### Rendern von PDF-Seiten in PNG mit Originalseitengröße
#### Überblick
Mit dieser Funktion können Sie jede Seite eines PDF-Dokuments in ein PNG-Bild umwandeln und dabei die Originalabmessungen beibehalten. Dies ist besonders nützlich für Anwendungen, die eine präzise visuelle Darstellung von Dokumenten erfordern.

##### Schritt 1: Pfade einrichten und Viewer initialisieren
Erstellen Sie Variablen für Ihren PDF-Eingabepfad und Ihr Ausgabeverzeichnis:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Initialisieren Sie den `Viewer` Klasse mit Ihrem Quelldokumentpfad:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Der Codeblock wird im nächsten Schritt fortgesetzt
}
```
##### Schritt 2: Konfigurieren Sie PngViewOptions
Erstellen Sie eine Instanz von `PngViewOptions`, wobei ein Dateibenennungsmuster für die Ausgabebilder angegeben wird:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Konfigurieren Sie die Viewer-Optionen, um jede Seite in ihrer Originalgröße darzustellen:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Schritt 3: Dokumentseiten rendern
Rufen Sie die `View` Methode auf Ihrem `Viewer` Instanz, indem Sie die konfigurierten Ansichtsoptionen übergeben:
```csharp
viewer.View(viewOptions);
```
### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass die Pfade korrekt sind und Verzeichnisse vorhanden sind.
- Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen zum Lesen aus Eingabeverzeichnissen und zum Schreiben in Ausgabeverzeichnisse verfügen.

## Praktische Anwendungen
1. **Dokumentendigitalisierung**: Konvertieren Sie archivierte PDF-Dokumente in digitale Bilder, um den Zugriff und die Verteilung zu erleichtern.
2. **Webportale**: Zeigen Sie Dokumentvorschauen auf Websites an, ohne dass PDF-Reader erforderlich sind.
3. **Content-Management-Systeme (CMS)**: Integrieren Sie CMS-Plattformen, um große Mengen an PDF-Inhalten effizient zu verwalten und anzuzeigen.

## Überlegungen zur Leistung
So optimieren Sie die Leistung Ihrer Anwendung mit GroupDocs.Viewer für .NET:
- Begrenzen Sie die Speichernutzung, indem Sie Dokumente bei großen Dateien in Blöcken verarbeiten.
- Verwenden Sie nach Möglichkeit asynchrone Methoden, um das Blockieren von Threads während des Renderings zu vermeiden.
- Entsorgen `Viewer` Instanzen umgehend nach der Verwendung, um Ressourcen freizugeben.

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie PDF-Seiten mit GroupDocs.Viewer für .NET als PNG-Bilder rendern und dabei ihre Originalgröße beibehalten. Wir haben die Einrichtung Ihrer Umgebung, die Konfiguration der notwendigen Optionen für optimale Ergebnisse und praktische Anwendungen dieser Funktionalität erläutert.

Zu den nächsten Schritten gehört das Experimentieren mit anderen in GroupDocs.Viewer verfügbaren Rendering-Optionen oder die Integration in größere Projekte, um die Dokumentverwaltungsfunktionen zu verbessern.

## FAQ-Bereich
1. **Wie lassen sich große PDF-Dateien mit GroupDocs.Viewer am besten verarbeiten?**
   - Verarbeiten Sie Dokumente in kleineren Blöcken und verwenden Sie asynchrone Methoden, um die Leistung aufrechtzuerhalten.
2. **Kann ich die Namen der PNG-Ausgabedateien anpassen?**
   - Ja, durch Angabe eines Namensmusters in `PngViewOptions`.
3. **Ist es möglich, nur bestimmte Seiten darzustellen?**
   - Absolut, Sie können konfigurieren `PageNumbers` In `PngViewOptions` um anzugeben, welche Seiten gerendert werden sollen.
4. **Wie handhabe ich die Lizenzierung für GroupDocs.Viewer?**
   - Zu den Optionen gehören eine kostenlose Testversion, eine temporäre Lizenz oder der Kauf einer Volllizenz.
5. **Kann dieses Setup in Webanwendungen verwendet werden?**
   - Ja, es eignet sich für die serverseitige Darstellung von PDFs in ASP.NET Core und anderen .NET-basierten Web-Frameworks.

## Ressourcen
- [Dokumentation](https://docs.groupdocs.com/viewer/net/)
- [API-Referenz](https://reference.groupdocs.com/viewer/net/)
- [GroupDocs.Viewer herunterladen](https://releases.groupdocs.com/viewer/net/)
- [Lizenz erwerben](https://purchase.groupdocs.com/buy)
- [Kostenlose Testversion](https://releases.groupdocs.com/viewer/net/)
- [Temporäre Lizenz](https://purchase.groupdocs.com/temporary-license/)
- [Support-Forum](https://forum.groupdocs.com/c/viewer/9)