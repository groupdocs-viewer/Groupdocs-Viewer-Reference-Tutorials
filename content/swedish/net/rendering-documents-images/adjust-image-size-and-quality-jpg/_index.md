---
title: Justera bildstorlek och kvalitet (JPG)
linktitle: Justera bildstorlek och kvalitet (JPG)
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du optimerar bildstorlek och kvalitet i JPEG-format med Groupdocs.Viewer för .NET. Förbättra din dokumentvisningsupplevelse.
weight: 11
url: /sv/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---

# Justera bildstorlek och kvalitet (JPG)

## Introduktion
Groupdocs.Viewer för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att sömlöst integrera dokumentvisningsfunktioner i sina .NET-applikationer. Ett vanligt krav i dokumentvisningsapplikationer är möjligheten att justera storleken och kvaliteten på bilder, särskilt när det gäller JPEG-bilder (JPG). I den här självstudien går vi igenom processen att justera bildstorlek och kvalitet med Groupdocs.Viewer för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Grundläggande förståelse för programmeringsspråket C#.
2. Visual Studio installerat på ditt system.
3.  Groupdocs.Viewer för .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).

## Importera namnområden
Först måste du importera de nödvändiga namnrymden till din C#-kod. Dessa namnområden ger åtkomst till de klasser och metoder som krävs för att arbeta med Groupdocs.Viewer.
## Steg 1: Importera namnområden
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss nu dela upp exempelkoden som tillhandahålls i flera steg för en bättre förståelse.
## Steg 2: Ställ in utdatakatalog och sidfilssökvägsformat
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
I det här steget anger vi utdatakatalogen där de renderade bilderna ska sparas och definierar formatet för filsökvägen för varje sidbild.
## Steg 3: Initiera Viewer och konfigurera JPG-vyalternativ
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Här initierar vi Viewer-objektet med sökvägen till dokumentet som ska visas. Sedan skapar vi en instans av JpgViewOptions och ställer in önskad bredd och höjd för JPEG-bilderna.
## Steg 4: Återge källdokument
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Slutligen skriver vi ut ett meddelande som indikerar framgångsrik rendering av källdokumentet och platsen där utdatabilderna sparas.

## Slutsats
den här handledningen har vi lärt oss hur man justerar storleken och kvaliteten på JPEG-bilder med Groupdocs.Viewer för .NET. Genom att följa stegen som beskrivs ovan kan du enkelt införliva denna funktion i dina .NET-applikationer, vilket ger användarna en optimerad bildvisningsupplevelse.
## FAQ's
### Kan jag justera bildkvaliteten också?
Ja, du kan justera bildkvaliteten genom att ställa in egenskapen Quality i JpgViewOptions.
### Vilka dokumentformat stöds av Groupdocs.Viewer för .NET?
Groupdocs.Viewer för .NET stöder ett brett utbud av dokumentformat inklusive DOCX, PDF, PPTX, XLSX och mer.
### Är Groupdocs.Viewer för .NET kompatibel med .NET Core?
Ja, Groupdocs.Viewer för .NET är kompatibel med .NET Core tillsammans med det traditionella .NET Framework.
### Kan jag anpassa namngivningsformatet för utdatafilen?
Ja, du kan anpassa namngivningsformatet för utdatafilen genom att ändra variabeln pageFilePathFormat i koden.
### Stöder Groupdocs.Viewer för .NET dokumentkommentarer?
Ja, Groupdocs.Viewer för .NET ger omfattande stöd för dokumentkommentarer inklusive textmarkering, understrykningar och kommentarer.