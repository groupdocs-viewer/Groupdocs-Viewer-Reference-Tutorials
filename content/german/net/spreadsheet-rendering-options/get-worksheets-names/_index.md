---
"description": "Entdecken Sie die Vorteile von GroupDocs.Viewer für .NET – integrieren Sie die Dokumentanzeige nahtlos in Ihre Anwendungen. Testen Sie jetzt die kostenlose Testversion!"
"linktitle": "Arbeitsblattnamen abrufen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Arbeitsblattnamen abrufen"
"url": "/de/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# Arbeitsblattnamen abrufen

## Einführung
Willkommen in der faszinierenden Welt von GroupDocs.Viewer für .NET! Wenn Sie Entwickler oder Enthusiast sind und leistungsstarke Dokumentanzeigefunktionen in Ihren .NET-Anwendungen erkunden möchten, erwartet Sie hier ein echter Leckerbissen. In dieser umfassenden Anleitung vertiefen wir uns in die Feinheiten des Abrufs von Arbeitsblattnamen mit GroupDocs.Viewer. Also, schnallen Sie sich an und begeben Sie sich auf diese spannende Reise!
## Voraussetzungen
Bevor wir uns in die Programmiermagie stürzen, stellen wir sicher, dass Sie alles eingerichtet haben:
1. Installieren Sie GroupDocs.Viewer für .NET: Gehen Sie zum [Download-Link](https://releases.groupdocs.com/viewer/net/) um die neueste Version von GroupDocs.Viewer für .NET zu erhalten. Folgen Sie den Installationsanweisungen, um es nahtlos in Ihre Entwicklungsumgebung zu integrieren.
2. Bereiten Sie Ihr Dokument vor: Stellen Sie sicher, dass Sie in Ihrem vorgesehenen Dokumentverzeichnis ein Zieldokument haben, beispielsweise eine Excel-Datei mit dem Namen „file.xlsx“.
## Namespaces importieren
Nachdem Sie die Voraussetzungen geschaffen haben, können wir mit dem Importieren der erforderlichen Namespaces beginnen. Dadurch wird sichergestellt, dass Ihre Anwendung die von GroupDocs.Viewer für .NET bereitgestellten Funktionen erkennt und nutzen kann.
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
Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den Pfad zum Verzeichnis, in dem sich Ihr Zieldokument befindet.
## 2. Initialisieren des Viewers
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
In diesem Schritt erstellen wir eine Instanz der Viewer-Klasse und geben den Pfad zu Ihrer Excel-Datei an.
## 3. Konfigurieren der Anzeigeinformationsoptionen
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Hier konfigurieren wir die ViewInfoOptions, um HTML-Ansichten zu generieren und legen zusätzliche Optionen für die Tabellenkalkulationsdarstellung fest.
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
Durchlaufen Sie die abgerufenen Seiten und drucken Sie den Namen jedes Arbeitsblatts auf der Konsole.
## Abschluss
Herzlichen Glückwunsch! Sie haben den Prozess zum Abrufen von Arbeitsblattnamen mit GroupDocs.Viewer für .NET erfolgreich abgeschlossen. Dies eröffnet Ihnen unzählige Möglichkeiten zur Verbesserung der Dokumentanzeigefunktionen in Ihren Anwendungen.
## FAQs
### Kann ich GroupDocs.Viewer für .NET mit anderen Dokumentformaten verwenden?
Absolut! GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office und mehr.
### Gibt es eine kostenlose Testversion?
Ja, Sie können GroupDocs.Viewer für .NET mit unserem [kostenlose Testversion](https://releases.groupdocs.com/).
### Wo finde ich zusätzliche Unterstützung?
Gehen Sie zum [GroupDocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9) für Community-Support und Diskussionen.
### Kann ich eine vorläufige Lizenz erhalten?
Sicher! Besuchen Sie [dieser Link](https://purchase.groupdocs.com/temporary-license/) um Ihren vorläufigen Führerschein zu erhalten.
### Stehen ausführliche Dokumentationsressourcen zur Verfügung?
Absolut! Schauen Sie sich die [offizielle Dokumentation](https://tutorials.groupdocs.com/viewer/net/) für ausführliche Informationen und Anleitungen.