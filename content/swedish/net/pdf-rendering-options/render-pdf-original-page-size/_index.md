---
"description": "Lär dig hur du renderar PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET. Följ vår steg-för-steg-guide och integrera sömlöst den här funktionen."
"linktitle": "Rendera PDF med original sidstorlek"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera PDF med original sidstorlek"
"url": "/sv/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
type: docs
---
# Rendera PDF med original sidstorlek

## Introduktion
Inom .NET-utveckling framstår GroupDocs.Viewer som ett kraftfullt verktyg för att rendera olika dokumentformat, inklusive PDF-filer. Ett vanligt krav vid dokumenthantering är att rendera PDF-filer samtidigt som de behåller sina ursprungliga sidstorlekar. För att uppnå denna uppgift utan problem krävs en omfattande förståelse av GroupDocs.Viewer för .NET och dess funktioner.

![Rendera PDF med original sidstorlek med GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Förkunskapskrav
Innan du börjar rendera PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET, se till att du har följande förutsättningar på plats:
### 1. Installera GroupDocs.Viewer för .NET
Börja med att ladda ner GroupDocs.Viewer-biblioteket från webbplatsen. Du kan hämta biblioteket från den medföljande [nedladdningslänk](https://releases.groupdocs.com/viewer/net/)Följ installationsanvisningarna i dokumentationen för att integrera det effektivt i ditt .NET-projekt.
### 2. Konfigurera utvecklingsmiljön
Se till att du har en utvecklingsmiljö konfigurerad för .NET-utveckling. Detta inkluderar att ha en kompatibel IDE installerad, till exempel Visual Studio, och grundläggande förståelse för C#-programmering.
### 3. Hämta ett PDF-dokument
Du behöver ett exempel på en PDF-fil för att rendera den med GroupDocs.Viewer. Du kan använda vilket PDF-dokument som helst för teständamål. Om du inte har något kan du ladda ner ett exempel på en PDF-fil från olika onlinekällor.

## Importera namnrymder
Innan du fortsätter med att rendera PDF-filer är det viktigt att importera nödvändiga namnrymder till ditt C#-projekt. Det här steget ger dig åtkomst till nödvändiga klasser och metoder från GroupDocs.Viewer-biblioteket.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu när du har förutsättningarna på plats och de nödvändiga namnrymderna importerats, låt oss dela upp processen för att rendera PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET i enkla steg:
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Se till att du anger katalogen där du vill att de renderade sidorna ska sparas. `"Your Document Directory"` med sökvägen till önskad katalog.
## Steg 2: Definiera format för sidfilens sökväg
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Ställ in formatet för namngivning av de renderade sidfilerna. I det här exemplet sparas sidorna som PNG-bilder med filnamn i formatet `"page_1.png"`, `"page_2.png"`, och så vidare.
## Steg 3: Rendera PDF med original sidstorlek
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Instansiera en `Viewer` objektet med sökvägen till din PDF-fil. Skapa sedan `PngViewOptions` med det angivna formatet för sökvägen till sidfilen. Ställ in `RenderOriginalPageSize` egendom till `true` för att bevara de ursprungliga sidstorlekarna under rendering.
## Steg 4: Visa platsen för det renderade dokumentet
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Skriv ut ett meddelande som indikerar att renderingen lyckades och ange katalogen där de renderade sidorna sparas.

## Slutsats
Att rendera PDF-filer med ursprungliga sidstorlekar med GroupDocs.Viewer för .NET är en enkel process när du följer stegen som beskrivs i den här handledningen. Genom att importera nödvändiga namnrymder och följa steg-för-steg-guiden kan du sömlöst integrera den här funktionen i dina .NET-applikationer.
## Vanliga frågor
### Kan GroupDocs.Viewer rendera andra dokumentformat förutom PDF?
Ja, GroupDocs.Viewer stöder rendering av olika dokumentformat, inklusive Word, Excel, PowerPoint med flera.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer är kompatibel med både .NET Framework- och .NET Core-miljöer.
### Kan jag anpassa utdataformatet för renderade sidor?
Ja, du kan anpassa utdataformatet genom att justera alternativen som tillhandahålls av GroupDocs.Viewer, till exempel att ställa in olika bildformat eller ange anpassade renderingsalternativ.
### Erbjuder GroupDocs.Viewer stöd för molnbaserad dokumentrendering?
Ja, GroupDocs.Viewer tillhandahåller API:er för molnbaserad dokumentrendering, vilket gör att du kan rendera dokument direkt från molnlagringsleverantörer.
### Finns det en gratis provversion av GroupDocs.Viewer?
Ja, du kan utforska GroupDocs.Viewer med en gratis provperiod genom att besöka den medföljande [länk](https://releases.groupdocs.com/).