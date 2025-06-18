---
"description": "Erfahren Sie, wie Sie EMZ- und EMF-Bilder mit GroupDocs.Viewer für .NET in verschiedene Formate rendern. Leicht verständliches Tutorial für Entwickler."
"linktitle": "Rendern Sie EMZ- und EMF-Bilder"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendern Sie EMZ- und EMF-Bilder"
"url": "/de/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# Rendern Sie EMZ- und EMF-Bilder

## Einführung

GroupDocs.Viewer für .NET ist eine leistungsstarke API zur Dokumentdarstellung, die es Entwicklern ermöglicht, verschiedene Dokumenttypen, darunter EMZ- (Enhanced Windows Metafile) und EMF- (Enhanced Metafile) Bilder, in ihren .NET-Anwendungen anzuzeigen. In diesem Tutorial erfahren Sie, wie Sie EMZ- und EMF-Bilder mit GroupDocs.Viewer für .NET in verschiedene Formate wie HTML, JPG, PNG und PDF rendern.

![Rendern Sie EMZ- und EMF-Bilder mit GroupDocs.Viewer für .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. GroupDocs.Viewer für .NET: Sie können die Bibliothek herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine kompatible Entwicklungsumgebung für die .NET-Entwicklung eingerichtet haben.
3. Beispielbilder von EMZ/EMF: Halten Sie Beispielbilder von EMZ und EMF zum Rendern bereit.

## Namespaces importieren

Bevor wir uns in den Code vertiefen, importieren wir die erforderlichen Namespaces:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Lassen Sie uns nun jedes Beispiel in Form einer Schritt-für-Schritt-Anleitung in mehrere Schritte unterteilen:

## Rendern von EMZ/EMF-Bildern in HTML

### Schritt 1: Ausgabeverzeichnis festlegen:
```csharp
string outputDirectory = "Your Document Directory";
```
Ersetzen `"Your Document Directory"` durch den Pfad, in dem Sie die gerenderte HTML-Datei speichern möchten.

### Schritt 2: Definieren Sie das Auslagerungsdateipfadformat:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Dadurch wird das Dateipfadformat für die gerenderte HTML-Datei angegeben.

### Schritt 3: In HTML rendern:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Dieser Code initialisiert die `Viewer` Objekt mit dem EMZ-Beispielbild und rendert es mithilfe der angegebenen Optionen in das HTML-Format.

## Rendern von EMZ/EMF-Bildern in JPG, PNG und PDF

Wiederholen Sie die folgenden Schritte zum Rendern in die Formate JPG, PNG und PDF:

### Schritt 1: Definieren Sie das Auslagerungsdateipfadformat:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Passen Sie den Dateinamen und die Erweiterung entsprechend dem gewünschten Ausgabeformat an (`jpg`, `png`, oder `pdf`).

### Schritt 2: In das jeweilige Format rendern:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Passen Sie die Optionen entsprechend dem Ausgabeformat (Jpg, Png, Pdf) an.
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Ersetzen `JpgViewOptions` mit `PngViewOptions` oder `PdfViewOptions` basierend auf dem gewünschten Ausgabeformat.

## Abschluss

Zusammenfassend lässt sich sagen, dass GroupDocs.Viewer für .NET eine nahtlose Lösung für die Darstellung von EMZ- und EMF-Bildern in verschiedenen Formaten in .NET-Anwendungen bietet. Mit den in diesem Tutorial beschriebenen Schritten können Entwickler Dokumentrendering-Funktionen mühelos in ihre Anwendungen integrieren.

## Häufig gestellte Fragen

### F: Kann GroupDocs.Viewer neben EMZ- und EMF-Bildern auch andere Dokumentformate rendern?
A: Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, DOCX, PPTX, XLSX und mehr.

### F: Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
A: Ja, Sie können auf die kostenlose Testversion zugreifen [Hier](https://releases.groupdocs.com/).

### F: Bietet GroupDocs.Viewer Support für Entwickler?
A: Ja, GroupDocs bietet Support über seine [Forum](https://forum.groupdocs.com/c/viewer/9) wo Entwickler Fragen stellen und Hilfe suchen können.

### F: Kann ich eine temporäre Lizenz für GroupDocs.Viewer für .NET erwerben?
A: Ja, temporäre Lizenzen sind zum Kauf verfügbar [Hier](https://purchase.groupdocs.com/temporary-license/).

### F: Wo finde ich eine ausführliche Dokumentation für GroupDocs.Viewer für .NET?
A: Sie können in der Dokumentation nachschlagen [Hier](https://tutorials.groupdocs.com/viewer/net/) für umfassende Anleitungen zur Verwendung der API.