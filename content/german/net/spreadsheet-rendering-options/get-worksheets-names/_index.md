---
title: Rufen Sie Arbeitsblattnamen ab
linktitle: Rufen Sie Arbeitsblattnamen ab
second_title: GroupDocs.Viewer .NET-API
description: Entdecken Sie die Magie von GroupDocs.Viewer für .NET – integrieren Sie die Dokumentenanzeige nahtlos in Ihre Anwendungen. Probieren Sie jetzt die kostenlose Testversion aus!
weight: 11
url: /de/net/spreadsheet-rendering-options/get-worksheets-names/
---

# Rufen Sie Arbeitsblattnamen ab

## Einführung
Willkommen in der faszinierenden Welt von GroupDocs.Viewer für .NET! Wenn Sie ein Entwickler oder Enthusiast sind und die leistungsstarken Dokumentanzeigefunktionen in Ihren .NET-Anwendungen erkunden möchten, werden Sie sich freuen. In diesem umfassenden Leitfaden befassen wir uns mit den Feinheiten des Abrufens von Arbeitsblattnamen mithilfe von GroupDocs.Viewer. Also, schnallen Sie sich an und begeben wir uns auf diese aufregende Reise!
## Voraussetzungen
Bevor wir uns in die Codierungsmagie stürzen, stellen wir sicher, dass Sie alles eingerichtet haben:
1.  Installieren Sie GroupDocs.Viewer für .NET: Gehen Sie zu[Download-Link](https://releases.groupdocs.com/viewer/net/)um die neueste Version von GroupDocs.Viewer für .NET zu erhalten. Befolgen Sie die Installationsanweisungen, um es nahtlos in Ihre Entwicklungsumgebung zu integrieren.
2. Bereiten Sie Ihr Dokument vor: Stellen Sie sicher, dass Sie ein Zieldokument, beispielsweise eine Excel-Datei mit dem Namen „file.xlsx“, in Ihrem angegebenen Dokumentverzeichnis haben.
## Namespaces importieren
Nachdem Sie nun die Voraussetzungen geschaffen haben, beginnen wir mit dem Import der erforderlichen Namespaces. Dadurch wird sichergestellt, dass Ihre Anwendung die von GroupDocs.Viewer für .NET bereitgestellten Funktionen erkennt und nutzen kann.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Einrichten des Dokumentenverzeichnisses
```csharp
string outputDirectory = "Your Document Directory";
```
Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den Pfad zu dem Verzeichnis, in dem sich Ihr Zieldokument befindet.
## 2. Initialisierung des Viewers
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
In diesem Schritt erstellen wir eine Instanz der Viewer-Klasse und geben den Pfad zu Ihrer Excel-Datei an.
## 3. Konfigurieren der Optionen zum Anzeigen von Informationen
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Hier konfigurieren wir ViewInfoOptions zum Generieren von HTML-Ansichten und legen zusätzliche Optionen für das Rendern von Tabellenkalkulationen fest.
## 4. Abrufen von Ansichtsinformationen
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Nutzen Sie die Viewer-Instanz, um Ansichtsinformationen basierend auf den konfigurierten Optionen abzurufen.
## 5. Arbeitsblattnamen anzeigen
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Durchlaufen Sie die abgerufenen Seiten und geben Sie den Namen jedes Arbeitsblatts auf der Konsole aus.
## Abschluss
Glückwunsch! Sie haben den Prozess des Abrufens von Arbeitsblattnamen mit GroupDocs.Viewer für .NET erfolgreich durchlaufen. Dies eröffnet unzählige Möglichkeiten zur Verbesserung der Dokumentanzeigefunktionen in Ihren Anwendungen.
## FAQs
### Kann ich GroupDocs.Viewer für .NET mit anderen Dokumentformaten verwenden?
Absolut! GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office und mehr.
### Gibt es eine kostenlose Testversion?
 Ja, Sie können GroupDocs.Viewer für .NET mit unserem erkunden[Kostenlose Testphase](https://releases.groupdocs.com/).
### Wo finde ich zusätzliche Unterstützung?
 Gehen Sie zum[GroupDocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9) für Community-Unterstützung und Diskussionen.
### Kann ich eine temporäre Lizenz erhalten?
 Sicherlich! Besuchen[dieser Link](https://purchase.groupdocs.com/temporary-license/) um Ihren vorläufigen Führerschein zu erhalten.
### Sind detaillierte Dokumentationsressourcen verfügbar?
 Absolut! Besuche die[offizielle Dokumentation](https://tutorials.groupdocs.com/viewer/net/) für ausführliche Informationen und Anleitungen.