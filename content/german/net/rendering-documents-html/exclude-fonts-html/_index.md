---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET Schriftarten aus gerendertem HTML ausschließen. Folgen Sie dieser Schritt-für-Schritt-Anleitung für eine nahtlose Dokumentanzeige."
"linktitle": "Schriftarten aus gerendertem HTML ausschließen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Schriftarten aus gerendertem HTML ausschließen"
"url": "/de/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# Schriftarten aus gerendertem HTML ausschließen

## Einführung
GroupDocs.Viewer für .NET ist eine leistungsstarke Bibliothek zur Dokumentdarstellung, die es Entwicklern ermöglicht, über 50 Dokumentformate in ihren .NET-Anwendungen ohne externe Abhängigkeiten anzuzeigen. In diesem Tutorial konzentrieren wir uns auf eine spezielle Funktion von GroupDocs.Viewer: den Ausschluss von Schriftarten aus der gerenderten HTML-Ausgabe. 
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Grundlegende Kenntnisse der C#- und .NET-Entwicklung.
2. GroupDocs.Viewer für .NET installiert. Sie können es herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio oder eine andere IDE für die C#-Entwicklung.

## Namespaces importieren
Achten Sie darauf, in Ihrem C#-Code die erforderlichen Namespaces einzuschließen:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Schritt 1: Ausgabeverzeichnis definieren
Richten Sie das Verzeichnis ein, in dem die gerenderten HTML-Dateien gespeichert werden sollen.
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
Geben Sie das Format für die Dateipfade einzelner Seiten des gerenderten Dokuments an.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Viewer-Objekt initialisieren
Instanziieren Sie das Viewer-Objekt mit dem Dokument, das Sie rendern möchten.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Ihr Code kommt hier hin
}
```
## Schritt 4: HTML-Ansichtsoptionen festlegen
Definieren Sie die Optionen für die HTML-Wiedergabe, einschließlich des Formats eingebetteter Ressourcen und auszuschließender Schriftarten.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Schritt 5: Dokument rendern
Übergeben Sie die HTML-Ansichtsoptionen an das Viewer-Objekt, um das Dokument zu rendern.
```csharp
viewer.View(options);
```
## Schritt 6: Speicherort des gerenderten Dokuments ausgeben
Informieren Sie den Benutzer über den Speicherort der gerenderten HTML-Dateien.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie mit GroupDocs.Viewer für .NET Schriftarten aus der gerenderten HTML-Ausgabe ausschließen. Mit den oben beschriebenen Schritten können Sie den Rendering-Prozess an Ihre spezifischen Anforderungen anpassen und so eine optimale Anzeige von Dokumenten in Ihren Anwendungen gewährleisten.
## Häufig gestellte Fragen
### Kann ich mehrere Schriftarten aus dem gerenderten HTML ausschließen?
Ja, Sie können mehrere Schriftartnamen hinzufügen. `FontsToExclude` Liste in den HTML-Ansichtsoptionen.
### Ist GroupDocs.Viewer mit allen .NET-Frameworks kompatibel?
Ja, GroupDocs.Viewer unterstützt .NET Framework 4.6.1 und höher.
### Kann ich Dokumente von Remote-Speicherorten rendern?
Ja, GroupDocs.Viewer unterstützt das Rendern von Dokumenten aus dem lokalen Speicher sowie von Remote-Speicherorten und -Streams.
### Unterstützt GroupDocs.Viewer Responsive Design für HTML-Ausgabe?
Ja, Sie können Responsive Rendering aktivieren, indem Sie die HTML-Ansichtsoptionen entsprechend anpassen.
### Gibt es technischen Support für GroupDocs.Viewer?
Ja, Sie können Hilfe suchen und an Diskussionen teilnehmen auf der [GroupDocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9).