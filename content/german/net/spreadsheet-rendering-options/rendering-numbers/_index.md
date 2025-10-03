---
"description": "Entdecken Sie die Leistungsfähigkeit von Groupdocs.Viewer für .NET beim nahtlosen Rendern von Numbers-Dateien. Konvertieren Sie mühelos in HTML, JPG, PNG und PDF."
"linktitle": "Rendering-Zahlen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendering-Zahlen"
"url": "/de/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
type: docs
---
# Rendering-Zahlen

## Einführung
Willkommen zu diesem Schritt-für-Schritt-Tutorial zum Rendern von Numbers-Dateien mit Groupdocs.Viewer für .NET. Egal, ob Sie erfahrener Entwickler oder Anfänger sind, diese Anleitung führt Sie durch die Konvertierung von Numbers-Dokumenten in verschiedene Formate. Groupdocs.Viewer für .NET ist ein leistungsstarkes Tool, mit dem Sie die Dokumentanzeige nahtlos in Ihre .NET-Anwendungen integrieren können.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Praktische Kenntnisse in der C#- und .NET-Entwicklung.
- Groupdocs.Viewer für .NET-Bibliothek installiert. Sie können es herunterladen [Hier](https://releases.groupdocs.com/viewer/net/).
- Ihr Dokumentverzeichnispfad, in dem die Ausgabedateien gespeichert werden.
## Namespaces importieren
Stellen Sie in Ihrem C#-Projekt sicher, dass Sie die erforderlichen Namespaces importieren, um die Bibliothek Groupdocs.Viewer zu verwenden:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis einrichten
Bevor Sie mit dem Rendern beginnen, legen Sie das Ausgabeverzeichnis fest, in dem die konvertierten Dateien gespeichert werden. Ersetzen Sie "Ihr Dokumentverzeichnis" durch den tatsächlichen Pfad:
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: In mehrseitiges HTML rendern
Verwenden Sie den folgenden Code, um die Numbers-Datei in mehrseitiges HTML zu konvertieren:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Schritt 3: In JPG rendern
Konvertieren Sie die Numbers-Datei mit dem folgenden Code in das JPG-Format:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Schritt 4: In PNG rendern
Wandeln Sie die Numbers-Datei mit dem folgenden Code in das PNG-Format um:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Schritt 5: In PDF rendern
Konvertieren Sie abschließend die Numbers-Datei mit dem folgenden Code in das PDF-Format:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Herzlichen Glückwunsch! Sie haben Numbers-Dateien mit Groupdocs.Viewer für .NET erfolgreich in verschiedene Formate gerendert.
## Abschluss
In diesem Tutorial haben wir die Grundlagen des Renderns von Numbers-Dateien mit Groupdocs.Viewer für .NET behandelt. Diese leistungsstarke Bibliothek ermöglicht die nahtlose Integration zum Anzeigen und Konvertieren von Dokumenten in Ihren .NET-Anwendungen.
## FAQs
### Kann ich Groupdocs.Viewer für .NET mit anderen Dokumenttypen verwenden?
Ja, Groupdocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter Word, Excel, PDF und mehr.
### Ist eine temporäre Lizenz zu Testzwecken verfügbar?
Ja, Sie können eine vorübergehende Lizenz erhalten [Hier](https://purchase.groupdocs.com/temporary-license/) zum Testen.
### Wo finde ich Unterstützung für Groupdocs.Viewer für .NET?
Besuchen Sie die [Groupdocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) für Hilfe und Diskussionen.
### Wie kaufe ich die Vollversion von Groupdocs.Viewer für .NET?
Sie können die Vollversion erwerben [Hier](https://purchase.groupdocs.com/buy).
### Gibt es eine kostenlose Testversion?
Ja, Sie können die kostenlose Testversion erkunden [Hier](https://releases.groupdocs.com/).