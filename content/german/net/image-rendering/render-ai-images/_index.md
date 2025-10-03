---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET mühelos KI-Bilder in .NET-Anwendungen rendern. Folgen Sie unserem Schritt-für-Schritt-Tutorial für eine nahtlose Integration."
"linktitle": "Rendern von KI-Bildern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendern von KI-Bildern"
"url": "/de/net/image-rendering/render-ai-images/"
"weight": 10
type: docs
---
# Rendern von KI-Bildern

## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, verschiedene Dokumentformate mühelos in ihren .NET-Anwendungen darzustellen. Ob Sie KI-Bilder, PDFs oder andere Dokumenttypen anzeigen möchten – GroupDocs.Viewer vereinfacht den Prozess und bietet verschiedene Ausgabeformate für die nahtlose Integration in Ihre Projekte. Dieses Tutorial führt Sie Schritt für Schritt durch das Rendern von KI-Bildern mit GroupDocs.Viewer für .NET.

![Rendern Sie KI-Bilder mit GroupDocs.Viewer für .NET](/viewer/image-rendering/render-ai-images.png)

## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Visual Studio: Installieren Sie Visual Studio IDE auf Ihrem System.
2. GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von der [Webseite](https://releases.groupdocs.com/viewer/net/).
3. Grundkenntnisse in C#: Zum Verständnis der Codebeispiele sind Kenntnisse der Programmiersprache C# erforderlich.

## Namespaces importieren
Importieren Sie in Ihr C#-Projekt die erforderlichen Namespaces, um auf die Funktionen von GroupDocs.Viewer für .NET zuzugreifen.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Das Rendern von KI-Bildern mit GroupDocs.Viewer für .NET umfasst mehrere Schritte, die jeweils auf ein bestimmtes Ausgabeformat zugeschnitten sind. Im Folgenden wird der Prozess zur Vereinfachung in einzelne Schritte unterteilt.
## Schritt 1: Ausgabeverzeichnis angeben
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Rendern in HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 3: Rendern in JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 4: Rendern in PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 5: Rendern in PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Abschluss
GroupDocs.Viewer für .NET bietet eine nahtlose Lösung zum Rendern von KI-Bildern und verschiedenen Dokumentformaten in .NET-Anwendungen. Mithilfe der Schritt-für-Schritt-Anleitung in diesem Tutorial können Entwickler Dokumentrendering-Funktionen mühelos in ihre Projekte integrieren.
## Häufig gestellte Fragen
### Kann ich das Ausgabeerscheinungsbild beim Rendern von KI-Bildern anpassen?
Ja, GroupDocs.Viewer für .NET bietet verschiedene Optionen zum Anpassen des Ausgabeerscheinungsbilds, einschließlich Seitengröße, Bildqualität und mehr.
### Gibt es eine Testversion zum Testen?
Ja, Sie können eine kostenlose Testversion von GroupDocs herunterladen. [Webseite](https://releases.groupdocs.com/viewer/net/) um die Funktionen der Bibliothek zu bewerten, bevor Sie einen Kauf tätigen.
### Unterstützt GroupDocs.Viewer das Rendern verschlüsselter KI-Bilder?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern verschlüsselter KI-Bilder mit den bereitgestellten entsprechenden Entschlüsselungsschlüsseln.
### Kann ich KI-Bilder direkt aus URLs rendern?
Ja, GroupDocs.Viewer für .NET ermöglicht das Rendern von KI-Bildern aus URLs, indem der URL-Pfad anstelle eines lokalen Dateipfads angegeben wird.
### Ist technischer Support für GroupDocs.Viewer für .NET verfügbar?
Ja, technischer Support ist über die GroupDocs verfügbar [Forum](https://forum.groupdocs.com/c/viewer/9), wo Sie Fragen stellen, Probleme melden und die Community um Hilfe bitten können.