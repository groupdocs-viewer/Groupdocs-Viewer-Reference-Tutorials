---
title: Legen Sie Bildgrößenbeschränkungen fest
linktitle: Legen Sie Bildgrößenbeschränkungen fest
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET mühelos Bildgrößenbeschränkungen in .NET-Anwendungen festlegen und so das Anzeigeerlebnis von Dokumenten verbessern.
type: docs
weight: 21
url: /de/net/rendering-options/set-image-size-limits/
---
## Einführung
GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool, das die nahtlose Anzeige von Dokumenten in .NET-Anwendungen ermöglicht. Mit seinen robusten Funktionen und der intuitiven Benutzeroberfläche können Entwickler mühelos Dokumentanzeigefunktionen in ihre Projekte integrieren und so das Benutzererlebnis und die Produktivität verbessern. In diesem Tutorial erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET Bildgrößenbeschränkungen festlegen, um eine optimale Anzeige von Dokumenten bei gleichzeitiger Beibehaltung von Leistung und Effizienz sicherzustellen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  GroupDocs.Viewer für .NET: Stellen Sie sicher, dass die erforderliche GroupDocs.Viewer für .NET-Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können es hier herunterladen[Webseite](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Richten Sie Ihre bevorzugte .NET-Entwicklungsumgebung wie Visual Studio mit den erforderlichen Konfigurationen ein.
3. Dokumentenverzeichnis: Legen Sie ein bestimmtes Verzeichnis fest, in dem Ihre Dokumente gespeichert werden, und stellen Sie sicher, dass der Verzeichnispfad innerhalb Ihrer Anwendung zugänglich ist.

## Namespaces importieren
Bevor Sie mit der Implementierung fortfahren, müssen Sie unbedingt die erforderlichen Namespaces importieren, um effektiv auf die Funktionen von GroupDocs.Viewer für .NET zugreifen zu können.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis und Dateipfad definieren
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
 Stellen Sie sicher, dass Sie es ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.
## Schritt 2: Viewer-Objekt initialisieren und Dokumentpfad angeben
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX stellt den Pfad zum Beispieldokument dar.
    // Ersetzen Sie es durch den Pfad zu Ihrem gewünschten Dokument.
```
 Ersetzen`TestFiles.SAMPLE_DOCX` mit dem Pfad zu Ihrem Dokument. Dies kann ein DOCX-, PDF- oder ein anderes unterstütztes Dateiformat sein.
## Schritt 3: Konfigurieren Sie die JPEG-Ansichtsoptionen
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
 Verstelle die`MaxWidth` -Eigenschaft, um die maximale Breite des gerenderten Bilds gemäß Ihren Anforderungen festzulegen. Dadurch wird sichergestellt, dass das Bild die angegebene Breite nicht überschreitet und eine optimale Anzeige gewährleistet ist.
## Schritt 4: Dokument mit angegebenen Optionen rendern
```csharp
viewer.View(options);
```
Diese Codezeile löst den Rendervorgang aus und generiert das Ausgabebild mit den definierten Größenbeschränkungen.
## Schritt 5: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nach erfolgreichem Rendern wird eine Meldung über den erfolgreichen Abschluss zusammen mit dem Ausgabeverzeichnispfad angezeigt.

## Abschluss
Zusammenfassend lässt sich sagen, dass die Beherrschung der Kunst, Bildgrößenbeschränkungen mithilfe von GroupDocs.Viewer für .NET festzulegen, das Anzeigeerlebnis von Dokumenten in Ihren .NET-Anwendungen erheblich verbessern kann. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie die Bildanzeige mühelos optimieren und gleichzeitig Leistung und Effizienz sicherstellen.
## FAQs
### Kann ich sowohl die maximale Breite als auch die maximale Höhe für die gerenderten Bilder festlegen?
Ja, Sie können sowohl die maximale Breite als auch die maximale Höhe festlegen, indem Sie die entsprechenden Eigenschaften in den Ansichtsoptionen verwenden.
### Welche Dokumentformate werden von GroupDocs.Viewer für .NET unterstützt?
GroupDocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter DOCX, PDF, PPT, XLS und mehr.
### Ist GroupDocs.Viewer für .NET mit .NET Core kompatibel?
Ja, GroupDocs.Viewer für .NET bietet Kompatibilität mit .NET Core und ermöglicht so eine nahtlose Integration in moderne .NET-Anwendungen.
### Kann ich ein anderes Ausgabebildformat als JPEG anpassen?
Ja, GroupDocs.Viewer für .NET bietet Unterstützung für verschiedene Ausgabeformate, einschließlich PNG, TIFF und PDF.
### Gibt es eine Testversion zum Testen vor dem Kauf?
 Ja, Sie können eine kostenlose Testversion von der nutzen[Webseite](https://releases.groupdocs.com/viewer/net/). um die Features und Funktionalitäten von GroupDocs.Viewer für .NET zu erkunden, bevor Sie einen Kauf tätigen.