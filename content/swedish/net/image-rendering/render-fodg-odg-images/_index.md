---
title: Återge FODG- och ODG-bilder
linktitle: Återge FODG- och ODG-bilder
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar FODG- och ODG-bilder till HTML, JPG, PNG och PDF med GroupDocs.Viewer för .NET. Förbättra din dokumenthantering.
weight: 15
url: /sv/net/image-rendering/render-fodg-odg-images/
---
## Introduktion
I en värld av mjukvaruutveckling är effektiv hantering av dokumentformat av största vikt. GroupDocs.Viewer för .NET är ett kraftfullt verktyg utformat för att förenkla processen att rendera FODG- och ODG-bilder i .NET-applikationer. Den här handledningen går igenom stegen som krävs för att rendera dessa bilder till olika format, som HTML, JPG, PNG och PDF, med hjälp av GroupDocs.Viewer för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
1.  GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från[här](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Se till att du har .NET Framework installerat på ditt system.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# kommer att vara till hjälp.

## Importera namnområden
Innan du börjar med implementeringen, importera de nödvändiga namnrymden:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Steg 1: Ställ in utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
 Byta ut`"Your Document Directory"`med katalogsökvägen där du vill spara de renderade bilderna.
## Steg 2: Rendera till HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Detta steg renderar FODG-bilden till HTML-format.
## Steg 3: Återge till JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Här renderas FODG-bilden till JPG-format.
## Steg 4: Rendera till PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Detta steg konverterar FODG-bilden till PNG-format.
## Steg 5: Rendera till PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Slutligen renderas FODG-bilden till PDF-format.

## Slutsats
I den här handledningen har vi utforskat hur man renderar FODG- och ODG-bilder till olika format med GroupDocs.Viewer för .NET. Genom att följa dessa steg kan du sömlöst integrera funktioner för dokumentåtergivning i dina .NET-applikationer.
## FAQ's
### Är GroupDocs.Viewer för .NET kompatibel med alla versioner av .NET Framework?
GroupDocs.Viewer för .NET är kompatibel med ett brett utbud av .NET Framework-versioner, inklusive de senaste.
### Kan jag rendera dokument asynkront med GroupDocs.Viewer för .NET?
Ja, GroupDocs.Viewer för .NET tillhandahåller asynkron renderingsfunktioner för förbättrad prestanda.
### Stöder GroupDocs.Viewer för .NET rendering av krypterade dokument?
Ja, GroupDocs.Viewer för .NET stöder rendering av krypterade dokument med lämpliga dekrypteringsnycklar.
### Är det möjligt att anpassa renderingen med GroupDocs.Viewer för .NET?
Absolut, GroupDocs.Viewer för .NET erbjuder olika anpassningsalternativ för att skräddarsy renderingen efter dina krav.
### Kan jag rendera dokument från fjärrlagringsplatser med GroupDocs.Viewer för .NET?
Ja, GroupDocs.Viewer för .NET stöder rendering av dokument från både lokala och fjärrlagringsplatser.