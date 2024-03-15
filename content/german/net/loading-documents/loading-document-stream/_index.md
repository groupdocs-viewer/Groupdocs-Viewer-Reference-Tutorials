---
title: Dokumente aus Stream laden
linktitle: Dokumente aus Stream laden
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET Dokumente nahtlos aus Streams laden. Erweitern Sie Ihre .NET-Anwendungen mit leistungsstarken Dokumentanzeigefunktionen.
type: docs
weight: 12
url: /de/net/loading-documents/loading-document-stream/
---
## Einführung
Im Bereich der .NET-Entwicklung ist die effiziente Verwaltung und Anzeige von Dokumenten von größter Bedeutung. Mit dem Aufkommen fortschrittlicher Tools und Bibliotheken werden Aufgaben, die einst entmutigend erschienen, jetzt vereinfacht. Unter diesen Tools sticht GroupDocs.Viewer für .NET als vielseitige Lösung für die nahtlose Verarbeitung verschiedener Dokumentformate hervor. In diesem umfassenden Leitfaden befassen wir uns mit den Feinheiten der Verwendung von GroupDocs.Viewer für .NET zum Laden von Dokumenten aus einem Stream. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, dieses Tutorial vermittelt Ihnen das Wissen, um die Leistungsfähigkeit von GroupDocs.Viewer effektiv zu nutzen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Grundlegendes Verständnis von C# und .NET Framework: Vertrautheit mit der Programmiersprache C# und dem .NET Framework hilft beim Verständnis der besprochenen Konzepte.
   
2.  Installation von GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET von herunter und installieren Sie es[Webseite](https://releases.groupdocs.com/viewer/net/).
3. IDE: Installieren Sie zum Codieren und Testen eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio.
4. Dokumentenstrom: Bereiten Sie einen Dokumentenstrom zum Laden vor. Dies kann ein Dateistream oder eine andere kompatible Streamquelle sein.

## Namespaces importieren
Stellen Sie vor der Implementierung des Codes zum Laden von Dokumenten aus einem Stream sicher, dass Sie die erforderlichen Namespaces importieren:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Legen Sie den Verzeichnispfad fest, in dem das gerenderte Dokument gespeichert wird.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definieren Sie das Format für den Dateipfad jeder Seite. Hier wird „{0}“ durch die Seitenzahl ersetzt.
## Schritt 3: Holen Sie sich den Dokumentenstream
```csharp
Stream stream = GetFileStream();
```
Beziehen Sie den Dokumentenstrom von der gewünschten Quelle. Dies kann ein Dateistream, ein Speicherstream oder ein anderer kompatibler Stream sein.
## Schritt 4: Dokument mit Viewer laden
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Initialisieren Sie eine neue Instanz der Viewer-Klasse mit dem Dokumentstream. Konfigurieren Sie dann die HTML-Ansichtsoptionen und rendern Sie das Dokument.
## Schritt 5: Ausgabeverzeichnis anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informieren Sie den Benutzer über die erfolgreiche Darstellung des Dokuments und geben Sie den Speicherort der Ausgabe an.

## Abschluss
Zusammenfassend bietet GroupDocs.Viewer für .NET eine robuste Lösung zum mühelosen Laden und Anzeigen von Dokumenten aus Streams. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Funktionen zur Dokumentanzeige nahtlos in Ihre .NET-Anwendungen integrieren und so die Benutzererfahrung und Produktivität verbessern.
## FAQs
### Kann GroupDocs.Viewer für .NET verschiedene Dokumentformate verarbeiten?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, DOCX, XLSX, PPTX und mehr.
### Ist GroupDocs.Viewer für .NET sowohl für Web- als auch für Desktop-Anwendungen geeignet?
Absolut! GroupDocs.Viewer kann nahtlos in Web- und Desktop-Anwendungen integriert werden, die mit .NET entwickelt wurden.
### Bietet GroupDocs.Viewer Anpassungsoptionen für die Dokumentwiedergabe?
Ja, Sie können verschiedene Aspekte der Dokumentwiedergabe, wie z. B. Wasserzeichen, Seitendrehung und Zoomstufe, entsprechend Ihren Anforderungen anpassen.
### Kann ich GroupDocs.Viewer für .NET in kommerziellen Projekten verwenden?
Ja, GroupDocs.Viewer bietet Lizenzoptionen, die für kommerzielle Projekte geeignet sind. Sie können Lizenzen beim Beamten erwerben[Webseite](https://purchase.groupdocs.com/temporary-license/).
### Ist technischer Support für GroupDocs.Viewer für .NET verfügbar?
 Ja, Sie können technische Unterstützung und Beratung im speziellen Support-Forum von anfordern[GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).