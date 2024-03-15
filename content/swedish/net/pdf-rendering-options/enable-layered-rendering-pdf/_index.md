---
title: Aktivera Layered Rendering i PDF
linktitle: Aktivera Layered Rendering i PDF
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du aktiverar lagerrendering i PDF-dokument med GroupDocs.Viewer för .NET. Förbättra dokumentvisningsupplevelsen utan ansträngning.
type: docs
weight: 15
url: /sv/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Introduktion
I den här självstudien kommer vi att fördjupa oss i processen för att aktivera skiktad rendering i PDF-dokument med GroupDocs.Viewer för .NET. Layered rendering möjliggör förbättrad dokumentvisning och manipulering, vilket ger användarna en mer interaktiv tittarupplevelse.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. GroupDocs.Viewer för .NET: Se till att du har installerat det nödvändiga paketet eller biblioteket för att använda GroupDocs.Viewer för .NET i ditt projekt.
2. Visual Studio: Du bör ha Visual Studio installerat på ditt system för kodning och exekvering av exemplen.
3. Grundläggande förståelse för C#: Denna handledning förutsätter bekantskap med C#s programmeringsspråkssyntax och begrepp.

## Importera namnområden
Börja med att importera de nödvändiga namnrymden till ditt projekt:
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
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Detta steg ställer in formatet för filsökvägarna för enskilda sidor i den renderade utdata.`{0}` är en platshållare för sidnumret.
## Steg 3: Aktivera Layered Rendering
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Här skapar vi en`Viewer` objekt och ange PDF-dokumentet som ska bearbetas. Vi konfigurerar sedan`HtmlViewOptions` med det definierade sökvägsformatet för sidan. Genom att sätta`EnableLayeredRendering` egendom till`true` i`PdfOptions`, aktiverar vi lagerrendering för PDF-dokumentet.
## Steg 4: Visa utdatakatalog
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Slutligen skriver vi ut ett meddelande som indikerar framgångsrik rendering av källdokumentet och uppmanar användaren att kontrollera utdata i den angivna katalogen.

## Slutsats
Genom att aktivera skiktad rendering i PDF-dokument med GroupDocs.Viewer för .NET förbättras dokumentvisningsmöjligheterna, vilket ger användarna en rikare och mer interaktiv upplevelse. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera den här funktionen i dina .NET-applikationer.
## FAQ's
### Vad är skiktad rendering i PDF-dokument?
Layered rendering möjliggör separation och manipulering av olika komponenter i ett PDF-dokument, vilket möjliggör interaktiv visning och förbättrad användarupplevelse.
### Kan jag anpassa utdatakatalogen för renderade dokument?
Ja, du kan ange valfri katalogsökväg för utdata enligt dina krav.
### Stöder GroupDocs.Viewer andra filformat än PDF?
Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat inklusive Word, Excel, PowerPoint och mer.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer är kompatibel med både .NET Framework- och .NET Core-miljöer.
### Var kan jag hitta ytterligare stöd eller hjälp?
Du kan besöka GroupDocs.Viewer-forumet för alla frågor eller hjälp angående tittarbiblioteket.