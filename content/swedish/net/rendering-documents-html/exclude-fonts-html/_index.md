---
"description": "Lär dig hur du exkluderar teckensnitt från renderad HTML med GroupDocs.Viewer för .NET. Följ den här steg-för-steg-guiden för sömlös dokumentvisning."
"linktitle": "Exkludera teckensnitt från renderad HTML"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Exkludera teckensnitt från renderad HTML"
"url": "/sv/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# Exkludera teckensnitt från renderad HTML

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt dokumentrenderingsbibliotek som låter utvecklare visa över 50 dokumentformat i sina .NET-applikationer utan behov av externa beroenden. I den här handledningen fokuserar vi på en specifik funktion i GroupDocs.Viewer: att exkludera teckensnitt från renderad HTML-utdata. 
## Förkunskapskrav
Innan du börjar, se till att du har följande:
1. Grundläggande förståelse för C# och .NET-utveckling.
2. GroupDocs.Viewer för .NET installerat. Du kan ladda ner det från [här](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio eller någon annan IDE för C#-utveckling.

## Importera namnrymder
Se till att inkludera nödvändiga namnrymder i din C#-kod:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Steg 1: Definiera utdatakatalog
Ställ in katalogen där du vill att de renderade HTML-filerna ska sparas.
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera format för sidfilens sökväg
Ange formatet för filsökvägarna för enskilda sidor i det renderade dokumentet.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Initiera visningsobjektet
Instansiera Viewer-objektet med det dokument du vill rendera.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Din kod hamnar här
}
```
## Steg 4: Ange HTML-visningsalternativ
Definiera alternativen för HTML-rendering, inklusive formatet för inbäddade resurser och teckensnitt som ska exkluderas.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Steg 5: Rendera dokument
Skicka HTML-visningsalternativen till Viewer-objektet för att rendera dokumentet.
```csharp
viewer.View(options);
```
## Steg 6: Plats för utdatarenderat dokument
Informera användaren om var de renderade HTML-filerna sparas.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
I den här handledningen har vi lärt oss hur man använder GroupDocs.Viewer för .NET för att exkludera teckensnitt från renderad HTML-utdata. Genom att följa stegen som beskrivs ovan kan du anpassa renderingsprocessen för att möta dina specifika krav och säkerställa optimal visning av dokument i dina applikationer.
## Vanliga frågor
### Kan jag exkludera flera teckensnitt från den renderade HTML-koden?
Ja, du kan lägga till flera teckensnittsnamn till `FontsToExclude` lista i HTML-vyalternativen.
### Är GroupDocs.Viewer kompatibel med alla .NET-ramverk?
Ja, GroupDocs.Viewer stöder .NET Framework 4.6.1 och senare.
### Kan jag rendera dokument från fjärrlagringsplatser?
Ja, GroupDocs.Viewer stöder rendering av dokument från lokal lagring samt fjärrlagringsplatser och strömmar.
### Stöder GroupDocs.Viewer responsiv design för HTML-utdata?
Ja, du kan aktivera responsiv rendering genom att justera HTML-visningsalternativen därefter.
### Finns teknisk support tillgänglig för GroupDocs.Viewer?
Ja, du kan söka hjälp och delta i diskussioner om [GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).