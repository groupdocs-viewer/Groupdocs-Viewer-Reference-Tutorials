---
title: Återge arkiv till enstaka eller flera HTML-sidor
linktitle: Återge arkiv till enstaka eller flera HTML-sidor
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar arkiv till HTML-sidor med GroupDocs.Viewer för .NET. Integrera enkelt dokumentvisningsmöjligheter i dina .NET-applikationer.
weight: 12
url: /sv/net/rendering-archive-files/render-archives-html/
---
## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt dokumentåtergivningsbibliotek som låter utvecklare enkelt integrera dokumentvisningsmöjligheter i sina .NET-applikationer. Oavsett om du behöver rendera arkiv till enstaka eller flera HTML-sidor, kommer den här handledningen att guida dig genom processen steg för steg.
## Förutsättningar
Innan du dyker in i den här handledningen, se till att du har följande förutsättningar:
1.  GroupDocs.Viewer för .NET: Se till att du har biblioteket installerat i ditt projekt. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Ha en fungerande utvecklingsmiljö inrättad för .NET-utveckling.
3. Dokumentkatalog: Förbered en katalog där dina dokument lagras.
4. Grundläggande förståelse för C#: Bekanta dig med grunderna i programmeringsspråket i C#.

## Importera namnområden
Se till att importera de nödvändiga namnrymden i din C#-kod:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Följ dessa steg för att återge arkiv till enstaka eller flera HTML-sidor med GroupDocs.Viewer för .NET:
## Steg 1: Ställ in utdatakatalog
Definiera katalogen där du vill att de renderade HTML-sidorna ska sparas:
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera filsökvägsformat
Ange filsökvägsformatet för HTML-sidorna. För ensidig rendering:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
För flersidig rendering:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Steg 3: Rendera HTML till en sida
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Steg 4: Återge HTML till flera sidor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Ställ in objekt per sida
    viewer.View(options);
}
```
## Steg 5: Kontrollera utdata
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Att rendera arkiv till HTML-sidor med GroupDocs.Viewer för .NET är en enkel process. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera dokumentvisningsmöjligheter i dina .NET-applikationer.
## FAQ's
### Kan jag återge andra dokumentformat än arkiv?
Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat inklusive PDF, DOCX, XLSX, PPTX och mer.
### Är GroupDocs.Viewer lämplig för både skrivbords- och webbapplikationer?
Absolut, GroupDocs.Viewer kan användas i både skrivbords- och webbapplikationer sömlöst.
### Erbjuder GroupDocs.Viewer anpassningsalternativ för visningsgränssnittet?
Ja, du kan anpassa visningsgränssnittet efter dina krav.
### Kan jag rendera dokument asynkront med GroupDocs.Viewer?
Ja, GroupDocs.Viewer tillhandahåller asynkron renderingsfunktioner för förbättrad prestanda.
### Stöder GroupDocs.Viewer dokumentkommentarer?
Ja, GroupDocs.Viewer tillåter användare att se och hantera dokumentkommentarer effektivt.