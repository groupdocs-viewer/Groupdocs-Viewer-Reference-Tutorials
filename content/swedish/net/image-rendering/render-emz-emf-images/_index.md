---
title: Återge EMZ- och EMF-bilder
linktitle: Återge EMZ- och EMF-bilder
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du återger EMZ- och EMF-bilder till olika format med GroupDocs.Viewer för .NET. Lätt att följa handledning för utvecklare.
weight: 14
url: /sv/net/image-rendering/render-emz-emf-images/
---

# Återge EMZ- och EMF-bilder

## Introduktion

GroupDocs.Viewer för .NET är ett kraftfullt dokumentåtergivnings-API som låter utvecklare visa olika dokumenttyper, inklusive EMZ (Enhanced Windows Metafile) och EMF (Enhanced Metafile)-bilder, i sina .NET-applikationer. I den här handledningen kommer vi att utforska hur man renderar EMZ- och EMF-bilder till olika format som HTML, JPG, PNG och PDF med GroupDocs.Viewer för .NET.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:

1.  GroupDocs.Viewer för .NET: Du kan ladda ner biblioteket från[här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Se till att du har en kompatibel utvecklingsmiljö inställd för .NET-utveckling.
3. Exempel på EMZ/EMF-bilder: Ha exempel på EMZ- och EMF-bilder tillgängliga för rendering.

## Importera namnområden

Innan vi dyker in i koden, låt oss importera de nödvändiga namnrymden:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Låt oss nu dela upp varje exempel i flera steg i ett steg-för-steg-guideformat:

## Återge EMZ/EMF-bilder till HTML

### Steg 1: Ställ in utdatakatalog:
```csharp
string outputDirectory = "Your Document Directory";
```
 Byta ut`"Your Document Directory"`med sökvägen där du vill spara den renderade HTML-filen.

### Steg 2: Definiera sidfilssökvägsformat:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Detta kommer att ange filsökvägsformatet för den renderade HTML-filen.

### Steg 3: Rendera till HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Denna kod initierar`Viewer` objektet med EMZ-exemplet och renderar det till HTML-format med angivna alternativ.

## Återge EMZ/EMF-bilder till JPG, PNG och PDF

Upprepa följande steg för att rendera till JPG-, PNG- och PDF-format:

### Steg 1: Definiera sidfilssökvägsformat:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Justera filnamnet och filtillägget enligt önskat utdataformat (`jpg`, `png` , eller`pdf`).

### Steg 2: Rendera till respektive format:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Justera alternativen enligt utdataformatet (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Byta ut`JpgViewOptions` med`PngViewOptions` eller`PdfViewOptions` baserat på önskat utdataformat.

## Slutsats

Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en sömlös lösning för att rendera EMZ- och EMF-bilder till olika format i .NET-applikationer. Genom att följa stegen som beskrivs i denna handledning kan utvecklare enkelt integrera dokumentåtergivningsmöjligheter i sina applikationer.

## FAQ's

### F: Kan GroupDocs.Viewer återge andra dokumentformat förutom EMZ- och EMF-bilder?
S: Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat inklusive PDF, DOCX, PPTX, XLSX och mer.

### F: Finns det en gratis testversion tillgänglig för GroupDocs.Viewer för .NET?
 S: Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.groupdocs.com/).

### F: Erbjuder GroupDocs.Viewer stöd för utvecklare?
 S: Ja, GroupDocs tillhandahåller support genom sin[forum](https://forum.groupdocs.com/c/viewer/9) där utvecklare kan ställa frågor och söka hjälp.

### F: Kan jag köpa en tillfällig licens för GroupDocs.Viewer för .NET?
 S: Ja, tillfälliga licenser finns att köpa[här](https://purchase.groupdocs.com/temporary-license/).

### F: Var kan jag hitta detaljerad dokumentation för GroupDocs.Viewer för .NET?
 S: Du kan hänvisa till dokumentationen[här](https://tutorials.groupdocs.com/viewer/net/)för omfattande vägledning om hur du använder API.