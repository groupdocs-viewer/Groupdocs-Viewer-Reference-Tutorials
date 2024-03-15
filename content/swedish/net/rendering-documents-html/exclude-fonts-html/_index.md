---
title: Uteslut teckensnitt från renderad HTML
linktitle: Uteslut teckensnitt från renderad HTML
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du utesluter teckensnitt från renderad HTML med GroupDocs.Viewer för .NET. Följ denna steg-för-steg-guide för sömlös dokumentvisning.
type: docs
weight: 10
url: /sv/net/rendering-documents-html/exclude-fonts-html/
---
## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt dokumentåtergivningsbibliotek som tillåter utvecklare att visa över 50 dokumentformat i sina .NET-applikationer utan behov av externa beroenden. I den här handledningen kommer vi att fokusera på en specifik funktion i GroupDocs.Viewer: exkludera teckensnitt från HTML-utdata. 
## Förutsättningar
Innan du börjar, se till att du har följande:
1. Grundläggande förståelse för C# och .NET utveckling.
2.  GroupDocs.Viewer för .NET installerat. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio eller någon annan IDE för C#-utveckling.

## Importera namnområden
Se till att inkludera de nödvändiga namnrymden i din C#-kod:
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
## Steg 2: Definiera sidfilssökvägsformat
Ange formatet för filsökvägarna för enskilda sidor i det renderade dokumentet.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Initiera Viewer Object
Instantiera Viewer-objektet med dokumentet du vill rendera.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Din kod kommer hit
}
```
## Steg 4: Ställ in HTML-vyalternativ
Definiera alternativen för HTML-rendering, inklusive formatet på inbäddade resurser och teckensnitt som ska uteslutas.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Steg 5: Gör dokumentet
Skicka HTML-vyalternativen till Viewer-objektet för att rendera dokumentet.
```csharp
viewer.View(options);
```
## Steg 6: Mata ut plats för renderat dokument
Informera användaren om platsen där de renderade HTML-filerna sparas.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
I den här handledningen har vi lärt oss hur man använder GroupDocs.Viewer för .NET för att utesluta teckensnitt från HTML-utdata. Genom att följa stegen som beskrivs ovan kan du anpassa renderingsprocessen för att uppfylla dina specifika krav, vilket säkerställer optimal visning av dokument i dina applikationer.
## FAQ's
### Kan jag utesluta flera teckensnitt från den renderade HTML-koden?
 Ja, du kan lägga till flera teckensnittsnamn till`FontsToExclude` lista i HTML-vyalternativen.
### Är GroupDocs.Viewer kompatibel med alla .NET-ramverk?
Ja, GroupDocs.Viewer stöder .NET Framework 4.6.1 och högre.
### Kan jag återge dokument från fjärrlagringsplatser?
Ja, GroupDocs.Viewer stöder rendering av dokument från lokal lagring samt fjärrlagringsplatser och strömmar.
### Stöder GroupDocs.Viewer responsiv design för HTML-utdata?
Ja, du kan aktivera responsiv rendering genom att justera HTML-vyalternativen därefter.
### Finns teknisk support tillgänglig för GroupDocs.Viewer?
 Ja, du kan söka hjälp och delta i diskussioner om[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).