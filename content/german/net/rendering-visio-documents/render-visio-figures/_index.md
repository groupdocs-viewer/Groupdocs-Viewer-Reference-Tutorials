---
"description": "Erfahren Sie, wie Sie Visio-Abbildungen mit GroupDocs.Viewer für .NET rendern. Verbessern Sie die Dokumentanzeige in Ihren .NET-Anwendungen."
"linktitle": "Visio-Figuren rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Visio-Figuren rendern"
"url": "/de/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
type: docs
---
# Visio-Figuren rendern

## Einführung
Im digitalen Zeitalter spielt die Dokumentdarstellung in verschiedenen Anwendungen eine entscheidende Rolle. Ob bei der Anzeige von Dokumenten auf einer Website oder deren Konvertierung in verschiedene Formate – effizientes Rendering ist unerlässlich. GroupDocs.Viewer für .NET bietet eine robuste Lösung zum Anzeigen und Bearbeiten von Dokumenten in .NET-Anwendungen. In diesem Tutorial erfahren Sie mehr über das Rendern von Visio-Abbildungen mit GroupDocs.Viewer für .NET und gliedern den Prozess in einfache Schritte.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Umgebungseinrichtung: Stellen Sie sicher, dass Sie über eine funktionierende Umgebung für die .NET-Entwicklung verfügen.
2. GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von der [Download-Link](https://releases.groupdocs.com/viewer/net/).
3. Grundlegende Kenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
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
- Ausgabeverzeichnis: Definieren Sie das Verzeichnis, in dem das gerenderte HTML gespeichert wird.
- Seitendateipfadformat: Geben Sie das Pfadformat für die HTML-Seite an.
- Viewer-Initialisierung: Initialisieren Sie das Viewer-Objekt mit dem Pfad zum Visio-Dokument.
- HTML-Anzeigeoptionen: Konfigurieren Sie Optionen für die HTML-Wiedergabe.
- Visio-Rendering-Optionen: Legen Sie Optionen fest, die speziell für das Visio-Rendering gelten, z. B. das Rendern nur von Abbildungen und der Abbildungsbreite.
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
- Die Konfiguration für das Rendern im PNG-Format folgt einem ähnlichen Muster wie das Rendern von JPG.
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
- Konfigurieren Sie zum Rendern in PDF die Optionen, die speziell für das PDF-Format gelten.

## Abschluss
In diesem Tutorial haben wir gezeigt, wie Sie Visio-Abbildungen mit GroupDocs.Viewer für .NET rendern. Mit der Schritt-für-Schritt-Anleitung können Sie Dokumentrendering-Funktionen nahtlos in Ihre .NET-Anwendungen integrieren und so Benutzerfreundlichkeit und Produktivität steigern.
## Häufig gestellte Fragen
### Kann ich die Rendering-Optionen für Visio-Abbildungen anpassen?
Ja, GroupDocs.Viewer für .NET bietet umfangreiche Optionen zum Anpassen der Darstellung, einschließlich Abbildungsbreite, Darstellung nur von Abbildungen und mehr.
### Ist GroupDocs.Viewer für .NET für die groß angelegte Dokumentwiedergabe geeignet?
Auf jeden Fall, GroupDocs.Viewer für .NET ist für die effiziente Verarbeitung der Dokumentwiedergabe im großen Maßstab optimiert.
### Unterstützt GroupDocs.Viewer außer Visio auch andere Dokumentformate?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office, AutoCAD und mehr.
### Kann ich GroupDocs.Viewer in Webanwendungen integrieren?
Ja, GroupDocs.Viewer kann nahtlos in Webanwendungen zur Anzeige und Bearbeitung von Dokumenten integriert werden.
### Gibt es eine Testversion zum Testen vor dem Kauf?
Ja, Sie können eine kostenlose Testversion nutzen von der [Webseite](https://releases.groupdocs.com/) um die Funktionen von GroupDocs.Viewer für .NET zu testen.