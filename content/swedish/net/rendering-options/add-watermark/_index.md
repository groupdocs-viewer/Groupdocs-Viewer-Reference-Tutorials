---
title: Lägg till vattenstämpel i dokument
linktitle: Lägg till vattenstämpel i dokument
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du sömlöst lägger till vattenstämplar i dokument med GroupDocs.Viewer för .NET. Förbättra dokumentsäkerhet och varumärkesbyggande med denna lättanvända handledning.
type: docs
weight: 10
url: /sv/net/rendering-options/add-watermark/
---
## Introduktion
I dagens digitala tidsålder är hantering och visning av olika dokumentformat sömlöst en nödvändighet för många företag och privatpersoner. Lyckligtvis blir det enkelt att hantera dokument med verktyg som GroupDocs.Viewer för .NET. Detta kraftfulla .NET-bibliotek gör det möjligt för utvecklare att enkelt integrera dokumentvisningsfunktioner i sina applikationer, så att användare kan se dokument utan att behöva originalprogramvaran som skapade dem.
## Förutsättningar
Innan du börjar använda GroupDocs.Viewer för .NET för att lägga till vattenstämplar i dokument, se till att du har följande:
1. Miljöinställningar: Ha en utvecklingsmiljö inställd med .NET Framework eller .NET Core installerat.
2.  GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET-biblioteket från[nedladdningssida](https://releases.groupdocs.com/viewer/net/).
3. Dokumentfiler: Förbered de dokumentfiler du vill arbeta med, till exempel DOCX, PDF eller andra.
4. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# är nödvändigt för att implementera kodexemplen.

## Importera namnområden
Innan du börjar lägga till vattenstämplar i dokument med GroupDocs.Viewer för .NET, se till att importera de nödvändiga namnrymden i din C#-kod. Detta steg låter dig komma åt klasserna och metoderna som tillhandahålls av biblioteket sömlöst.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss nu gå igenom processen att lägga till en vattenstämpel i ett dokument med GroupDocs.Viewer för .NET. Följ dessa steg för att sömlöst integrera vattenmärkningsfunktioner i din applikation.
## Steg 1: Ställ in utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Ange katalogen där du vill att utdatafilerna ska sparas efter att du har applicerat vattenstämpeln.
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ställ in formatet för filsökvägarna för de renderade sidorna. I det här exemplet kommer HTML-filer med sidnummer att genereras.
## Steg 3: Instantiera Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Koden fortsätter i nästa steg...
}
```
Skapa en instans av Viewer-klassen och skicka sökvägen till dokumentfilen som en parameter. I det här exemplet använder vi en DOCX-exempelfil.
## Steg 4: Konfigurera HTML-vyalternativ
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Konfigurera HTML-vyalternativen, inklusive vattenstämpeltexten som du vill lägga till i dokumentet.
## Steg 5: Visa dokument med vattenstämpel
```csharp
viewer.View(options);
```
Anropa View-metoden för Viewer-objektet och skicka de konfigurerade alternativen. Detta kommer att återge dokumentet med den angivna vattenstämpeln.
## Steg 6: Visa sökväg för utdatakatalog
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informera användaren om den framgångsrika renderingen av dokumentet och ange katalogen där utdatafilerna sparas.

## Slutsats
GroupDocs.Viewer för .NET ger ett bekvämt sätt att lägga till vattenstämplar till dokument programmatiskt. Genom att följa stegen som beskrivs i denna handledning kan du sömlöst integrera vattenmärkningsfunktioner i dina .NET-applikationer, vilket förbättrar dokumentsäkerheten och varumärket.
## FAQ's
### Kan jag anpassa utseendet på vattenstämpeln?
Ja, du kan anpassa olika egenskaper för vattenstämpeln, såsom text, teckensnitt, färg, storlek och position.
### Har GroupDocs.Viewer stöd för visning av dokument från fjärrkällor?
Ja, GroupDocs.Viewer stöder visning av dokument från lokal lagring samt fjärrwebbadresser.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
Ja, du kan ladda ner en gratis testversion från[här](https://releases.groupdocs.com/).
### Kan jag lägga till vattenstämplar på flera sidor i ett dokument?
Absolut, GroupDocs.Viewer tillåter att lägga till vattenstämplar på enskilda sidor eller alla sidor i ett dokument.
### Hur kan jag få support eller hjälp om jag stöter på några problem?
 Du kan söka hjälp och stöd från GroupDocs community-forum[här](https://forum.groupdocs.com/c/viewer/9).