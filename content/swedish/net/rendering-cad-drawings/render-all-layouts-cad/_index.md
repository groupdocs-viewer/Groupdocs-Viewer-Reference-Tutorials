---
title: Gör alla layouter i CAD-ritningar
linktitle: Gör alla layouter i CAD-ritningar
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar alla layouter i CAD-ritningar med GroupDocs.Viewer för .NET. Följ vår omfattande handledning för sömlös integration.
type: docs
weight: 11
url: /sv/net/rendering-cad-drawings/render-all-layouts-cad/
---
## Introduktion
När det gäller dokumenthantering och visualisering står GroupDocs.Viewer för .NET högt som en mångsidig lösning som ger utvecklare möjlighet att utan ansträngning rendera olika dokumenttyper i sina .NET-applikationer. Bland dess otaliga funktioner finns förmågan att effektivt rendera CAD-ritningar, inklusive de intrikata layouter de innebär. I den här handledningen kommer vi att fördjupa oss i processen att utnyttja GroupDocs.Viewer för .NET för att rendera alla layouter som finns i CAD-ritningar. 
## Förutsättningar
Innan du börjar med den här handledningen, se till att du har följande förutsättningar:
1. Grundläggande förståelse för .NET-utveckling: Bekantskap med .NET-utvecklingsgrunderna kommer att vara fördelaktigt för att förstå implementeringsstegen som beskrivs i denna handledning.
2.  Installation av GroupDocs.Viewer för .NET: Se till att du har installerat GroupDocs.Viewer för .NET-biblioteket. Du kan ladda ner den från[hemsida](https://releases.groupdocs.com/viewer/net/).
3. CAD-ritningsfiler: Skaffa de CAD-ritningsfiler du tänker rendera. Dessa kan inkludera DWG-filer med flera layouter.
4. Utvecklingsmiljö: Konfigurera din föredragna utvecklingsmiljö med nödvändiga verktyg och beroenden.

## Importera namnområden
Se först till att du importerar de nödvändiga namnrymden till ditt .NET-projekt. Dessa namnrymder ger tillgång till de funktioner som behövs för att rendera CAD-ritningar med GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 2: Importera System.IO-namnutrymme
```csharp
using System.IO;
```
## Steg 1: Ange utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Definiera katalogen där du vill att den renderade utdata ska sparas.
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ställ in formatet för filsökvägarna för de renderade sidorna. I det här fallet kommer sidorna att sparas som HTML-filer.
## Steg 3: Instantiera Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Skapa en instans av Viewer-klassen och skicka sökvägen till CAD-ritningsfilen som en parameter.
## Steg 4: Konfigurera HTML-vyalternativ
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Konfigurera HTML-vyalternativen och ange att layouter ska renderas för CAD-ritningar.
## Steg 5: Gör CAD-ritning
```csharp
viewer.View(options);
```
Anropa View-metoden för Viewer-objektet och skicka de konfigurerade alternativen för att rendera CAD-ritningen.
## Steg 6: Visa utdatakatalog
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informera användaren om den framgångsrika renderingen och platsen för utdatakatalogen.

## Slutsats
den här handledningen har vi utforskat hur man använder GroupDocs.Viewer för .NET för att rendera alla layouter som finns i CAD-ritningar. Genom att följa den steg-för-steg-guide och implementera de medföljande kodavsnitten kan du sömlöst integrera den här funktionen i dina .NET-applikationer och därigenom förbättra dokumentvisualiseringsmöjligheterna.
## FAQ's
### Är GroupDocs.Viewer kompatibel med olika CAD-format?
Ja, GroupDocs.Viewer stöder rendering av CAD-ritningar i format som DWG och DXF.
### Kan jag anpassa renderingen enligt kraven i min applikation?
Absolut, GroupDocs.Viewer erbjuder ett brett utbud av alternativ för att anpassa renderingen, inklusive bildkvalitet, sidstorlek och mer.
### Kräver GroupDocs.Viewer några ytterligare licenser för kommersiellt bruk?
Ja, för kommersiellt bruk kan du behöva skaffa en licens. Du kan skaffa tillfälliga licenser för teständamål eller köpa en kommersiell licens från webbplatsen.
### Kan jag rendera CAD-ritningar asynkront med GroupDocs.Viewer?
Ja, GroupDocs.Viewer tillhandahåller asynkron renderingsmöjligheter, vilket möjliggör effektiv hantering av stora CAD-ritningar utan att blockera huvudtråden.
### Erbjuder GroupDocs.Viewer stöd för felsökning och teknisk assistans?
 Visst, du kan söka stöd och hjälp från GroupDocs.Viewer-gemenskapsforumet, tillgängligt[här](https://forum.groupdocs.com/c/viewer/9).