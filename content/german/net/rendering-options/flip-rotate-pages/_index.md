---
title: Seiten spiegeln und drehen
linktitle: Seiten spiegeln und drehen
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie Groupdocs.Viewer für .NET in Ihre Anwendungen integrieren, um ein nahtloses Rendern, Spiegeln und Drehen von Dokumenten zu ermöglichen.
weight: 12
url: /de/net/rendering-options/flip-rotate-pages/
---

# Seiten spiegeln und drehen

## Einführung
In diesem Tutorial befassen wir uns mit den Funktionen von Groupdocs.Viewer für .NET und konzentrieren uns dabei insbesondere auf das Umblättern und Drehen von Seiten. Groupdocs.Viewer für .NET ist ein leistungsstarkes Tool zum Rendern von Dokumenten in verschiedenen Formaten in .NET-Anwendungen. Unabhängig davon, ob Sie ein Dokumentenverwaltungssystem entwickeln oder Funktionen zur Dokumentenanzeige in Ihre Software integrieren müssen, bietet Groupdocs.Viewer für .NET eine effiziente Lösung.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### Groupdocs.Viewer für .NET installieren
 Um Groupdocs.Viewer für .NET verwenden zu können, müssen Sie das Paket über den NuGet Package Manager installieren. Eine ausführliche Installationsanleitung finden Sie im[Dokumentation](https://tutorials.groupdocs.com/viewer/net/).

## Namespaces importieren
Stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importiert haben, um Groupdocs.Viewer für .NET effektiv nutzen zu können.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns den Vorgang des Umdrehens und Drehens von Seiten mithilfe von Groupdocs.Viewer für .NET in einfache Schritte unterteilen:
## Schritt 1: Ausgabeverzeichnis und Dateipfad festlegen
Definieren Sie das Verzeichnis, in dem die Ausgabedatei gespeichert werden soll, und geben Sie den Pfad der Ausgabedatei an.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Schritt 2: Viewer-Objekt initialisieren
Erstellen Sie eine Instanz der Viewer-Klasse, indem Sie den Pfad zu dem Dokument übergeben, das Sie anzeigen möchten.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Schritt 3: Ansichtsoptionen konfigurieren
Richten Sie die Ansichtsoptionen ein, z. B. die Angabe des Ausgabedateiformats und etwaiger zusätzlicher Einstellungen wie der Seitendrehung.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Schritt 4: Dokument rendern
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die Ansichtsoptionen.
```csharp
viewer.View(viewOptions);
```
## Schritt 5: Erfolgsmeldung anzeigen
Informieren Sie den Benutzer darüber, dass das Dokument erfolgreich gerendert wurde, und geben Sie das Ausgabeverzeichnis zur Überprüfung an.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Zusammenfassend bietet Groupdocs.Viewer für .NET leistungsstarke Funktionen zum Rendern von Dokumenten, einschließlich Umdrehen und Drehen von Seiten. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie diese Funktionen nahtlos in Ihre .NET-Anwendungen integrieren und so die Anzeigeerfahrung von Dokumenten für Ihre Benutzer verbessern.
## FAQs
### Ist Groupdocs.Viewer für .NET mit allen Dokumentformaten kompatibel?
Ja, Groupdocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter DOCX, PDF, PPTX und mehr.
### Kann ich die Anzeigeoptionen über das Umblättern und Drehen von Seiten hinaus anpassen?
Absolut, Groupdocs.Viewer für .NET bietet verschiedene Anpassungsoptionen für die Anzeige von Dokumenten, sodass Sie das Erlebnis an Ihre Anforderungen anpassen können.
### Gibt es eine kostenlose Testversion für Groupdocs.Viewer für .NET?
 Ja, Sie können eine kostenlose Testversion von Groupdocs.Viewer für .NET nutzen, indem Sie die besuchen[Webseite](https://releases.groupdocs.com/).
### Wie erhalte ich Unterstützung für Groupdocs.Viewer für .NET?
 Sie können Hilfe suchen und sich über die Community engagieren[Groupdocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9).
### Wo kann ich eine temporäre Lizenz für Groupdocs.Viewer für .NET erhalten?
 Temporäre Lizenzen für Groupdocs.Viewer für .NET können bei bezogen werden[Kaufseite](https://purchase.groupdocs.com/temporary-license/).