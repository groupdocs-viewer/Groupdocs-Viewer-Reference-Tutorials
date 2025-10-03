---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET PDFs in Originalseitengröße rendern. Folgen Sie unserer Schritt-für-Schritt-Anleitung und integrieren Sie diese Funktionalität nahtlos."
"linktitle": "PDF mit Originalseitengröße rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF mit Originalseitengröße rendern"
"url": "/de/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
type: docs
---
# PDF mit Originalseitengröße rendern

## Einführung
Im Bereich der .NET-Entwicklung zeichnet sich GroupDocs.Viewer als leistungsstarkes Tool zum Rendern verschiedener Dokumentformate, einschließlich PDFs, aus. Eine häufige Anforderung bei der Dokumentenverarbeitung ist das Rendern von PDFs unter Beibehaltung ihrer ursprünglichen Seitengröße. Um diese Aufgabe reibungslos zu bewältigen, ist ein umfassendes Verständnis von GroupDocs.Viewer für .NET und seinen Funktionen erforderlich.

![Rendern Sie PDF mit der Originalseitengröße mit GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Voraussetzungen
Bevor Sie mit dem Rendern von PDFs mit Originalseitengrößen mithilfe von GroupDocs.Viewer für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installieren Sie GroupDocs.Viewer für .NET
Laden Sie zunächst die Bibliothek GroupDocs.Viewer von der Website herunter. Sie erhalten die Bibliothek über die bereitgestellte [Download-Link](https://releases.groupdocs.com/viewer/net/). Befolgen Sie die Installationsanweisungen in der Dokumentation, um es effektiv in Ihr .NET-Projekt zu integrieren.
### 2. Entwicklungsumgebung einrichten
Stellen Sie sicher, dass Sie eine Entwicklungsumgebung für die .NET-Entwicklung eingerichtet haben. Dazu gehört die Installation einer kompatiblen IDE wie Visual Studio und grundlegende Kenntnisse der C#-Programmierung.
### 3. Erhalten Sie ein PDF-Dokument
Sie benötigen ein Beispiel-PDF-Dokument zum Rendern mit GroupDocs.Viewer. Sie können jedes beliebige PDF-Dokument zu Testzwecken verwenden. Falls Sie noch keins haben, können Sie ein Beispiel-PDF aus verschiedenen Online-Quellen herunterladen.

## Namespaces importieren
Bevor Sie mit dem Rendern von PDFs fortfahren, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Dieser Schritt ermöglicht Ihnen den Zugriff auf die benötigten Klassen und Methoden aus der GroupDocs.Viewer-Bibliothek.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nachdem Sie nun die Voraussetzungen geschaffen und die erforderlichen Namespaces importiert haben, unterteilen wir den Prozess des Renderns von PDFs mit Originalseitengrößen mit GroupDocs.Viewer für .NET in einfache Schritte:
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Stellen Sie sicher, dass Sie das Verzeichnis angeben, in dem die gerenderten Seiten gespeichert werden sollen. Ersetzen Sie `"Your Document Directory"` durch den Pfad Ihres gewünschten Verzeichnisses.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Richten Sie das Format für die Benennung der gerenderten Seitendateien ein. In diesem Beispiel werden die Seiten als PNG-Bilder mit Dateinamen im Format `"page_1.png"`, `"page_2.png"`, und so weiter.
## Schritt 3: PDF mit Originalseitengröße rendern
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Instanziieren Sie ein `Viewer` Objekt mit dem Pfad zu Ihrer PDF-Datei. Erstellen Sie dann `PngViewOptions` mit dem angegebenen Seitendateipfadformat. Setzen `RenderOriginalPageSize` Eigentum zu `true` um die ursprünglichen Seitengrößen beim Rendern beizubehalten.
## Schritt 4: Anzeige des gerenderten Dokumentspeicherorts
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Drucken Sie eine Meldung, die das erfolgreiche Rendern bestätigt, und geben Sie das Verzeichnis an, in dem die gerenderten Seiten gespeichert sind.

## Abschluss
Das Rendern von PDFs in Originalseitengröße mit GroupDocs.Viewer für .NET ist ein unkomplizierter Vorgang, wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen. Durch Importieren der erforderlichen Namespaces und Befolgen der Schritt-für-Schritt-Anleitung können Sie diese Funktionalität nahtlos in Ihre .NET-Anwendungen integrieren.
## Häufig gestellte Fragen
### Kann GroupDocs.Viewer neben PDF auch andere Dokumentformate rendern?
Ja, GroupDocs.Viewer unterstützt die Darstellung verschiedener Dokumentformate, darunter Word, Excel, PowerPoint und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer ist sowohl mit .NET Framework- als auch mit .NET Core-Umgebungen kompatibel.
### Kann ich das Ausgabeformat gerenderter Seiten anpassen?
Ja, Sie können das Ausgabeformat anpassen, indem Sie die von GroupDocs.Viewer bereitgestellten Optionen anpassen, z. B. durch Festlegen verschiedener Bildformate oder Festlegen benutzerdefinierter Rendering-Optionen.
### Bietet GroupDocs.Viewer Unterstützung für die cloudbasierte Dokumentwiedergabe?
Ja, GroupDocs.Viewer bietet APIs für die cloudbasierte Dokumentwiedergabe, sodass Sie Dokumente direkt von Cloud-Speicheranbietern rendern können.
### Gibt es eine kostenlose Testversion für GroupDocs.Viewer?
Ja, Sie können GroupDocs.Viewer mit einer kostenlosen Testversion erkunden, indem Sie die bereitgestellte [Link](https://releases.groupdocs.com/).