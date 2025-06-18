---
"description": "Erfahren Sie, wie Sie CHM-Dateien in .NET mit GroupDocs.Viewer rendern. Konvertieren Sie CHM mühelos in die Formate HTML, JPG, PNG und PDF."
"linktitle": "CHM-Dateien rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CHM-Dateien rendern"
"url": "/de/net/rendering-web-documents/render-chm/"
"weight": 10
---

# CHM-Dateien rendern

## Einführung
In diesem Tutorial erfahren Sie, wie Sie CHM-Dateien (Compiled HTML Help) mit GroupDocs.Viewer für .NET rendern. GroupDocs.Viewer für .NET ist eine leistungsstarke API zur Dokumentdarstellung, mit der Entwickler über 170 Dokumenttypen in ihren .NET-Anwendungen anzeigen können, ohne externe Software installieren zu müssen.

## Voraussetzungen

Bevor wir mit dem Rendern von CHM-Dateien beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

### Installieren von GroupDocs.Viewer für .NET

Um zu beginnen, müssen Sie GroupDocs.Viewer für .NET installieren. Sie können die Bibliothek von der [GroupDocs-Website](https://releases.groupdocs.com/viewer/net/) oder installieren Sie es über den NuGet-Paketmanager, indem Sie den folgenden Befehl in der Paketmanager-Konsole ausführen:

```bash
Install-Package GroupDocs.Viewer
```

## Namespaces importieren

Stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Rendering-Prozess in mehrere Schritte unterteilen:

## Schritt 1: Ausgabeverzeichnis definieren

Definieren Sie das Verzeichnis, in dem die gerenderten Dateien gespeichert werden sollen:

```csharp
string outputDirectory = "Your Document Directory";
```

## Schritt 2: In HTML rendern

Um CHM-Dateien in HTML zu rendern, verwenden Sie den folgenden Codeausschnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Auf „true“ setzen, um den gesamten CHM-Inhalt in eine einzelne Seite zu konvertieren

    viewer.View(options); // Alle Seiten konvertieren
}
```

## Schritt 3: In JPG rendern

Um CHM-Dateien in JPG-Bilder umzuwandeln, verwenden Sie den folgenden Codeausschnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konvertieren Sie nur die Seiten 1, 2, 3
}
```

## Schritt 4: In PNG rendern

Um CHM-Dateien in PNG-Bilder umzuwandeln, verwenden Sie den folgenden Codeausschnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konvertieren Sie nur die Seiten 1, 2, 3
}
```

## Schritt 5: In PDF rendern

Um CHM-Dateien in ein PDF-Dokument umzuwandeln, verwenden Sie den folgenden Codeausschnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Alle Seiten konvertieren
}
```

## Schritt 6: Ausgabe prüfen

Sobald der Rendervorgang abgeschlossen ist, überprüfen Sie das angegebene Ausgabeverzeichnis auf die gerenderten Dateien:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss

Das Rendern von CHM-Dateien mit GroupDocs.Viewer für .NET ist unkompliziert. Mit den in diesem Tutorial beschriebenen Schritten können Sie CHM-Dokumente in Ihren .NET-Anwendungen effizient in verschiedene Formate wie HTML, Bilder (JPG, PNG) und PDF konvertieren.

## Häufig gestellte Fragen

### F1: Kann GroupDocs.Viewer außer CHM auch andere Dokumentformate rendern?

A1: Ja, GroupDocs.Viewer unterstützt die Darstellung von über 170 Dokumentformaten, darunter PDF, DOCX, XLSX, PPTX und mehr.

### F2: Ist GroupDocs.Viewer mit .NET Core kompatibel?

A2: Ja, GroupDocs.Viewer unterstützt neben dem traditionellen .NET Framework auch .NET Core.

### F3: Kann ich die Rendering-Optionen für verschiedene Ausgabeformate anpassen?

A3: Ja, GroupDocs.Viewer bietet verschiedene Optionen zum Anpassen des Rendering-Prozesses, z. B. das Festlegen von Seitenzahlen, das Einstellen der Bildqualität und das Konfigurieren von Ausgabepfaden.

### F4: Benötigt GroupDocs.Viewer externe Abhängigkeiten zum Rendern von Dokumenten?

A4: Nein, GroupDocs.Viewer ist eine eigenständige Bibliothek und erfordert keine externen Abhängigkeiten oder Softwareinstallationen von Drittanbietern.

### F5: Gibt es eine kostenlose Testversion für GroupDocs.Viewer?

A5: Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer nutzen, indem Sie die [Webseite](https://releases.groupdocs.com/).