---
title: Zeitüberschreitung beim Laden von Ressourcen festlegen (erweitert)
linktitle: Zeitüberschreitung beim Laden von Ressourcen festlegen (erweitert)
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie Zeitüberschreitungen beim Laden von Ressourcen in GroupDocs.Viewer für .NET effizient konfigurieren. Präzise und stabile Wiedergabe von Masterdokumenten.
type: docs
weight: 13
url: /de/net/advanced-loading/set-resource-loading-timeout/
---
## Einführung
Im Bereich der .NET-Entwicklung bietet GroupDocs.Viewer ein leistungsstarkes Toolset zum präzisen und effizienten Rendern von Dokumenten und Bildern. Um seine Fähigkeiten nutzen zu können, muss man seine Feinheiten verstehen, einschließlich der Festlegung von Timeouts für das Laden von Ressourcen. In diesem Tutorial befassen wir uns mit dem Prozess der Konfiguration von Zeitüberschreitungen beim Laden von Ressourcen in GroupDocs.Viewer für .NET.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Grundkenntnisse der .NET-Entwicklung: Vertrautheit mit der C#-Programmierung und den Grundlagen des .NET Frameworks ist unerlässlich.
2.  Installation von GroupDocs.Viewer für .NET: Laden Sie die GroupDocs.Viewer für .NET-Bibliothek von herunter und installieren Sie sie[Download-Seite](https://releases.groupdocs.com/viewer/net/).
3. Integrierte Entwicklungsumgebung (IDE): Installieren Sie eine IDE wie Visual Studio auf Ihrem System.

## Namespaces importieren
Bevor Sie mit dem Codierungsprozess beginnen, importieren Sie die erforderlichen Namespaces:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Schritt 1: Ausgabeverzeichnis definieren
Definieren Sie zunächst das Verzeichnis, in dem die gerenderten Dokumente gespeichert werden:
```csharp
string outputDirectory = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"`mit dem Pfad, in dem Sie die gerenderten Dokumente speichern möchten.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
Definieren Sie das Format für die Dateipfade einzelner Seiten:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Dieses Format generiert Dateinamen wie`page_1.html`, `page_2.html`usw. im angegebenen Ausgabeverzeichnis.
## Schritt 3: Ladeoptionen konfigurieren
Konfigurieren Sie die Ladeoptionen, einschließlich des Zeitlimits für das Laden der Ressource:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
In diesem Beispiel ist für das Laden der Ressource ein Timeout von 5 Sekunden eingestellt.
## Schritt 4: Viewer-Objekt initialisieren
 Initialisieren Sie die`Viewer` Objekt mit dem zu rendernden Dokument und den definierten Ladeoptionen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Ersetzen`TestFiles.WITH_EXTERNAL_IMAGE_DOC` mit dem Pfad zu dem Dokument, das Sie rendern möchten.
## Schritt 5: Konfigurieren Sie die HTML-Ansichtsoptionen
Konfigurieren Sie HTML-Ansichtsoptionen für eingebettete Ressourcen:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Diese Konfiguration stellt sicher, dass eingebettete Ressourcen wie Bilder im gerenderten HTML enthalten sind.
## Schritt 6: Dokument rendern
Rendern Sie das Dokument mit den konfigurierten Optionen:
```csharp
viewer.View(options);
```
Dieser Schritt leitet den Rendervorgang ein.
## Schritt 7: Ausgabeverzeichnis anzeigen
Zeigt eine Meldung an, die das erfolgreiche Rendern und den Speicherort des Ausgabeverzeichnisses angibt:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Die Beherrschung der Zeitüberschreitungen beim Laden von Ressourcen in GroupDocs.Viewer für .NET ist entscheidend für die Gewährleistung reibungsloser Dokument-Rendering-Prozesse. Durch das Befolgen dieses Tutorials haben Sie Einblicke in die effektive Konfiguration von Zeitüberschreitungen gewonnen und so Ihre Kenntnisse in der .NET-Entwicklung verbessert.
## FAQs
### Welche Bedeutung hat das Festlegen von Zeitüberschreitungen beim Laden von Ressourcen?
Durch das Festlegen von Zeitüberschreitungen beim Laden von Ressourcen wird sichergestellt, dass Rendering-Prozesse nicht auf unbestimmte Zeit hängen bleiben, wodurch die Stabilität der Anwendung verbessert wird.
### Können Zeitüberschreitungen beim Laden von Ressourcen je nach Dokumenttyp angepasst werden?
Ja, Zeitüberschreitungen beim Laden von Ressourcen können je nach Komplexität und Größe der gerenderten Dokumente angepasst werden.
### Gibt es Auswirkungen auf die Leistung, wenn kürzere Zeitüberschreitungen festgelegt werden?
Kürzere Zeitüberschreitungen können zu einer unvollständigen Darstellung komplexer Dokumente führen, wenn Ressourcen nicht innerhalb der angegebenen Dauer geladen werden können.
### Eignet sich GroupDocs.Viewer zum Rendern verschiedener Dokumentformate?
Ja, GroupDocs.Viewer unterstützt das Rendern einer Vielzahl von Dokumentformaten, darunter PDF, DOCX, XLSX und mehr.
### Können Zeitüberschreitungen beim Laden von Ressourcen deaktiviert werden?
Obwohl dies nicht empfohlen wird, können Zeitüberschreitungen beim Laden von Ressourcen je nach spezifischen Anforderungen auf einen hohen Wert eingestellt oder ganz deaktiviert werden.