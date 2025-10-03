---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET mühelos CMX-Bilder in verschiedene Formate rendern. Optimieren Sie Ihr Dokumentenmanagement."
"linktitle": "CMX-Bilder rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CMX-Bilder rendern"
"url": "/de/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# CMX-Bilder rendern

## Einführung
Im Bereich der Dokumentenverwaltung und -bearbeitung ist die Darstellung von Bildern in verschiedenen Formaten eine zentrale Aufgabe. GroupDocs.Viewer für .NET vereinfacht diesen Prozess durch umfassende Funktionen zur Darstellung von CMX-Bildern in verschiedenen Formaten wie HTML, JPG, PNG und PDF. Dieses Tutorial führt Sie Schritt für Schritt durch die Darstellung von CMX-Bildern mit GroupDocs.Viewer für .NET.

![Rendern Sie CMX-Bilder mit GroupDocs.Viewer für .NET](/viewer/image-rendering/render-cmx-images.png)

## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. GroupDocs.Viewer für .NET-Bibliothek: Laden Sie die GroupDocs.Viewer für .NET-Bibliothek herunter und installieren Sie sie von [Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Richten Sie eine funktionierende Entwicklungsumgebung mit .NET Framework ein.
3. CMX-Bilddatei: Besorgen Sie sich eine CMX-Bilddatei, die Sie rendern möchten.

## Namespaces importieren
Bevor Sie fortfahren, stellen Sie sicher, dass Sie die erforderlichen Namespaces importieren, um auf die GroupDocs.Viewer-Funktionen in Ihrer .NET-Anwendung zuzugreifen:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Rendern in HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Ausgabeverzeichnis definieren: Legen Sie das Verzeichnis fest, in dem Sie die gerenderten HTML-Dateien speichern möchten.
- Dateipfadformat angeben: Definieren Sie das Format für die HTML-Ausgabedateien.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- HTML-Rendering-Optionen: Konfigurieren Sie HTML-Rendering-Optionen, beispielsweise das Einbetten von Ressourcen.
- CMX in HTML rendern: Rufen Sie die View-Methode des Viewer-Objekts auf, um das CMX-Bild in HTML zu rendern.
## Rendern in JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Ausgabeverzeichnis definieren: Legen Sie das Verzeichnis zum Speichern der gerenderten JPG-Dateien fest.
- Dateipfadformat angeben: Definieren Sie das Format für die JPG-Ausgabedateien.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- JPG-Rendering-Optionen: Konfigurieren Sie die JPG-Rendering-Optionen.
- CMX in JPG rendern: Rufen Sie die View-Methode des Viewer-Objekts auf, um das CMX-Bild in JPG zu rendern.
## Rendern in PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Ausgabeverzeichnis definieren: Legen Sie das Verzeichnis zum Speichern der gerenderten PNG-Dateien fest.
- Dateipfadformat angeben: Definieren Sie das Format für die PNG-Ausgabedateien.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- PNG-Rendering-Optionen: Konfigurieren Sie die PNG-Rendering-Optionen.
- CMX in PNG rendern: Rufen Sie die View-Methode des Viewer-Objekts auf, um das CMX-Bild in PNG zu rendern.
## Rendern in PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Ausgabeverzeichnis definieren: Legen Sie das Verzeichnis zum Speichern der gerenderten PDF-Datei fest.
- Dateipfadformat angeben: Definieren Sie das Format für die PDF-Ausgabedatei.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- PDF-Rendering-Optionen: Konfigurieren Sie PDF-Rendering-Optionen.
- CMX in PDF rendern: Rufen Sie die View-Methode des Viewer-Objekts auf, um das CMX-Bild in PDF zu rendern.

## Abschluss
Zusammenfassend lässt sich sagen, dass GroupDocs.Viewer für .NET eine robuste Lösung für die nahtlose Darstellung von CMX-Bildern in verschiedenen Formaten bietet. Mit den in diesem Tutorial beschriebenen Schritten können Sie CMX-Bildrendering-Funktionen mühelos in Ihre .NET-Anwendungen integrieren und so die Effizienz Ihres Dokumentenmanagements steigern.
## Häufig gestellte Fragen
### Kann ich bestimmte Seiten eines CMX-Bildes rendern?
Ja, Sie können bestimmte Seiten rendern, indem Sie die Seitenzahl in den Renderoptionen angeben.
### Ist GroupDocs.Viewer für .NET mit allen .NET-Frameworks kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit mehreren .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Framework.
### Unterstützt GroupDocs.Viewer das Rendern verschlüsselter CMX-Bilder?
Ja, GroupDocs.Viewer unterstützt das Rendern verschlüsselter CMX-Bilder mit entsprechenden Entschlüsselungsschlüsseln.
### Kann ich die Rendering-Optionen für verschiedene Ausgabeformate anpassen?
Absolut, GroupDocs.Viewer bietet umfangreiche Optionen zum Anpassen der Rendering-Parameter basierend auf Ihren Anforderungen.
### Gibt es ein Community-Forum für GroupDocs.Viewer-Support?
Ja, Sie können Hilfe suchen und sich mit der GroupDocs.Viewer-Community im Support-Forum austauschen. [Hier](https://forum.groupdocs.com/c/viewer/9).