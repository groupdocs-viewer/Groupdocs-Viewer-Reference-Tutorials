---
"description": "Förbättra dokumentvisningen i .NET! Lär dig rendera rad- och kolumnrubriker med GroupDocs.Viewer för .NET. Utforska HTML-, JPG-, PNG- och PDF-utdata."
"linktitle": "Rendera rad- och kolumnrubriker"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera rad- och kolumnrubriker"
"url": "/sv/net/spreadsheet-rendering-options/render-row-column-headings/"
"weight": 18
type: docs
---
# Rendera rad- och kolumnrubriker

## Introduktion
Vill du förbättra din dokumentvisningsupplevelse i .NET-applikationer? Med GroupDocs.Viewer för .NET kan du smidigt rendera rad- och kolumnrubriker från dina kalkylbladsfiler. I den här handledningen guidar vi dig genom processen att rendera rad- och kolumnrubriker med olika utdataformat som HTML, JPG, PNG och PDF.
## Förkunskapskrav
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Installerade GroupDocs.Viewer för .NET-biblioteket.
- En exempel-XLSX-fil för teständamål.
- Goda kunskaper i C# och .NET-utveckling.
## Importera namnrymder
din C#-kod, se till att du importerar de namnrymder som krävs för att använda GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Konfigurera utdatakatalogen
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. Rendera till HTML
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. Rendera till JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. Rendera till PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. Rendera till PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## Slutsats
Grattis! Du har lyckats rendera rad- och kolumnrubriker från ditt kalkylblad med GroupDocs.Viewer för .NET. Experimentera med olika utdataformat som passar ditt programs behov.
## Vanliga frågor
### F: Kan jag anpassa utdatakatalogen för de renderade dokumenten?
A: Ja, du kan ange önskad utdatakatalog i koden där `outputDirectory` variabeln är definierad.
### F: Är GroupDocs.Viewer kompatibelt med andra kalkylbladsformat?
A: Ja, GroupDocs.Viewer stöder olika kalkylbladsformat, inklusive XLS, XLSX, CSV med flera.
### F: Hur kan jag hantera undantag under renderingsprocessen?
A: Du kan implementera try-catch-block för att hantera undantag och logga eller visa lämpliga meddelanden för användaren.
### F: Finns det några licenskrav för att använda GroupDocs.Viewer i mitt program?
A: Ja, du behöver en giltig licens. Du kan skaffa en tillfällig licens för teständamål eller köpa en fullständig licens för produktion.
### F: Var kan jag hitta ytterligare stöd eller diskussioner i gemenskapen?
A: Besök [GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för stöd och diskussioner.