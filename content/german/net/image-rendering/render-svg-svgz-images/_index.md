---
"description": "Erfahren Sie, wie Sie SVG- und SVGZ-Bilder mit GroupDocs.Viewer für .NET rendern. Konvertieren Sie Vektorgrafiken mühelos in HTML, JPG, PNG und PDF."
"linktitle": "Rendern von SVG- und SVGZ-Bildern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendern von SVG- und SVGZ-Bildern"
"url": "/de/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# Rendern von SVG- und SVGZ-Bildern

## Einführung
In diesem Tutorial führen wir Sie durch das Rendern von SVG- und SVGZ-Bildern mit GroupDocs.Viewer für .NET. GroupDocs.Viewer für .NET ist eine leistungsstarke API zum Rendern von Dokumenten, die es Entwicklern ermöglicht, verschiedene Dokumentformate in ihren .NET-Anwendungen zu rendern. SVG und SVGZ sind beliebte Bildformate für Vektorgrafiken. Mit GroupDocs.Viewer für .NET können Sie diese problemlos in verschiedene Ausgabeformate wie HTML, JPG, PNG und PDF rendern.

![Rendern Sie SVG- und SVGZ-Bilder mit GroupDocs.Viewer für .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen installiert und eingerichtet haben:
1. GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von [Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie über eine funktionierende Entwicklungsumgebung für die .NET-Entwicklung verfügen, beispielsweise Visual Studio.
3. Beispiel-SVGZ-Datei: Halten Sie eine Beispiel-SVGZ-Datei zum Testen bereit.

## Namespaces importieren
Bevor wir uns in den Code vertiefen, importieren wir die erforderlichen Namespaces:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Schritt 1: SVGZ in HTML rendern
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Schritt 2: SVGZ in JPG rendern
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Schritt 3: SVGZ in PNG rendern
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Schritt 4: SVGZ in PDF rendern
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man SVG- und SVGZ-Bilder mit GroupDocs.Viewer für .NET rendert. Mit nur wenigen einfachen Schritten können Sie SVGZ-Bilder in verschiedene Ausgabeformate wie HTML, JPG, PNG und PDF konvertieren und sie so in verschiedenen Umgebungen zugänglich und sichtbar machen.
## Häufig gestellte Fragen
### Kann GroupDocs.Viewer andere Bildformate rendern?
Ja, GroupDocs.Viewer unterstützt das Rendern verschiedener Bildformate, darunter PNG, JPEG, BMP, TIFF, GIF und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer ist sowohl mit .NET Framework als auch mit .NET Core kompatibel.
### Kann ich die Rendering-Optionen anpassen?
Ja, GroupDocs.Viewer bietet umfangreiche Rendering-Optionen, mit denen Sie die Ausgabe entsprechend Ihren Anforderungen anpassen können.
### Benötigt GroupDocs.Viewer Abhängigkeiten von Drittanbietern?
Nein, GroupDocs.Viewer ist eine eigenständige API und erfordert keine Abhängigkeiten von Drittanbietern zum Rendern von Dokumenten.
### Gibt es eine Testversion zum Testen?
Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer herunterladen von [Hier](https://releases.groupdocs.com/) um die Funktionen vor dem Kauf zu bewerten.