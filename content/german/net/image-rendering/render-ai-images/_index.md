---
title: Rendern Sie KI-Bilder
linktitle: Rendern Sie KI-Bilder
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET mühelos KI-Bilder in .NET-Anwendungen rendern. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
weight: 10
url: /de/net/image-rendering/render-ai-images/
---
## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, mühelos verschiedene Dokumentformate in ihren .NET-Anwendungen zu rendern. Unabhängig davon, ob Sie KI-Bilder, PDFs oder andere Dokumenttypen anzeigen müssen, GroupDocs.Viewer vereinfacht den Prozess und bietet mehrere Ausgabeformate für eine nahtlose Integration in Ihre Projekte. Dieses Tutorial führt Sie Schritt für Schritt durch das Rendern von KI-Bildern mit GroupDocs.Viewer für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Visual Studio: Installieren Sie die Visual Studio-IDE auf Ihrem System.
2.  GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET von herunter und installieren Sie es[Webseite](https://releases.groupdocs.com/viewer/net/).
3. Grundkenntnisse in C#: Zum Verständnis der Codebeispiele sind Kenntnisse der Programmiersprache C# erforderlich.

## Namespaces importieren
Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um auf die Funktionen von GroupDocs.Viewer für .NET zuzugreifen.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Das Rendern von KI-Bildern mit GroupDocs.Viewer für .NET umfasst mehrere Schritte, die jeweils auf ein bestimmtes Ausgabeformat zugeschnitten sind. Im Folgenden unterteilen wir den Prozess zur besseren Übersichtlichkeit in einzelne Schritte.
## Schritt 1: Geben Sie das Ausgabeverzeichnis an
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
GroupDocs.Viewer für .NET bietet eine nahtlose Lösung zum Rendern von KI-Bildern und verschiedenen Dokumentformaten in .NET-Anwendungen. Durch Befolgen der Schritt-für-Schritt-Anleitung in diesem Tutorial können Entwickler mühelos Dokument-Rendering-Funktionen in ihre Projekte integrieren.
## FAQs
### Kann ich das Erscheinungsbild der Ausgabe beim Rendern von AI-Bildern anpassen?
Ja, GroupDocs.Viewer für .NET bietet verschiedene Optionen zum Anpassen der Ausgabedarstellung, einschließlich Seitengröße, Bildqualität und mehr.
### Gibt es zu Testzwecken eine Testversion?
 Ja, Sie können eine kostenlose Testversion von GroupDocs herunterladen[Webseite](https://releases.groupdocs.com/viewer/net/) um die Funktionen der Bibliothek vor dem Kauf zu bewerten.
### Unterstützt GroupDocs.Viewer das Rendern verschlüsselter KI-Bilder?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern verschlüsselter KI-Bilder mit den entsprechenden bereitgestellten Entschlüsselungsschlüsseln.
### Kann ich KI-Bilder direkt von URLs rendern?
Ja, GroupDocs.Viewer für .NET ermöglicht das Rendern von KI-Bildern von URLs durch Angabe des URL-Pfads anstelle eines lokalen Dateipfads.
### Ist technischer Support für GroupDocs.Viewer für .NET verfügbar?
 Ja, technischer Support ist über GroupDocs verfügbar[Forum](https://forum.groupdocs.com/c/viewer/9), wo Sie Fragen stellen, Probleme melden und Hilfe von der Community suchen können.