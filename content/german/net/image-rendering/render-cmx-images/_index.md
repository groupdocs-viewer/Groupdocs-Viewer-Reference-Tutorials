---
title: CMX-Bilder rendern
linktitle: CMX-Bilder rendern
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie CMX-Bilder mit GroupDocs.Viewer für .NET mühelos in verschiedene Formate rendern. Verbessern Sie Ihr Dokumentenmanagement.
type: docs
weight: 13
url: /de/net/image-rendering/render-cmx-images/
---
## Einführung
Im Bereich der Dokumentenverwaltung und -bearbeitung ist das Rendern von Bildern aus verschiedenen Formaten eine zentrale Aufgabe. GroupDocs.Viewer für .NET vereinfacht diesen Prozess, indem es umfassende Funktionen zum Rendern von CMX-Bildern in verschiedene Formate wie HTML, JPG, PNG und PDF bereitstellt. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess des Renderns von CMX-Bildern mit GroupDocs.Viewer für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  GroupDocs.Viewer für .NET-Bibliothek: Laden Sie die GroupDocs.Viewer für .NET-Bibliothek von herunter und installieren Sie sie[Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Richten Sie eine funktionierende Entwicklungsumgebung mit dem .NET Framework ein.
3. CMX-Bilddatei: Besorgen Sie sich eine CMX-Bilddatei, die Sie rendern möchten.

## Namensräume importieren
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
- Dateipfadformat angeben: Definieren Sie das Format für die ausgegebenen HTML-Dateien.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- HTML-Rendering-Optionen: Konfigurieren Sie HTML-Rendering-Optionen, z. B. das Einbetten von Ressourcen.
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
- Dateipfadformat angeben: Definieren Sie das Format für die ausgegebenen JPG-Dateien.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- JPG-Rendering-Optionen: Konfigurieren Sie JPG-Rendering-Optionen.
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
- Dateipfadformat angeben: Definieren Sie das Format für die ausgegebenen PNG-Dateien.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- PNG-Rendering-Optionen: Konfigurieren Sie PNG-Rendering-Optionen.
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
- Dateipfadformat angeben: Definieren Sie das Format für die Ausgabe-PDF-Datei.
- Viewer-Objekt instanziieren: Erstellen Sie eine Instanz der Viewer-Klasse mit der CMX-Bilddatei.
- PDF-Rendering-Optionen: Konfigurieren Sie PDF-Rendering-Optionen.
- CMX in PDF rendern: Rufen Sie die View-Methode des Viewer-Objekts auf, um das CMX-Bild in PDF zu rendern.

## Abschluss
Zusammenfassend bietet GroupDocs.Viewer für .NET eine robuste Lösung zum nahtlosen Rendern von CMX-Bildern in verschiedene Formate. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie CMX-Bildwiedergabefunktionen mühelos in Ihre .NET-Anwendungen integrieren und so die Effizienz der Dokumentenverwaltung steigern.
## FAQs
### Kann ich bestimmte Seiten eines CMX-Bildes rendern?
Ja, Sie können bestimmte Seiten rendern, indem Sie die Seitenzahl in den Rendering-Optionen angeben.
### Ist GroupDocs.Viewer für .NET mit allen .NET-Frameworks kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit mehreren .NET Frameworks kompatibel, einschließlich .NET Core und .NET Framework.
### Unterstützt GroupDocs.Viewer das Rendern verschlüsselter CMX-Bilder?
Ja, GroupDocs.Viewer unterstützt das Rendern verschlüsselter CMX-Bilder mit entsprechenden Entschlüsselungsschlüsseln.
### Kann ich die Rendering-Optionen für verschiedene Ausgabeformate anpassen?
Auf jeden Fall bietet GroupDocs.Viewer umfangreiche Optionen zum Anpassen der Rendering-Parameter entsprechend Ihren Anforderungen.
### Gibt es ein Community-Forum für GroupDocs.Viewer-Unterstützung?
 Ja, Sie können im Support-Forum Hilfe suchen und mit der GroupDocs.Viewer-Community in Kontakt treten[Hier](https://forum.groupdocs.com/c/viewer/9).