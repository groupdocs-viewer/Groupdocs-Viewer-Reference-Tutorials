---
title: Renderspezifisches Projektzeitintervall (MS Project)
linktitle: Renderspezifisches Projektzeitintervall (MS Project)
second_title: GroupDocs.Viewer .NET-API
description: Integrieren Sie GroupDocs.Viewer für .NET nahtlos in Ihre Anwendungen für eine effiziente Dokumentenanzeige. Steigern Sie die Produktivität mit vielseitigen Rendering-Funktionen.
type: docs
weight: 12
url: /de/net/rendering-ms-project-documents/render-project-time-interval-ms-project/
---
## Einführung
Im Bereich der Softwareentwicklung kommt es auf die effiziente Handhabung und Darstellung verschiedener Dokumentformate an. Ganz gleich, ob es um die Anzeige oder Bearbeitung von Dokumenten geht: Mit den richtigen Tools können Sie die Produktivität erheblich steigern und Prozesse optimieren. GroupDocs.Viewer für .NET zeichnet sich durch eine vielseitige Lösung aus, die Entwicklern die Möglichkeit bietet, Dokumentanzeigefunktionen nahtlos in ihre .NET-Anwendungen zu integrieren.
## Voraussetzungen
Bevor Sie sich mit der Integration von GroupDocs.Viewer für .NET befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Vertrautheit mit .NET Framework
Stellen Sie sicher, dass Sie über grundlegende Kenntnisse des .NET-Frameworks verfügen, einschließlich der Programmiersprache C# und der Visual Studio-IDE.
### 2. Installation von GroupDocs.Viewer für .NET
 Laden Sie GroupDocs.Viewer für .NET von herunter und installieren Sie es[Download-Link](https://releases.groupdocs.com/viewer/net/). Befolgen Sie die bereitgestellten Installationsanweisungen, um die Bibliothek in Ihrer Entwicklungsumgebung einzurichten.
### 3. Gültige Lizenz oder temporäre Lizenz
 Erwerben Sie eine gültige Lizenz von[Gruppendokumente](https://purchase.groupdocs.com/buy) oder erhalten Sie eine temporäre Lizenz von[Hier](https://purchase.groupdocs.com/temporary-license/) um die volle Funktionalität von GroupDocs.Viewer für .NET zu nutzen.
### 4. Beispieldokument
Halten Sie ein Beispieldokument, beispielsweise eine MS Project-Datei, zum Testen der Rendering-Funktionalität bereit.

## Namespaces importieren
Integrieren Sie die erforderlichen Namespaces in Ihr Projekt, um auf die von GroupDocs.Viewer für .NET bereitgestellten Funktionen zuzugreifen.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Lassen Sie uns das Beispiel des Renderns eines bestimmten Projektzeitintervalls aus einer MS Project-Datei in mehrere Schritte unterteilen:
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Geben Sie das Verzeichnis an, in dem die gerenderten HTML-Seiten gespeichert werden.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Legen Sie das Format für den Dateipfad jeder gerenderten HTML-Seite fest.
## Schritt 3: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Erstellen Sie eine Instanz der Viewer-Klasse und übergeben Sie den Pfad zur Beispiel-MS-Project-Datei.
## Schritt 4: Konfigurieren Sie die HTML-Ansichtsoptionen
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Konfigurieren Sie HTML-Ansichtsoptionen für das Rendering und geben Sie das Format für eingebettete Ressourcen an.
## Schritt 5: Informationen zur Projektmanagementansicht abrufen
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
Rufen Sie Informationen zur Projektmanagementansicht ab, um das Start- und Enddatum des Projekts zu bestimmen.
## Schritt 6: Legen Sie Start- und Enddatum fest
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
Legen Sie das Start- und Enddatum für das zu rendernde Projektintervall fest.
## Schritt 7: Dokument rendern
```csharp
viewer.View(options);
```
Starten Sie den Rendervorgang mit den angegebenen Optionen.
## Schritt 8: Ausgabeverzeichnis anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Benachrichtigen Sie den Benutzer über das erfolgreiche Rendern und zeigen Sie das Verzeichnis an, in dem die Ausgabe gespeichert ist.

## Abschluss
Durch die Integration von GroupDocs.Viewer für .NET in Ihre Projekte können Sie Aufgaben zur Dokumentenanzeige effizient erledigen und so die Benutzererfahrung und Produktivität verbessern. Wenn Sie der bereitgestellten Schritt-für-Schritt-Anleitung folgen, können Sie Funktionen zur Dokumentwiedergabe nahtlos in Ihre .NET-Anwendungen integrieren.
## FAQs
### Ist GroupDocs.Viewer für .NET mit allen Dokumentformaten kompatibel?
GroupDocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter Microsoft Office, PDF, CAD und mehr.
### Kann ich das Erscheinungsbild gerenderter Dokumente anpassen?
Ja, Sie können verschiedene Aspekte des Rendering-Prozesses anpassen, z. B. Seitenlayout, Wasserzeichen und Seitenrotation.
### Ist GroupDocs.Viewer für .NET für Webanwendungen geeignet?
Auf jeden Fall kann GroupDocs.Viewer für .NET nahtlos in Webanwendungen integriert werden, um Funktionen zur Dokumentenanzeige bereitzustellen.
### Bietet GroupDocs.Viewer für .NET Unterstützung für mobile Plattformen?
Ja, GroupDocs.Viewer für .NET unterstützt mobile Plattformen und ermöglicht Ihnen die Erstellung von Anwendungen mit reaktionsschnellen Funktionen zur Dokumentenanzeige.
### Gibt es ein Community-Forum, in dem ich Hilfe zu GroupDocs.Viewer für .NET suchen kann?
 Ja, Sie können die besuchen[GroupDocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9) um Fragen zu stellen, Ideen auszutauschen und mit anderen Benutzern und Entwicklern zu interagieren.