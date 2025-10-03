---
"description": "Lär dig hur du aktiverar lagerrendering i PDF-dokument med GroupDocs.Viewer för .NET. Förbättra dokumentvisningsupplevelsen utan ansträngning."
"linktitle": "Aktivera lagerrendering i PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Aktivera lagerrendering i PDF"
"url": "/sv/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
type: docs
---
# Aktivera lagerrendering i PDF

## Introduktion
den här handledningen ska vi gå in på processen att aktivera lagerrendering i PDF-dokument med GroupDocs.Viewer för .NET. Lagerrendering möjliggör förbättrad dokumentvisning och manipulation, vilket ger användarna en mer interaktiv visningsupplevelse.

![Aktivera lagerrendering i PDF med GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Förkunskapskrav
Innan vi börjar, se till att du har följande förutsättningar:
1. GroupDocs.Viewer för .NET: Se till att du har installerat det paket eller bibliotek som krävs för att använda GroupDocs.Viewer för .NET i ditt projekt.
2. Visual Studio: Du bör ha Visual Studio installerat på ditt system för att kunna koda och köra de medföljande exemplen.
3. Grundläggande förståelse för C#: Den här handledningen förutsätter att du är förtrogen med syntax och koncept i programmeringsspråket C#.

## Importera namnrymder
Börja med att importera de namnrymder som krävs till ditt projekt:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Se till att ange katalogsökvägen där du vill att den renderade utdata ska sparas.
## Steg 2: Definiera format för sidfilens sökväg
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Det här steget anger formatet för filsökvägarna för enskilda sidor i den renderade utdata. `{0}` är en platshållare för sidnumret.
## Steg 3: Aktivera lagerrendering
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Här skapar vi en `Viewer` objektet och ange PDF-dokumentet som ska bearbetas. Vi konfigurerar sedan `HtmlViewOptions` med det definierade formatet för sökvägen till sidfilen. Genom att ställa in `EnableLayeredRendering` egendom till `true` i `PdfOptions`, aktiverar vi lagervis rendering för PDF-dokumentet.
## Steg 4: Visa utdatakatalogen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Slutligen skriver vi ut ett meddelande som indikerar att källdokumentet har renderats och uppmanar användaren att kontrollera utdata i den angivna katalogen.

## Slutsats
Att aktivera lagerrendering i PDF-dokument med GroupDocs.Viewer för .NET förbättrar dokumentvisningsfunktionerna och ger användarna en rikare och mer interaktiv upplevelse. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera den här funktionen i dina .NET-applikationer.
## Vanliga frågor
### Vad är lagerrendering i PDF-dokument?
Skiktad rendering möjliggör separering och manipulation av olika komponenter i ett PDF-dokument, vilket möjliggör interaktiv visning och en förbättrad användarupplevelse.
### Kan jag anpassa utdatakatalogen för renderade dokument?
Ja, du kan ange vilken katalogsökväg som helst för utdata enligt dina behov.
### Stöder GroupDocs.Viewer andra filformat förutom PDF?
Ja, GroupDocs.Viewer stöder en mängd olika dokumentformat, inklusive Word, Excel, PowerPoint och fler.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer är kompatibel med både .NET Framework- och .NET Core-miljöer.
### Var kan jag hitta ytterligare stöd eller hjälp?
Du kan besöka GroupDocs.Viewer-forumet för frågor eller hjälp angående visningsprogrambiblioteket.