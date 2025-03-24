---
title: Justera bildkvaliteten i PDF
linktitle: Justera bildkvaliteten i PDF
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du justerar bildkvaliteten i PDF-dokument med GroupDocs.Viewer för .NET. Följ vår steg-för-steg handledning för sömlös integration.
weight: 10
url: /sv/net/pdf-rendering-options/adjust-image-quality-pdf/
---

# Justera bildkvaliteten i PDF

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt bibliotek som tillåter utvecklare att integrera dokumentåtergivningsmöjligheter i sina .NET-applikationer utan ansträngning. En av nyckelfunktionerna i detta bibliotek är möjligheten att justera bildkvaliteten vid rendering av PDF-dokument. I den här handledningen går vi igenom processen att justera bildkvaliteten steg för steg med hjälp av GroupDocs.Viewer för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Grundläggande kunskaper i C#-programmering.
2. Visual Studio installerat på ditt system.
3. GroupDocs.Viewer för .NET-bibliotek har laddats ner och installerats. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).

## Importera namnområden
Först måste du importera de nödvändiga namnområdena för att arbeta med GroupDocs.Viewer för .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
 Byta ut`"Your Document Directory"` med sökvägen där du vill spara de renderade HTML-sidorna.
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Den här raden definierar formatet för filsökvägen för varje renderad HTML-sida.`{0}` är en platshållare för sidnumret.
## Steg 3: Justera bildkvaliteten
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 Byta ut`"Your PDF File Path"` med sökvägen till ditt PDF-dokument.
## Steg 4: Visa utdatasökväg
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Den här raden visar sökvägen där de renderade HTML-sidorna sparas.

## Slutsats
I den här handledningen har vi lärt oss hur du justerar bildkvaliteten när du renderar PDF-dokument med GroupDocs.Viewer för .NET. Genom att följa de enkla stegen ovan kan du enkelt anpassa bildkvaliteten efter dina krav.
## FAQ's
### Kan jag justera bildkvaliteten för andra dokumentformat än PDF?
Ja, GroupDocs.Viewer för .NET stöder olika dokumentformat, och du kan justera bildkvaliteten för de flesta av dem.
### Vilka är de tillgängliga bildkvalitetsalternativen?
GroupDocs.Viewer för .NET ger alternativ för låg, medium och hög bildkvalitet.
### Finns det något sätt att förhandsgranska dokumentet innan du renderar det med justerad bildkvalitet?
Ja, du kan använda GroupDocs.Viewer för .NET för att generera dokumentförhandsvisningar med olika bildkvalitetsinställningar.
### Kräver GroupDocs.Viewer för .NET en licens för kommersiellt bruk?
 Ja, du måste skaffa en licens för kommersiell användning. Du kan köpa en licens från[här](https://purchase.groupdocs.com/buy).
### Var kan jag få support för GroupDocs.Viewer för .NET?
 Du kan få support från GroupDocs.Viewer-forumet[här](https://forum.groupdocs.com/c/viewer/9).