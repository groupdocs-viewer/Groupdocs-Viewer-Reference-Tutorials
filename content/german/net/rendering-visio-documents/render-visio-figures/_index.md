---
title: Visio-Figuren rendern
linktitle: Visio-Figuren rendern
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie in diesem umfassenden Handbuch, wie Sie Visio-Figuren mit GroupDocs.Viewer für .NET rendern. Erweitern Sie die Anzeigefunktionen für Dokumente in Ihren .NET-Anwendungen.
type: docs
weight: 10
url: /de/net/rendering-visio-documents/render-visio-figures/
---
## Einführung
Im heutigen digitalen Zeitalter spielt das Rendern von Dokumenten in verschiedenen Anwendungen eine entscheidende Rolle. Unabhängig davon, ob es darum geht, Dokumente auf einer Website anzuzeigen oder in verschiedene Formate zu konvertieren, ist ein effizientes Rendering unerlässlich. GroupDocs.Viewer für .NET bietet eine robuste Lösung zum Anzeigen und Bearbeiten von Dokumenten in .NET-Anwendungen. In diesem Tutorial befassen wir uns intensiv mit dem Rendern von Visio-Figuren mit GroupDocs.Viewer für .NET und unterteilen den Vorgang in einfache Schritte.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Umgebungseinrichtung: Stellen Sie sicher, dass Sie über eine Arbeitsumgebung für die .NET-Entwicklung verfügen.
2.  GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET von herunter und installieren Sie es[Download-Link](https://releases.groupdocs.com/viewer/net/).
3. Grundlegendes Verständnis von C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
4. Beispiel-Visio-Dokument: Halten Sie ein Beispiel-Visio-Dokument zum Rendern bereit.

## Namespaces importieren
Beginnen Sie in Ihrem C#-Projekt mit dem Importieren der erforderlichen Namespaces:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Rendern in HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Ausgabeverzeichnis: Definieren Sie das Verzeichnis, in dem der gerenderte HTML-Code gespeichert wird.
- Format des Seitendateipfads: Geben Sie das Pfadformat für die HTML-Seite an.
- Viewer-Initialisierung: Initialisieren Sie das Viewer-Objekt mit dem Pfad zum Visio-Dokument.
- HTML-Ansichtsoptionen: Konfigurieren Sie Optionen zum Rendern von HTML.
- Visio-Rendering-Optionen: Legen Sie spezifische Optionen für das Visio-Rendering fest, z. B. nur das Rendern von Figuren und die Figurenbreite.
## 2. Rendern in JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Konfigurieren Sie ähnlich wie beim Rendern in HTML die Optionen für das Rendern im JPG-Format.
## 3. Rendern in PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Die Konfiguration für das Rendern im PNG-Format folgt einem ähnlichen Muster wie das JPG-Rendering.
## 4. Rendern in PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Konfigurieren Sie zum Rendern in PDF spezifische Optionen für das PDF-Format.

## Abschluss
In diesem Tutorial haben wir untersucht, wie man Visio-Figuren mit GroupDocs.Viewer für .NET rendert. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie Funktionen zur Dokumentwiedergabe nahtlos in Ihre .NET-Anwendungen integrieren und so die Benutzererfahrung und Produktivität verbessern.
## FAQs
### Kann ich die Rendering-Optionen für Visio-Figuren anpassen?
Ja, GroupDocs.Viewer für .NET bietet umfangreiche Optionen zum Anpassen des Renderings, einschließlich der Figurenbreite, der Darstellung nur von Figuren und mehr.
### Ist GroupDocs.Viewer für .NET für die Darstellung umfangreicher Dokumente geeignet?
Absolut, GroupDocs.Viewer für .NET ist für die effiziente Handhabung umfangreicher Dokumentwiedergabe optimiert.
### Unterstützt GroupDocs.Viewer neben Visio auch andere Dokumentformate?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office, AutoCAD und mehr.
### Kann ich GroupDocs.Viewer in Webanwendungen integrieren?
Ja, GroupDocs.Viewer kann nahtlos in Webanwendungen zur Anzeige und Bearbeitung von Dokumenten integriert werden.
### Gibt es eine Testversion zum Testen vor dem Kauf?
Ja, Sie können eine kostenlose Testversion nutzen[Webseite](https://releases.groupdocs.com/) um die Fähigkeiten von GroupDocs.Viewer für .NET zu testen.