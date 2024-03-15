---
title: Wasserzeichen im Dokument hinzufügen
linktitle: Wasserzeichen im Dokument hinzufügen
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET nahtlos Wasserzeichen zu Dokumenten hinzufügen. Verbessern Sie die Dokumentensicherheit und das Branding mit diesem leicht verständlichen Tutorial.
type: docs
weight: 10
url: /de/net/rendering-options/add-watermark/
---
## Einführung
Im heutigen digitalen Zeitalter ist die nahtlose Verwaltung und Anzeige verschiedener Dokumentformate für viele Unternehmen und Privatpersonen gleichermaßen eine Notwendigkeit. Glücklicherweise wird die Handhabung von Dokumenten mit Tools wie GroupDocs.Viewer für .NET zum Kinderspiel. Diese leistungsstarke .NET-Bibliothek ermöglicht Entwicklern die mühelose Integration von Dokumentanzeigefunktionen in ihre Anwendungen, sodass Benutzer Dokumente anzeigen können, ohne die Originalsoftware zu benötigen, mit der sie erstellt wurden.
## Voraussetzungen
Bevor Sie GroupDocs.Viewer für .NET zum Hinzufügen von Wasserzeichen zu Dokumenten verwenden, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Umgebungseinrichtung: Richten Sie eine Entwicklungsumgebung mit installiertem .NET Framework oder .NET Core ein.
2.  GroupDocs.Viewer für .NET: Laden Sie die GroupDocs.Viewer für .NET-Bibliothek von herunter und installieren Sie sie[Download-Seite](https://releases.groupdocs.com/viewer/net/).
3. Dokumentdateien: Bereiten Sie die Dokumentdateien vor, mit denen Sie arbeiten möchten, z. B. DOCX, PDF oder andere.
4. Grundkenntnisse in C#: Zur Umsetzung der Codebeispiele sind Kenntnisse der Programmiersprache C# erforderlich.

## Namespaces importieren
Bevor Sie mit dem Hinzufügen von Wasserzeichen zu Dokumenten mit GroupDocs.Viewer für .NET beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihren C#-Code importieren. Dieser Schritt ermöglicht Ihnen den nahtlosen Zugriff auf die von der Bibliothek bereitgestellten Klassen und Methoden.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Prozess des Hinzufügens eines Wasserzeichens zu einem Dokument mithilfe von GroupDocs.Viewer für .NET durchgehen. Befolgen Sie diese Schritte, um die Wasserzeichenfunktion nahtlos in Ihre Anwendung zu integrieren.
## Schritt 1: Ausgabeverzeichnis festlegen
```csharp
string outputDirectory = "Your Document Directory";
```
Geben Sie das Verzeichnis an, in dem die Ausgabedateien nach dem Anwenden des Wasserzeichens gespeichert werden sollen.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Legen Sie das Format für die Dateipfade der gerenderten Seiten fest. In diesem Beispiel werden HTML-Dateien mit Seitenzahlen generiert.
## Schritt 3: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Der Code wird im nächsten Schritt fortgesetzt ...
}
```
Erstellen Sie eine Instanz der Viewer-Klasse und übergeben Sie den Pfad zur Dokumentdatei als Parameter. In diesem Beispiel verwenden wir eine Beispiel-DOCX-Datei.
## Schritt 4: Konfigurieren Sie die HTML-Ansichtsoptionen
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Konfigurieren Sie die HTML-Ansichtsoptionen, einschließlich des Wasserzeichentexts, den Sie dem Dokument hinzufügen möchten.
## Schritt 5: Dokument mit Wasserzeichen anzeigen
```csharp
viewer.View(options);
```
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die konfigurierten Optionen. Dadurch wird das Dokument mit dem angegebenen Wasserzeichen gerendert.
## Schritt 6: Ausgabeverzeichnispfad anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informieren Sie den Benutzer über die erfolgreiche Darstellung des Dokuments und geben Sie das Verzeichnis an, in dem die Ausgabedateien gespeichert werden.

## Abschluss
GroupDocs.Viewer für .NET bietet eine praktische Möglichkeit, Wasserzeichen programmgesteuert zu Dokumenten hinzuzufügen. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Wasserzeichenfunktionen nahtlos in Ihre .NET-Anwendungen integrieren und so die Dokumentensicherheit und das Branding verbessern.
## FAQs
### Kann ich das Erscheinungsbild des Wasserzeichens anpassen?
Ja, Sie können verschiedene Eigenschaften des Wasserzeichens anpassen, z. B. Text, Schriftart, Farbe, Größe und Position.
### Unterstützt GroupDocs.Viewer das Anzeigen von Dokumenten aus Remote-Quellen?
Ja, GroupDocs.Viewer unterstützt die Anzeige von Dokumenten aus dem lokalen Speicher sowie von Remote-URLs.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.groupdocs.com/).
### Kann ich mehreren Seiten eines Dokuments Wasserzeichen hinzufügen?
Auf jeden Fall ermöglicht GroupDocs.Viewer das Hinzufügen von Wasserzeichen zu einzelnen Seiten oder allen Seiten eines Dokuments.
### Wie kann ich Unterstützung oder Unterstützung erhalten, wenn ich auf Probleme stoße?
 Sie können Hilfe und Unterstützung in den Community-Foren von GroupDocs suchen[Hier](https://forum.groupdocs.com/c/viewer/9).