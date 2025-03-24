---
title: Notizen rendern und Zeiteinheiten anpassen (MS Project)
linktitle: Notizen rendern und Zeiteinheiten anpassen (MS Project)
second_title: GroupDocs.Viewer .NET-API
description: Meistern Sie das Rendern von MS Project-Dokumenten mit GroupDocs.Viewer für .NET. Rendern Sie Notizen, passen Sie Zeiteinheiten an und erkunden Sie mühelos verschiedene Ausgabeformate.
weight: 11
url: /de/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke API zum Rendern von Dokumenten, mit der Entwickler verschiedene Dokumentformate in ihren .NET-Anwendungen anzeigen und bearbeiten können. In diesem Tutorial konzentrieren wir uns auf das Rendern von Notizen und das Anpassen von Zeiteinheiten speziell für MS Project-Dokumente.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie die GroupDocs.Viewer für .NET-Bibliothek heruntergeladen und installiert haben. Sie können es herunterladen unter[Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung mit .NET-Unterstützung ein.
3. MS-Project-Dokument: Halten Sie ein Beispiel-MS-Project-Dokument zum Testen bereit.
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
Um ein MS Project-Dokument mit Notizen in das HTML-Format zu rendern, gehen Sie folgendermaßen vor:
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
Sie können MS Project-Dokumente auch in Bildformate wie JPG und PNG rendern. Hier ist wie:
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
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie MS Project-Dokumente rendern und Zeiteinheiten mit GroupDocs.Viewer für .NET anpassen. Integrieren Sie dieses Wissen in Ihre Projekte, um die Anzeigemöglichkeiten für Dokumente zu verbessern.
## FAQs
### Kann ich MS Project-Dokumente in andere Formate als HTML, Bilder und PDF rendern?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern in verschiedene Formate wie DOCX, XLSX, PPTX und mehr.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
 Ja, Sie können eine kostenlose Testversion von erhalten[Hier](https://releases.groupdocs.com/).
### Wie kann ich eine temporäre Lizenz für GroupDocs.Viewer für .NET erhalten?
 Besuchen[dieser Link](https://purchase.groupdocs.com/temporary-license/) eine befristete Lizenz zu erhalten.
### Wo finde ich Dokumentation für GroupDocs.Viewer für .NET?
 Weitere Informationen finden Sie in der Dokumentation[Hier](https://tutorials.groupdocs.com/viewer/net/).
### Wo kann ich Unterstützung suchen oder Fragen zu GroupDocs.Viewer für .NET stellen?
 Sie können das Support-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9).