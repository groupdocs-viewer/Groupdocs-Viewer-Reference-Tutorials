---
title: Dokument in PDF rendern
linktitle: Dokument in PDF rendern
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie Dokumente mit GroupDocs.Viewer für .NET in PDF rendern. Schritt-für-Schritt-Anleitung mit Voraussetzungen und FAQs enthalten.
weight: 10
url: /de/net/rendering-documents-pdf/render-to-pdf/
---

# Dokument in PDF rendern

## Einführung
GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool zum Rendern verschiedener Dokumentformate in PDF. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess.
## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  GroupDocs.Viewer für .NET-Bibliothek: Sie können die Bibliothek herunterladen von[Hier](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Stellen Sie sicher, dass auf Ihrem Computer die entsprechende Version von .NET Framework installiert ist.
3. Dokumentdateien: Bereiten Sie die Dokumentdateien vor, die Sie rendern möchten. Zu den unterstützten Formaten gehören DOCX, PDF, PPTX, XLSX und mehr.

## Namensräume importieren:
Stellen Sie vor dem Eintauchen in den Code sicher, dass Sie die erforderlichen Namespaces importieren:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Rendervorgang in mehrere Schritte unterteilen:
## Schritt 1: Ausgabeverzeichnis und Dateipfad definieren
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
 Stellen Sie sicher, dass Sie es ersetzen`"Your Document Directory"` mit dem Verzeichnis, in dem Sie die gerenderte PDF-Datei speichern möchten.
## Schritt 2: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Ihr Code hier
}
```
 Ersetzen`TestFiles.SAMPLE_DOCX` mit dem Pfad zu Ihrer Dokumentdatei.
## Schritt 3: PDF-Ansichtsoptionen festlegen
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Schritt 4: Dokument in PDF rendern
```csharp
viewer.View(options);
```
## Schritt 5: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nachdem Sie diese Schritte ausgeführt haben, haben Sie Ihr Dokument mit GroupDocs.Viewer für .NET erfolgreich in PDF gerendert.

## Abschluss
Das Rendern von Dokumenten in PDF ist eine häufige Anforderung in verschiedenen Anwendungen. Mit GroupDocs.Viewer für .NET wird dieser Prozess nahtlos und effizient, sodass Sie eine Vielzahl von Dokumentformaten problemlos verarbeiten können.
## FAQs
### Kann ich andere Dokumente als DOCX in PDF rendern?
Ja, GroupDocs.Viewer für .NET unterstützt verschiedene Formate wie PDF, PPTX, XLSX und mehr.
### Gibt es eine Testversion?
 Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.groupdocs.com/).
### Wie kann ich Unterstützung erhalten, wenn ich auf Probleme stoße?
 Sie können das GroupDocs.Viewer-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9) zur Hilfe.
### Benötige ich zu Testzwecken eine temporäre Lizenz?
 Ja, Sie können eine temporäre Lizenz erhalten von[Hier](https://purchase.groupdocs.com/temporary-license/).
### Wo kann ich eine Volllizenz erwerben?
 Sie können eine Lizenz erwerben bei[Hier](https://purchase.groupdocs.com/buy).