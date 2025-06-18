---
"description": "Lär dig hur du renderar CHM-filer i .NET med GroupDocs.Viewer. Konvertera CHM till HTML-, JPG-, PNG- och PDF-format utan problem."
"linktitle": "Rendera CHM-filer"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera CHM-filer"
"url": "/sv/net/rendering-web-documents/render-chm/"
"weight": 10
---

# Rendera CHM-filer

## Introduktion
I den här handledningen ska vi utforska hur man renderar CHM-filer (Compiled HTML Help) med GroupDocs.Viewer för .NET. GroupDocs.Viewer för .NET är ett kraftfullt API för dokumentrendering som låter utvecklare visa över 170 dokumenttyper i sina .NET-applikationer utan att kräva några externa programvaruinstallationer.

## Förkunskapskrav

Innan vi går in på att rendera CHM-filer, se till att du har följande förutsättningar:

### Installera GroupDocs.Viewer för .NET

För att komma igång behöver du installera GroupDocs.Viewer för .NET. Du kan ladda ner biblioteket från [GroupDocs webbplats](https://releases.groupdocs.com/viewer/net/) eller installera det via NuGet Package Manager genom att köra följande kommando i Package Manager-konsolen:

```bash
Install-Package GroupDocs.Viewer
```

## Importera namnrymder

Se till att importera nödvändiga namnrymder till ditt projekt:

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
    options.RenderToSinglePage = true; // Ange till sant för att konvertera allt CHM-innehåll till en enda sida

    viewer.View(options); // Konvertera alla sidor
}
```

## Steg 3: Rendera till JPG

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

    viewer.View(options); // Konvertera alla sidor
}
```

## Steg 6: Kontrollera utdata

När renderingsprocessen är klar, kontrollera den angivna utdatakatalogen för de renderade filerna:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats

Att rendera CHM-filer med GroupDocs.Viewer för .NET är en enkel process. Genom att följa stegen som beskrivs i den här handledningen kan du effektivt konvertera CHM-dokument till olika format som HTML, bilder (JPG, PNG och PDF i dina .NET-applikationer.

## Vanliga frågor

### F1: Kan GroupDocs.Viewer rendera andra dokumentformat förutom CHM?

A1: Ja, GroupDocs.Viewer stöder rendering av över 170 dokumentformat, inklusive PDF, DOCX, XLSX, PPTX med flera.

### F2: Är GroupDocs.Viewer kompatibel med .NET Core?

A2: Ja, GroupDocs.Viewer har stöd för .NET Core utöver det traditionella .NET Framework.

### F3: Kan jag anpassa renderingsalternativen för olika utdataformat?

A3: Ja, GroupDocs.Viewer erbjuder olika alternativ för att anpassa renderingsprocessen, till exempel att ange sidnummer, ställa in bildkvalitet och konfigurera utdatasökvägar.

### F4: Kräver GroupDocs.Viewer några externa beroenden för att rendera dokument?

A4: Nej, GroupDocs.Viewer är ett fristående bibliotek och kräver inga externa beroenden eller installationer av programvara från tredje part.

### F5: Finns det en gratis provversion av GroupDocs.Viewer?

A5: Ja, du kan få en gratis provversion av GroupDocs.Viewer genom att besöka [webbplats](https://releases.groupdocs.com/).