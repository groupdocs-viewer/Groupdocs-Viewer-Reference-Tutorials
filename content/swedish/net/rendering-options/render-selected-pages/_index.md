---
"description": "Lär dig hur du renderar valda sidor från dokument med Groupdocs.Viewer för .NET. Steg-för-steg-handledning med kodexempel inkluderade."
"linktitle": "Rendera valda sidor"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera valda sidor"
"url": "/sv/net/rendering-options/render-selected-pages/"
"weight": 17
---

# Rendera valda sidor

## Introduktion

I den här handledningen går vi in på hur man använder Groupdocs.Viewer för .NET för att rendera valda sidor från ett dokument. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här steg-för-steg-guiden att guida dig genom processen med lätthet.

## Förkunskapskrav

Innan vi börjar, se till att du har följande förutsättningar på plats:

### 1. Installation

Se till att du har Groupdocs.Viewer för .NET installerat i din utvecklingsmiljö. Om inte kan du ladda ner det från [Nedladdningslänk](https://releases.groupdocs.com/viewer/net/).

## Importera namnrymder

Importera de namnrymder som behövs för att komma åt de obligatoriska klasserna och metoderna i din C#-kodfil. Du kan göra detta med hjälp av `using` direktiv:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu ska vi dela upp exempelkoden i flera steg:

## Steg 1: Ställ in utdatakatalog

Definiera katalogen där du vill att de renderade sidorna ska sparas. Ersätt `"Your Document Directory"` med önskad katalogsökväg.

```csharp
string outputDirectory = "Your Document Directory";
```

## Steg 2: Definiera format för sidfilens sökväg

Ange formatet för sökvägarna till de renderade sidorna. Detta kommer att användas för att spara varje sida som en HTML-fil i utdatakatalogen.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Steg 3: Instansiera Viewer-objekt

Skapa en instans av Viewer-klassen och skicka sökvägen till det dokument du vill rendera som ett argument.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Steg 4: Konfigurera HTML-visningsalternativ

Konfigurera HTML-vyalternativen för rendering. I det här exemplet konfigurerar vi alternativ för att bädda in resurser i HTML-utdata.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Steg 5: Rendera valda sidor

Ange de sidnummer du vill rendera. I det här fallet renderar vi sidorna 1 till 3. Anropa sedan View-metoden på Viewer-objektet och skicka alternativen och sidnumren som argument.

```csharp
viewer.View(options, 1, 3);
```

## Steg 6: Resultat

Slutligen visas ett meddelande som anger att dokumentet har renderats och var utdatafilerna sparas.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats

Grattis! Du har nu lärt dig hur man renderar valda sidor från ett dokument med Groupdocs.Viewer för .NET. Med den här kunskapen kan du nu enkelt integrera dokumentrenderingsfunktioner i dina .NET-applikationer.

## Vanliga frågor

### F: Kan jag rendera sidor från olika typer av dokument, till exempel PDF-filer eller bilder?

A: Ja, Groupdocs.Viewer för .NET stöder rendering av sidor från olika dokumentformat, inklusive PDF-filer, Microsoft Office-dokument och bildfiler.

### F: Finns det en testversion tillgänglig för testning innan köp?

A: Ja, du kan få tillgång till en gratis testversion av Groupdocs.Viewer för .NET från [webbplats](https://releases.groupdocs.com/).

### F: Kan jag anpassa utdataformatet till något annat än HTML?

A: Absolut, Groupdocs.Viewer för .NET erbjuder alternativ för att rendera sidor som bilder, PDF-filer och mer, utöver HTML.

### F: Hur kan jag få tillfälliga licenser för teständamål?

A: Tillfälliga licenser kan erhållas från [sida om tillfällig licens](https://purchase.groupdocs.com/temporary-license/) på Groupdocs webbplats.

### F: Var kan jag söka hjälp eller få hjälp med eventuella problem jag stöter på?

A: Du kan besöka [Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för stöd och vägledning från communityn och utvecklare.