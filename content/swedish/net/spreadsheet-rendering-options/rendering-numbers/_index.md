---
"description": "Utforska kraften hos Groupdocs.Viewer för .NET för att rendera Numbers-filer sömlöst. Konvertera till HTML, JPG, PNG och PDF utan ansträngning."
"linktitle": "Rendering av siffror"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendering av siffror"
"url": "/sv/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# Rendering av siffror

## Introduktion
Välkommen till den här steg-för-steg-handledningen om hur du renderar Numbers-filer med Groupdocs.Viewer för .NET. Oavsett om du är en erfaren utvecklare eller nybörjare, kommer den här guiden att guida dig genom processen att konvertera Numbers-dokument till olika format. Groupdocs.Viewer för .NET är ett kraftfullt verktyg som låter dig sömlöst integrera dokumentvisningsfunktioner i dina .NET-applikationer.
## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förutsättningar på plats:
- Goda kunskaper i C# och .NET-utveckling.
- Groupdocs.Viewer för .NET-biblioteket är installerat. Du kan ladda ner det. [här](https://releases.groupdocs.com/viewer/net/).
- Sökvägen till din dokumentkatalog där utdatafilerna kommer att sparas.
## Importera namnrymder
I ditt C#-projekt, se till att du importerar de namnrymder som krävs för att använda Groupdocs.Viewer-biblioteket:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Konfigurera utdatakatalogen
Innan du börjar rendera, definiera utdatakatalogen där de konverterade filerna ska sparas. Ersätt "Din dokumentkatalog" med den faktiska sökvägen:
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Rendera till flersidig HTML
Använd följande kod för att konvertera Numbers-filen till flersidig HTML:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 3: Rendera till JPG
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
Grattis! Du har lyckats rendera Numbers-filer till olika format med Groupdocs.Viewer för .NET.
## Slutsats
den här handledningen gick vi igenom grunderna i att rendera Numbers-filer med Groupdocs.Viewer för .NET. Detta kraftfulla bibliotek erbjuder sömlös integration för visning och konvertering av dokument i dina .NET-applikationer.
## Vanliga frågor
### Kan jag använda Groupdocs.Viewer för .NET med andra dokumenttyper?
Ja, Groupdocs.Viewer stöder en mängd olika dokumentformat, inklusive Word, Excel, PDF och mer.
### Finns det en tillfällig licens tillgänglig för teständamål?
Ja, du kan få ett tillfälligt körkort [här](https://purchase.groupdocs.com/temporary-license/) för testning.
### Var kan jag hitta support för Groupdocs.Viewer för .NET?
Besök [Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för hjälp och diskussioner.
### Hur köper jag den fullständiga versionen av Groupdocs.Viewer för .NET?
Du kan köpa den fullständiga versionen [här](https://purchase.groupdocs.com/buy).
### Finns det en gratis testversion tillgänglig?
Ja, du kan utforska den kostnadsfria testversionen [här](https://releases.groupdocs.com/).