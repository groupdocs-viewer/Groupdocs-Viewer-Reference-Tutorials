---
title: Återge PDF med original sidstorlek
linktitle: Återge PDF med original sidstorlek
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET. Följ vår steg-för-steg-guide och integrera denna funktion sömlöst.
weight: 17
url: /sv/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Introduktion
Inom .NET-utvecklingen framstår GroupDocs.Viewer som ett kraftfullt verktyg för att rendera olika dokumentformat, inklusive PDF-filer. Ett vanligt krav vid dokumenthantering är att rendera PDF-filer samtidigt som de behåller sina ursprungliga sidstorlekar. För att uppnå denna uppgift sömlöst krävs en omfattande förståelse av GroupDocs.Viewer för .NET och dess funktioner.
## Förutsättningar
Innan du börjar rendera PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET, se till att du har följande förutsättningar:
### 1. Installera GroupDocs.Viewer för .NET
 Börja med att ladda ner GroupDocs.Viewer-biblioteket från webbplatsen. Du kan hämta biblioteket från det tillhandahållna[nedladdningslänk](https://releases.groupdocs.com/viewer/net/). Följ installationsinstruktionerna i dokumentationen för att effektivt integrera det i ditt .NET-projekt.
### 2. Ställ in utvecklingsmiljön
Se till att du har en utvecklingsmiljö inställd för .NET-utveckling. Detta inkluderar att ha en kompatibel IDE installerad, som Visual Studio, och en grundläggande förståelse för C#-programmering.
### 3. Skaffa ett PDF-dokument
Du behöver ett exempel på PDF-dokument för att rendera med GroupDocs.Viewer. Du kan använda vilket PDF-dokument som helst för teständamål. Om du inte har en, kan du ladda ner ett exempel på PDF från olika onlinekällor.

## Importera namnområden
Innan du fortsätter med att rendera PDF-filer är det viktigt att importera de nödvändiga namnrymden till ditt C#-projekt. Detta steg låter dig komma åt de klasser och metoder som krävs från GroupDocs.Viewer-biblioteket.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu när du har förutsättningarna på plats och de nödvändiga namnrymden importerade, låt oss dela upp processen för att rendera PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET i enkla steg:
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
 Se till att du anger katalogen där du vill att de renderade sidorna ska sparas. Byta ut`"Your Document Directory"` med sökvägen till din önskade katalog.
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Ställ in formatet för att namnge de renderade sidfilerna. I det här exemplet kommer sidorna att sparas som PNG-bilder med filnamn i formatet`"page_1.png"`, `"page_2.png"`, och så vidare.
## Steg 3: Återge PDF med originalsidans storlek
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Instantiera en`Viewer` objekt med sökvägen till din PDF-fil. Skapa sedan`PngViewOptions` med det angivna sökvägsformatet för sidan. Uppsättning`RenderOriginalPageSize` egendom till`true` för att bevara de ursprungliga sidstorlekarna under renderingen.
## Steg 4: Visa renderat dokumentplats
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Skriv ut ett meddelande som indikerar framgångsrik rendering och ange katalogen där de renderade sidorna sparas.

## Slutsats
Att rendera PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET är en enkel process när du följer stegen som beskrivs i den här handledningen. Genom att importera de nödvändiga namnområdena och följa den steg-för-steg-guiden kan du sömlöst integrera denna funktion i dina .NET-applikationer.
## FAQ's
### Kan GroupDocs.Viewer återge andra dokumentformat än PDF?
Ja, GroupDocs.Viewer stöder rendering av olika dokumentformat, inklusive Word, Excel, PowerPoint och mer.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer är kompatibel med både .NET Framework- och .NET Core-miljöer.
### Kan jag anpassa utdataformatet för renderade sidor?
Ja, du kan anpassa utdataformatet genom att justera alternativen som tillhandahålls av GroupDocs.Viewer, som att ställa in olika bildformat eller ange anpassade renderingsalternativ.
### Erbjuder GroupDocs.Viewer stöd för molnbaserad dokumentrendering?
Ja, GroupDocs.Viewer tillhandahåller API:er för molnbaserad dokumentrendering, så att du kan rendera dokument direkt från molnlagringsleverantörer.
### Finns det en gratis testversion tillgänglig för GroupDocs.Viewer?
 Ja, du kan utforska GroupDocs.Viewer med en gratis provperiod genom att besöka den medföljande[länk](https://releases.groupdocs.com/).