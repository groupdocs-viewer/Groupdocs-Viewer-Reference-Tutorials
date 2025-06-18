---
"description": "Erfahren Sie, wie Sie Groupdocs.Viewer für .NET in Ihre Anwendungen integrieren, um Dokumente nahtlos wiederzugeben, umzudrehen und zu drehen."
"linktitle": "Seiten umdrehen und drehen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Seiten umdrehen und drehen"
"url": "/de/net/rendering-options/flip-rotate-pages/"
"weight": 12
---

# Seiten umdrehen und drehen

## Einführung
In diesem Tutorial vertiefen wir uns in die Funktionen von Groupdocs.Viewer für .NET und konzentrieren uns dabei insbesondere auf das Umblättern und Drehen von Seiten. Groupdocs.Viewer für .NET ist ein leistungsstarkes Tool zum Rendern von Dokumenten in verschiedenen Formaten innerhalb von .NET-Anwendungen. Egal, ob Sie ein Dokumentenmanagementsystem entwickeln oder Funktionen zur Dokumentanzeige in Ihre Software integrieren möchten – Groupdocs.Viewer für .NET bietet eine effiziente Lösung.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
### Installieren von Groupdocs.Viewer für .NET
Um Groupdocs.Viewer für .NET zu verwenden, müssen Sie das Paket über den NuGet-Paketmanager installieren. Detaillierte Installationsanweisungen finden Sie im [Dokumentation](https://tutorials.groupdocs.com/viewer/net/).

## Namespaces importieren
Stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importiert haben, um Groupdocs.Viewer für .NET effektiv zu nutzen.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns den Vorgang des Umblätterns und Drehens von Seiten mit Groupdocs.Viewer für .NET in einfache Schritte unterteilen:
## Schritt 1: Ausgabeverzeichnis und Dateipfad festlegen
Definieren Sie das Verzeichnis, in dem die Ausgabedatei gespeichert werden soll, und geben Sie den Ausgabedateipfad an.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Schritt 2: Viewer-Objekt initialisieren
Erstellen Sie eine Instanz der Viewer-Klasse, indem Sie den Pfad zum Dokument übergeben, das Sie anzeigen möchten.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Schritt 3: Anzeigeoptionen konfigurieren
Richten Sie die Anzeigeoptionen ein, z. B. die Angabe des Ausgabedateiformats und aller zusätzlichen Einstellungen wie die Seitendrehung.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Schritt 4: Dokument rendern
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die Anzeigeoptionen.
```csharp
viewer.View(viewOptions);
```
## Schritt 5: Erfolgsmeldung anzeigen
Informieren Sie den Benutzer, dass das Dokument erfolgreich gerendert wurde, und geben Sie das Ausgabeverzeichnis zur Überprüfung an.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Zusammenfassend lässt sich sagen, dass Groupdocs.Viewer für .NET leistungsstarke Funktionen zum Rendern von Dokumenten bietet, darunter das Umblättern und Drehen von Seiten. Mit den in diesem Tutorial beschriebenen Schritten können Sie diese Funktionen nahtlos in Ihre .NET-Anwendungen integrieren und so die Dokumentanzeige für Ihre Benutzer verbessern.
## Häufig gestellte Fragen
### Ist Groupdocs.Viewer für .NET mit allen Dokumentformaten kompatibel?
Ja, Groupdocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter DOCX, PDF, PPTX und mehr.
### Kann ich die Anzeigeoptionen über das Umblättern und Drehen von Seiten hinaus anpassen?
Auf jeden Fall, Groupdocs.Viewer für .NET bietet verschiedene Anpassungsoptionen zum Anzeigen von Dokumenten, sodass Sie das Erlebnis an Ihre Anforderungen anpassen können.
### Gibt es eine kostenlose Testversion für Groupdocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion von Groupdocs.Viewer für .NET nutzen, indem Sie die [Webseite](https://releases.groupdocs.com/).
### Wie erhalte ich Support für Groupdocs.Viewer für .NET?
Sie können Unterstützung suchen und sich mit der Community austauschen über [Groupdocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9).
### Wo kann ich eine temporäre Lizenz für Groupdocs.Viewer für .NET erhalten?
Temporäre Lizenzen für Groupdocs.Viewer für .NET erhalten Sie bei der [Kaufseite](https://purchase.groupdocs.com/temporary-license/).