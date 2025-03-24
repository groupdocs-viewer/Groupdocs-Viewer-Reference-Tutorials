---
title: Bildgröße und -qualität anpassen (JPG)
linktitle: Bildgröße und -qualität anpassen (JPG)
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie Bildgröße und -qualität im JPEG-Format mit Groupdocs.Viewer für .NET optimieren. Verbessern Sie Ihr Erlebnis beim Anzeigen von Dokumenten.
weight: 11
url: /de/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Einführung
Groupdocs.Viewer für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, Funktionen zur Dokumentenanzeige nahtlos in ihre .NET-Anwendungen zu integrieren. Eine häufige Anforderung bei Dokumentenanzeigeanwendungen ist die Möglichkeit, die Größe und Qualität von Bildern anzupassen, insbesondere beim Umgang mit JPEG-Bildern (JPG). In diesem Tutorial führen wir Sie durch den Prozess der Anpassung der Bildgröße und -qualität mit Groupdocs.Viewer für .NET.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Grundlegendes Verständnis der Programmiersprache C#.
2. Visual Studio ist auf Ihrem System installiert.
3.  Groupdocs.Viewer für .NET-Bibliothek installiert. Sie können es herunterladen unter[Hier](https://releases.groupdocs.com/viewer/net/).

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren. Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die für die Arbeit mit Groupdocs.Viewer erforderlich sind.
## Schritt 1: Namespaces importieren
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun zum besseren Verständnis den bereitgestellten Beispielcode in mehrere Schritte aufteilen.
## Schritt 2: Legen Sie das Ausgabeverzeichnis und das Seitendateipfadformat fest
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
In diesem Schritt geben wir das Ausgabeverzeichnis an, in dem die gerenderten Bilder gespeichert werden, und definieren das Format für den Dateipfad jedes Seitenbilds.
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
Abschließend drucken wir eine Meldung aus, die das erfolgreiche Rendern des Quelldokuments und den Speicherort der Ausgabebilder angibt.

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie die Größe und Qualität von JPEG-Bildern mit Groupdocs.Viewer für .NET anpassen. Wenn Sie die oben beschriebenen Schritte ausführen, können Sie diese Funktionalität problemlos in Ihre .NET-Anwendungen integrieren und Benutzern ein optimiertes Bildbetrachtungserlebnis bieten.
## FAQs
### Kann ich auch die Bildqualität anpassen?
Ja, Sie können die Bildqualität anpassen, indem Sie die Quality-Eigenschaft in den JpgViewOptions festlegen.
### Welche Dokumentformate werden von Groupdocs.Viewer für .NET unterstützt?
Groupdocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter DOCX, PDF, PPTX, XLSX und mehr.
### Ist Groupdocs.Viewer für .NET mit .NET Core kompatibel?
Ja, Groupdocs.Viewer für .NET ist mit .NET Core und dem herkömmlichen .NET Framework kompatibel.
### Kann ich das Benennungsformat der Ausgabedatei anpassen?
Ja, Sie können das Benennungsformat der Ausgabedatei anpassen, indem Sie die Variable pageFilePathFormat im Code ändern.
### Unterstützt Groupdocs.Viewer für .NET Dokumentanmerkungen?
Ja, Groupdocs.Viewer für .NET bietet umfassende Unterstützung für Dokumentanmerkungen, einschließlich Texthervorhebung, Unterstreichung und Kommentierung.