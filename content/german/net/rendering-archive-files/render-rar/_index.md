---
"description": "Erfahren Sie, wie Sie RAR-Archive mit GroupDocs.Viewer für .NET in die Formate HTML, JPG, PNG oder PDF rendern. Zeigen Sie RAR-Archivinhalte einfach an und teilen Sie sie."
"linktitle": "RAR-Archive rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "RAR-Archive rendern"
"url": "/de/net/rendering-archive-files/render-rar/"
"weight": 13
type: docs
---
# RAR-Archive rendern

## Einführung
RAR-Archive sind ein beliebtes Format zum Komprimieren und Speichern mehrerer Dateien und Ordner in einem einzigen Container. Das Rendern von RAR-Archiven in verschiedene Formate wie HTML, JPG, PNG oder PDF kann für die Anzeige oder Freigabe der Archivinhalte unerlässlich sein. In diesem Tutorial erfahren Sie, wie Sie RAR-Archive mit GroupDocs.Viewer für .NET rendern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. GroupDocs.Viewer für .NET: Installieren Sie die Bibliothek GroupDocs.Viewer für .NET aus dem [Download-Link](https://releases.groupdocs.com/viewer/net/).
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
## Schritt 3: In JPG rendern
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
## Schritt 5: In PDF rendern
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Abschluss
Das Rendern von RAR-Archiven in verschiedene Formate wird mit GroupDocs.Viewer für .NET zum Kinderspiel. Mit den in diesem Tutorial beschriebenen Schritten können Sie RAR-Archive mühelos in die Formate HTML, JPG, PNG oder PDF konvertieren und so deren Inhalte einfach anzeigen und teilen.
## Häufig gestellte Fragen
### Kann GroupDocs.Viewer für .NET verschlüsselte RAR-Archive verarbeiten?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern verschlüsselter RAR-Archive, vorausgesetzt, dass während des Rendervorgangs die erforderlichen Kennwörter angegeben werden.
### Ist es möglich, das Ausgabeerscheinungsbild gerenderter Dokumente anzupassen?
Absolut! GroupDocs.Viewer für .NET bietet umfangreiche Anpassungsoptionen, mit denen Benutzer das Erscheinungsbild gerenderter Dokumente an ihre Bedürfnisse anpassen können.
### Unterstützt GroupDocs.Viewer für .NET das Rendern anderer Archivformate außer RAR?
Ja, GroupDocs.Viewer für .NET unterstützt das Rendern verschiedener Archivformate, darunter ZIP, TAR, 7z und mehr.
### Kann ich GroupDocs.Viewer für .NET in meine Webanwendung integrieren?
Sicher! GroupDocs.Viewer für .NET bietet APIs, die sich sowohl für die Integration in Desktop- als auch in Webanwendungen eignen.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer für .NET nutzen von der [Webseite](https://releases.groupdocs.com/).