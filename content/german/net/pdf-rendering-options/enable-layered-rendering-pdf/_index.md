---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET die Ebenendarstellung in PDF-Dokumenten aktivieren. Verbessern Sie mühelos die Dokumentanzeige."
"linktitle": "Aktivieren Sie die geschichtete Darstellung in PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Aktivieren Sie die geschichtete Darstellung in PDF"
"url": "/de/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
---

# Aktivieren Sie die geschichtete Darstellung in PDF

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET die Ebenendarstellung in PDF-Dokumenten aktivieren. Die Ebenendarstellung ermöglicht eine verbesserte Dokumentanzeige und -bearbeitung und bietet Benutzern ein interaktiveres Anzeigeerlebnis.

![Aktivieren Sie die geschichtete Darstellung in PDF mit GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie das erforderliche Paket oder die erforderliche Bibliothek für die Verwendung von GroupDocs.Viewer für .NET in Ihrem Projekt installiert haben.
2. Visual Studio: Zum Codieren und Ausführen der bereitgestellten Beispiele sollte Visual Studio auf Ihrem System installiert sein.
3. Grundlegende Kenntnisse in C#: Dieses Tutorial setzt voraus, dass Sie mit der Syntax und den Konzepten der Programmiersprache C# vertraut sind.

## Namespaces importieren
Beginnen Sie, indem Sie die erforderlichen Namespaces in Ihr Projekt importieren:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Stellen Sie sicher, dass Sie den Verzeichnispfad angeben, in dem die gerenderte Ausgabe gespeichert werden soll.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Dieser Schritt legt das Format für die Dateipfade einzelner Seiten in der gerenderten Ausgabe fest. `{0}` ist ein Platzhalter für die Seitenzahl.
## Schritt 3: Aktivieren Sie das Layered Rendering
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Hier erstellen wir eine `Viewer` Objekt und geben das zu verarbeitende PDF-Dokument an. Anschließend konfigurieren wir `HtmlViewOptions` mit dem definierten Seitendateipfadformat. Durch die Einstellung `EnableLayeredRendering` Eigentum zu `true` In `PdfOptions`aktivieren wir die Ebenendarstellung für das PDF-Dokument.
## Schritt 4: Ausgabeverzeichnis anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Abschließend drucken wir eine Meldung, die die erfolgreiche Wiedergabe des Quelldokuments anzeigt, und fordern den Benutzer auf, die Ausgabe im angegebenen Verzeichnis zu überprüfen.

## Abschluss
Die Aktivierung der mehrschichtigen Darstellung in PDF-Dokumenten mit GroupDocs.Viewer für .NET verbessert die Dokumentanzeige und bietet Benutzern ein umfassenderes und interaktiveres Erlebnis. Mit den in diesem Tutorial beschriebenen Schritten können Sie diese Funktion nahtlos in Ihre .NET-Anwendungen integrieren.
## Häufig gestellte Fragen
### Was ist Layered Rendering in PDF-Dokumenten?
Durch die geschichtete Darstellung können verschiedene Komponenten in einem PDF-Dokument getrennt und bearbeitet werden, was eine interaktive Anzeige und ein verbessertes Benutzererlebnis ermöglicht.
### Kann ich das Ausgabeverzeichnis für gerenderte Dokumente anpassen?
Ja, Sie können je nach Bedarf einen beliebigen Verzeichnispfad für die Ausgabe angeben.
### Unterstützt GroupDocs.Viewer neben PDF auch andere Dateiformate?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter Word, Excel, PowerPoint und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer ist sowohl mit .NET Framework- als auch mit .NET Core-Umgebungen kompatibel.
### Wo finde ich zusätzliche Unterstützung oder Hilfe?
Sie können das GroupDocs.Viewer-Forum besuchen, wenn Sie Fragen haben oder Hilfe zur Viewer-Bibliothek benötigen.