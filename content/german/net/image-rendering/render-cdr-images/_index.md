---
"description": "Erfahren Sie, wie Sie CDR-Bilder mit GroupDocs.Viewer für .NET in HTML, JPG, PNG und PDF konvertieren. Mit diesem Tutorial können Sie CorelDRAW-Dateien ganz einfach konvertieren."
"linktitle": "CDR-Bilder rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CDR-Bilder rendern"
"url": "/de/net/image-rendering/render-cdr-images/"
"weight": 12
---

# CDR-Bilder rendern

## Einführung
In diesem Tutorial führen wir Sie durch das Rendern von CDR-Bildern (CorelDRAW) mit GroupDocs.Viewer für .NET. CDR ist ein Dateiformat, das hauptsächlich mit CorelDRAW, einem Vektorgrafik-Editor, verknüpft ist. Mit GroupDocs.Viewer können Sie CDR-Dateien problemlos in verschiedene Formate wie HTML, JPG, PNG und PDF konvertieren.

![Rendern Sie CDR-Bilder mit GroupDocs.Viewer für .NET](/viewer/image-rendering/render-cdr-images.png)

## Voraussetzungen
Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie GroupDocs.Viewer für .NET installiert haben. Sie können es herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
2. Dokumentverzeichnis: Bereiten Sie ein Verzeichnis vor, in dem Sie die gerenderten Bilder speichern möchten.
3. Grundkenntnisse in C#: Zum Verständnis der Codebeispiele sind Kenntnisse der Programmiersprache C# erforderlich.
## Namespaces importieren
Bevor Sie sich in die Codebeispiele vertiefen, importieren Sie die erforderlichen Namespaces in Ihre C#-Datei:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Lassen Sie uns nun jedes Beispiel in mehrere Schritte unterteilen:
## Rendern in HTML
1. Definieren Sie das Ausgabeverzeichnis, in dem Sie die gerenderten HTML-Dateien speichern möchten:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Geben Sie das Dateipfadformat für HTML-Dateien an:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Verwenden Sie die Viewer-Klasse, um die CDR-Datei in HTML zu rendern:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendern in JPG
1. Definieren Sie das Dateipfadformat für JPG-Dateien:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Verwenden Sie die Viewer-Klasse, um die CDR-Datei in JPG zu rendern:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendern in PNG
1. Definieren Sie das Dateipfadformat für PNG-Dateien:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Verwenden Sie die Viewer-Klasse, um die CDR-Datei in PNG zu rendern:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendern in PDF
1. Definieren Sie das Dateipfadformat für PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Verwenden Sie die Viewer-Klasse, um die CDR-Datei in PDF zu rendern:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Optional können Sie Rendering-Optionen angeben oder bestimmte Seiten rendern, indem Sie zusätzliche Parameter an die `viewer.View()` Verfahren.
## Abschluss
Das Rendern von CDR-Bildern in verschiedene Formate wie HTML, JPG, PNG und PDF mit GroupDocs.Viewer für .NET ist unkompliziert. Mit den in diesem Tutorial beschriebenen Schritten können Sie CDR-Dateien effizient und Ihren Anforderungen entsprechend in verschiedene Formate konvertieren.
## Häufig gestellte Fragen
### Ist GroupDocs.Viewer für .NET mit allen Versionen von CDR-Dateien kompatibel?
GroupDocs.Viewer für .NET unterstützt das Rendern von CDR-Dateien, die mit verschiedenen Versionen von CorelDRAW erstellt wurden.
### Kann ich die Ausgabe gerenderter Dateien anpassen?
Ja, GroupDocs.Viewer für .NET bietet verschiedene Optionen zum Anpassen der Ausgabe, z. B. zum Anpassen der Bildqualität, zum Festlegen eines Wasserzeichens usw.
### Erfordert GroupDocs.Viewer für .NET externe Abhängigkeiten?
Nein, GroupDocs.Viewer für .NET ist eine eigenständige Bibliothek und erfordert keine externen Abhängigkeiten zum Rendern von Dokumenten.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer für .NET herunterladen von [Hier](https://releases.groupdocs.com/).
### Wo erhalte ich Support für GroupDocs.Viewer für .NET?
Sie erhalten Unterstützung im GroupDocs.Viewer-Community-Forum [Hier](https://forum.groupdocs.com/c/viewer/9).