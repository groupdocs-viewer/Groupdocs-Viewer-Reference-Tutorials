---
title: Passen Sie die Bildqualität in PDF an
linktitle: Passen Sie die Bildqualität in PDF an
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie die Bildqualität in PDF-Dokumenten mit GroupDocs.Viewer für .NET anpassen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 10
url: /de/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, Funktionen zur Dokumentwiedergabe mühelos in ihre .NET-Anwendungen zu integrieren. Eine der Hauptfunktionen dieser Bibliothek ist die Möglichkeit, die Bildqualität beim Rendern von PDF-Dokumenten anzupassen. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Anpassung der Bildqualität mit GroupDocs.Viewer für .NET.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Grundkenntnisse der C#-Programmierung.
2. Visual Studio ist auf Ihrem System installiert.
3. GroupDocs.Viewer für .NET-Bibliothek heruntergeladen und installiert. Sie können es herunterladen unter[Hier](https://releases.groupdocs.com/viewer/net/).

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit GroupDocs.Viewer für .NET zu arbeiten:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"` mit dem Pfad, in dem Sie die gerenderten HTML-Seiten speichern möchten.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Diese Zeile definiert das Format für den Dateipfad jeder gerenderten HTML-Seite.`{0}` ist ein Platzhalter für die Seitenzahl.
## Schritt 3: Passen Sie die Bildqualität an
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 Ersetzen`"Your PDF File Path"` mit dem Pfad zu Ihrem PDF-Dokument.
## Schritt 4: Ausgabepfad anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
In dieser Zeile wird der Pfad angezeigt, in dem die gerenderten HTML-Seiten gespeichert werden.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Bildqualität beim Rendern von PDF-Dokumenten mit GroupDocs.Viewer für .NET anpasst. Indem Sie die oben beschriebenen einfachen Schritte befolgen, können Sie die Bildqualität ganz einfach an Ihre Anforderungen anpassen.
## FAQs
### Kann ich die Bildqualität für andere Dokumentformate außer PDF anpassen?
Ja, GroupDocs.Viewer für .NET unterstützt verschiedene Dokumentformate und Sie können die Bildqualität für die meisten davon anpassen.
### Welche Bildqualitätsoptionen stehen zur Verfügung?
GroupDocs.Viewer für .NET bietet Optionen für niedrige, mittlere und hohe Bildqualität.
### Gibt es eine Möglichkeit, eine Vorschau des Dokuments anzuzeigen, bevor es mit angepasster Bildqualität gerendert wird?
Ja, Sie können GroupDocs.Viewer für .NET verwenden, um Dokumentvorschauen mit unterschiedlichen Bildqualitätseinstellungen zu erstellen.
### Benötigt GroupDocs.Viewer für .NET eine Lizenz für die kommerzielle Nutzung?
 Ja, für die kommerzielle Nutzung benötigen Sie eine Lizenz. Sie können eine Lizenz erwerben bei[Hier](https://purchase.groupdocs.com/buy).
### Wo erhalte ich Unterstützung für GroupDocs.Viewer für .NET?
 Unterstützung erhalten Sie im GroupDocs.Viewer-Forum[Hier](https://forum.groupdocs.com/c/viewer/9).