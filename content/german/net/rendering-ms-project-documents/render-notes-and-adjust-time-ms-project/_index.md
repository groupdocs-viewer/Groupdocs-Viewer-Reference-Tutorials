---
"description": "Rendern Sie MS Project-Dokumente mit GroupDocs.Viewer für .NET. Erstellen Sie mühelos Notizen, passen Sie Zeiteinheiten an und erkunden Sie verschiedene Ausgabeformate."
"linktitle": "Notizen rendern und Zeiteinheiten anpassen (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Notizen rendern und Zeiteinheiten anpassen (MS Project)"
"url": "/de/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# Notizen rendern und Zeiteinheiten anpassen (MS Project)

## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke API zur Dokumentdarstellung, mit der Entwickler verschiedene Dokumentformate in ihren .NET-Anwendungen anzeigen und bearbeiten können. In diesem Tutorial konzentrieren wir uns auf die Darstellung von Notizen und die Anpassung von Zeiteinheiten speziell für MS Project-Dokumente.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie die Bibliothek GroupDocs.Viewer für .NET heruntergeladen und installiert haben. Sie können sie hier herunterladen: [Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung mit .NET-Unterstützung ein.
3. MS Project-Dokument: Halten Sie ein Beispieldokument von MS Project zum Testen bereit.
## Namespaces importieren
Importieren wir zunächst die erforderlichen Namespaces, um mit dem Rendern von MS Project-Dokumenten zu beginnen:
## Schritt 1: Namespaces importieren
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nachdem wir nun die erforderlichen Namespaces importiert haben, unterteilen wir jedes Beispiel für ein umfassendes Verständnis in mehrere Schritte.
## Rendern eines MS Project-Dokuments in HTML
Um ein MS Project-Dokument mit Notizen in das HTML-Format zu rendern, führen Sie die folgenden Schritte aus:
### Schritt 2: Ausgabeverzeichnis und Dateiformat festlegen
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Schritt 3: Viewer-Objekt initialisieren und Optionen festlegen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Schritt 4: Dokument in HTML rendern
```csharp
viewer.View(options);
```
## Rendern von MS Project-Dokumenten in Bildformate
Sie können MS Project-Dokumente auch in Bildformate wie JPG und PNG umwandeln. So geht's:
### Schritt 5: Ausgabeverzeichnis und Dateiformat für JPG festlegen
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Schritt 6: Viewer-Objekt initialisieren und JPG-Optionen festlegen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Schritt 7: Dokument in JPG rendern
```csharp
viewer.View(options);
```
Wiederholen Sie ähnliche Schritte zum Rendern in PNG und andere Bildformate.
## Rendern eines MS Project-Dokuments in PDF
Um ein MS Project-Dokument in das PDF-Format zu rendern, gehen Sie wie folgt vor:
### Schritt 8: Ausgabeverzeichnis und Dateiformat für PDF festlegen
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Schritt 9: Viewer-Objekt initialisieren und PDF-Optionen festlegen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Schritt 10: Dokument in PDF rendern
```csharp
viewer.View(options);
```

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie MS Project-Dokumente mit GroupDocs.Viewer für .NET rendern und Zeiteinheiten anpassen. Integrieren Sie dieses Wissen in Ihre Projekte, um die Dokumentanzeige zu verbessern.
## Häufig gestellte Fragen
### Kann ich MS Project-Dokumente in andere Formate als HTML, Bilder und PDF rendern?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern in verschiedene Formate wie DOCX, XLSX, PPTX und mehr.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion erhalten von [Hier](https://releases.groupdocs.com/).
### Wie kann ich eine temporäre Lizenz für GroupDocs.Viewer für .NET erhalten?
Besuchen [dieser Link](https://purchase.groupdocs.com/temporary-license/) um eine vorläufige Lizenz zu erhalten.
### Wo finde ich Dokumentation für GroupDocs.Viewer für .NET?
Weitere Informationen finden Sie in der Dokumentation [Hier](https://tutorials.groupdocs.com/viewer/net/).
### Wo kann ich Unterstützung erhalten oder Fragen zu GroupDocs.Viewer für .NET stellen?
Sie können das Support-Forum besuchen [Hier](https://forum.groupdocs.com/c/viewer/9).