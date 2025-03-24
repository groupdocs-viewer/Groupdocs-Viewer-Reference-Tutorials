---
title: Fehlende Schriftart ersetzen
linktitle: Fehlende Schriftart ersetzen
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie mit GroupDocs.Viewer mühelos fehlende Schriftarten in .NET-Dokumenten ersetzen. Stellen Sie mit einfachen Schritten eine genaue Wiedergabe sicher.
weight: 20
url: /de/net/rendering-options/replace-missing-font/
---
## Einführung
In der Welt der .NET-Entwicklung ist eine effiziente Dokumentenverarbeitung von entscheidender Bedeutung. GroupDocs.Viewer für .NET bietet eine leistungsstarke Lösung zum Anzeigen verschiedener Dokumentformate in Ihren .NET-Anwendungen. In diesem Tutorial erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET fehlende Schriftarten in Dokumenten ersetzen. Egal, ob Sie PDFs, PowerPoint-Präsentationen oder Word-Dokumente bearbeiten, GroupDocs.Viewer vereinfacht den Prozess und stellt sicher, dass Ihre Dokumente korrekt wiedergegeben werden, auch wenn Schriftarten fehlen.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. GroupDocs.Viewer für .NET: Laden Sie die GroupDocs.Viewer-Bibliothek von der Website herunter und installieren Sie sie](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung ein, z. B. Visual Studio.
3. Grundlegende C#-Kenntnisse: Vertrautheit mit der Programmiersprache C# und dem .NET Framework.

## Namespaces importieren
Importieren Sie in Ihrem C#-Code die erforderlichen Namespaces, um auf die GroupDocs.Viewer-Funktionen zuzugreifen.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Prozess des Ersetzens fehlender Schriftarten in Dokumenten mithilfe von GroupDocs.Viewer für .NET durchgehen.
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Legen Sie das Verzeichnis fest, in dem die gerenderten Dokumentseiten gespeichert werden.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Geben Sie das Format für die Benennung der ausgegebenen HTML-Dateien an. In diesem Beispiel wird jede Seite als HTML-Datei mit der Namenskonvention „Seite“ gespeichert_{page_number}.html".
## Schritt 3: Viewer-Objekt initialisieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Initialisieren Sie eine neue Instanz der Viewer-Klasse und übergeben Sie dabei den Pfad zur Dokumentdatei (in diesem Fall eine PowerPoint-Präsentation mit fehlenden Schriftarten) als Parameter.
## Schritt 4: Legen Sie die HTML-Ansichtsoptionen fest
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Erstellen Sie eine Instanz von HtmlViewOptions und konfigurieren Sie sie zum Einbetten von Ressourcen in die HTML-Ausgabe. Geben Sie einen Standardschriftnamen an, der als Ersatz für fehlende Schriftarten verwendet werden soll.
## Schritt 5: Dokument rendern
```csharp
viewer.View(options);
```
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die HTML-Ansichtsoptionen. Dadurch werden die Dokumentseiten mit den angegebenen Optionen gerendert.
## Schritt 6: Ausgabepfad anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Geben Sie eine Meldung aus, die das erfolgreiche Rendern des Dokuments anzeigt, und geben Sie den Pfad an, in dem die ausgegebenen HTML-Dateien gespeichert werden.

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie GroupDocs.Viewer für .NET verwenden, um fehlende Schriftarten in Dokumenten zu ersetzen. Durch Befolgen dieser Schritte können Sie sicherstellen, dass Ihre Dokumente korrekt wiedergegeben werden, auch wenn bestimmte Schriftarten nicht verfügbar sind. GroupDocs.Viewer vereinfacht den Prozess, sodass Sie sich auf die Erstellung robuster .NET-Anwendungen konzentrieren können, ohne sich über Probleme mit der Schriftartenkompatibilität Gedanken machen zu müssen.
## FAQs
### Kann GroupDocs.Viewer andere Arten von Schriftartenproblemen bewältigen?
Ja, GroupDocs.Viewer bietet verschiedene schriftartbezogene Funktionen, einschließlich Schriftartenersetzung und Schriftartenerkennung.
### Ist GroupDocs.Viewer mit allen .NET Frameworks kompatibel?
GroupDocs.Viewer unterstützt eine breite Palette von .NET-Frameworks, einschließlich .NET Core und .NET Standard.
### Kann ich die Standardschriftersetzung in GroupDocs.Viewer anpassen?
Sie können auf jeden Fall eine beliebige Schriftart Ihrer Wahl als Standardersatz für fehlende Schriftarten angeben.
### Unterstützt GroupDocs.Viewer die Stapelverarbeitung von Dokumenten?
Ja, GroupDocs.Viewer ermöglicht Ihnen die gleichzeitige Verarbeitung mehrerer Dokumente und eignet sich daher ideal für Stapelverarbeitungsszenarien.
### Wo finde ich weitere Hilfe oder Unterstützung für GroupDocs.Viewer?
 Sie können das GroupDocs.Viewer-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9) für jegliche Hilfe oder Supportanfragen.