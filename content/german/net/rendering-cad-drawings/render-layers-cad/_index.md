---
title: Rendern Sie Ebenen in CAD-Zeichnungen
linktitle: Rendern Sie Ebenen in CAD-Zeichnungen
second_title: GroupDocs.Viewer .NET-API
description: Rendern Sie CAD-Zeichnungen nahtlos in .NET-Anwendungen mit GroupDocs.Viewer für .NET. Entdecken Sie Rendering-Optionen, passen Sie Ebenen an und mehr.
type: docs
weight: 13
url: /de/net/rendering-cad-drawings/render-layers-cad/
---
## Einführung
GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool, mit dem Entwickler Funktionen zur Dokumentwiedergabe nahtlos in ihre .NET-Anwendungen integrieren können. Ganz gleich, ob Sie CAD-Zeichnungen, PDFs, Microsoft Office-Dokumente oder mehr rendern müssen, GroupDocs.Viewer bietet eine umfassende Lösung.
## Voraussetzungen
Bevor Sie GroupDocs.Viewer für .NET verwenden, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundlegendes Verständnis der Programmiersprache C#.
- .NET-Entwicklungsumgebung auf Ihrem Computer eingerichtet.
-  GroupDocs.Viewer für .NET installiert. Sie können es herunterladen unter[Hier](https://releases.groupdocs.com/viewer/net/).
-  Zugriff auf die GroupDocs.Viewer für .NET-Dokumentation als Referenz, die Sie finden können[Hier](https://reference.groupdocs.com/viewer/net/).

## Namespaces importieren
Um GroupDocs.Viewer für .NET verwenden zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Folge diesen Schritten:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte unterteilen:
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Viewer-Objekt initialisieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Codeblock wird fortgesetzt...
}
```
## Schritt 4: Legen Sie die HTML-Ansichtsoptionen fest
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Schritt 5: CAD-Ebenen definieren
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Schritt 6: Dokument rendern
```csharp
viewer.View(options);
```
## Schritt 7: Speicherort des gerenderten Dokuments ausgeben
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Mit GroupDocs.Viewer für .NET wird das Rendern von CAD-Zeichnungen in Ihren .NET-Anwendungen zu einem nahtlosen Prozess. Indem Sie die in diesem Leitfaden beschriebenen Schritte befolgen, können Sie Funktionen zur Dokumentwiedergabe ganz einfach in Ihre Projekte integrieren.
## FAQs
### Ist GroupDocs.Viewer mit allen Arten von CAD-Zeichnungen kompatibel?
Ja, GroupDocs.Viewer unterstützt das Rendern einer Vielzahl von CAD-Zeichnungsformaten, einschließlich DWG und DXF.
### Kann ich die Rendering-Optionen für CAD-Zeichnungen anpassen?
Auf jeden Fall bietet GroupDocs.Viewer verschiedene Anpassungsoptionen, z. B. die Angabe von zu rendernden Ebenen oder die Festlegung von Ausgabeformaten.
### Benötigt GroupDocs.Viewer eine Internetverbindung zum Rendern von Dokumenten?
Nein, GroupDocs.Viewer führt das Rendern lokal durch, ohne dass eine Internetverbindung erforderlich ist.
### Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
 Ja, Sie können auf eine kostenlose Testversion von GroupDocs.Viewer für .NET zugreifen[Hier](https://releases.groupdocs.com/).
### Wo erhalte ich Unterstützung für GroupDocs.Viewer für .NET?
 Für technische Unterstützung oder Fragen können Sie das GroupDocs.Viewer-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9).