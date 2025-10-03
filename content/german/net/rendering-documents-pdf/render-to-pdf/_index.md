---
"description": "Erfahren Sie, wie Sie mit GroupDocs.Viewer für .NET Dokumente in PDF umwandeln. Schritt-für-Schritt-Anleitung mit Voraussetzungen und FAQs."
"linktitle": "Dokument als PDF rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Dokument als PDF rendern"
"url": "/de/net/rendering-documents-pdf/render-to-pdf/"
"weight": 10
type: docs
---
# Dokument als PDF rendern

## Einführung
GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool zum Rendern verschiedener Dokumentformate in PDF. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess.
## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. GroupDocs.Viewer für .NET-Bibliothek: Sie können die Bibliothek herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Stellen Sie sicher, dass auf Ihrem Computer die entsprechende Version von .NET Framework installiert ist.
3. Dokumentdateien: Bereiten Sie die Dokumentdateien vor, die Sie rendern möchten. Unterstützte Formate sind unter anderem DOCX, PDF, PPTX und XLSX.

## Namespaces importieren:
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie die erforderlichen Namespaces importieren:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Rendering-Prozess in mehrere Schritte unterteilen:
## Schritt 1: Ausgabeverzeichnis und Dateipfad festlegen
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
Stellen Sie sicher, dass Sie `"Your Document Directory"` mit dem Verzeichnis, in dem Sie die gerenderte PDF-Datei speichern möchten.
## Schritt 2: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Ihr Code hier
}
```
Ersetzen `TestFiles.SAMPLE_DOCX` mit dem Pfad zu Ihrer Dokumentdatei.
## Schritt 3: PDF-Ansichtsoptionen festlegen
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Schritt 4: Dokument als PDF rendern
```csharp
viewer.View(options);
```
## Schritt 5: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nachdem Sie diese Schritte ausgeführt haben, haben Sie Ihr Dokument mit GroupDocs.Viewer für .NET erfolgreich in PDF gerendert.

## Abschluss
Das Rendern von Dokumenten im PDF-Format ist in vielen Anwendungen üblich. Mit GroupDocs.Viewer für .NET wird dieser Prozess nahtlos und effizient und ermöglicht Ihnen die problemlose Verarbeitung einer Vielzahl von Dokumentformaten.
## Häufig gestellte Fragen
### Kann ich andere Dokumente als DOCX in PDF umwandeln?
Ja, GroupDocs.Viewer für .NET unterstützt verschiedene Formate wie PDF, PPTX, XLSX und mehr.
### Gibt es eine Testversion?
Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.groupdocs.com/).
### Wie erhalte ich Unterstützung, wenn Probleme auftreten?
Sie können das GroupDocs.Viewer-Forum besuchen [Hier](https://forum.groupdocs.com/c/viewer/9) um Hilfe.
### Benötige ich zu Testzwecken eine temporäre Lizenz?
Ja, Sie können eine vorläufige Lizenz erhalten von [Hier](https://purchase.groupdocs.com/temporary-license/).
### Wo kann ich eine Volllizenz erwerben?
Sie können eine Lizenz erwerben bei [Hier](https://purchase.groupdocs.com/buy).