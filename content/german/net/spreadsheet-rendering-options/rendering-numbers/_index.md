---
title: Zahlen rendern
linktitle: Zahlen rendern
second_title: GroupDocs.Viewer .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Groupdocs.Viewer für .NET beim nahtlosen Rendern von Numbers-Dateien. Konvertieren Sie mühelos in HTML, JPG, PNG und PDF.
weight: 15
url: /de/net/spreadsheet-rendering-options/rendering-numbers/
---

# Zahlen rendern

## Einführung
Willkommen zu dieser Schritt-für-Schritt-Anleitung zum Rendern von Numbers-Dateien mit Groupdocs.Viewer für .NET. Egal, ob Sie ein erfahrener Entwickler oder ein Anfänger sind, dieser Leitfaden führt Sie durch den Prozess der Konvertierung von Numbers-Dokumenten in verschiedene Formate. Groupdocs.Viewer für .NET ist ein leistungsstarkes Tool, mit dem Sie Dokumentanzeigefunktionen nahtlos in Ihre .NET-Anwendungen integrieren können.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse in der C#- und .NET-Entwicklung.
-  Groupdocs.Viewer für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.groupdocs.com/viewer/net/).
- Ihr Dokumentverzeichnispfad, in dem die Ausgabedateien gespeichert werden.
## Namespaces importieren
Stellen Sie in Ihrem C#-Projekt sicher, dass Sie die erforderlichen Namespaces importieren, um die Groupdocs.Viewer-Bibliothek zu verwenden:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis einrichten
Bevor Sie mit dem Rendern beginnen, definieren Sie das Ausgabeverzeichnis, in dem die konvertierten Dateien gespeichert werden. Ersetzen Sie „Ihr Dokumentenverzeichnis“ durch den tatsächlichen Pfad:
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
## Schritt 3: Als JPG rendern
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
## Schritt 5: Als PDF rendern
Konvertieren Sie abschließend die Numbers-Datei mit dem folgenden Code in das PDF-Format:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Glückwunsch! Sie haben Numbers-Dateien mit Groupdocs.Viewer für .NET erfolgreich in verschiedene Formate gerendert.
## Abschluss
In diesem Tutorial haben wir die Grundlagen des Renderns von Numbers-Dateien mit Groupdocs.Viewer für .NET behandelt. Diese leistungsstarke Bibliothek bietet eine nahtlose Integration zum Anzeigen und Konvertieren von Dokumenten in Ihren .NET-Anwendungen.
## FAQs
### Kann ich Groupdocs.Viewer für .NET mit anderen Dokumenttypen verwenden?
Ja, Groupdocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter Word, Excel, PDF und mehr.
### Ist eine temporäre Lizenz zu Testzwecken verfügbar?
 Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.groupdocs.com/temporary-license/) zum Prüfen.
### Wo finde ich Unterstützung für Groupdocs.Viewer für .NET?
 Besuche den[Groupdocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9) für Hilfe und Diskussionen.
### Wie kaufe ich die Vollversion von Groupdocs.Viewer für .NET?
 Sie können die Vollversion erwerben[Hier](https://purchase.groupdocs.com/buy).
### Gibt es eine kostenlose Testversion?
 Ja, Sie können die kostenlose Testversion ausprobieren[Hier](https://releases.groupdocs.com/).