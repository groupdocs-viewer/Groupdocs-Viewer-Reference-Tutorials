---
"description": "Leer hoe u SVG- en SVGZ-afbeeldingen kunt renderen met GroupDocs.Viewer voor .NET. Converteer vectorafbeeldingen moeiteloos naar HTML, JPG, PNG en PDF."
"linktitle": "SVG- en SVGZ-afbeeldingen renderen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "SVG- en SVGZ-afbeeldingen renderen"
"url": "/nl/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# SVG- en SVGZ-afbeeldingen renderen

## Invoering
In deze tutorial begeleiden we je door het proces van het renderen van SVG- en SVGZ-afbeeldingen met GroupDocs.Viewer voor .NET. GroupDocs.Viewer voor .NET is een krachtige API voor documentrendering waarmee ontwikkelaars verschillende documentformaten in hun .NET-applicaties kunnen renderen. SVG en SVGZ zijn populaire afbeeldingsformaten voor vectorafbeeldingen, en met GroupDocs.Viewer voor .NET kun je ze eenvoudig renderen in verschillende uitvoerformaten, zoals HTML, JPG, PNG en PDF.

![SVG- en SVGZ-afbeeldingen renderen met GroupDocs.Viewer voor .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat de volgende vereisten zijn geïnstalleerd en ingesteld:
1. GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET van [hier](https://releases.groupdocs.com/viewer/net/).
2. Ontwikkelomgeving: Zorg dat u over een werkende ontwikkelomgeving voor .NET-ontwikkeling beschikt, zoals Visual Studio.
3. Voorbeeld van een SVGZ-bestand: Zorg dat u een voorbeeld van een SVGZ-bestand bij de hand hebt om te testen.

## Naamruimten importeren
Voordat we in de code duiken, importeren we de benodigde naamruimten:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Stap 1: SVGZ naar HTML renderen
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Stap 2: SVGZ naar JPG renderen
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Stap 3: SVGZ naar PNG renderen
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Stap 4: SVGZ naar PDF renderen
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusie
In deze tutorial hebben we geleerd hoe je SVG- en SVGZ-afbeeldingen kunt renderen met GroupDocs.Viewer voor .NET. Met slechts een paar eenvoudige stappen kun je SVGZ-afbeeldingen converteren naar verschillende uitvoerformaten zoals HTML, JPG, PNG en PDF, waardoor ze in verschillende omgevingen toegankelijk en zichtbaar zijn.
## Veelgestelde vragen
### Kan GroupDocs.Viewer andere afbeeldingsformaten weergeven?
Ja, GroupDocs.Viewer ondersteunt het renderen van verschillende afbeeldingsformaten, waaronder PNG, JPEG, BMP, TIFF, GIF en meer.
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer is compatibel met zowel .NET Framework als .NET Core.
### Kan ik de renderopties aanpassen?
Ja, GroupDocs.Viewer biedt uitgebreide renderingopties waarmee u de uitvoer naar uw wensen kunt aanpassen.
### Heeft GroupDocs.Viewer afhankelijkheden van derden nodig?
Nee, GroupDocs.Viewer is een zelfstandige API en vereist geen afhankelijkheden van derden om documenten weer te geven.
### Is er een proefversie beschikbaar om te testen?
Ja, u kunt een gratis proefversie van GroupDocs.Viewer downloaden van [hier](https://releases.groupdocs.com/) om de functies ervan te evalueren voordat u tot aankoop overgaat.