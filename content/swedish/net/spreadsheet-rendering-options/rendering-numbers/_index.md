---
title: Återgivningssiffror
linktitle: Återgivningssiffror
second_title: GroupDocs.Viewer .NET API
description: Utforska kraften i Groupdocs.Viewer för .NET när det gäller att rendera Numbers-filer sömlöst. Konvertera till HTML, JPG, PNG och PDF utan ansträngning.
type: docs
weight: 15
url: /sv/net/spreadsheet-rendering-options/rendering-numbers/
---
## Introduktion
Välkommen till denna steg-för-steg handledning om hur du renderar Numbers-filer med Groupdocs.Viewer för .NET. Oavsett om du är en erfaren utvecklare eller nybörjare, kommer den här guiden att leda dig genom processen att konvertera Numbers-dokument till olika format. Groupdocs.Viewer för .NET är ett kraftfullt verktyg som låter dig sömlöst integrera dokumentvisningsmöjligheter i dina .NET-applikationer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- En praktisk kunskap om C# och .NET utveckling.
-  Groupdocs.Viewer för .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.groupdocs.com/viewer/net/).
- Sökvägen till din dokumentkatalog där utdatafilerna kommer att sparas.
## Importera namnområden
Se till att du importerar de nödvändiga namnrymden i ditt C#-projekt för att använda biblioteket Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Konfigurera utdatakatalog
Innan du börjar rendera, definiera utdatakatalogen där de konverterade filerna ska sparas. Ersätt "Din dokumentkatalog" med den faktiska sökvägen:
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Återge HTML till flera sidor
Använd följande kod för att konvertera Numbers-filen till HTML med flera sidor:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 3: Återge till JPG
Konvertera Numbers-filen till JPG-format med följande kod:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 4: Rendera till PNG
Omvandla Numbers-filen till PNG-format med följande kod:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 5: Rendera till PDF
Slutligen, konvertera Numbers-filen till PDF-format med följande kod:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Grattis! Du har framgångsrikt renderat Numbers-filer till olika format med Groupdocs.Viewer för .NET.
## Slutsats
I den här handledningen täckte vi grunderna för att rendera Numbers-filer med Groupdocs.Viewer för .NET. Detta kraftfulla bibliotek ger sömlös integration för att visa och konvertera dokument i dina .NET-applikationer.
## Vanliga frågor
### Kan jag använda Groupdocs.Viewer för .NET med andra dokumenttyper?
Ja, Groupdocs.Viewer stöder ett brett utbud av dokumentformat, inklusive Word, Excel, PDF och mer.
### Finns en tillfällig licens tillgänglig för teständamål?
 Ja, du kan få en tillfällig licens[här](https://purchase.groupdocs.com/temporary-license/) för provning.
### Var kan jag hitta support för Groupdocs.Viewer för .NET?
 Besök[Groupdocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) för hjälp och diskussioner.
### Hur köper jag den fullständiga versionen av Groupdocs.Viewer för .NET?
 Du kan köpa den fullständiga versionen[här](https://purchase.groupdocs.com/buy).
### Finns det en gratis testversion tillgänglig?
 Ja, du kan utforska den kostnadsfria testversionen[här](https://releases.groupdocs.com/).