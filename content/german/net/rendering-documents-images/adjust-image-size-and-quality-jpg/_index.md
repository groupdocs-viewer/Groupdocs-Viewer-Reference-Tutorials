---
"description": "Erfahren Sie, wie Sie Bildgröße und -qualität im JPEG-Format mit Groupdocs.Viewer für .NET optimieren. Verbessern Sie die Anzeige Ihrer Dokumente."
"linktitle": "Bildgröße und -qualität anpassen (JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Bildgröße und -qualität anpassen (JPG)"
"url": "/de/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
type: docs
---
# Bildgröße und -qualität anpassen (JPG)

## Einführung
Groupdocs.Viewer für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, Dokumentanzeigefunktionen nahtlos in ihre .NET-Anwendungen zu integrieren. Eine häufige Anforderung in Anwendungen zur Dokumentanzeige ist die Möglichkeit, Größe und Qualität von Bildern anzupassen, insbesondere bei JPEG-Bildern (JPG). In diesem Tutorial führen wir Sie durch den Prozess der Anpassung von Bildgröße und -qualität mit Groupdocs.Viewer für .NET.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Grundlegende Kenntnisse der Programmiersprache C#.
2. Visual Studio ist auf Ihrem System installiert.
3. Groupdocs.Viewer für .NET-Bibliothek installiert. Sie können es herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren. Diese Namespaces ermöglichen den Zugriff auf die Klassen und Methoden, die für die Arbeit mit Groupdocs.Viewer erforderlich sind.
## Schritt 1: Namespaces importieren
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den bereitgestellten Beispielcode zum besseren Verständnis in mehrere Schritte aufteilen.
## Schritt 2: Ausgabeverzeichnis und Seitendateipfadformat festlegen
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
In diesem Schritt geben wir das Ausgabeverzeichnis an, in dem die gerenderten Bilder gespeichert werden, und definieren das Format für den Dateipfad jedes Seitenbildes.
## Schritt 3: Viewer initialisieren und JPG-Ansichtsoptionen konfigurieren
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Hier initialisieren wir das Viewer-Objekt mit dem Pfad zum anzuzeigenden Dokument. Anschließend erstellen wir eine Instanz von JpgViewOptions und legen die gewünschte Breite und Höhe für die JPEG-Bilder fest.
## Schritt 4: Quelldokument rendern
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Abschließend drucken wir eine Meldung, die die erfolgreiche Wiedergabe des Quelldokuments und den Speicherort der Ausgabebilder angibt.

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie die Größe und Qualität von JPEG-Bildern mit Groupdocs.Viewer für .NET anpassen. Mit den oben beschriebenen Schritten können Sie diese Funktionalität problemlos in Ihre .NET-Anwendungen integrieren und Ihren Benutzern so ein optimiertes Bilderlebnis bieten.
## Häufig gestellte Fragen
### Kann ich auch die Bildqualität anpassen?
Ja, Sie können die Bildqualität anpassen, indem Sie die Eigenschaft „Qualität“ in den JpgViewOptions festlegen.
### Welche Dokumentformate werden von Groupdocs.Viewer für .NET unterstützt?
Groupdocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter DOCX, PDF, PPTX, XLSX und mehr.
### Ist Groupdocs.Viewer für .NET mit .NET Core kompatibel?
Ja, Groupdocs.Viewer für .NET ist mit .NET Core und dem herkömmlichen .NET Framework kompatibel.
### Kann ich das Benennungsformat der Ausgabedatei anpassen?
Ja, Sie können das Benennungsformat der Ausgabedatei anpassen, indem Sie die Variable pageFilePathFormat im Code ändern.
### Unterstützt Groupdocs.Viewer für .NET Dokumentanmerkungen?
Ja, Groupdocs.Viewer für .NET bietet umfassende Unterstützung für Dokumentanmerkungen, einschließlich Texthervorhebung, Unterstreichung und Kommentierung.