---
title: CHM-Dateien rendern
linktitle: CHM-Dateien rendern
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie CHM-Dateien in .NET mit GroupDocs.Viewer rendern. Konvertieren Sie CHM mühelos in die Formate HTML, JPG, PNG und PDF.
type: docs
weight: 10
url: /de/net/rendering-web-documents/render-chm/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie CHM-Dateien (Compiled HTML Help) mit GroupDocs.Viewer für .NET rendern. GroupDocs.Viewer für .NET ist eine leistungsstarke API zum Rendern von Dokumenten, mit der Entwickler über 170 Dokumenttypen in ihren .NET-Anwendungen anzeigen können, ohne dass externe Softwareinstallationen erforderlich sind.

## Voraussetzungen

Bevor wir uns mit dem Rendern von CHM-Dateien befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

### GroupDocs.Viewer für .NET installieren

 Um zu beginnen, müssen Sie GroupDocs.Viewer für .NET installieren. Sie können die Bibliothek unter herunterladen[GroupDocs-Website](https://releases.groupdocs.com/viewer/net/) oder installieren Sie es über NuGet Package Manager, indem Sie den folgenden Befehl in der Package Manager-Konsole ausführen:

```bash
Install-Package GroupDocs.Viewer
```

## Namensräume importieren

Stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Rendervorgang in mehrere Schritte unterteilen:

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
    options.RenderToSinglePage = true; // Auf „true“ setzen, um den gesamten CHM-Inhalt auf eine einzige Seite umzuwandeln

    viewer.View(options); //Konvertieren Sie alle Seiten
}
```

## Schritt 3: Als JPG rendern

Um CHM-Dateien in JPG-Bilder zu rendern, verwenden Sie den folgenden Codeausschnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konvertieren Sie nur die Seiten 1, 2, 3
}
```

## Schritt 4: In PNG rendern

Um CHM-Dateien in PNG-Bilder zu rendern, verwenden Sie den folgenden Codeausschnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konvertieren Sie nur die Seiten 1, 2, 3
}
```

## Schritt 5: Als PDF rendern

Um CHM-Dateien in ein PDF-Dokument zu rendern, verwenden Sie den folgenden Codeausschnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Konvertieren Sie alle Seiten
}
```

## Schritt 6: Überprüfen Sie die Ausgabe

Sobald der Rendervorgang abgeschlossen ist, überprüfen Sie das angegebene Ausgabeverzeichnis auf die gerenderten Dateien:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss

Das Rendern von CHM-Dateien mit GroupDocs.Viewer für .NET ist ein unkomplizierter Vorgang. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie CHM-Dokumente in Ihren .NET-Anwendungen effizient in verschiedene Formate wie HTML, Bilder (JPG, PNG) und PDF konvertieren.

## FAQs

### F1: Kann GroupDocs.Viewer neben CHM auch andere Dokumentformate rendern?

A1: Ja, GroupDocs.Viewer unterstützt das Rendern von über 170 Dokumentformaten, darunter PDF, DOCX, XLSX, PPTX und mehr.

### F2: Ist GroupDocs.Viewer mit .NET Core kompatibel?

A2: Ja, GroupDocs.Viewer unterstützt .NET Core zusätzlich zum herkömmlichen .NET Framework.

### F3: Kann ich die Rendering-Optionen für verschiedene Ausgabeformate anpassen?

A3: Ja, GroupDocs.Viewer bietet verschiedene Optionen zum Anpassen des Rendering-Prozesses, z. B. das Festlegen von Seitenzahlen, das Festlegen der Bildqualität und das Konfigurieren von Ausgabepfaden.

### F4: Benötigt GroupDocs.Viewer externe Abhängigkeiten zum Rendern von Dokumenten?

A4: Nein, GroupDocs.Viewer ist eine eigenständige Bibliothek und erfordert keine externen Abhängigkeiten oder Softwareinstallationen von Drittanbietern.

### F5: Gibt es eine kostenlose Testversion für GroupDocs.Viewer?

 A5: Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer nutzen, indem Sie die besuchen[Webseite](https://releases.groupdocs.com/).