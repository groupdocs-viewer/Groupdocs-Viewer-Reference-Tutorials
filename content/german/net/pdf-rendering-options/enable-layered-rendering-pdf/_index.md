---
title: Aktivieren Sie Layer-Rendering in PDF
linktitle: Aktivieren Sie Layer-Rendering in PDF
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET das Layer-Rendering in PDF-Dokumenten aktivieren. Verbessern Sie mühelos das Anzeigeerlebnis von Dokumenten.
weight: 15
url: /de/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Einführung
In diesem Tutorial befassen wir uns mit dem Prozess der Aktivierung des Layer-Rendering in PDF-Dokumenten mithilfe von GroupDocs.Viewer für .NET. Das mehrschichtige Rendering ermöglicht eine verbesserte Anzeige und Bearbeitung von Dokumenten und bietet Benutzern ein interaktiveres Anzeigeerlebnis.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie das erforderliche Paket oder die erforderliche Bibliothek für die Verwendung von GroupDocs.Viewer für .NET in Ihrem Projekt installiert haben.
2. Visual Studio: Sie sollten Visual Studio auf Ihrem System installiert haben, um die bereitgestellten Beispiele zu programmieren und auszuführen.
3. Grundlegendes Verständnis von C#: Dieses Tutorial setzt Vertrautheit mit der Syntax und den Konzepten der Programmiersprache C# voraus.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihr Projekt:
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
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Dieser Schritt legt das Format für die Dateipfade einzelner Seiten in der gerenderten Ausgabe fest.`{0}` ist ein Platzhalter für die Seitenzahl.
## Schritt 3: Aktivieren Sie das Layer-Rendering
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Hier erstellen wir eine`Viewer` Objekt und geben Sie das zu verarbeitende PDF-Dokument an. Anschließend konfigurieren wir`HtmlViewOptions` mit dem definierten Auslagerungsdateipfadformat. Indem man es einstellt`EnableLayeredRendering` Eigentum zu`true` In`PdfOptions`, aktivieren wir das Layer-Rendering für das PDF-Dokument.
## Schritt 4: Ausgabeverzeichnis anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Abschließend drucken wir eine Meldung aus, die die erfolgreiche Wiedergabe des Quelldokuments anzeigt, und fordern den Benutzer auf, die Ausgabe im angegebenen Verzeichnis zu überprüfen.

## Abschluss
Durch die Aktivierung der mehrschichtigen Darstellung in PDF-Dokumenten mithilfe von GroupDocs.Viewer für .NET werden die Anzeigefunktionen für Dokumente verbessert und Benutzern ein umfassenderes und interaktiveres Erlebnis geboten. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie diese Funktion nahtlos in Ihre .NET-Anwendungen integrieren.
## FAQs
### Was ist Layer-Rendering in PDF-Dokumenten?
Das Ebenen-Rendering ermöglicht die Trennung und Bearbeitung verschiedener Komponenten innerhalb eines PDF-Dokuments und ermöglicht so eine interaktive Anzeige und ein verbessertes Benutzererlebnis.
### Kann ich das Ausgabeverzeichnis für gerenderte Dokumente anpassen?
Ja, Sie können je nach Ihren Anforderungen einen beliebigen Verzeichnispfad für die Ausgabe angeben.
### Unterstützt GroupDocs.Viewer neben PDF auch andere Dateiformate?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter Word, Excel, PowerPoint und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer ist sowohl mit .NET Framework- als auch mit .NET Core-Umgebungen kompatibel.
### Wo finde ich zusätzliche Unterstützung oder Hilfe?
Sie können das GroupDocs.Viewer-Forum besuchen, wenn Sie Fragen oder Hilfe zur Viewer-Bibliothek haben.