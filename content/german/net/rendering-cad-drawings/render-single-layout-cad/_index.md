---
title: Rendern Sie ein einzelnes Layout in CAD-Zeichnungen
linktitle: Rendern Sie ein einzelnes Layout in CAD-Zeichnungen
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET ein einzelnes Layout in CAD-Zeichnungen rendern. Einfache Schritte für eine nahtlose Integration in Ihre .NET-Anwendungen.
type: docs
weight: 14
url: /de/net/rendering-cad-drawings/render-single-layout-cad/
---
## Einführung
Im Bereich der .NET-Entwicklung ist die Handhabung und Anzeige von CAD-Zeichnungen eine häufige Anforderung. GroupDocs.Viewer für .NET vereinfacht diese Aufgabe, indem es eine umfassende Lösung zum Rendern von CAD-Zeichnungen in .NET-Anwendungen bereitstellt. In diesem Tutorial befassen wir uns mit der Darstellung eines einzelnen Layouts in CAD-Zeichnungen mithilfe von GroupDocs.Viewer für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundlegende Kenntnisse der Programmiersprache C# und des .NET Frameworks.
- Visual Studio ist auf Ihrem System installiert.
-  GroupDocs.Viewer für .NET-Bibliothek heruntergeladen und in Ihrem Projekt referenziert. Sie können es herunterladen unter[Hier](https://releases.groupdocs.com/viewer/net/).
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
## Schritt 2: Definieren Sie das Format des Seitendateipfads
Definieren Sie das Format für den Dateipfad jeder gerenderten Seite.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Viewer-Objekt instanziieren
Erstellen Sie eine Instanz der Viewer-Klasse, die von GroupDocs.Viewer bereitgestellt wird.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Schritt 4: Konfigurieren Sie die HTML-Ansichtsoptionen
Konfigurieren Sie Optionen zum Rendern der HTML-Ausgabe mit eingebetteten Ressourcen.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Schritt 5: Geben Sie den Namen des CAD-Layouts an
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
Informieren Sie den Benutzer über die erfolgreiche Darstellung des Quelldokuments.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Das Rendern von CAD-Zeichnungen, insbesondere wenn es um Layouts geht, kann eine entmutigende Aufgabe sein. Mit GroupDocs.Viewer für .NET wird der Prozess jedoch nahtlos und effizient. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie mühelos ein einzelnes Layout in CAD-Zeichnungen in Ihren .NET-Anwendungen rendern.
## FAQs
### Kann ich mit GroupDocs.Viewer für .NET mehrere Layouts gleichzeitig rendern?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern mehrerer Layouts aus CAD-Zeichnungen.
### Ist GroupDocs.Viewer mit verschiedenen CAD-Dateiformaten kompatibel?
Auf jeden Fall unterstützt GroupDocs.Viewer eine Vielzahl von CAD-Dateiformaten, darunter DWG, DXF, DGN und mehr.
### Kann ich die Rendering-Optionen für CAD-Zeichnungen anpassen?
Ja, GroupDocs.Viewer bietet umfangreiche Optionen, um die Rendering-Einstellungen entsprechend Ihren Anforderungen anzupassen.
### Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
 Ja, Sie können die Funktionen von GroupDocs.Viewer mit einer kostenlosen Testversion erkunden[Hier](https://releases.groupdocs.com/).
### Wo erhalte ich Unterstützung für GroupDocs.Viewer für .NET?
 Bei Fragen oder Hilfe können Sie das GroupDocs.Viewer-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9).