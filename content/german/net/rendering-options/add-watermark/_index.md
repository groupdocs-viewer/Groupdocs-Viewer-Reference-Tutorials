---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET nahtlos Wasserzeichen zu Dokumenten hinzufügen. Verbessern Sie die Dokumentensicherheit und das Branding mit diesem leicht verständlichen Tutorial."
"linktitle": "Wasserzeichen zum Dokument hinzufügen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Wasserzeichen zum Dokument hinzufügen"
"url": "/de/net/rendering-options/add-watermark/"
"weight": 10
---

# Wasserzeichen zum Dokument hinzufügen

## Einführung
Im digitalen Zeitalter ist die nahtlose Verwaltung und Anzeige verschiedener Dokumentformate für viele Unternehmen und Privatpersonen unerlässlich. Mit Tools wie GroupDocs.Viewer für .NET wird die Dokumentenverwaltung zum Kinderspiel. Diese leistungsstarke .NET-Bibliothek ermöglicht Entwicklern die mühelose Integration von Dokumentanzeigefunktionen in ihre Anwendungen. So können Benutzer Dokumente anzeigen, ohne die ursprüngliche Software zu benötigen, mit der sie erstellt wurden.
## Voraussetzungen
Bevor Sie GroupDocs.Viewer für .NET verwenden, um Dokumenten Wasserzeichen hinzuzufügen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Umgebungseinrichtung: Richten Sie eine Entwicklungsumgebung mit installiertem .NET Framework oder .NET Core ein.
2. GroupDocs.Viewer für .NET: Laden Sie die Bibliothek GroupDocs.Viewer für .NET herunter und installieren Sie sie von der [Download-Seite](https://releases.groupdocs.com/viewer/net/).
3. Dokumentdateien: Bereiten Sie die Dokumentdateien vor, mit denen Sie arbeiten möchten, z. B. DOCX, PDF oder andere.
4. Grundkenntnisse in C#: Zur Implementierung der Codebeispiele sind Kenntnisse der Programmiersprache C# erforderlich.

## Namespaces importieren
Bevor Sie mit GroupDocs.Viewer für .NET Wasserzeichen in Dokumente einfügen, importieren Sie die erforderlichen Namespaces in Ihren C#-Code. Dieser Schritt ermöglicht Ihnen den nahtlosen Zugriff auf die von der Bibliothek bereitgestellten Klassen und Methoden.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Prozess zum Hinzufügen eines Wasserzeichens zu einem Dokument mit GroupDocs.Viewer für .NET durchgehen. Befolgen Sie diese Schritte, um die Wasserzeichenfunktion nahtlos in Ihre Anwendung zu integrieren.
## Schritt 1: Ausgabeverzeichnis festlegen
```csharp
string outputDirectory = "Your Document Directory";
```
Geben Sie das Verzeichnis an, in dem die Ausgabedateien nach dem Anwenden des Wasserzeichens gespeichert werden sollen.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
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
Erstellen Sie eine Instanz der Viewer-Klasse und übergeben Sie den Pfad zur Dokumentdatei als Parameter. In diesem Beispiel verwenden wir eine DOCX-Beispieldatei.
## Schritt 4: HTML-Ansichtsoptionen konfigurieren
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Konfigurieren Sie die HTML-Ansichtsoptionen, einschließlich des Wasserzeichentextes, den Sie dem Dokument hinzufügen möchten.
## Schritt 5: Dokument mit Wasserzeichen anzeigen
```csharp
viewer.View(options);
```
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die konfigurierten Optionen. Dadurch wird das Dokument mit dem angegebenen Wasserzeichen gerendert.
## Schritt 6: Ausgabeverzeichnispfad anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informieren Sie den Benutzer über die erfolgreiche Darstellung des Dokuments und geben Sie das Verzeichnis an, in dem die Ausgabedateien gespeichert sind.

## Abschluss
GroupDocs.Viewer für .NET bietet eine komfortable Möglichkeit, Dokumente programmgesteuert mit Wasserzeichen zu versehen. Mit den in diesem Tutorial beschriebenen Schritten können Sie die Wasserzeichenfunktion nahtlos in Ihre .NET-Anwendungen integrieren und so die Dokumentensicherheit und das Branding verbessern.
## Häufig gestellte Fragen
### Kann ich das Erscheinungsbild des Wasserzeichens anpassen?
Ja, Sie können verschiedene Eigenschaften des Wasserzeichens anpassen, z. B. Text, Schriftart, Farbe, Größe und Position.
### Unterstützt GroupDocs.Viewer das Anzeigen von Dokumenten aus Remotequellen?
Ja, GroupDocs.Viewer unterstützt das Anzeigen von Dokumenten aus dem lokalen Speicher sowie von Remote-URLs.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.groupdocs.com/).
### Kann ich mehreren Seiten eines Dokuments Wasserzeichen hinzufügen?
Auf jeden Fall, GroupDocs.Viewer ermöglicht das Hinzufügen von Wasserzeichen zu einzelnen oder allen Seiten eines Dokuments.
### Wie kann ich Unterstützung oder Hilfe erhalten, wenn ich auf Probleme stoße?
Sie können Hilfe und Unterstützung in den GroupDocs-Community-Foren suchen [Hier](https://forum.groupdocs.com/c/viewer/9).