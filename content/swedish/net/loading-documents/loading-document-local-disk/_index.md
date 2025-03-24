---
title: Ladda dokument från lokal disk
linktitle: Ladda dokument från lokal disk
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du sömlöst renderar dokument från din lokala disk med Groupdocs.Viewer för .NET. Förbättra dina .NET-applikationer med effektiva dokument.
weight: 10
url: /sv/net/loading-documents/loading-document-local-disk/
---
## Introduktion
dagens digitala tidsålder är effektiv dokumentåtergivning avgörande för olika applikationer. Groupdocs.Viewer för .NET erbjuder en kraftfull lösning för att rendera dokument direkt från din lokala disk. I den här handledningen guidar vi dig genom processen att ladda dokument från din lokala disk med Groupdocs.Viewer för .NET. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här steg-för-steg-guiden dig att sömlöst integrera dokumentåtergivning i dina .NET-applikationer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
1.  Groupdocs.Viewer för .NET: Ladda ner och installera den senaste versionen från[här](https://releases.groupdocs.com/viewer/net/).
2. .NET-utvecklingsmiljö: Se till att du har en fungerande .NET-utvecklingsmiljö inställd på ditt system.
3. Lokala dokument: Ha de dokument du vill rendera lagrade lokalt på din disk.

## Importera namnområden
Låt oss först importera de nödvändiga namnområdena för att komma åt funktionerna i Groupdocs.Viewer för .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Ladda dokument från lokal disk
Börja med att ställa in utdatakatalogen där de renderade HTML-sidorna kommer att sparas.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 2: Initiera Viewer och rendera dokument
Initiera Viewer-objektet med dokumentets sökväg och rendera det med HTML-vyalternativ.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Steg 3: Visa utdata
När renderingen är klar visar du ett meddelande som indikerar framgångsrik rendering av källdokumentet och platsen för utdatafilerna.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du laddar dokument från din lokala disk med Groupdocs.Viewer för .NET. Detta kraftfulla verktyg öppnar upp en värld av möjligheter för dokumentrendering i dina .NET-applikationer.
## FAQ's
### Kan jag rendera dokument i olika format med Groupdocs.Viewer för .NET?
Ja, Groupdocs.Viewer för .NET stöder ett brett utbud av dokumentformat inklusive DOCX, PDF, XLSX, PPTX och mer.
### Är Groupdocs.Viewer för .NET kompatibel med alla .NET-ramverk?
Groupdocs.Viewer för .NET är kompatibel med de flesta .NET-ramverk inklusive .NET Core, .NET Framework och .NET Standard.
### Kan jag anpassa renderingsalternativen för mina dokument?
Absolut! Groupdocs.Viewer för .NET erbjuder omfattande anpassningsalternativ som gör att du kan skräddarsy renderingsprocessen efter dina specifika krav.
### Finns det en testversion tillgänglig för Groupdocs.Viewer för .NET?
Ja, du kan ladda ner en gratis testversion från[här](https://releases.groupdocs.com/).
### Var kan jag hitta support eller ytterligare resurser för Groupdocs.Viewer för .NET?
 För support och ytterligare resurser, besök Groupdocs.Viewer för .NET[forum](https://forum.groupdocs.com/c/viewer/9).