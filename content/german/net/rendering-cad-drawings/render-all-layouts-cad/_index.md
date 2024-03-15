---
title: Rendern Sie alle Layouts in CAD-Zeichnungen
linktitle: Rendern Sie alle Layouts in CAD-Zeichnungen
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie alle Layouts in CAD-Zeichnungen mit GroupDocs.Viewer für .NET rendern. Folgen Sie unserem umfassenden Tutorial für eine nahtlose Integration.
type: docs
weight: 11
url: /de/net/rendering-cad-drawings/render-all-layouts-cad/
---
## Einführung
Im Bereich der Dokumentenverwaltung und -visualisierung sticht GroupDocs.Viewer für .NET als vielseitige Lösung hervor, die es Entwicklern ermöglicht, mühelos verschiedene Dokumenttypen in ihren .NET-Anwendungen zu rendern. Zu den unzähligen Funktionen gehört die Fähigkeit, CAD-Zeichnungen, einschließlich der damit verbundenen komplizierten Layouts, effizient zu rendern. In diesem Tutorial befassen wir uns mit dem Prozess der Nutzung von GroupDocs.Viewer für .NET zum Rendern aller in CAD-Zeichnungen vorhandenen Layouts. 
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Grundlegendes Verständnis der .NET-Entwicklung: Vertrautheit mit den Grundlagen der .NET-Entwicklung ist für das Verständnis der in diesem Tutorial beschriebenen Implementierungsschritte von Vorteil.
2.  Installation von GroupDocs.Viewer für .NET: Stellen Sie sicher, dass Sie die GroupDocs.Viewer für .NET-Bibliothek installiert haben. Sie können es hier herunterladen[Webseite](https://releases.groupdocs.com/viewer/net/).
3. CAD-Zeichnungsdateien: Besorgen Sie sich die CAD-Zeichnungsdateien, die Sie rendern möchten. Dazu können DWG-Dateien mit mehreren Layouts gehören.
4. Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung mit den erforderlichen Tools und Abhängigkeiten ein.

## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr .NET-Projekt importieren. Diese Namespaces bieten Zugriff auf die Funktionen, die zum Rendern von CAD-Zeichnungen mit GroupDocs.Viewer erforderlich sind.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 2: System.IO-Namespace importieren
```csharp
using System.IO;
```
## Schritt 1: Geben Sie das Ausgabeverzeichnis an
```csharp
string outputDirectory = "Your Document Directory";
```
Definieren Sie das Verzeichnis, in dem die gerenderte Ausgabe gespeichert werden soll.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Richten Sie das Format für die Dateipfade der gerenderten Seiten ein. In diesem Fall werden die Seiten als HTML-Dateien gespeichert.
## Schritt 3: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Erstellen Sie eine Instanz der Viewer-Klasse und übergeben Sie den Pfad zur CAD-Zeichnungsdatei als Parameter.
## Schritt 4: Konfigurieren Sie die HTML-Ansichtsoptionen
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Konfigurieren Sie die HTML-Ansichtsoptionen und geben Sie an, dass Layouts für CAD-Zeichnungen gerendert werden sollen.
## Schritt 5: CAD-Zeichnung rendern
```csharp
viewer.View(options);
```
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die konfigurierten Optionen zum Rendern der CAD-Zeichnung.
## Schritt 6: Ausgabeverzeichnis anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informieren Sie den Benutzer über das erfolgreiche Rendern und den Speicherort des Ausgabeverzeichnisses.

## Abschluss
In diesem Tutorial haben wir untersucht, wie Sie GroupDocs.Viewer für .NET verwenden, um alle in CAD-Zeichnungen vorhandenen Layouts darzustellen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und die bereitgestellten Codeausschnitte implementieren, können Sie diese Funktionalität nahtlos in Ihre .NET-Anwendungen integrieren und so die Möglichkeiten zur Dokumentvisualisierung verbessern.
## FAQs
### Ist GroupDocs.Viewer mit verschiedenen CAD-Formaten kompatibel?
Ja, GroupDocs.Viewer unterstützt das Rendern von CAD-Zeichnungen in Formaten wie DWG und DXF.
### Kann ich die Rendering-Ausgabe entsprechend den Anforderungen meiner Anwendung anpassen?
Absolut, GroupDocs.Viewer bietet eine breite Palette von Optionen zum Anpassen der Rendering-Ausgabe, einschließlich Bildqualität, Seitengröße und mehr.
### Benötigt GroupDocs.Viewer für die kommerzielle Nutzung zusätzliche Lizenzen?
Ja, für die kommerzielle Nutzung müssen Sie möglicherweise eine Lizenz erwerben. Sie können temporäre Lizenzen zu Testzwecken erwerben oder eine kommerzielle Lizenz auf der Website erwerben.
### Kann ich CAD-Zeichnungen asynchron mit GroupDocs.Viewer rendern?
Ja, GroupDocs.Viewer bietet asynchrone Rendering-Funktionen, die eine effiziente Bearbeitung großer CAD-Zeichnungen ermöglichen, ohne den Hauptthread zu blockieren.
### Bietet GroupDocs.Viewer Unterstützung bei der Fehlerbehebung und technische Hilfe?
 Natürlich können Sie Unterstützung und Unterstützung im zugänglichen GroupDocs.Viewer-Community-Forum suchen[Hier](https://forum.groupdocs.com/c/viewer/9).