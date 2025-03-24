---
title: Ställ in bildstorleksgränser
linktitle: Ställ in bildstorleksgränser
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du ställer in bildstorleksgränser i .NET-program utan ansträngning med GroupDocs.Viewer för .NET, vilket förbättrar dokumentvisningsupplevelsen.
weight: 21
url: /sv/net/rendering-options/set-image-size-limits/
---

# Ställ in bildstorleksgränser

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt verktyg utformat för att underlätta sömlös dokumentvisning i .NET-applikationer. Med sina robusta funktioner och intuitiva gränssnitt kan utvecklare enkelt integrera dokumentvisningsmöjligheter i sina projekt, vilket förbättrar användarupplevelsen och produktiviteten. I den här handledningen kommer vi att utforska hur man ställer in bildstorleksgränser med GroupDocs.Viewer för .NET, vilket säkerställer optimal visning av dokument samtidigt som prestanda och effektivitet bibehålls.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1.  GroupDocs.Viewer för .NET: Se till att du har det nödvändiga GroupDocs.Viewer för .NET-biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner den från[hemsida](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Konfigurera din föredragna .NET-utvecklingsmiljö, som Visual Studio, med de nödvändiga konfigurationerna.
3. Dokumentkatalog: Ha en utsedd katalog där dina dokument lagras och se till att katalogsökvägen är tillgänglig i ditt program.

## Importera namnområden
Innan du fortsätter med implementeringen är det viktigt att importera de nödvändiga namnområdena för att effektivt få tillgång till funktionerna i GroupDocs.Viewer för .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Definiera utdatakatalog och filsökväg
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
 Se till att byta ut`"Your Document Directory"` med den faktiska sökvägen till din dokumentkatalog.
## Steg 2: Initiera visningsobjekt och ange dokumentsökväg
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX representerar sökvägen till exempeldokumentet.
    // Ersätt den med sökvägen till önskat dokument.
```
 Byta ut`TestFiles.SAMPLE_DOCX` med sökvägen till ditt dokument. Detta kan vara ett DOCX, PDF eller något annat filformat som stöds.
## Steg 3: Konfigurera JPEG-vyalternativ
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
 Justera`MaxWidth` egenskap för att ställa in den maximala bredden på den renderade bilden enligt dina krav. Detta säkerställer att bilden inte överskrider den angivna bredden, vilket bibehåller optimal visning.
## Steg 4: Återge dokument med specificerade alternativ
```csharp
viewer.View(options);
```
Denna kodrad utlöser renderingsprocessen och genererar utdatabilden med de definierade storleksgränserna.
## Steg 5: Visa framgångsmeddelande
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Efter framgångsrik rendering visas ett meddelande som indikerar framgångsrikt slutförande tillsammans med utdatakatalogens sökväg.

## Slutsats
Sammanfattningsvis, att behärska konsten att ställa in bildstorleksgränser med GroupDocs.Viewer för .NET kan avsevärt förbättra dokumentvisningsupplevelsen i dina .NET-applikationer. Genom att följa den steg-för-steg-guide som beskrivs i denna handledning kan du enkelt optimera bildvisningen samtidigt som du säkerställer prestanda och effektivitet.
## FAQ's
### Kan jag ställa in både maximal bredd och höjd för de renderade bilderna?
Ja, du kan ställa in både maximal bredd och höjd med lämpliga egenskaper i vyalternativen.
### Vilka dokumentformat stöds av GroupDocs.Viewer för .NET?
GroupDocs.Viewer för .NET stöder ett brett utbud av dokumentformat, inklusive DOCX, PDF, PPT, XLS och mer.
### Är GroupDocs.Viewer för .NET kompatibel med .NET Core?
Ja, GroupDocs.Viewer för .NET erbjuder kompatibilitet med .NET Core, vilket möjliggör sömlös integrering i moderna .NET-applikationer.
### Kan jag anpassa det utgående bildformatet annat än JPEG?
Ja, GroupDocs.Viewer för .NET ger stöd för olika utdataformat, inklusive PNG, TIFF och PDF.
### Finns det en testversion tillgänglig för testning innan du köper?
 Ja, du kan använda en gratis testversion från[hemsida](https://releases.groupdocs.com/viewer/net/). att utforska funktionerna och funktionerna i GroupDocs.Viewer för .NET innan du gör ett köp.