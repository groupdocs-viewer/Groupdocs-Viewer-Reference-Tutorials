---
title: Passen Sie die Ausgabebildgröße für CAD-Zeichnungen an
linktitle: Passen Sie die Ausgabebildgröße für CAD-Zeichnungen an
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie die Ausgabebildgröße für CAD-Zeichnungen mit GroupDocs.Viewer für .NET anpassen. Verbessern Sie mühelos Sichtbarkeit und Benutzerfreundlichkeit.
type: docs
weight: 15
url: /de/net/rendering-cad-drawings/adjust-output-image-size-cad/
---
## Einführung
CAD-Zeichnungen erfordern häufig spezifische Anpassungen für eine optimale Anzeige und Präsentation. GroupDocs.Viewer für .NET bietet ein leistungsstarkes Toolset zum Verwalten und Anpassen der CAD-Zeichnungsausgabe. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Anpassung der Ausgabebildgröße für CAD-Zeichnungen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von[Hier](https://releases.groupdocs.com/viewer/net/).
2. Dokumentenverzeichnis: Bereiten Sie das Verzeichnis vor, in dem sich Ihr Dokument befindet.
3. Grundverständnis: Machen Sie sich mit den Grundkonzepten der .NET-Programmierung vertraut.

## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces importieren, um auf die GroupDocs.Viewer-Funktionen zugreifen zu können:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis festlegen
Definieren Sie das Verzeichnis, in dem Sie die Ausgabebilder von CAD-Zeichnungen speichern möchten:
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Definieren Sie das Format des Seitendateipfads
Legen Sie das Format für Auslagerungsdateipfade fest. Dieses Format wird verwendet, um einzelne Seiten zu benennen und als HTML-Dateien zu speichern:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Passen Sie die Bildgröße an
Passen Sie in einem Verwendungsblock für das Viewer-Objekt die Bildgröße für CAD-Zeichnungen an, indem Sie die entsprechenden Optionen festlegen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Schritt 4: Ausgabeverzeichnis anzeigen
Zeigen Sie nach dem Rendern des Dokuments eine Meldung über das erfolgreiche Rendern an und geben Sie den Speicherort des Ausgabeverzeichnisses an:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Die Anpassung der Ausgabebildgröße für CAD-Zeichnungen ist entscheidend für die Verbesserung ihrer Sichtbarkeit und Benutzerfreundlichkeit. Mit GroupDocs.Viewer für .NET wird dieser Prozess rationalisiert und effizient, sodass Sie die Ausgabe entsprechend Ihren spezifischen Anforderungen anpassen können.
## FAQs
### Kann ich die Ausgabebildgröße für andere Dokumenttypen außer CAD-Zeichnungen anpassen?
Ja, GroupDocs.Viewer für .NET unterstützt verschiedene Dokumenttypen und Sie können die Ausgabebildgröße für die meisten Dokumentformate anpassen.
### Ist GroupDocs.Viewer für .NET mit verschiedenen Versionen des .NET-Frameworks kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit mehreren Versionen des .NET-Frameworks kompatibel und gewährleistet so Flexibilität und Benutzerfreundlichkeit in verschiedenen Umgebungen.
### Gibt es Lizenzoptionen für GroupDocs.Viewer für .NET?
Ja, Sie können je nach Bedarf verschiedene Lizenzierungsoptionen erkunden, darunter temporäre Lizenzen und kommerzielle Lizenzen.
### Kann ich das Ausgabeformat gerenderter Dokumente anpassen?
Auf jeden Fall bietet GroupDocs.Viewer für .NET verschiedene Anpassungsoptionen, mit denen Sie das Ausgabeformat nach Ihren Wünschen anpassen können.
### Wo finde ich zusätzliche Unterstützung oder Hilfe zu GroupDocs.Viewer für .NET?
 Sie können das GroupDocs.Viewer-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9) um Unterstützung zu erhalten, Fragen zu stellen und mit der Community in Kontakt zu treten.