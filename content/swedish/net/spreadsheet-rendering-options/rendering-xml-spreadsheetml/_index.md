---
"description": "Utforska den sömlösa renderingen av XML SpreadSheetML-filer i olika format med GroupDocs.Viewer för .NET. Integrera enkelt i dina applikationer."
"linktitle": "Rendera XML-kalkylblad"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera XML-kalkylblad"
"url": "/sv/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
---

# Rendera XML-kalkylblad

## Introduktion
Välkommen till GroupDocs.Viewer för .NET! I den här handledningen guidar vi dig genom att enkelt rendera XML SpreadSheetML-filer med GroupDocs.Viewer, ett kraftfullt .NET-bibliotek. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här steg-för-steg-guiden dig att enkelt integrera XML SpreadSheetML-rendering i dina applikationer.
## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förutsättningar konfigurerade:
- En utvecklingsmiljö med stöd för .NET.
- GroupDocs.Viewer för .NET-biblioteket är installerat. Du kan ladda ner det. [här](https://releases.groupdocs.com/viewer/net/).
- Grundläggande förståelse för C#-programmering.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna till ditt C#-projekt. Detta säkerställer att du har tillgång till funktionerna som tillhandahålls av GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Steg 1: Konfigurera din dokumentkatalog
Definiera sökvägen till din dokumentkatalog där utdata ska sparas.
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Ange sökvägar till utdatafiler
Ange de fullständiga sökvägarna för HTML-, JPG-, PNG- och PDF-utdatafilerna.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Steg 3: Ange laddningsalternativ
Ange explicit filtypen som Excel 2003 XML SpreadSheetML för att återge den korrekt.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Steg 4: Rendera till flersidig HTML
Använd HTML-vyalternativen för att rendera XML SpreadSheetML-filen till ett flersidigt HTML-dokument.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 5: Rendera till JPG
Rendera XML SpreadSheetML-filen till en JPG-bild med de angivna alternativen.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 6: Rendera till PNG
På samma sätt, rendera filen till en PNG-bild med de angivna alternativen.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 7: Rendera till PDF
Slutligen, rendera XML SpreadSheetML-filen till ett PDF-dokument med de angivna alternativen.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Slutsats
Grattis! Du har nu lärt dig hur man renderar XML SpreadSheetML-filer med GroupDocs.Viewer för .NET. Förbättra dina dokumentvisningsmöjligheter genom att utforska fler funktioner och alternativ som erbjuds av detta mångsidiga bibliotek.
## Vanliga frågor
### Är GroupDocs.Viewer kompatibel med andra filformat?
Ja, GroupDocs.Viewer stöder en mängd olika dokumentformat, inklusive PDF, Word, Excel och mer.
### Kan jag anpassa utseendet på de renderade dokumenten?
Absolut! GroupDocs.Viewer erbjuder olika anpassningsalternativ, så att du kan skräddarsy resultatet efter dina specifika behov.
### Var kan jag hitta ytterligare stöd och resurser?
Besök [GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för samhällsstöd och utforska [dokumentation](https://tutorials.groupdocs.com/viewer/net/) för detaljerad information.
### Finns det en gratis provperiod tillgänglig?
Ja, du kan få tillgång till gratis provperioden [här](https://releases.groupdocs.com/).
### Hur får jag en tillfällig licens?
Du kan få en tillfällig licens [här](https://purchase.groupdocs.com/temporary-license/).