---
title: Rendera XML SpreadSheetML
linktitle: Rendera XML SpreadSheetML
second_title: GroupDocs.Viewer .NET API
description: Utforska den sömlösa renderingen av XML SpreadSheetML-filer i olika format med GroupDocs.Viewer för .NET. Integrera enkelt i dina applikationer.
type: docs
weight: 16
url: /sv/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## Introduktion
Välkommen till världen av GroupDocs.Viewer för .NET! I den här handledningen guidar vi dig genom att enkelt rendera XML SpreadSheetML-filer med GroupDocs.Viewer, ett kraftfullt .NET-bibliotek. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här steg-för-steg-guiden dig att enkelt integrera XML SpreadSheetML-rendering i dina applikationer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar inställda:
- En utvecklingsmiljö med .NET-stöd.
-  GroupDocs.Viewer för .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.groupdocs.com/viewer/net/).
- En grundläggande förståelse för C#-programmering.
## Importera namnområden
Börja med att importera de nödvändiga namnrymden till ditt C#-projekt. Detta säkerställer att du har tillgång till funktionerna som tillhandahålls av GroupDocs.Viewer.
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
## Steg 2: Ange sökvägar för utdatafil
Ställ in de fullständiga sökvägarna för HTML-, JPG-, PNG- och PDF-utdatafilerna.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Steg 3: Ange laddningsalternativ
Ange uttryckligen filtypen som Excel 2003 XML SpreadSheetML för att återge den korrekt.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Steg 4: Återge till flersidig HTML
Använd HTML-vyalternativen för att rendera XML SpreadSheetML-filen till ett flersidigt HTML-dokument.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 5: Återge till JPG
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
Gör på samma sätt filen till en PNG-bild med de angivna alternativen.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Steg 7: Rendera till PDF
Gör slutligen XML SpreadSheetML-filen till ett PDF-dokument med de angivna alternativen.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du renderar XML SpreadSheetML-filer med GroupDocs.Viewer för .NET. Förbättra dina dokumentvisningsmöjligheter genom att utforska fler funktioner och alternativ som tillhandahålls av detta mångsidiga bibliotek.
## Vanliga frågor
### Är GroupDocs.Viewer kompatibel med andra filformat?
Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive PDF, Word, Excel och mer.
### Kan jag anpassa utseendet på de renderade dokumenten?
Absolut! GroupDocs.Viewer erbjuder olika anpassningsalternativ, så att du kan skräddarsy utskriften efter dina specifika behov.
### Var kan jag hitta ytterligare support och resurser?
 Besök[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för samhällsstöd och utforska[dokumentation](https://reference.groupdocs.com/viewer/net/)för detaljerad information.
### Finns det en gratis provperiod?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.groupdocs.com/).
### Hur får jag en tillfällig licens?
 Du kan få en tillfällig licens[här](https://purchase.groupdocs.com/temporary-license/).