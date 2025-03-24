---
title: Rendern Sie EMZ- und EMF-Bilder
linktitle: Rendern Sie EMZ- und EMF-Bilder
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie EMZ- und EMF-Bilder mit GroupDocs.Viewer für .NET in verschiedene Formate rendern. Leicht verständliches Tutorial für Entwickler.
weight: 14
url: /de/net/image-rendering/render-emz-emf-images/
---

# Rendern Sie EMZ- und EMF-Bilder

## Einführung

GroupDocs.Viewer für .NET ist eine leistungsstarke API zum Rendern von Dokumenten, mit der Entwickler verschiedene Dokumenttypen, einschließlich EMZ-Bilder (Enhanced Windows Metafile) und EMF-Bilder (Enhanced Metafile), in ihren .NET-Anwendungen anzeigen können. In diesem Tutorial erfahren Sie, wie Sie EMZ- und EMF-Bilder mit GroupDocs.Viewer für .NET in verschiedene Formate wie HTML, JPG, PNG und PDF rendern.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1.  GroupDocs.Viewer für .NET: Sie können die Bibliothek herunterladen von[Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine kompatible Entwicklungsumgebung für die .NET-Entwicklung eingerichtet haben.
3. EMZ/EMF-Beispielbilder: Halten Sie EMZ- und EMF-Beispielbilder zum Rendern bereit.

## Namespaces importieren

Bevor wir uns mit dem Code befassen, importieren wir die erforderlichen Namespaces:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Lassen Sie uns nun jedes Beispiel in einer Schritt-für-Schritt-Anleitung in mehrere Schritte unterteilen:

## Rendern von EMZ/EMF-Bildern in HTML

### Schritt 1: Ausgabeverzeichnis festlegen:
```csharp
string outputDirectory = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"`mit dem Pfad, in dem Sie die gerenderte HTML-Datei speichern möchten.

### Schritt 2: Definieren Sie das Format des Seitendateipfads:
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
 Dieser Code initialisiert die`Viewer` Objekt mit dem EMZ-Beispielbild und rendert es mithilfe der angegebenen Optionen in das HTML-Format.

## Rendern von EMZ/EMF-Bildern in JPG, PNG und PDF

Wiederholen Sie die folgenden Schritte zum Rendern in den Formaten JPG, PNG und PDF:

### Schritt 1: Definieren Sie das Format des Seitendateipfads:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Passen Sie den Dateinamen und die Erweiterung entsprechend dem gewünschten Ausgabeformat an (`jpg`, `png` , oder`pdf`).

### Schritt 2: Im entsprechenden Format rendern:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Passen Sie die Optionen entsprechend dem Ausgabeformat (JPG, PNG, PDF) an.
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Ersetzen`JpgViewOptions` mit`PngViewOptions` oder`PdfViewOptions` basierend auf dem gewünschten Ausgabeformat.

## Abschluss

Zusammenfassend bietet GroupDocs.Viewer für .NET eine nahtlose Lösung zum Rendern von EMZ- und EMF-Bildern in verschiedenen Formaten in .NET-Anwendungen. Durch Befolgen der in diesem Tutorial beschriebenen Schritte können Entwickler mühelos Dokument-Rendering-Funktionen in ihre Anwendungen integrieren.

## FAQs

### F: Kann GroupDocs.Viewer neben EMZ- und EMF-Bildern auch andere Dokumentformate rendern?
A: Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, DOCX, PPTX, XLSX und mehr.

### F: Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
 A: Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.groupdocs.com/).

### F: Bietet GroupDocs.Viewer Unterstützung für Entwickler?
 A: Ja, GroupDocs bietet Support durch[Forum](https://forum.groupdocs.com/c/viewer/9) Hier können Entwickler Fragen stellen und Hilfe suchen.

### F: Kann ich eine temporäre Lizenz für GroupDocs.Viewer für .NET erwerben?
 A: Ja, temporäre Lizenzen können erworben werden[Hier](https://purchase.groupdocs.com/temporary-license/).

### F: Wo finde ich eine ausführliche Dokumentation für GroupDocs.Viewer für .NET?
 A: Sie können sich auf die Dokumentation beziehen[Hier](https://tutorials.groupdocs.com/viewer/net/)Eine umfassende Anleitung zur Verwendung der API finden Sie hier.