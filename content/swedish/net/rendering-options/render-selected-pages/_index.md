---
title: Rendera valda sidor
linktitle: Rendera valda sidor
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar valda sidor från dokument med Groupdocs.Viewer för .NET. Steg-för-steg handledning med kodexempel ingår.
type: docs
weight: 17
url: /sv/net/rendering-options/render-selected-pages/
---
## Introduktion

I den här handledningen kommer vi att fördjupa oss i hur man använder Groupdocs.Viewer för .NET för att rendera utvalda sidor från ett dokument. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här steg-för-steg-guiden att leda dig genom processen med lätthet.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

### 1. Installation

 Se till att du har Groupdocs.Viewer för .NET installerat i din utvecklingsmiljö. Om inte kan du ladda ner den från[Nedladdningslänk](https://releases.groupdocs.com/viewer/net/).

## Importera namnområden

 din C#-kodfil, importera de nödvändiga namnområdena för att komma åt de obligatoriska klasserna och metoderna. Du kan göra detta med hjälp av`using` direktiv:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss nu dela upp exempelkoden som tillhandahålls i flera steg:

## Steg 1: Ställ in utdatakatalog

 Definiera katalogen där du vill att de renderade sidorna ska sparas. Byta ut`"Your Document Directory"` med önskad katalogsökväg.

```csharp
string outputDirectory = "Your Document Directory";
```

## Steg 2: Definiera sidfilssökvägsformat

Ange formatet för filsökvägarna för de renderade sidorna. Detta kommer att användas för att spara varje sida som en HTML-fil i utdatakatalogen.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Steg 3: Instantiera Viewer Object

Skapa en instans av Viewer-klassen och skicka sökvägen till dokumentet du vill rendera som ett argument.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Steg 4: Konfigurera HTML-vyalternativ

Ställ in HTML-vyalternativen för rendering. I det här exemplet konfigurerar vi alternativ för att bädda in resurser i HTML-utdata.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Steg 5: Rendera valda sidor

Ange sidnumren du vill återge. I det här fallet renderar vi sidorna 1 till 3. Anropa sedan View-metoden på Viewer-objektet och skicka alternativen och sidnumren som argument.

```csharp
viewer.View(options, 1, 3);
```

## Steg 6: Utdataresultat

Visa slutligen ett meddelande som anger att dokumentet har renderats och platsen där utdatafilerna sparas.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du renderar valda sidor från ett dokument med Groupdocs.Viewer för .NET. Med denna kunskap kan du nu enkelt integrera dokumentåtergivningsmöjligheter i dina .NET-applikationer.

## FAQ's

### F: Kan jag rendera sidor från olika typer av dokument, till exempel PDF-filer eller bilder?

S: Ja, Groupdocs.Viewer för .NET stöder rendering av sidor från olika dokumentformat, inklusive PDF-filer, Microsoft Office-dokument och bildfiler.

### F: Finns det en testversion tillgänglig för testning innan du köper?

 S: Ja, du kan komma åt en gratis testversion av Groupdocs.Viewer för .NET från[hemsida](https://releases.groupdocs.com/).

### F: Kan jag anpassa utdataformatet annat än HTML?

S: Absolut, Groupdocs.Viewer för .NET erbjuder alternativ för att rendera sidor som bilder, PDF-filer och mer, förutom HTML.

### F: Hur kan jag få tillfälliga licenser för teständamål?

S: Tillfälliga licenser kan erhållas från[sida för tillfällig licens](https://purchase.groupdocs.com/temporary-license/) på Groupdocs webbplats.

### F: Var kan jag söka hjälp eller få hjälp med eventuella problem jag stöter på?

 A: Du kan besöka[Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för stöd och vägledning från samhället och utvecklare.