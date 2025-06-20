---
"description": "Erfahren Sie, wie Sie die Ausgabebildgröße für CAD-Zeichnungen mit GroupDocs.Viewer für .NET anpassen. Verbessern Sie mühelos Sichtbarkeit und Benutzerfreundlichkeit."
"linktitle": "Passen Sie die Ausgabebildgröße für CAD-Zeichnungen an"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Passen Sie die Ausgabebildgröße für CAD-Zeichnungen an"
"url": "/de/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Passen Sie die Ausgabebildgröße für CAD-Zeichnungen an

## Einführung
CAD-Zeichnungen erfordern oft spezifische Anpassungen für eine optimale Anzeige und Präsentation. GroupDocs.Viewer für .NET bietet leistungsstarke Tools zur Verwaltung und Anpassung der CAD-Zeichnungsausgabe. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Anpassung der Ausgabebildgröße für CAD-Zeichnungen.
## Voraussetzungen
Stellen Sie vor dem Beginn sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von [Hier](https://releases.groupdocs.com/viewer/net/).
2. Dokumentverzeichnis: Bereiten Sie das Verzeichnis vor, in dem sich Ihr Dokument befindet.
3. Grundlegendes Verständnis: Machen Sie sich mit den grundlegenden Konzepten der .NET-Programmierung vertraut.

## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces importieren, um auf die Funktionen von GroupDocs.Viewer zuzugreifen:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis festlegen
Definieren Sie das Verzeichnis, in dem Sie die Ausgabebilder der CAD-Zeichnungen speichern möchten:
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
Legen Sie das Format für Seitendateipfade fest. Dieses Format wird verwendet, um einzelne Seiten zu benennen und als HTML-Dateien zu speichern:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Bildgröße anpassen
Passen Sie in einem Using-Block für das Viewer-Objekt die Bildgröße für CAD-Zeichnungen an, indem Sie entsprechende Optionen festlegen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Schritt 4: Ausgabeverzeichnis anzeigen
Zeigen Sie nach dem Rendern des Dokuments eine Meldung an, die das erfolgreiche Rendern bestätigt, und geben Sie den Speicherort des Ausgabeverzeichnisses an:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Die Anpassung der Ausgabebildgröße für CAD-Zeichnungen ist entscheidend für deren Sichtbarkeit und Benutzerfreundlichkeit. Mit GroupDocs.Viewer für .NET wird dieser Prozess optimiert und effizienter, sodass Sie die Ausgabe an Ihre spezifischen Anforderungen anpassen können.
## Häufig gestellte Fragen
### Kann ich die Ausgabebildgröße für andere Dokumenttypen als CAD-Zeichnungen anpassen?
Ja, GroupDocs.Viewer für .NET unterstützt verschiedene Dokumenttypen und Sie können die Ausgabebildgröße für die meisten Dokumentformate anpassen.
### Ist GroupDocs.Viewer für .NET mit verschiedenen Versionen des .NET-Frameworks kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit mehreren Versionen des .NET-Frameworks kompatibel und gewährleistet so Flexibilität und Benutzerfreundlichkeit in unterschiedlichen Umgebungen.
### Gibt es Lizenzierungsoptionen für GroupDocs.Viewer für .NET?
Ja, Sie können verschiedene Lizenzierungsoptionen erkunden, darunter temporäre Lizenzen und kommerzielle Lizenzen, die Ihren Anforderungen entsprechen.
### Kann ich das Ausgabeformat gerenderter Dokumente anpassen?
Auf jeden Fall, GroupDocs.Viewer für .NET bietet verschiedene Anpassungsoptionen, mit denen Sie das Ausgabeformat Ihren Anforderungen entsprechend anpassen können.
### Wo finde ich zusätzlichen Support oder Hilfe zu GroupDocs.Viewer für .NET?
Sie können das GroupDocs.Viewer-Forum besuchen [Hier](https://forum.groupdocs.com/c/viewer/9) um Unterstützung zu erhalten, Fragen zu stellen und sich mit der Community auszutauschen.