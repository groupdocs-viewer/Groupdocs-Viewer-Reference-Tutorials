---
"description": "Erfahren Sie, wie Sie die Textauswahl in PDF-Dateien mit GroupDocs.Viewer für .NET deaktivieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung für eine nahtlose Integration."
"linktitle": "Textauswahl in PDF deaktivieren"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Textauswahl in PDF deaktivieren"
"url": "/de/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
---

# Textauswahl in PDF deaktivieren

## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke API zur Dokumentdarstellung, mit der Entwickler mühelos Dokumentanzeigefunktionen in ihre .NET-Anwendungen integrieren können. Eine der wichtigsten Funktionen von GroupDocs.Viewer ist die Möglichkeit, die Textauswahl in PDF-Dokumenten zu deaktivieren. Diese Funktion ist besonders nützlich, wenn Sie Benutzer daran hindern möchten, Text aus vertraulichen Dokumenten zu kopieren und so die Sicherheit und Integrität von Dokumenten gewährleisten möchten.

![Deaktivieren Sie die Textauswahl in PDF mit GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Voraussetzungen
Bevor wir uns in die Schritt-für-Schritt-Anleitung zum Deaktivieren der Textauswahl in PDF mit GroupDocs.Viewer für .NET vertiefen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Installation von GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie GroupDocs.Viewer für .NET von der heruntergeladen und installiert haben [Download-Link](https://releases.groupdocs.com/viewer/net/).
2. Dokumentverzeichnis: Bereiten Sie ein Verzeichnis vor, in dem Ihre Dokumente gespeichert werden. Sie müssen dieses Verzeichnis im Codeausschnitt angeben, um das PDF-Dokument darzustellen.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um auf die Funktionen von GroupDocs.Viewer für .NET zugreifen zu können. So geht's:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Vorgang zum Deaktivieren der Textauswahl in einem PDF-Dokument mit GroupDocs.Viewer für .NET in mehrere Schritte aufteilen:
## Schritt 1: Ausgabeverzeichnis angeben
```csharp
string outputDirectory = "Your Document Directory";
```
In diesem Schritt ersetzen `"Your Document Directory"` durch den Verzeichnispfad, in dem sich Ihr PDF-Dokument befindet.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
In diesem Schritt wird das Format für die Dateipfade der gerenderten HTML-Seiten definiert. Jede Seite des PDF-Dokuments wird in eine HTML-Datei mit fortlaufender Seitennummer konvertiert.
## Schritt 3: PDF-Dokument mit deaktivierter Textauswahl rendern
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Ersetzen `"Path to Your PDF Document"` mit dem tatsächlichen Pfad zu Ihrer PDF-Datei. Dieser Codeausschnitt initialisiert eine `Viewer` Objekt, konfiguriert HTML-Ansichtsoptionen zum Einbetten von Ressourcen und deaktiviert die Textauswahl durch die Einstellung `RenderTextAsImage` Eigentum zu `true`.
## Schritt 4: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nach dem Rendern des PDF-Dokuments zeigt dieser Schritt eine Erfolgsmeldung zusammen mit dem Verzeichnis an, in dem die gerenderten HTML-Seiten gespeichert sind.

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie die Textauswahl in PDF-Dokumenten mit GroupDocs.Viewer für .NET deaktivieren. Mit der Schritt-für-Schritt-Anleitung können Sie diese Funktion nahtlos in Ihre .NET-Anwendungen integrieren, die Dokumentensicherheit gewährleisten und das Benutzererlebnis verbessern.
## Häufig gestellte Fragen
### Kann ich das Ausgabeverzeichnis für gerenderte HTML-Seiten anpassen?
Ja, Sie können einen beliebigen Verzeichnispfad angeben, in dem die gerenderten HTML-Seiten gespeichert werden sollen.
### Ist GroupDocs.Viewer für .NET mit verschiedenen Versionen des .NET-Frameworks kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit verschiedenen Versionen des .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Framework.
### Hat das Deaktivieren der Textauswahl Auswirkungen auf andere Funktionen des PDF-Dokuments?
Nein, durch die Deaktivierung der Textauswahl wird lediglich verhindert, dass Benutzer Text aus dem Dokument auswählen und kopieren können. Andere Funktionen bleiben erhalten.
### Kann ich die Textauswahl nach dem Rendern des Dokuments wieder aktivieren?
Ja, Sie können die Textauswahl aktivieren, indem Sie einfach die `RenderTextAsImage` Eigentum zu `false` in den HTML-Ansichtsoptionen.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können auf eine kostenlose Testversion von GroupDocs.Viewer für .NET zugreifen über [Webseite](https://releases.groupdocs.com/).