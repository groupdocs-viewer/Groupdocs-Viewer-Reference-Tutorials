---
title: Återge SVG- och SVGZ-bilder
linktitle: Återge SVG- och SVGZ-bilder
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar SVG- och SVGZ-bilder med GroupDocs.Viewer för .NET. Konvertera vektorgrafik till HTML, JPG, PNG och PDF utan ansträngning.
weight: 16
url: /sv/net/image-rendering/render-svg-svgz-images/
---

# Återge SVG- och SVGZ-bilder

## Introduktion
den här handledningen guidar vi dig genom processen att rendera SVG- och SVGZ-bilder med GroupDocs.Viewer för .NET. GroupDocs.Viewer för .NET är ett kraftfullt API för dokumentrendering som gör det möjligt för utvecklare att rendera olika dokumentformat i sina .NET-applikationer. SVG och SVGZ är populära bildformat som används för vektorgrafik, och med GroupDocs.Viewer för .NET kan du enkelt rendera dem till olika utdataformat som HTML, JPG, PNG och PDF.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar installerade och konfigurerade:
1.  GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från[här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Se till att du har en fungerande utvecklingsmiljö för .NET-utveckling, som Visual Studio.
3. Exempel SVGZ-fil: Ha en exempel-SVGZ-fil redo för testning.

## Importera namnområden
Innan vi dyker in i koden, låt oss importera de nödvändiga namnrymden:
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

## Steg 2: Gör SVGZ till JPG
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

## Steg 4: Gör SVGZ till PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Slutsats
den här handledningen har vi lärt oss hur man renderar SVG- och SVGZ-bilder med GroupDocs.Viewer för .NET. Med bara några enkla steg kan du konvertera SVGZ-bilder till olika utdataformat som HTML, JPG, PNG och PDF, vilket gör dem tillgängliga och synliga i olika miljöer.
## FAQ's
### Kan GroupDocs.Viewer återge andra bildformat?
Ja, GroupDocs.Viewer stöder rendering av olika bildformat inklusive PNG, JPEG, BMP, TIFF, GIF och mer.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer är kompatibel med både .NET Framework och .NET Core.
### Kan jag anpassa renderingsalternativen?
Ja, GroupDocs.Viewer erbjuder omfattande renderingsalternativ så att du kan anpassa utdata enligt dina krav.
### Kräver GroupDocs.Viewer några beroenden från tredje part?
Nej, GroupDocs.Viewer är ett fristående API och kräver inga tredjepartsberoenden för att rendera dokument.
### Finns det en testversion tillgänglig för testning?
Ja, du kan ladda ner en gratis testversion av GroupDocs.Viewer från[här](https://releases.groupdocs.com/) för att utvärdera dess funktioner innan du gör ett köp.