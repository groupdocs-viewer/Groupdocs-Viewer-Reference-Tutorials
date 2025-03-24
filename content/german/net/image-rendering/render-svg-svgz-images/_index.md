---
title: Rendern Sie SVG- und SVGZ-Bilder
linktitle: Rendern Sie SVG- und SVGZ-Bilder
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie SVG- und SVGZ-Bilder mit GroupDocs.Viewer für .NET rendern. Konvertieren Sie Vektorgrafiken mühelos in HTML, JPG, PNG und PDF.
weight: 16
url: /de/net/image-rendering/render-svg-svgz-images/
---

# Rendern Sie SVG- und SVGZ-Bilder

## Einführung
In diesem Tutorial führen wir Sie durch den Prozess des Renderns von SVG- und SVGZ-Bildern mit GroupDocs.Viewer für .NET. GroupDocs.Viewer für .NET ist eine leistungsstarke API zum Rendern von Dokumenten, mit der Entwickler verschiedene Dokumentformate in ihren .NET-Anwendungen rendern können. SVG und SVGZ sind beliebte Bildformate für Vektorgrafiken, und mit GroupDocs.Viewer für .NET können Sie sie problemlos in verschiedene Ausgabeformate wie HTML, JPG, PNG und PDF rendern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen installiert und eingerichtet sind:
1.  GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von[Hier](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie über eine funktionierende Entwicklungsumgebung für die .NET-Entwicklung verfügen, z. B. Visual Studio.
3. Beispiel-SVGZ-Datei: Halten Sie eine Beispiel-SVGZ-Datei zum Testen bereit.

## Namespaces importieren
Bevor wir uns mit dem Code befassen, importieren wir die erforderlichen Namespaces:
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
## FAQs
### Kann GroupDocs.Viewer andere Bildformate rendern?
Ja, GroupDocs.Viewer unterstützt das Rendern verschiedener Bildformate, darunter PNG, JPEG, BMP, TIFF, GIF und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer ist sowohl mit .NET Framework als auch .NET Core kompatibel.
### Kann ich die Rendering-Optionen anpassen?
Ja, GroupDocs.Viewer bietet umfangreiche Rendering-Optionen, mit denen Sie die Ausgabe entsprechend Ihren Anforderungen anpassen können.
### Erfordert GroupDocs.Viewer Abhängigkeiten von Drittanbietern?
Nein, GroupDocs.Viewer ist eine eigenständige API und erfordert keine Abhängigkeiten von Drittanbietern zum Rendern von Dokumenten.
### Gibt es eine Testversion zum Testen?
Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer herunterladen unter[Hier](https://releases.groupdocs.com/) um die Funktionen vor dem Kauf zu bewerten.