---
"description": "Erfahren Sie, wie Sie FODG- und ODG-Bilder mit GroupDocs.Viewer für .NET in HTML, JPG, PNG und PDF umwandeln. Optimieren Sie Ihre Dokumentenverwaltung."
"linktitle": "Rendern von FODG- und ODG-Bildern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendern von FODG- und ODG-Bildern"
"url": "/de/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# Rendern von FODG- und ODG-Bildern

## Einführung
In der Softwareentwicklung ist der effiziente Umgang mit Dokumentformaten von größter Bedeutung. GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool, das die Darstellung von FODG- und ODG-Bildern in .NET-Anwendungen vereinfacht. Dieses Tutorial führt Sie durch die erforderlichen Schritte zum Rendern dieser Bilder in verschiedene Formate wie HTML, JPG, PNG und PDF mit GroupDocs.Viewer für .NET.

![Rendern Sie FODG- und ODG-Bilder mit GroupDocs.Viewer für .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von [Hier](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Stellen Sie sicher, dass .NET Framework auf Ihrem System installiert ist.
3. Grundkenntnisse in C#: Kenntnisse der Programmiersprache C# sind hilfreich.

## Namespaces importieren
Bevor Sie mit der Implementierung beginnen, importieren Sie die erforderlichen Namespaces:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Schritt 1: Ausgabeverzeichnis festlegen
```csharp
string outputDirectory = "Your Document Directory";
```
Ersetzen `"Your Document Directory"` durch den Verzeichnispfad, in dem Sie die gerenderten Bilder speichern möchten.
## Schritt 2: In HTML rendern
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Dieser Schritt rendert das FODG-Bild in das HTML-Format.
## Schritt 3: In JPG rendern
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Hier wird das FODG-Bild im JPG-Format gerendert.
## Schritt 4: In PNG rendern
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Dieser Schritt konvertiert das FODG-Bild in das PNG-Format.
## Schritt 5: In PDF rendern
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Schließlich wird das FODG-Bild im PDF-Format gerendert.

## Abschluss
In diesem Tutorial haben wir gezeigt, wie Sie FODG- und ODG-Bilder mit GroupDocs.Viewer für .NET in verschiedene Formate rendern. Mit diesen Schritten können Sie Dokumentrendering-Funktionen nahtlos in Ihre .NET-Anwendungen integrieren.
## Häufig gestellte Fragen
### Ist GroupDocs.Viewer für .NET mit allen Versionen von .NET Framework kompatibel?
GroupDocs.Viewer für .NET ist mit einer Vielzahl von .NET Framework-Versionen kompatibel, einschließlich der neuesten.
### Kann ich mit GroupDocs.Viewer für .NET Dokumente asynchron rendern?
Ja, GroupDocs.Viewer für .NET bietet asynchrone Rendering-Funktionen für eine verbesserte Leistung.
### Unterstützt GroupDocs.Viewer für .NET das Rendern verschlüsselter Dokumente?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern verschlüsselter Dokumente mit entsprechenden Entschlüsselungsschlüsseln.
### Ist es möglich, die Rendering-Ausgabe mit GroupDocs.Viewer für .NET anzupassen?
Absolut, GroupDocs.Viewer für .NET bietet verschiedene Anpassungsoptionen, um die Rendering-Ausgabe an Ihre Anforderungen anzupassen.
### Kann ich mit GroupDocs.Viewer für .NET Dokumente aus Remote-Speicherorten rendern?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern von Dokumenten sowohl von lokalen als auch von Remote-Speicherorten.