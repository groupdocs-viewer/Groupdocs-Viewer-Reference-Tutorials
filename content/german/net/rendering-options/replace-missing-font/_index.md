---
"description": "Erfahren Sie, wie Sie fehlende Schriftarten in .NET-Dokumenten mühelos mit GroupDocs.Viewer ersetzen. Sorgen Sie mit einfachen Schritten für eine präzise Darstellung."
"linktitle": "Fehlende Schriftart ersetzen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Fehlende Schriftart ersetzen"
"url": "/de/net/rendering-options/replace-missing-font/"
"weight": 20
---

# Fehlende Schriftart ersetzen

## Einführung
In der .NET-Entwicklung ist effiziente Dokumentenverwaltung entscheidend. GroupDocs.Viewer für .NET bietet eine leistungsstarke Lösung zum Anzeigen verschiedener Dokumentformate in Ihren .NET-Anwendungen. In diesem Tutorial erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET fehlende Schriftarten in Dokumenten ersetzen. Ob PDFs, PowerPoint-Präsentationen oder Word-Dokumente – GroupDocs.Viewer vereinfacht den Prozess und stellt sicher, dass Ihre Dokumente auch bei fehlenden Schriftarten korrekt dargestellt werden.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. GroupDocs.Viewer für .NET: Laden Sie die GroupDocs.Viewer-Bibliothek von der Website herunter und installieren Sie sie](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung wie Visual Studio ein.
3. Grundlegende C#-Kenntnisse: Vertrautheit mit der Programmiersprache C# und dem .NET-Framework.

## Namespaces importieren
Importieren Sie in Ihren C#-Code die erforderlichen Namespaces, um auf die GroupDocs.Viewer-Funktionen zuzugreifen.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Prozess zum Ersetzen fehlender Schriftarten in Dokumenten mithilfe von GroupDocs.Viewer für .NET durchgehen.
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Legen Sie das Verzeichnis fest, in dem die gerenderten Dokumentseiten gespeichert werden.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Geben Sie das Format für die Benennung der HTML-Ausgabedateien an. In diesem Beispiel wird jede Seite als HTML-Datei mit der Benennungskonvention „page_{Seitennummer}.html“ gespeichert.
## Schritt 3: Viewer-Objekt initialisieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Initialisieren Sie eine neue Instanz der Viewer-Klasse und übergeben Sie den Pfad zur Dokumentdatei (in diesem Fall eine PowerPoint-Präsentation mit fehlenden Schriftarten) als Parameter.
## Schritt 4: HTML-Ansichtsoptionen festlegen
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Erstellen Sie eine Instanz von HtmlViewOptions und konfigurieren Sie diese so, dass Ressourcen in die HTML-Ausgabe eingebettet werden. Geben Sie einen Standardschriftnamen an, der als Ersatz für fehlende Schriftarten verwendet werden soll.
## Schritt 5: Dokument rendern
```csharp
viewer.View(options);
```
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die HTML-Ansichtsoptionen. Dadurch werden die Dokumentseiten mit den angegebenen Optionen gerendert.
## Schritt 6: Ausgabepfad anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Drucken Sie eine Meldung, die die erfolgreiche Wiedergabe des Dokuments bestätigt, und geben Sie den Pfad an, unter dem die HTML-Ausgabedateien gespeichert sind.

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie mit GroupDocs.Viewer für .NET fehlende Schriftarten in Dokumenten ersetzen. Mit diesen Schritten stellen Sie sicher, dass Ihre Dokumente auch dann korrekt dargestellt werden, wenn bestimmte Schriftarten nicht verfügbar sind. GroupDocs.Viewer vereinfacht den Prozess und ermöglicht Ihnen, sich auf die Entwicklung robuster .NET-Anwendungen zu konzentrieren, ohne sich um Schriftartenkompatibilität kümmern zu müssen.
## Häufig gestellte Fragen
### Kann GroupDocs.Viewer andere Arten von Schriftartproblemen behandeln?
Ja, GroupDocs.Viewer bietet verschiedene Schriftarten-bezogene Funktionen, darunter Schriftartenersetzung und Schriftartenerkennung.
### Ist GroupDocs.Viewer mit allen .NET-Frameworks kompatibel?
GroupDocs.Viewer unterstützt eine breite Palette von .NET-Frameworks, einschließlich .NET Core und .NET Standard.
### Kann ich den Standardschriftartenersatz in GroupDocs.Viewer anpassen?
Natürlich können Sie jede beliebige Schriftart als Standardersatz für fehlende Schriftarten angeben.
### Unterstützt GroupDocs.Viewer die Stapelverarbeitung von Dokumenten?
Ja, GroupDocs.Viewer ermöglicht Ihnen die gleichzeitige Verarbeitung mehrerer Dokumente und ist daher ideal für Stapelverarbeitungsszenarien.
### Wo finde ich weitere Hilfe oder Unterstützung für GroupDocs.Viewer?
Sie können das GroupDocs.Viewer-Forum besuchen [Hier](https://forum.groupdocs.com/c/viewer/9) für jegliche Hilfe- oder Supportanfragen.