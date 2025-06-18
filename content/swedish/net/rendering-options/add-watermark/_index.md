---
"description": "Lär dig hur du enkelt lägger till vattenstämplar i dokument med GroupDocs.Viewer för .NET. Förbättra dokumentsäkerhet och varumärkesbyggande med den här lättförståeliga handledningen."
"linktitle": "Lägg till vattenstämpel i dokument"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Lägg till vattenstämpel i dokument"
"url": "/sv/net/rendering-options/add-watermark/"
"weight": 10
---

# Lägg till vattenstämpel i dokument

## Introduktion
I dagens digitala tidsålder är det en nödvändighet för många företag och privatpersoner att smidigt hantera och visa olika dokumentformat. Lyckligtvis blir dokumenthanteringen en barnlek med verktyg som GroupDocs.Viewer för .NET. Detta kraftfulla .NET-bibliotek gör det möjligt för utvecklare att enkelt integrera dokumentvisningsfunktioner i sina applikationer, vilket gör att användare kan visa dokument utan att behöva den ursprungliga programvaran som skapade dem.
## Förkunskapskrav
Innan du börjar använda GroupDocs.Viewer för .NET för att lägga till vattenstämplar i dokument, se till att du har följande:
1. Miljökonfiguration: Ha en utvecklingsmiljö konfigurerad med .NET Framework eller .NET Core installerat.
2. GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET-biblioteket från [nedladdningssida](https://releases.groupdocs.com/viewer/net/).
3. Dokumentfiler: Förbered de dokumentfiler du vill arbeta med, till exempel DOCX, PDF eller andra.
4. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# är nödvändig för att implementera kodexemplen.

## Importera namnrymder
Innan du börjar lägga till vattenstämplar i dokument med GroupDocs.Viewer för .NET, se till att importera de namnrymder som krävs i din C#-kod. Det här steget låter dig komma åt de klasser och metoder som tillhandahålls av biblioteket sömlöst.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu ska vi gå igenom processen för att lägga till en vattenstämpel i ett dokument med GroupDocs.Viewer för .NET. Följ dessa steg för att sömlöst integrera vattenstämpelfunktioner i ditt program.
## Steg 1: Ställ in utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Ange katalogen där du vill att utdatafilerna ska sparas efter att vattenstämpeln har applicerats.
## Steg 2: Definiera format för sidfilens sökväg
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ange formatet för sökvägarna till de renderade sidorna. I det här exemplet genereras HTML-filer med sidnummer.
## Steg 3: Instansiera Viewer-objekt
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Koden fortsätter i nästa steg...
}
```
Skapa en instans av Viewer-klassen och skicka sökvägen till dokumentfilen som en parameter. I det här exemplet använder vi en exempel-DOCX-fil.
## Steg 4: Konfigurera HTML-visningsalternativ
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Konfigurera HTML-visningsalternativen, inklusive vattenstämpeltexten som du vill lägga till i dokumentet.
## Steg 5: Visa dokument med vattenstämpel
```csharp
viewer.View(options);
```
Anropa View-metoden för Viewer-objektet och skicka de konfigurerade alternativen. Detta kommer att rendera dokumentet med den angivna vattenstämpeln.
## Steg 6: Visa sökvägen till utdatakatalogen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informera användaren om att dokumentet har renderats och ange katalogen där utdatafilerna sparas.

## Slutsats
GroupDocs.Viewer för .NET erbjuder ett bekvämt sätt att lägga till vattenstämplar i dokument programmatiskt. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera vattenstämpelfunktioner i dina .NET-applikationer, vilket förbättrar dokumentsäkerhet och varumärkesbyggande.
## Vanliga frågor
### Kan jag anpassa vattenstämpelns utseende?
Ja, du kan anpassa olika egenskaper för vattenstämpeln, till exempel text, teckensnitt, färg, storlek och position.
### Stöder GroupDocs.Viewer visning av dokument från fjärrkällor?
Ja, GroupDocs.Viewer stöder visning av dokument från lokal lagring såväl som fjärr-URL:er.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
Ja, du kan ladda ner en gratis testversion från [här](https://releases.groupdocs.com/).
### Kan jag lägga till vattenstämplar på flera sidor i ett dokument?
Absolut, GroupDocs.Viewer tillåter att lägga till vattenstämplar på enskilda sidor eller alla sidor i ett dokument.
### Hur kan jag få stöd eller hjälp om jag stöter på några problem?
Du kan söka hjälp och stöd från GroupDocs communityforum [här](https://forum.groupdocs.com/c/viewer/9).