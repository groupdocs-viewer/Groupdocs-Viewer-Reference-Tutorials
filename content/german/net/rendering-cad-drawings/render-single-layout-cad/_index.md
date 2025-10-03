---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET einzelne Layouts in CAD-Zeichnungen rendern. Einfache Schritte für die nahtlose Integration in Ihre .NET-Anwendungen."
"linktitle": "Rendern einzelner Layouts in CAD-Zeichnungen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendern einzelner Layouts in CAD-Zeichnungen"
"url": "/de/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# Rendern einzelner Layouts in CAD-Zeichnungen

## Einführung
In der .NET-Entwicklung ist die Bearbeitung und Anzeige von CAD-Zeichnungen eine häufige Anforderung. GroupDocs.Viewer für .NET vereinfacht diese Aufgabe durch eine umfassende Lösung zum Rendern von CAD-Zeichnungen in .NET-Anwendungen. In diesem Tutorial befassen wir uns mit der Darstellung eines einzelnen Layouts in CAD-Zeichnungen mithilfe von GroupDocs.Viewer für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundlegende Kenntnisse der Programmiersprache C# und des .NET-Frameworks.
- Visual Studio ist auf Ihrem System installiert.
- GroupDocs.Viewer für .NET-Bibliothek heruntergeladen und Tutorials in Ihrem Projekt. Sie können es herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
- Vertrautheit mit CAD-Dateiformaten und deren Strukturen.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihren C#-Code, um auf die GroupDocs.Viewer-Funktionen zuzugreifen.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Schritt 1: Ausgabeverzeichnis definieren
Geben Sie das Verzeichnis an, in dem die gerenderte Ausgabe gespeichert werden soll.
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
Definieren Sie das Format für den Dateipfad jeder gerenderten Seite.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Viewer-Objekt instanziieren
Erstellen Sie eine Instanz der von GroupDocs.Viewer bereitgestellten Viewer-Klasse.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Schritt 4: HTML-Ansichtsoptionen konfigurieren
Konfigurieren Sie Optionen zum Rendern der HTML-Ausgabe mit eingebetteten Ressourcen.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Schritt 5: CAD-Layoutnamen angeben
Geben Sie den Namen des CAD-Layouts an, das Sie rendern möchten.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Schritt 6: CAD-Zeichnung rendern
Rufen Sie die View-Methode des Viewer-Objekts mit den angegebenen Optionen auf.
```csharp
viewer.View(options);
```
## Schritt 7: Erfolgsmeldung anzeigen
Informieren Sie den Benutzer über die erfolgreiche Wiedergabe des Quelldokuments.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Das Rendern von CAD-Zeichnungen, insbesondere von Layouts, kann eine anspruchsvolle Aufgabe sein. Mit GroupDocs.Viewer für .NET wird der Prozess jedoch nahtlos und effizient. Mit den in diesem Tutorial beschriebenen Schritten können Sie mühelos ein einzelnes Layout in CAD-Zeichnungen in Ihren .NET-Anwendungen rendern.
## Häufig gestellte Fragen
### Kann ich mit GroupDocs.Viewer für .NET mehrere Layouts gleichzeitig rendern?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern mehrerer Layouts aus CAD-Zeichnungen.
### Ist GroupDocs.Viewer mit verschiedenen CAD-Dateiformaten kompatibel?
Absolut, GroupDocs.Viewer unterstützt eine breite Palette von CAD-Dateiformaten, darunter DWG, DXF, DGN und mehr.
### Kann ich die Rendering-Optionen für CAD-Zeichnungen anpassen?
Ja, GroupDocs.Viewer bietet umfangreiche Optionen zum Anpassen der Rendering-Einstellungen entsprechend Ihren Anforderungen.
### Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können die Funktionen von GroupDocs.Viewer mit einer kostenlosen Testversion erkunden. [Hier](https://releases.groupdocs.com/).
### Wo erhalte ich Support für GroupDocs.Viewer für .NET?
Bei Fragen oder Hilfe können Sie das GroupDocs.Viewer-Forum besuchen [Hier](https://forum.groupdocs.com/c/viewer/9).