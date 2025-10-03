---
"description": "Entdecken Sie die nahtlose Darstellung von XML SpreadSheetML-Dateien in verschiedenen Formaten mit GroupDocs.Viewer für .NET. Mühelose Integration in Ihre Anwendungen."
"linktitle": "Rendern von XML SpreadSheetML"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendern von XML SpreadSheetML"
"url": "/de/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
type: docs
---
# Rendern von XML SpreadSheetML

## Einführung
Willkommen in der Welt von GroupDocs.Viewer für .NET! In diesem Tutorial zeigen wir Ihnen, wie Sie XML SpreadSheetML-Dateien mithilfe von GroupDocs.Viewer, einer leistungsstarken .NET-Bibliothek, mühelos rendern. Egal, ob Sie bereits erfahrener Entwickler sind oder gerade erst anfangen – diese Schritt-für-Schritt-Anleitung hilft Ihnen, XML SpreadSheetML-Rendering mühelos in Ihre Anwendungen zu integrieren.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Eine Entwicklungsumgebung mit .NET-Unterstützung.
- GroupDocs.Viewer für .NET-Bibliothek installiert. Sie können es herunterladen [Hier](https://releases.groupdocs.com/viewer/net/).
- Grundlegende Kenntnisse der C#-Programmierung.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt. Dadurch stellen Sie sicher, dass Sie Zugriff auf die Funktionen von GroupDocs.Viewer haben.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein
Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem die Ausgabe gespeichert wird.
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Ausgabedateipfade angeben
Richten Sie die vollständigen Pfade für die HTML-, JPG-, PNG- und PDF-Ausgabedateien ein.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Schritt 3: Ladeoptionen festlegen
Geben Sie den Dateityp explizit als Excel 2003 XML SpreadSheetML an, um ihn genau darzustellen.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Schritt 4: In mehrseitiges HTML rendern
Nutzen Sie die HTML-Ansichtsoptionen, um die XML-SpreadSheetML-Datei in ein mehrseitiges HTML-Dokument umzuwandeln.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Schritt 5: In JPG rendern
Rendern Sie die XML SpreadSheetML-Datei mit den angegebenen Optionen in ein JPG-Bild.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Schritt 6: In PNG rendern
Rendern Sie die Datei auf ähnliche Weise mit den angegebenen Optionen in ein PNG-Bild.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Schritt 7: In PDF rendern
Rendern Sie abschließend die XML-SpreadSheetML-Datei mit den angegebenen Optionen in ein PDF-Dokument.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie XML SpreadSheetML-Dateien mit GroupDocs.Viewer für .NET rendern. Erweitern Sie Ihre Dokumentanzeigefunktionen, indem Sie die weiteren Funktionen und Optionen dieser vielseitigen Bibliothek erkunden.
## FAQs
### Ist GroupDocs.Viewer mit anderen Dateiformaten kompatibel?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Word, Excel und mehr.
### Kann ich das Erscheinungsbild der gerenderten Dokumente anpassen?
Absolut! GroupDocs.Viewer bietet verschiedene Anpassungsoptionen, mit denen Sie die Ausgabe an Ihre spezifischen Bedürfnisse anpassen können.
### Wo finde ich zusätzliche Unterstützung und Ressourcen?
Besuchen Sie die [GroupDocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9) für Community-Unterstützung und erkunden Sie die [Dokumentation](https://tutorials.groupdocs.com/viewer/net/) für detaillierte Informationen.
### Gibt es eine kostenlose Testversion?
Ja, Sie können auf die kostenlose Testversion zugreifen [Hier](https://releases.groupdocs.com/).
### Wie erhalte ich eine vorläufige Lizenz?
Sie können eine vorübergehende Lizenz erhalten [Hier](https://purchase.groupdocs.com/temporary-license/).