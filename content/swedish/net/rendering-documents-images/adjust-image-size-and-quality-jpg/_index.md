---
"description": "Lär dig hur du optimerar bildstorlek och kvalitet i JPEG-format med Groupdocs.Viewer för .NET. Förbättra din dokumentvisningsupplevelse."
"linktitle": "Justera bildstorlek och kvalitet (JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Justera bildstorlek och kvalitet (JPG)"
"url": "/sv/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
type: docs
---
# Justera bildstorlek och kvalitet (JPG)

## Introduktion
Groupdocs.Viewer för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att sömlöst integrera dokumentvisningsfunktioner i sina .NET-applikationer. Ett vanligt krav i dokumentvisningsprogram är möjligheten att justera storlek och kvalitet på bilder, särskilt när det gäller JPEG-bilder (JPG). I den här handledningen guidar vi dig genom processen att justera bildstorlek och kvalitet med Groupdocs.Viewer för .NET.
## Förkunskapskrav
Innan vi börjar, se till att du har följande:
1. Grundläggande förståelse för programmeringsspråket C#.
2. Visual Studio installerat på ditt system.
3. Groupdocs.Viewer för .NET-biblioteket är installerat. Du kan ladda ner det från [här](https://releases.groupdocs.com/viewer/net/).

## Importera namnrymder
Först måste du importera de nödvändiga namnrymderna till din C#-kod. Dessa namnrymder ger åtkomst till de klasser och metoder som krävs för att arbeta med Groupdocs.Viewer.
## Steg 1: Importera namnrymder
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu ska vi dela upp exempelkoden i flera steg för en bättre förståelse.
## Steg 2: Ställ in utdatakatalog och sökvägsformat för sidfil
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
I det här steget anger vi utdatakatalogen där de renderade bilderna ska sparas och definierar formatet för filsökvägen för varje sidbild.
## Steg 3: Initiera visningsprogrammet och konfigurera JPG-visningsalternativ
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
## Steg 4: Rendera källdokument
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Slutligen skriver vi ut ett meddelande som anger att källdokumentet har renderats och var utdatabilderna sparas.

## Slutsats
den här handledningen har vi lärt oss hur man justerar storleken och kvaliteten på JPEG-bilder med Groupdocs.Viewer för .NET. Genom att följa stegen som beskrivs ovan kan du enkelt integrera den här funktionen i dina .NET-applikationer, vilket ger användarna en optimerad bildvisningsupplevelse.
## Vanliga frågor
### Kan jag justera bildkvaliteten också?
Ja, du kan justera bildkvaliteten genom att ställa in egenskapen Kvalitet i JpgViewOptions.
### Vilka dokumentformat stöds av Groupdocs.Viewer för .NET?
Groupdocs.Viewer för .NET stöder ett brett utbud av dokumentformat, inklusive DOCX, PDF, PPTX, XLSX och mer.
### Är Groupdocs.Viewer för .NET kompatibelt med .NET Core?
Ja, Groupdocs.Viewer för .NET är kompatibelt med .NET Core tillsammans med det traditionella .NET Framework.
### Kan jag anpassa namngivningsformatet för utdatafilerna?
Ja, du kan anpassa namngivningsformatet för utdatafilerna genom att ändra variabeln pageFilePathFormat i koden.
### Har Groupdocs.Viewer för .NET stöd för dokumentanteckningar?
Ja, Groupdocs.Viewer för .NET erbjuder omfattande stöd för dokumentanteckningar, inklusive textmarkering, understrykning och kommentarer.