---
title: RAR-Archive rendern
linktitle: RAR-Archive rendern
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie RAR-Archive mit GroupDocs.Viewer für .NET in die Formate HTML, JPG, PNG oder PDF rendern. Sehen Sie sich den Inhalt von RAR-Archiven ganz einfach an und teilen Sie ihn.
type: docs
weight: 13
url: /de/net/rendering-archive-files/render-rar/
---
## Einführung
RAR-Archive sind ein beliebtes Format zum Komprimieren und Speichern mehrerer Dateien und Ordner in einem einzigen Container. Das Rendern von RAR-Archiven in verschiedene Formate wie HTML, JPG, PNG oder PDF kann für die Anzeige oder Weitergabe der Inhalte dieser Archive von entscheidender Bedeutung sein. In diesem Tutorial erfahren Sie, wie Sie RAR-Archive mit GroupDocs.Viewer für .NET rendern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET: Installieren Sie die GroupDocs.Viewer für .NET-Bibliothek aus der[Download-Link](https://releases.groupdocs.com/viewer/net/).
2. Beispiel-RAR-Archiv: Halten Sie ein Beispiel-RAR-Archiv zum Rendern bereit.

## Namespaces importieren
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: In HTML rendern
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 3: Als JPG rendern
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 4: In PNG rendern
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 5: Als PDF rendern
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Abschluss
Mit GroupDocs.Viewer für .NET wird das Rendern von RAR-Archiven in verschiedene Formate vereinfacht. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie RAR-Archive mühelos in die Formate HTML, JPG, PNG oder PDF konvertieren und so deren Inhalte einfach anzeigen und teilen.
## FAQs
### Kann GroupDocs.Viewer für .NET mit verschlüsselten RAR-Archiven umgehen?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern verschlüsselter RAR-Archive, sofern während des Rendervorgangs die erforderlichen Passwörter bereitgestellt werden.
### Ist es möglich, das Ausgabebild gerenderter Dokumente anzupassen?
Absolut! GroupDocs.Viewer für .NET bietet umfangreiche Anpassungsoptionen, mit denen Benutzer das Erscheinungsbild gerenderter Dokumente nach ihren Wünschen anpassen können.
### Unterstützt GroupDocs.Viewer für .NET das Rendern anderer Archivformate außer RAR?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern verschiedener Archivformate, einschließlich ZIP, TAR, 7z und mehr.
### Kann ich GroupDocs.Viewer für .NET in meine Webanwendung integrieren?
Sicherlich! GroupDocs.Viewer für .NET bietet APIs, die für die Integration sowohl in Desktop- als auch Webanwendungen geeignet sind.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
 Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer für .NET unter herunterladen[Webseite](https://releases.groupdocs.com/).