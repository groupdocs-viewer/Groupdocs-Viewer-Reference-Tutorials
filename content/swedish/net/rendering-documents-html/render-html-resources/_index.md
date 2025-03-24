---
title: Rendera med inbäddade eller externa resurser
linktitle: Rendera med inbäddade eller externa resurser
second_title: GroupDocs.Viewer .NET API
description: Förbättra .NET-dokumentvisning med GroupDocs.Viewer för sömlös rendering. Följ vår handledning för effektiv integration och överlägsen användarupplevelse.
weight: 12
url: /sv/net/rendering-documents-html/render-html-resources/
---

# Rendera med inbäddade eller externa resurser

## Introduktion

en värld av .NET-utveckling är effektiv dokumentvisning en avgörande aspekt av många applikationer. GroupDocs.Viewer för .NET tillhandahåller en kraftfull lösning för att rendera dokument med inbäddade eller externa resurser. I den här självstudien kommer vi att undersöka hur man använder GroupDocs.Viewer för att rendera dokument sömlöst och dela upp varje steg för klarhet och förståelse.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar:

1. Grundläggande förståelse för .NET-utveckling: Bekantskap med programmeringsspråket C# och .NET-ramverket är nödvändigt.
2.  Installation av GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från[här](https://releases.groupdocs.com/viewer/net/).
3. Dokumentfil att rendera: Förbered en exempeldokumentfil (t.ex. DOCX, PDF) för rendering.

## Importera namnområden

Låt oss först importera de nödvändiga namnrymden för vårt .NET-projekt:

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

Låt oss nu dela upp processen att rendera ett dokument med inbäddade eller externa resurser i hanterbara steg:

## Steg 1: Definiera utdatakatalog

```csharp
string outputDirectory = "Your Document Directory";
```

Ange katalogen där du vill att de renderade HTML-sidorna ska sparas.

## Steg 2: Definiera sidfilssökvägsformat

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Ställ in formatet för filsökvägen där varje renderad sida ska sparas.`{0}` är en platshållare för sidnummer.

## Steg 3: Initiera Viewer Instance

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // Viewer-initieringskoden går här
}
```

Skapa en Viewer-instans genom att skicka sökvägen till dokumentfilen som ska renderas.

## Steg 4: Konfigurera HTML-vyalternativ

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

Konfigurera HTML-vyalternativ, ange formatet för inbäddade resurser och sökvägsformat för sidan.

## Steg 5: Gör dokumentet

```csharp
viewer.View(options);
```

 Åberopa`View` metoden på Viewer-instansen och skickar de konfigurerade HTML-vyalternativen.

## Steg 6: Visa sökväg för utdatakatalog

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

Skriv ut ett meddelande som indikerar framgångsrik rendering tillsammans med sökvägen till utdatakatalogen.

## Slutsats

GroupDocs.Viewer för .NET förenklar processen att rendera dokument med inbäddade eller externa resurser, vilket förbättrar dokumentvisningsmöjligheterna i .NET-applikationer. Genom att följa stegen som beskrivs i denna handledning kan utvecklare sömlöst integrera dokumentåtergivningsfunktioner i sina projekt, vilket ger användarna en smidig och effektiv dokumentvisningsupplevelse.

## FAQ's

### F: Är GroupDocs.Viewer för .NET kompatibelt med olika dokumentformat?

S: Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive DOCX, PDF, XLSX och mer.

### F: Kan jag anpassa renderingsalternativen enligt mina krav?

S: Absolut, GroupDocs.Viewer erbjuder omfattande alternativ för att konfigurera renderingsprocessen för att möta specifika behov.

### F: Finns det en gratis testversion tillgänglig för GroupDocs.Viewer för .NET?

 S: Ja, du kan utnyttja en gratis provperiod från[här](https://releases.groupdocs.com/).

### F: Hur kan jag få support eller hjälp med GroupDocs.Viewer-integrering?

 S: Du kan söka hjälp från GroupDocs.Viewers communityforum[här](https://forum.groupdocs.com/c/viewer/9).

### F: Finns tillfälliga licenser tillgängliga för teständamål?

 S: Ja, tillfälliga licenser kan erhållas från[här](https://purchase.groupdocs.com/temporary-license/).