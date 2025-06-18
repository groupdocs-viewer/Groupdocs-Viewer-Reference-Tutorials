---
"description": "Entdecken Sie, wie Sie mit GroupDocs.Viewer für .NET mühelos nachverfolgte Änderungen in Dokumenten darstellen. Steigern Sie die Effizienz Ihres Dokumentenmanagements."
"linktitle": "Nachverfolgte Änderungen rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Nachverfolgte Änderungen rendern"
"url": "/de/net/rendering-word-processing-documents/render-tracked-changes/"
"weight": 10
---

# Nachverfolgte Änderungen rendern

## Einführung
Im digitalen Zeitalter ist die effiziente Verwaltung und Anzeige von Dokumenten für Unternehmen und Privatpersonen gleichermaßen entscheidend. Mit dem Aufkommen fortschrittlicher Technologien haben Lösungen wie GroupDocs.Viewer für .NET die Interaktion mit verschiedenen Dokumentformaten, darunter Word-Dokumente, PDFs und mehr, revolutioniert. In diesem umfassenden Leitfaden erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET nachverfolgte Änderungen in Ihren Dokumenten nahtlos darstellen können.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET Installation: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von der [Webseite](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Stellen Sie sicher, dass das .NET Framework auf Ihrem System installiert ist.
3. Dokumentenverzeichnis: Bereiten Sie ein Verzeichnis vor, in dem Ihre Dokumente gespeichert werden.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihr Projekt. Diese Namespaces sind für die effektive Nutzung der GroupDocs.Viewer-Funktionen unerlässlich.
## Schritte:
1. Öffnen Sie Ihre IDE: Starten Sie Ihre bevorzugte integrierte Entwicklungsumgebung (IDE), beispielsweise Visual Studio.
2. Erstellen oder öffnen Sie Ihr Projekt: Starten Sie ein neues Projekt oder öffnen Sie ein vorhandenes, in dem Sie GroupDocs.Viewer verwenden möchten.
3. Namespaces importieren: Fügen Sie in Ihrer Projektdatei oder Codedatei die folgenden Namespaces hinzu:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen, um Sie durch die Darstellung nachverfolgter Änderungen mit GroupDocs.Viewer für .NET zu führen.
## Schritt 1: Ausgabeverzeichnis festlegen
Definieren Sie zunächst das Verzeichnis, in dem die gerenderte Ausgabe gespeichert werden soll.
```csharp
string outputDirectory = "Your Document Directory";
```
Ersetzen `"Your Document Directory"` mit dem Pfad zu Ihrem gewünschten Verzeichnis.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
Geben Sie das Format für die Seitendateipfade an. Dieses Format bestimmt, wie die gerenderten Seiten benannt und gespeichert werden.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Hier, `"page_{0}.html"` gibt an, dass die Seiten benannt werden als `page_1.html`, `page_2.html`, und so weiter.
## Schritt 3: Viewer-Objekt initialisieren
Initialisieren Sie ein `Viewer` Objekt, indem Sie den Pfad des Dokuments als Argument übergeben.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // Der Code wird im nächsten Schritt fortgesetzt ...
}
```
Stellen Sie sicher, dass Sie `TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` mit dem Pfad zu Ihrem Dokument.
## Schritt 4: HTML-Ansichtsoptionen konfigurieren
Konfigurieren Sie HTML-Ansichtsoptionen, um die Darstellungseinstellungen anzupassen, beispielsweise die Darstellung nachverfolgter Änderungen.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
Dieser Schritt ermöglicht die Darstellung nachverfolgter Änderungen im Ausgabe-HTML.
## Schritt 5: Dokument rendern
Rendern Sie das Dokument mit den konfigurierten Optionen.
```csharp
viewer.View(options);
```
Dieser Befehl startet den Rendering-Prozess basierend auf den bereitgestellten Einstellungen.
## Schritt 6: Ausgabeverzeichnis anzeigen
Informieren Sie den Benutzer über den Speicherort der gerenderten Ausgabe.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Diese Nachricht informiert den Benutzer über das erfolgreiche Rendern und darüber, wo die Ausgabedateien zu finden sind.

## Abschluss
Zusammenfassend lässt sich sagen, dass GroupDocs.Viewer für .NET eine leistungsstarke Lösung für die mühelose Darstellung nachverfolgter Änderungen in Dokumenten bietet. Mit der Schritt-für-Schritt-Anleitung in diesem Artikel können Sie diese Funktionalität nahtlos in Ihre .NET-Anwendungen integrieren und so die Effizienz Ihres Dokumentenmanagements steigern.
## Häufig gestellte Fragen
### Kann ich mit GroupDocs.Viewer für .NET nachverfolgte Änderungen in verschiedenen Dokumentformaten rendern?
Ja, GroupDocs.Viewer unterstützt die Darstellung nachverfolgter Änderungen in mehreren Formaten, darunter DOCX, PDF und mehr.
### Ist GroupDocs.Viewer für .NET mit allen .NET Framework-Versionen kompatibel?
Ja, GroupDocs.Viewer für .NET ist mit verschiedenen Versionen des .NET Frameworks kompatibel und gewährleistet so umfassende Kompatibilität.
### Bietet GroupDocs.Viewer eine kostenlose Testversion zu Testzwecken an?
Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer nutzen, um die Funktionen kennenzulernen, bevor Sie eine Kaufentscheidung treffen.
### Kann ich die Rendering-Einstellungen an bestimmte Anforderungen anpassen?
Auf jeden Fall, GroupDocs.Viewer bietet umfangreiche Anpassungsoptionen, mit denen Sie den Rendering-Prozess an Ihre Bedürfnisse anpassen können.
### Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße oder Fragen zu GroupDocs.Viewer habe?
Für Support und Community-Unterstützung können Sie das GroupDocs.Viewer-Forum unter besuchen. [dieser Link](https://forum.groupdocs.com/c/viewer/9).