---
"description": "Lär dig hur du renderar EMZ- och EMF-bilder till olika format med GroupDocs.Viewer för .NET. Lättförståelig handledning för utvecklare."
"linktitle": "Rendera EMZ- och EMF-bilder"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera EMZ- och EMF-bilder"
"url": "/sv/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# Rendera EMZ- och EMF-bilder

## Introduktion

GroupDocs.Viewer för .NET är ett kraftfullt API för dokumentrendering som låter utvecklare visa olika dokumenttyper, inklusive EMZ-bilder (Enhanced Windows Metafile) och EMF-bilder (Enhanced Metafile), i sina .NET-applikationer. I den här handledningen kommer vi att utforska hur man renderar EMZ- och EMF-bilder till olika format som HTML, JPG, PNG och PDF med GroupDocs.Viewer för .NET.

![Rendera EMZ- och EMF-bilder med GroupDocs.Viewer för .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Förkunskapskrav

Innan vi börjar, se till att du har följande förutsättningar:

1. GroupDocs.Viewer för .NET: Du kan ladda ner biblioteket från [här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Se till att du har en kompatibel utvecklingsmiljö konfigurerad för .NET-utveckling.
3. Exempel på EMZ/EMF-bilder: Ha exempel på EMZ- och EMF-bilder tillgängliga för rendering.

## Importera namnrymder

Innan vi går in i koden, låt oss importera de nödvändiga namnrymderna:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Nu ska vi dela upp varje exempel i flera steg i en steg-för-steg-guide:

## Rendera EMZ/EMF-bilder till HTML

### Steg 1: Ställ in utdatakatalog:
```csharp
string outputDirectory = "Your Document Directory";
```
Ersätta `"Your Document Directory"` med sökvägen där du vill spara den renderade HTML-filen.

### Steg 2: Definiera sökvägsformat för sidfil:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Detta anger sökvägsformatet för den renderade HTML-filen.

### Steg 3: Rendera till HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Denna kod initierar `Viewer` objektet med exempel-EMZ-bilden och renderar den till HTML-format med angivna alternativ.

## Rendera EMZ/EMF-bilder till JPG, PNG och PDF

Upprepa följande steg för att rendera till JPG-, PNG- och PDF-format:

### Steg 1: Definiera sökvägsformat för sidfil:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Justera filnamnet och filändelsen enligt önskat utdataformat (`jpg`, `png`, eller `pdf`).

### Steg 2: Rendera till respektive format:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Justera alternativen efter utdataformatet (JPG, PNG, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Ersätta `JpgViewOptions` med `PngViewOptions` eller `PdfViewOptions` baserat på önskat utdataformat.

## Slutsats

Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en sömlös lösning för att rendera EMZ- och EMF-bilder till olika format i .NET-applikationer. Genom att följa stegen som beskrivs i den här handledningen kan utvecklare enkelt integrera dokumentrenderingsfunktioner i sina applikationer.

## Vanliga frågor

### F: Kan GroupDocs.Viewer rendera andra dokumentformat förutom EMZ- och EMF-bilder?
A: Ja, GroupDocs.Viewer stöder en mängd olika dokumentformat, inklusive PDF, DOCX, PPTX, XLSX med flera.

### F: Finns det en gratis testversion av GroupDocs.Viewer för .NET?
A: Ja, du kan få tillgång till gratis provperioden [här](https://releases.groupdocs.com/).

### F: Erbjuder GroupDocs.Viewer stöd för utvecklare?
A: Ja, GroupDocs tillhandahåller support genom sina [forum](https://forum.groupdocs.com/c/viewer/9) där utvecklare kan ställa frågor och söka hjälp.

### F: Kan jag köpa en tillfällig licens för GroupDocs.Viewer för .NET?
A: Ja, tillfälliga licenser finns att köpa [här](https://purchase.groupdocs.com/temporary-license/).

### F: Var kan jag hitta detaljerad dokumentation för GroupDocs.Viewer för .NET?
A: Du kan hänvisa till dokumentationen [här](https://tutorials.groupdocs.com/viewer/net/) för omfattande vägledning om hur man använder API:et.