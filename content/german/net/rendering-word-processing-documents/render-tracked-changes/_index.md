---
title: Verfolgte Änderungen rendern
linktitle: Verfolgte Änderungen rendern
second_title: GroupDocs.Viewer .NET-API
description: Entdecken Sie, wie Sie mit GroupDocs.Viewer für .NET nachverfolgte Änderungen in Dokumenten mühelos rendern können. Steigern Sie die Effizienz Ihres Dokumentenmanagements.
weight: 10
url: /de/net/rendering-word-processing-documents/render-tracked-changes/
---

# Verfolgte Änderungen rendern

## Einführung
Im heutigen digitalen Zeitalter ist die effiziente Verwaltung und Anzeige von Dokumenten für Unternehmen und Privatpersonen gleichermaßen von entscheidender Bedeutung. Mit dem Aufkommen fortschrittlicher Technologien haben Lösungen wie GroupDocs.Viewer für .NET die Art und Weise revolutioniert, wie wir mit verschiedenen Dokumentformaten interagieren, darunter Word-Dokumente, PDFs und mehr. In diesem umfassenden Leitfaden erfahren Sie, wie Sie GroupDocs.Viewer für .NET nutzen können, um nachverfolgte Änderungen in Ihren Dokumenten nahtlos darzustellen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET-Installation: Laden Sie GroupDocs.Viewer für .NET von herunter und installieren Sie es[Webseite](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Stellen Sie sicher, dass .NET Framework auf Ihrem System installiert ist.
3. Dokumentenverzeichnis: Bereiten Sie ein Verzeichnis vor, in dem Ihre Dokumente gespeichert werden.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihr Projekt. Diese Namespaces sind für die effektive Nutzung der GroupDocs.Viewer-Funktionen unerlässlich.
## Schritte:
1. Öffnen Sie Ihre IDE: Starten Sie Ihre bevorzugte integrierte Entwicklungsumgebung (IDE), z. B. Visual Studio.
2. Erstellen oder öffnen Sie Ihr Projekt: Starten Sie ein neues Projekt oder öffnen Sie ein bestehendes, in dem Sie GroupDocs.Viewer verwenden möchten.
3. Namespaces importieren: Fügen Sie in Ihrer Projektdatei oder Codedatei die folgenden Namespaces hinzu:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen, um Sie durch das Rendern nachverfolgter Änderungen mit GroupDocs.Viewer für .NET zu führen.
## Schritt 1: Ausgabeverzeichnis festlegen
Definieren Sie zunächst das Verzeichnis, in dem die gerenderte Ausgabe gespeichert werden soll.
```csharp
string outputDirectory = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"`mit dem Pfad zu Ihrem gewünschten Verzeichnis.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
Geben Sie das Format für die Auslagerungsdateipfade an. Dieses Format bestimmt, wie die gerenderten Seiten benannt und gespeichert werden.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Hier,`"page_{0}.html"` gibt an, dass die Seiten benannt werden als`page_1.html`, `page_2.html`, und so weiter.
## Schritt 3: Viewer-Objekt initialisieren
 Initialisieren Sie a`Viewer` Objekt durch Übergabe des Pfads des Dokuments als Argument.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // Code wird im nächsten Schritt fortgesetzt...
}
```
 Stellen Sie sicher, dass Sie es ersetzen`TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` mit dem Pfad zu Ihrem Dokument.
## Schritt 4: Konfigurieren Sie die HTML-Ansichtsoptionen
Konfigurieren Sie HTML-Ansichtsoptionen, um die Rendering-Einstellungen anzupassen, z. B. das Rendern nachverfolgter Änderungen.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
Dieser Schritt ermöglicht das Rendern nachverfolgter Änderungen im Ausgabe-HTML.
## Schritt 5: Dokument rendern
Rendern Sie das Dokument mit den konfigurierten Optionen.
```csharp
viewer.View(options);
```
Dieser Befehl initiiert den Rendervorgang basierend auf den bereitgestellten Einstellungen.
## Schritt 6: Ausgabeverzeichnis anzeigen
Informieren Sie den Benutzer über den Speicherort der gerenderten Ausgabe.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Diese Meldung informiert den Benutzer über das erfolgreiche Rendern und darüber, wo sich die Ausgabedateien befinden.

## Abschluss
Zusammenfassend bietet GroupDocs.Viewer für .NET eine leistungsstarke Lösung zum mühelosen Rendern nachverfolgter Änderungen in Dokumenten. Wenn Sie die in diesem Artikel beschriebene Schritt-für-Schritt-Anleitung befolgen, können Sie diese Funktionalität nahtlos in Ihre .NET-Anwendungen integrieren und so die Effizienz der Dokumentenverwaltung steigern.
## FAQs
### Kann ich mit GroupDocs.Viewer für .NET nachverfolgte Änderungen in verschiedenen Dokumentformaten rendern?
Ja, GroupDocs.Viewer unterstützt das Rendern nachverfolgter Änderungen in mehreren Formaten, einschließlich DOCX, PDF und mehr.
### Ist GroupDocs.Viewer für .NET mit allen .NET Framework-Versionen kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit verschiedenen Versionen des .NET Framework kompatibel und gewährleistet so eine umfassende Kompatibilität.
### Bietet GroupDocs.Viewer eine kostenlose Testversion zu Testzwecken an?
Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer nutzen, um seine Funktionen zu erkunden, bevor Sie eine Kaufentscheidung treffen.
### Kann ich die Rendering-Einstellungen anpassen, um bestimmte Anforderungen zu erfüllen?
Auf jeden Fall bietet GroupDocs.Viewer umfangreiche Anpassungsoptionen, mit denen Sie den Rendering-Prozess an Ihre Bedürfnisse anpassen können.
### Wo kann ich Hilfe suchen, wenn ich auf Probleme stoße oder Fragen zu GroupDocs.Viewer habe?
 Für Unterstützung und Community-Unterstützung können Sie das GroupDocs.Viewer-Forum unter besuchen[dieser Link](https://forum.groupdocs.com/c/viewer/9).