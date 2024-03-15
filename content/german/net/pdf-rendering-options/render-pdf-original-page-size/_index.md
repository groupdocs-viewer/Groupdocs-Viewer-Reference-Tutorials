---
title: PDF mit Originalseitengröße rendern
linktitle: PDF mit Originalseitengröße rendern
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET PDFs mit Originalseitengrößen rendern. Befolgen Sie unsere Schritt-für-Schritt-Anleitung und integrieren Sie diese Funktionalität nahtlos.
type: docs
weight: 17
url: /de/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Einführung
Im Bereich der .NET-Entwicklung zeichnet sich GroupDocs.Viewer als leistungsstarkes Tool zum Rendern verschiedener Dokumentformate, einschließlich PDFs, aus. Eine häufige Anforderung bei der Dokumentenverarbeitung besteht darin, PDFs unter Beibehaltung ihrer ursprünglichen Seitengröße darzustellen. Um diese Aufgabe reibungslos zu bewältigen, ist ein umfassendes Verständnis von GroupDocs.Viewer für .NET und seinen Funktionalitäten erforderlich.
## Voraussetzungen
Bevor Sie mit dem Rendern von PDFs mit Originalseitengrößen mit GroupDocs.Viewer für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installieren Sie GroupDocs.Viewer für .NET
 Laden Sie zunächst die GroupDocs.Viewer-Bibliothek von der Website herunter. Sie können die Bibliothek über die bereitgestellte Website beziehen[Download-Link](https://releases.groupdocs.com/viewer/net/). Befolgen Sie die Installationsanweisungen in der Dokumentation, um es effektiv in Ihr .NET-Projekt zu integrieren.
### 2. Entwicklungsumgebung einrichten
Stellen Sie sicher, dass Sie eine Entwicklungsumgebung für die .NET-Entwicklung eingerichtet haben. Dazu gehört die Installation einer kompatiblen IDE, z. B. Visual Studio, und grundlegende Kenntnisse der C#-Programmierung.
### 3. Besorgen Sie sich ein PDF-Dokument
Sie benötigen ein Beispiel-PDF-Dokument zum Rendern mit GroupDocs.Viewer. Zu Testzwecken können Sie jedes beliebige PDF-Dokument verwenden. Wenn Sie noch keines haben, können Sie ein Beispiel-PDF aus verschiedenen Online-Quellen herunterladen.

## Namespaces importieren
Bevor Sie mit dem Rendern von PDFs fortfahren, müssen Sie unbedingt die erforderlichen Namespaces in Ihr C#-Projekt importieren. Dieser Schritt ermöglicht Ihnen den Zugriff auf die erforderlichen Klassen und Methoden aus der GroupDocs.Viewer-Bibliothek.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nachdem Sie nun die Voraussetzungen geschaffen und die erforderlichen Namespaces importiert haben, unterteilen wir den Prozess des Renderns von PDFs mit Originalseitengrößen mithilfe von GroupDocs.Viewer für .NET in einfache Schritte:
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
 Stellen Sie sicher, dass Sie das Verzeichnis angeben, in dem die gerenderten Seiten gespeichert werden sollen. Ersetzen`"Your Document Directory"` mit dem Pfad Ihres gewünschten Verzeichnisses.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Richten Sie das Format für die Benennung der gerenderten Seitendateien ein. In diesem Beispiel werden die Seiten als PNG-Bilder mit Dateinamen im Format gespeichert`"page_1.png"`, `"page_2.png"`, und so weiter.
## Schritt 3: PDF mit Originalseitengröße rendern
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Instanziieren Sie a`Viewer` Objekt mit dem Pfad zu Ihrer PDF-Datei. Dann erstellen Sie`PngViewOptions` mit dem angegebenen Auslagerungsdateipfadformat. Satz`RenderOriginalPageSize` Eigentum zu`true` um beim Rendern die ursprünglichen Seitengrößen beizubehalten.
## Schritt 4: Speicherort des gerenderten Dokuments anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Drucken Sie eine Meldung aus, die das erfolgreiche Rendern anzeigt, und geben Sie das Verzeichnis an, in dem die gerenderten Seiten gespeichert werden.

## Abschluss
Das Rendern von PDFs mit Originalseitengrößen mit GroupDocs.Viewer für .NET ist ein unkomplizierter Vorgang, wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen. Durch den Import der erforderlichen Namespaces und das Befolgen der Schritt-für-Schritt-Anleitung können Sie diese Funktionalität nahtlos in Ihre .NET-Anwendungen integrieren.
## FAQs
### Kann GroupDocs.Viewer neben PDF auch andere Dokumentformate rendern?
Ja, GroupDocs.Viewer unterstützt das Rendern verschiedener Dokumentformate, darunter Word, Excel, PowerPoint und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer ist sowohl mit .NET Framework- als auch mit .NET Core-Umgebungen kompatibel.
### Kann ich das Ausgabeformat gerenderter Seiten anpassen?
Ja, Sie können das Ausgabeformat anpassen, indem Sie die von GroupDocs.Viewer bereitgestellten Optionen anpassen, z. B. verschiedene Bildformate festlegen oder benutzerdefinierte Rendering-Optionen angeben.
### Bietet GroupDocs.Viewer Unterstützung für cloudbasiertes Dokument-Rendering?
Ja, GroupDocs.Viewer bietet APIs für cloudbasiertes Dokument-Rendering, sodass Sie Dokumente direkt von Cloud-Speicheranbietern rendern können.
### Gibt es eine kostenlose Testversion für GroupDocs.Viewer?
 Ja, Sie können GroupDocs.Viewer mit einer kostenlosen Testversion erkunden, indem Sie die bereitgestellte Website besuchen[Verknüpfung](https://releases.groupdocs.com/).