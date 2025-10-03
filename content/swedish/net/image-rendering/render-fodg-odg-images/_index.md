---
"description": "Lär dig hur du renderar FODG- och ODG-bilder till HTML, JPG, PNG och PDF med GroupDocs.Viewer för .NET. Förbättra din dokumenthantering."
"linktitle": "Rendera FODG- och ODG-bilder"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera FODG- och ODG-bilder"
"url": "/sv/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# Rendera FODG- och ODG-bilder

## Introduktion
I mjukvaruutvecklingens värld är effektiv hantering av dokumentformat av största vikt. GroupDocs.Viewer för .NET är ett kraftfullt verktyg utformat för att förenkla processen att rendera FODG- och ODG-bilder i .NET-applikationer. Den här handledningen guidar dig genom stegen som krävs för att rendera dessa bilder till olika format, som HTML, JPG, PNG och PDF, med GroupDocs.Viewer för .NET.

![Rendera FODG- och ODG-bilder med GroupDocs.Viewer för .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förkunskaper:
1. GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från [här](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Se till att du har .NET Framework installerat på ditt system.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# är meriterande.

## Importera namnrymder
Innan du börjar med implementeringen, importera nödvändiga namnrymder:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Steg 1: Ställ in utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Ersätta `"Your Document Directory"` med katalogsökvägen där du vill spara de renderade bilderna.
## Steg 2: Rendera till HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Det här steget renderar FODG-bilden till HTML-format.
## Steg 3: Rendera till JPG
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
Det här steget konverterar FODG-bilden till PNG-format.
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
den här handledningen har vi utforskat hur man renderar FODG- och ODG-bilder i olika format med GroupDocs.Viewer för .NET. Genom att följa dessa steg kan du sömlöst integrera dokumentrenderingsfunktioner i dina .NET-applikationer.
## Vanliga frågor
### Är GroupDocs.Viewer för .NET kompatibel med alla versioner av .NET Framework?
GroupDocs.Viewer för .NET är kompatibel med en mängd olika .NET Framework-versioner, inklusive de senaste.
### Kan jag rendera dokument asynkront med GroupDocs.Viewer för .NET?
Ja, GroupDocs.Viewer för .NET erbjuder asynkrona renderingsfunktioner för förbättrad prestanda.
### Har GroupDocs.Viewer för .NET stöd för rendering av krypterade dokument?
Ja, GroupDocs.Viewer för .NET stöder rendering av krypterade dokument med lämpliga dekrypteringsnycklar.
### Är det möjligt att anpassa renderingsutdata med GroupDocs.Viewer för .NET?
Absolut, GroupDocs.Viewer för .NET erbjuder olika anpassningsalternativ för att skräddarsy renderingsresultatet efter dina behov.
### Kan jag rendera dokument från fjärrlagringsplatser med GroupDocs.Viewer för .NET?
Ja, GroupDocs.Viewer för .NET stöder rendering av dokument från både lokala och fjärranslutna lagringsplatser.