---
title: Render SVG- en SVGZ-afbeeldingen
linktitle: Render SVG- en SVGZ-afbeeldingen
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u SVG- en SVGZ-afbeeldingen kunt renderen met GroupDocs.Viewer voor .NET. Converteer vectorafbeeldingen moeiteloos naar HTML, JPG, PNG en PDF.
weight: 16
url: /nl/net/image-rendering/render-svg-svgz-images/
---

# Render SVG- en SVGZ-afbeeldingen

## Invoering
In deze zelfstudie begeleiden we u bij het renderen van SVG- en SVGZ-afbeeldingen met GroupDocs.Viewer voor .NET. GroupDocs.Viewer voor .NET is een krachtige documentweergave-API waarmee ontwikkelaars verschillende documentformaten kunnen weergeven in hun .NET-toepassingen. SVG en SVGZ zijn populaire afbeeldingsindelingen die worden gebruikt voor vectorafbeeldingen, en met GroupDocs.Viewer voor .NET kunt u deze eenvoudig weergeven in verschillende uitvoerindelingen, zoals HTML, JPG, PNG en PDF.
## Vereisten
Voordat we beginnen, zorg ervoor dat u de volgende vereisten hebt geïnstalleerd en ingesteld:
1.  GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET van[hier](https://releases.groupdocs.com/viewer/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u over een werkende ontwikkelomgeving beschikt voor .NET-ontwikkeling, zoals Visual Studio.
3. Voorbeeld van een SVGZ-bestand: Zorg ervoor dat u een voorbeeld van een SVGZ-bestand gereed hebt om te testen.

## Naamruimten importeren
Voordat we in de code duiken, importeren we de benodigde naamruimten:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Stap 1: SVGZ renderen naar HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Stap 2: Render SVGZ naar JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Stap 3: Render SVGZ naar PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Stap 4: Render SVGZ naar PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u SVG- en SVGZ-afbeeldingen kunt renderen met GroupDocs.Viewer voor .NET. Met slechts een paar eenvoudige stappen kunt u SVGZ-afbeeldingen converteren naar verschillende uitvoerformaten zoals HTML, JPG, PNG en PDF, waardoor ze toegankelijk en zichtbaar worden in verschillende omgevingen.
## Veelgestelde vragen
### Kan GroupDocs.Viewer andere afbeeldingsformaten weergeven?
Ja, GroupDocs.Viewer ondersteunt het weergeven van verschillende afbeeldingsformaten, waaronder PNG, JPEG, BMP, TIFF, GIF en meer.
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer is compatibel met zowel .NET Framework als .NET Core.
### Kan ik de weergaveopties aanpassen?
Ja, GroupDocs.Viewer biedt uitgebreide weergaveopties waarmee u de uitvoer kunt aanpassen aan uw wensen.
### Vereist GroupDocs.Viewer afhankelijkheden van derden?
Nee, GroupDocs.Viewer is een zelfstandige API en vereist geen afhankelijkheden van derden voor het weergeven van documenten.
### Is er een proefversie beschikbaar om te testen?
Ja, u kunt een gratis proefversie van GroupDocs.Viewer downloaden van[hier](https://releases.groupdocs.com/) om de kenmerken ervan te evalueren voordat u een aankoop doet.