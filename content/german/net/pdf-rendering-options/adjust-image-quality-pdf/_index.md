---
"description": "Erfahren Sie, wie Sie die Bildqualität in PDF-Dokumenten mit GroupDocs.Viewer für .NET anpassen. Folgen Sie unserem Schritt-für-Schritt-Tutorial für eine nahtlose Integration."
"linktitle": "Bildqualität in PDF anpassen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Bildqualität in PDF anpassen"
"url": "/de/net/pdf-rendering-options/adjust-image-quality-pdf/"
"weight": 10
---

# Bildqualität in PDF anpassen

## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler mühelos Funktionen zur Dokumentdarstellung in ihre .NET-Anwendungen integrieren können. Eine der wichtigsten Funktionen dieser Bibliothek ist die Möglichkeit, die Bildqualität beim Rendern von PDF-Dokumenten anzupassen. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Anpassung der Bildqualität mit GroupDocs.Viewer für .NET.

![Passen Sie die Bildqualität in PDF mit GroupDocs.Viewer .NET an](/viewer/pdf-rendering-options/adjust-image-quality-in-pdf.png)

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Grundkenntnisse der C#-Programmierung.
2. Visual Studio ist auf Ihrem System installiert.
3. GroupDocs.Viewer für .NET-Bibliothek heruntergeladen und installiert. Sie können es herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).

## Namespaces importieren
Zuerst müssen Sie die erforderlichen Namespaces importieren, um mit GroupDocs.Viewer für .NET zu arbeiten:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Ersetzen `"Your Document Directory"` durch den Pfad, in dem Sie die gerenderten HTML-Seiten speichern möchten.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Diese Zeile definiert das Format für den Dateipfad jeder gerenderten HTML-Seite. `{0}` ist ein Platzhalter für die Seitenzahl.
## Schritt 3: Bildqualität anpassen
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
Ersetzen `"Your PDF File Path"` mit dem Pfad zu Ihrem PDF-Dokument.
## Schritt 4: Ausgabepfad anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Diese Zeile zeigt den Pfad an, in dem die gerenderten HTML-Seiten gespeichert werden.

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie die Bildqualität beim Rendern von PDF-Dokumenten mit GroupDocs.Viewer für .NET anpassen. Mit den oben beschriebenen einfachen Schritten können Sie die Bildqualität ganz einfach an Ihre Anforderungen anpassen.
## Häufig gestellte Fragen
### Kann ich die Bildqualität für andere Dokumentformate außer PDF anpassen?
Ja, GroupDocs.Viewer für .NET unterstützt verschiedene Dokumentformate und Sie können für die meisten davon die Bildqualität anpassen.
### Welche Bildqualitätsoptionen sind verfügbar?
GroupDocs.Viewer für .NET bietet Optionen für niedrige, mittlere und hohe Bildqualität.
### Gibt es eine Möglichkeit, eine Vorschau des Dokuments anzuzeigen, bevor es mit angepasster Bildqualität gerendert wird?
Ja, Sie können GroupDocs.Viewer für .NET verwenden, um Dokumentvorschauen mit unterschiedlichen Bildqualitätseinstellungen zu generieren.
### Benötigt GroupDocs.Viewer für .NET eine Lizenz für die kommerzielle Nutzung?
Ja, für die kommerzielle Nutzung benötigen Sie eine Lizenz. Sie können eine Lizenz erwerben bei [Hier](https://purchase.groupdocs.com/buy).
### Wo erhalte ich Support für GroupDocs.Viewer für .NET?
Sie erhalten Unterstützung im GroupDocs.Viewer-Forum [Hier](https://forum.groupdocs.com/c/viewer/9).