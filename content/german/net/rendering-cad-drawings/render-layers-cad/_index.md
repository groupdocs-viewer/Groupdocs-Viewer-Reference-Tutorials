---
"description": "Rendern Sie CAD-Zeichnungen nahtlos in .NET-Anwendungen mit GroupDocs.Viewer für .NET. Entdecken Sie Rendering-Optionen, passen Sie Ebenen an und vieles mehr."
"linktitle": "Renderebenen in CAD-Zeichnungen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderebenen in CAD-Zeichnungen"
"url": "/de/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
---

# Renderebenen in CAD-Zeichnungen

## Einführung
GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool, mit dem Entwickler Dokumentrendering-Funktionen nahtlos in ihre .NET-Anwendungen integrieren können. Ob Sie CAD-Zeichnungen, PDFs, Microsoft Office-Dokumente oder mehr rendern müssen – GroupDocs.Viewer bietet eine umfassende Lösung.
## Voraussetzungen
Bevor Sie mit der Verwendung von GroupDocs.Viewer für .NET beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundlegende Kenntnisse der Programmiersprache C#.
- Auf Ihrem Computer ist eine .NET-Entwicklungsumgebung eingerichtet.
- GroupDocs.Viewer für .NET installiert. Sie können es herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
- Zugriff auf die GroupDocs.Viewer für .NET-Dokumentation für Tutorials, die Sie finden können [Hier](https://tutorials.groupdocs.com/viewer/net/).

## Namespaces importieren
Um GroupDocs.Viewer für .NET zu verwenden, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Führen Sie dazu die folgenden Schritte aus:

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
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Viewer-Objekt initialisieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Codeblock wird fortgesetzt …
}
```
## Schritt 4: HTML-Ansichtsoptionen festlegen
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
Mit GroupDocs.Viewer für .NET wird das Rendern von CAD-Zeichnungen in Ihren .NET-Anwendungen zu einem nahtlosen Prozess. Mit den in dieser Anleitung beschriebenen Schritten können Sie Dokumentrendering-Funktionen problemlos in Ihre Projekte integrieren.
## Häufig gestellte Fragen
### Ist GroupDocs.Viewer mit allen Arten von CAD-Zeichnungen kompatibel?
Ja, GroupDocs.Viewer unterstützt das Rendern einer Vielzahl von CAD-Zeichnungsformaten, einschließlich DWG und DXF.
### Kann ich die Rendering-Optionen für CAD-Zeichnungen anpassen?
Auf jeden Fall, GroupDocs.Viewer bietet verschiedene Anpassungsoptionen, wie etwa das Festlegen der zu rendernden Ebenen oder das Einstellen von Ausgabeformaten.
### Benötigt GroupDocs.Viewer zum Rendern von Dokumenten eine Internetverbindung?
Nein, GroupDocs.Viewer führt das Rendering lokal durch, ohne dass eine Internetverbindung erforderlich ist.
### Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können auf eine kostenlose Testversion von GroupDocs.Viewer für .NET zugreifen [Hier](https://releases.groupdocs.com/).
### Wo erhalte ich Support für GroupDocs.Viewer für .NET?
Für technische Unterstützung oder Fragen können Sie das GroupDocs.Viewer-Forum besuchen [Hier](https://forum.groupdocs.com/c/viewer/9).