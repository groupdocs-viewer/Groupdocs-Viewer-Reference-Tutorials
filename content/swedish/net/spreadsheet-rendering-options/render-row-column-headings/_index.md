---
title: Återge rad- och kolumnrubriker
linktitle: Återge rad- och kolumnrubriker
second_title: GroupDocs.Viewer .NET API
description: Förbättra dokumentvisning i .NET! Lär dig att återge rad- och kolumnrubriker med GroupDocs.Viewer för .NET. Utforska HTML-, JPG-, PNG- och PDF-utdata.
weight: 18
url: /sv/net/spreadsheet-rendering-options/render-row-column-headings/
---
## Introduktion
Vill du förbättra din dokumentvisningsupplevelse i .NET-applikationer? Med GroupDocs.Viewer för .NET kan du sömlöst återge rad- och kolumnrubriker från dina kalkylbladsfiler. I den här självstudien guidar vi dig genom processen att rendera rad- och kolumnrubriker med olika utdataformat som HTML, JPG, PNG och PDF.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Installerade GroupDocs.Viewer för .NET-biblioteket.
- Ett exempel på XLSX-fil för teständamål.
- En praktisk kunskap om C# och .NET utveckling.
## Importera namnområden
Se till att du importerar de nödvändiga namnrymden i din C#-kod för att använda GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Ställ in utdatakatalogen
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
## 3. Återge till JPG
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
Grattis! Du har framgångsrikt renderat rad- och kolumnrubriker från ditt kalkylblad med GroupDocs.Viewer för .NET. Experimentera med olika utdataformat för att passa din applikations behov.
## Vanliga frågor
### F: Kan jag anpassa utdatakatalogen för de renderade dokumenten?
 S: Ja, du kan ställa in önskad utdatakatalog i koden där`outputDirectory` variabel definieras.
### F: Är GroupDocs.Viewer kompatibel med andra kalkylbladsformat?
S: Ja, GroupDocs.Viewer stöder olika kalkylbladsformat, inklusive XLS, XLSX, CSV och mer.
### F: Hur kan jag hantera undantag under renderingsprocessen?
S: Du kan implementera try-catch-block för att hantera undantag och logga eller visa lämpliga meddelanden för användaren.
### F: Finns det några licenskrav för att använda GroupDocs.Viewer i min applikation?
S: Ja, du behöver en giltig licens. Du kan skaffa en tillfällig licens för teständamål eller köpa en fullständig licens för produktion.
### F: Var kan jag hitta ytterligare stöd eller diskussioner i samhället?
 A: Besök[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för stöd och diskussioner.