---
title: Deaktivieren Sie die Textauswahl in PDF
linktitle: Deaktivieren Sie die Textauswahl in PDF
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie die Textauswahl in PDF mit GroupDocs.Viewer für .NET deaktivieren. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 13
url: /de/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke API zum Rendern von Dokumenten, mit der Entwickler mühelos Dokumentanzeigefunktionen in ihre .NET-Anwendungen integrieren können. Eine der wichtigsten Funktionen von GroupDocs.Viewer ist die Möglichkeit, die Textauswahl in PDF-Dokumenten zu deaktivieren. Diese Funktion ist besonders nützlich in Szenarien, in denen Sie verhindern müssen, dass Benutzer Text aus vertraulichen Dokumenten kopieren, um die Sicherheit und Integrität der Dokumente zu gewährleisten.
## Voraussetzungen
Bevor wir uns mit der Schritt-für-Schritt-Anleitung zum Deaktivieren der Textauswahl in PDF mit GroupDocs.Viewer für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Installation von GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie GroupDocs.Viewer für .NET von heruntergeladen und installiert haben[Download-Link](https://releases.groupdocs.com/viewer/net/).
2. Dokumentenverzeichnis: Bereiten Sie ein Verzeichnis vor, in dem Ihre Dokumente gespeichert werden. Sie müssen dieses Verzeichnis im Code-Snippet angeben, um das PDF-Dokument zu rendern.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um auf die von GroupDocs.Viewer für .NET bereitgestellten Funktionen zuzugreifen. So können Sie es machen:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Prozess der Deaktivierung der Textauswahl in einem PDF-Dokument mithilfe von GroupDocs.Viewer für .NET in mehrere Schritte unterteilen:
## Schritt 1: Geben Sie das Ausgabeverzeichnis an
```csharp
string outputDirectory = "Your Document Directory";
```
 In diesem Schritt ersetzen`"Your Document Directory"` mit dem Verzeichnispfad, in dem sich Ihr PDF-Dokument befindet.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Dieser Schritt definiert das Format für die Dateipfade der gerenderten HTML-Seiten. Jede Seite des PDF-Dokuments wird in eine HTML-Datei mit fortlaufender Seitennummer konvertiert.
## Schritt 3: PDF-Dokument mit deaktivierter Textauswahl rendern
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Ersetzen`"Path to Your PDF Document"` mit dem tatsächlichen Pfad zu Ihrer PDF-Datei. Dieses Code-Snippet initialisiert a`Viewer` Objekt, konfiguriert HTML-Ansichtsoptionen zum Einbetten von Ressourcen und deaktiviert die Textauswahl durch Einstellung`RenderTextAsImage` Eigentum zu`true`.
## Schritt 4: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nach dem Rendern des PDF-Dokuments zeigt dieser Schritt eine Erfolgsmeldung zusammen mit dem Verzeichnis an, in dem die gerenderten HTML-Seiten gespeichert sind.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Textauswahl in PDF-Dokumenten mit GroupDocs.Viewer für .NET deaktiviert. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktion nahtlos in Ihre .NET-Anwendungen integrieren und so die Dokumentensicherheit gewährleisten und das Benutzererlebnis verbessern.
## FAQs
### Kann ich das Ausgabeverzeichnis für gerenderte HTML-Seiten anpassen?
Ja, Sie können einen beliebigen Verzeichnispfad angeben, in dem die gerenderten HTML-Seiten gespeichert werden sollen.
### Ist GroupDocs.Viewer für .NET mit verschiedenen Versionen des .NET Frameworks kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit verschiedenen Versionen des .NET Frameworks kompatibel, einschließlich .NET Core und .NET Framework.
### Hat die Deaktivierung der Textauswahl Auswirkungen auf andere Funktionen des PDF-Dokuments?
Nein, die Deaktivierung der Textauswahl verhindert lediglich, dass Benutzer Text aus dem Dokument auswählen und kopieren können. Andere Funktionalitäten bleiben erhalten.
### Kann ich die Textauswahl nach dem Rendern des Dokuments wieder aktivieren?
 Ja, Sie können die Textauswahl aktivieren, indem Sie einfach das festlegen`RenderTextAsImage` Eigentum zu`false` in den HTML-Ansichtsoptionen.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
 Ja, Sie können auf eine kostenlose Testversion von GroupDocs.Viewer für .NET zugreifen[Webseite](https://releases.groupdocs.com/).