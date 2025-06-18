---
"description": "Lär dig hur du renderar SVG- och SVGZ-bilder med GroupDocs.Viewer för .NET. Konvertera vektorgrafik till HTML, JPG, PNG och PDF utan ansträngning."
"linktitle": "Rendera SVG- och SVGZ-bilder"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera SVG- och SVGZ-bilder"
"url": "/sv/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# Rendera SVG- och SVGZ-bilder

## Introduktion
den här handledningen guidar vi dig genom processen att rendera SVG- och SVGZ-bilder med GroupDocs.Viewer för .NET. GroupDocs.Viewer för .NET är ett kraftfullt API för dokumentrendering som gör det möjligt för utvecklare att rendera olika dokumentformat i sina .NET-applikationer. SVG och SVGZ är populära bildformat som används för vektorgrafik, och med GroupDocs.Viewer för .NET kan du enkelt rendera dem till olika utdataformat som HTML, JPG, PNG och PDF.

![Rendera SVG- och SVGZ-bilder med GroupDocs.Viewer för .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Förkunskapskrav
Innan vi börjar, se till att du har följande förutsättningar installerade och konfigurerade:
1. GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från [här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Se till att du har en fungerande utvecklingsmiljö för .NET-utveckling, till exempel Visual Studio.
3. Exempel på SVGZ-fil: Ha en exempel-SVGZ-fil redo för testning.

## Importera namnrymder
Innan vi går in i koden, låt oss importera de nödvändiga namnrymderna:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Steg 1: Rendera SVGZ till HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Steg 2: Konvertera SVGZ till JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Steg 3: Rendera SVGZ till PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Steg 4: Konvertera SVGZ till PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Slutsats
I den här handledningen har vi lärt oss hur man renderar SVG- och SVGZ-bilder med GroupDocs.Viewer för .NET. Med bara några få enkla steg kan du konvertera SVGZ-bilder till olika utdataformat som HTML, JPG, PNG och PDF, vilket gör dem tillgängliga och synliga i olika miljöer.
## Vanliga frågor
### Kan GroupDocs.Viewer rendera andra bildformat?
Ja, GroupDocs.Viewer stöder rendering av olika bildformat, inklusive PNG, JPEG, BMP, TIFF, GIF med flera.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer är kompatibel med både .NET Framework och .NET Core.
### Kan jag anpassa renderingsalternativen?
Ja, GroupDocs.Viewer erbjuder omfattande renderingsalternativ som gör att du kan anpassa resultatet efter dina behov.
### Kräver GroupDocs.Viewer några beroenden från tredje part?
Nej, GroupDocs.Viewer är ett fristående API och kräver inga tredjepartsberoenden för att rendera dokument.
### Finns det en testversion tillgänglig för testning?
Ja, du kan ladda ner en gratis testversion av GroupDocs.Viewer från [här](https://releases.groupdocs.com/) att utvärdera dess funktioner innan man gör ett köp.