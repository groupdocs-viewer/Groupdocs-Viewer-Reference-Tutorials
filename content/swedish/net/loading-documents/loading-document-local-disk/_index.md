---
"description": "Lär dig hur du sömlöst renderar dokument från din lokala disk med Groupdocs.Viewer för .NET. Förbättra dina .NET-applikationer med effektiv dokumenthantering."
"linktitle": "Läs in dokument från lokal disk"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Läs in dokument från lokal disk"
"url": "/sv/net/loading-documents/loading-document-local-disk/"
"weight": 10
type: docs
---
# Läs in dokument från lokal disk

## Introduktion
I dagens digitala tidsålder är effektiv dokumentrendering avgörande för olika applikationer. Groupdocs.Viewer för .NET erbjuder en kraftfull lösning för att rendera dokument direkt från din lokala disk. I den här handledningen guidar vi dig genom processen att ladda dokument från din lokala disk med Groupdocs.Viewer för .NET. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här steg-för-steg-guiden dig att sömlöst integrera dokumentrendering i dina .NET-applikationer.

![Ladda dokument från lokal disk med GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-local-disk.png)

## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förkunskaper:
1. Groupdocs.Viewer för .NET: Ladda ner och installera den senaste versionen från [här](https://releases.groupdocs.com/viewer/net/).
2. .NET-utvecklingsmiljö: Se till att du har en fungerande .NET-utvecklingsmiljö konfigurerad på ditt system.
3. Lokala dokument: Lagra de dokument du vill rendera lokalt på din disk.

## Importera namnrymder
Först, låt oss importera de namnrymder som behövs för att komma åt funktionerna i Groupdocs.Viewer för .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Ladda dokument från lokal disk
Börja med att konfigurera utdatakatalogen där de renderade HTML-sidorna ska sparas.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 2: Initiera visningsprogrammet och rendera dokument
Initiera Viewer-objektet med dokumentets sökväg och rendera det med HTML-visningsalternativ.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Steg 3: Displayutgång
När renderingen är klar visas ett meddelande som anger att källdokumentet har renderats och var utdatafilerna finns.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Grattis! Du har nu lärt dig hur du laddar dokument från din lokala disk med Groupdocs.Viewer för .NET. Det här kraftfulla verktyget öppnar upp en värld av möjligheter för dokumentrendering i dina .NET-applikationer.
## Vanliga frågor
### Kan jag rendera dokument i olika format med Groupdocs.Viewer för .NET?
Ja, Groupdocs.Viewer för .NET stöder ett brett utbud av dokumentformat, inklusive DOCX, PDF, XLSX, PPTX med flera.
### Är Groupdocs.Viewer för .NET kompatibelt med alla .NET-ramverk?
Groupdocs.Viewer för .NET är kompatibel med de flesta .NET-ramverk, inklusive .NET Core, .NET Framework och .NET Standard.
### Kan jag anpassa renderingsalternativen för mina dokument?
Absolut! Groupdocs.Viewer för .NET erbjuder omfattande anpassningsalternativ som gör att du kan skräddarsy renderingsprocessen efter dina specifika behov.
### Finns det en testversion tillgänglig för Groupdocs.Viewer för .NET?
Ja, du kan ladda ner en gratis testversion från [här](https://releases.groupdocs.com/).
### Var kan jag hitta support eller ytterligare resurser för Groupdocs.Viewer för .NET?
För support och ytterligare resurser, besök Groupdocs.Viewer för .NET. [forum](https://forum.groupdocs.com/c/viewer/9).