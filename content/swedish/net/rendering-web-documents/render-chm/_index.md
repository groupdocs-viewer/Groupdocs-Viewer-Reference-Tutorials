---
title: Rendera CHM-filer
linktitle: Rendera CHM-filer
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar CHM-filer i .NET med GroupDocs.Viewer. Konvertera CHM till HTML-, JPG-, PNG- och PDF-format utan ansträngning.
weight: 10
url: /sv/net/rendering-web-documents/render-chm/
---

# Rendera CHM-filer

## Introduktion
den här handledningen kommer vi att utforska hur man renderar CHM-filer (Compiled HTML Help) med GroupDocs.Viewer för .NET. GroupDocs.Viewer för .NET är ett kraftfullt dokumentåtergivnings-API som tillåter utvecklare att visa över 170 dokumenttyper i sina .NET-applikationer utan att kräva några externa programvaruinstallationer.

## Förutsättningar

Innan vi dyker in i rendering av CHM-filer, se till att du har följande förutsättningar:

### Installerar GroupDocs.Viewer för .NET

 För att komma igång måste du installera GroupDocs.Viewer för .NET. Du kan ladda ner biblioteket från[GroupDocs webbplats](https://releases.groupdocs.com/viewer/net/) eller installera det via NuGet Package Manager genom att köra följande kommando i Package Manager Console:

```bash
Install-Package GroupDocs.Viewer
```

## Importera namnområden

Se till att importera de nödvändiga namnrymden till ditt projekt:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss nu dela upp renderingsprocessen i flera steg:

## Steg 1: Definiera utdatakatalog

Definiera katalogen där du vill att de renderade filerna ska sparas:

```csharp
string outputDirectory = "Your Document Directory";
```

## Steg 2: Rendera till HTML

För att rendera CHM-filer till HTML, använd följande kodavsnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Ställ in på sant för att konvertera allt CHM-innehåll till en enda sida

    viewer.View(options); //Konvertera alla sidor
}
```

## Steg 3: Återge till JPG

För att rendera CHM-filer till JPG-bilder, använd följande kodavsnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konvertera endast sidorna 1, 2, 3
}
```

## Steg 4: Rendera till PNG

För att rendera CHM-filer till PNG-bilder, använd följande kodavsnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konvertera endast sidorna 1, 2, 3
}
```

## Steg 5: Rendera till PDF

För att rendera CHM-filer till ett PDF-dokument, använd följande kodavsnitt:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Konvertera alla sidor
}
```

## Steg 6: Kontrollera utdata

När renderingsprocessen är klar, kontrollera den angivna utdatakatalogen för de renderade filerna:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats

Att rendera CHM-filer med GroupDocs.Viewer för .NET är en enkel process. Genom att följa stegen som beskrivs i denna handledning kan du effektivt konvertera CHM-dokument till olika format som HTML, bilder (JPG, PNG) och PDF i dina .NET-applikationer.

## FAQ's

### F1: Kan GroupDocs.Viewer återge andra dokumentformat förutom CHM?

S1: Ja, GroupDocs.Viewer stöder rendering av över 170 dokumentformat inklusive PDF, DOCX, XLSX, PPTX och mer.

### F2: Är GroupDocs.Viewer kompatibel med .NET Core?

S2: Ja, GroupDocs.Viewer stöder .NET Core utöver det traditionella .NET Framework.

### F3: Kan jag anpassa renderingsalternativen för olika utdataformat?

S3: Ja, GroupDocs.Viewer tillhandahåller olika alternativ för att anpassa renderingsprocessen, som att ange sidnummer, ställa in bildkvalitet och konfigurera utmatningsvägar.

### F4: Kräver GroupDocs.Viewer några externa beroenden för att rendera dokument?

S4: Nej, GroupDocs.Viewer är ett fristående bibliotek och kräver inga externa beroenden eller programvaruinstallationer från tredje part.

### F5: Finns det en gratis testversion tillgänglig för GroupDocs.Viewer?

 S5: Ja, du kan använda en gratis provversion av GroupDocs.Viewer genom att besöka[hemsida](https://releases.groupdocs.com/).