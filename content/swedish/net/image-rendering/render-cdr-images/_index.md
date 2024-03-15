---
title: Återge CDR-bilder
linktitle: Återge CDR-bilder
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar CDR-bilder till HTML, JPG, PNG och PDF med GroupDocs.Viewer för .NET. Konvertera enkelt CorelDRAW-filer med denna handledning.
type: docs
weight: 12
url: /sv/net/image-rendering/render-cdr-images/
---
## Introduktion
I den här handledningen guidar vi dig genom processen att rendera CDR-bilder (CorelDRAW) med GroupDocs.Viewer för .NET. CDR är ett filformat som primärt förknippas med CorelDRAW, en vektorgrafikredigerare. Med GroupDocs.Viewer kan du enkelt konvertera CDR-filer till olika format som HTML, JPG, PNG och PDF.
## Förutsättningar
Innan du börjar, se till att du har följande förutsättningar:
1.  GroupDocs.Viewer för .NET: Se till att du har installerat GroupDocs.Viewer för .NET. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).
2. Dokumentkatalog: Förbered en katalog där du vill spara de renderade bilderna.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# är nödvändigt för att förstå kodexemplen.
## Importera namnområden
Innan du dyker in i kodexemplen, importera de nödvändiga namnrymden i din C#-fil:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Låt oss nu dela upp varje exempel i flera steg:
## Rendering till HTML
1. Definiera utdatakatalogen där du vill spara de renderade HTML-filerna:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Ange filsökvägsformatet för HTML-filer:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Använd Viewer-klassen för att rendera CDR-filen till HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering till JPG
1. Definiera filsökvägsformatet för JPG-filer:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Använd Viewer-klassen för att återge CDR-filen till JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderar till PNG
1. Definiera filsökvägsformatet för PNG-filer:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Använd Viewer-klassen för att återge CDR-filen till PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering till PDF
1. Definiera filsökvägsformatet för PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Använd Viewer-klassen för att rendera CDR-filen till PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Alternativt kan du ange renderingsalternativ eller rendera specifika sidor genom att skicka ytterligare parametrar till`viewer.View()` metod.
## Slutsats
Att rendera CDR-bilder till olika format som HTML, JPG, PNG och PDF med GroupDocs.Viewer för .NET är en enkel process. Genom att följa stegen som beskrivs i denna handledning kan du effektivt konvertera CDR-filer till olika format baserat på dina krav.
## FAQ's
### Är GroupDocs.Viewer för .NET kompatibel med alla versioner av CDR-filer?
GroupDocs.Viewer för .NET stöder rendering av CDR-filer skapade av olika versioner av CorelDRAW.
### Kan jag anpassa utdata från renderade filer?
Ja, GroupDocs.Viewer för .NET erbjuder olika alternativ för att anpassa utdata, som att justera bildkvalitet, ställa in vattenstämpel, etc.
### Kräver GroupDocs.Viewer för .NET några externa beroenden?
Nej, GroupDocs.Viewer för .NET är ett fristående bibliotek och kräver inga externa beroenden för att rendera dokument.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
 Ja, du kan ladda ner en gratis testversion av GroupDocs.Viewer för .NET från[här](https://releases.groupdocs.com/).
### Var kan jag få support för GroupDocs.Viewer för .NET?
 Du kan få support från GroupDocs.Viewers communityforum[här](https://forum.groupdocs.com/c/viewer/9).