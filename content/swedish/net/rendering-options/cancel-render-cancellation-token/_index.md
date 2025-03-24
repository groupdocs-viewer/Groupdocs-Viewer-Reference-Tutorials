---
title: Avbryt rendering med Cancellation Token
linktitle: Avbryt rendering med Cancellation Token
second_title: GroupDocs.Viewer .NET API
description: Integrera Groupdocs.Viewer för .NET sömlöst i dina .NET-projekt för effektiv dokumentvisning.
weight: 11
url: /sv/net/rendering-options/cancel-render-cancellation-token/
---

# Avbryt rendering med Cancellation Token

## Introduktion
Groupdocs.Viewer för .NET är ett kraftfullt verktyg utformat för att förenkla dokumentvisning och bearbetning inom .NET-applikationer. Oavsett om du har att göra med PDF-filer, Microsoft Office-dokument eller andra vanliga format, erbjuder det här biblioteket robusta funktioner för att sömlöst integrera dokumentvisningsmöjligheter i dina .NET-projekt.
## Förutsättningar
Innan du går in i integrationen av Groupdocs.Viewer för .NET, se till att du har följande förutsättningar:
1.  Installation: Ladda ner och installera Groupdocs.Viewer for .NET-biblioteket från det medföljande[nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
   
2.  Licens: Skaffa en licens från[Gruppdokument](https://purchase.groupdocs.com/buy) för att låsa upp bibliotekets fulla potential. Alternativt kan du börja med en gratis provperiod med hjälp av[tillfällig licens](https://purchase.groupdocs.com/temporary-license/).
   
3. Utvecklingsmiljö: Se till att du har en kompatibel utvecklingsmiljö inrättad, inklusive Visual Studio eller någon annan .NET IDE du väljer.

## Importera namnområden
För att kunna använda Groupdocs.Viewer för .NET effektivt måste du importera de nödvändiga namnrymden till ditt projekt. Följ dessa steg:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Låt oss nu dela upp exemplet i flera steg för bättre förståelse och implementering:
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Detta steg ställer in katalogen där de renderade dokumentsidorna ska lagras.
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Här definierar vi formatet för filsökvägarna för enskilda dokumentsidor.
## Steg 3: Initiera CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource används för att generera CancellationToken-instanser som kan användas för att avbryta asynkrona operationer.
## Steg 4: Skaffa CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Detta steg hämtar token från CancellationTokenSource, som kommer att användas för att avbryta renderingsoperationen.
## Steg 5: Rendera dokumentsidor
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Här initierar vi renderingen av dokumentsidor asynkront med Task.Run(). Viewer-instansen skapas med den angivna dokumentfilen (SAMPLE_DOCX), och renderingsalternativ konfigureras. Återgivningsprocessen startas sedan med Viewer-klassens View-metod.
## Steg 6: Ställ in renderingstidsgräns
```csharp
cancellationTokenSource.CancelAfter(10);
```
Detta steg ställer in en timeout på 10 millisekunder för renderingsoperationen. Om åtgärden överskrider denna timeout kommer den automatiskt att avbrytas.
## Steg 7: Visa framgångsmeddelande
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Slutligen visas ett framgångsmeddelande som indikerar att dokumentet har renderats framgångsrikt.

## Slutsats
I den här handledningen har vi täckt grunderna för att integrera Groupdocs.Viewer för .NET i dina projekt. Genom att följa stegen som beskrivs ovan kan du sömlöst införliva dokumentvisningsmöjligheter i dina .NET-applikationer, vilket förbättrar användarupplevelsen och produktiviteten.
## FAQ's
### Är Groupdocs.Viewer för .NET kompatibel med alla dokumentformat?
Groupdocs.Viewer för .NET stöder ett brett utbud av dokumentformat, inklusive PDF, Microsoft Office-dokument, bilder och mer.
### Kan jag anpassa utseendet på de renderade dokumentsidorna?
Ja, du kan anpassa olika aspekter av renderingsprocessen, inklusive sidstorlek, kvalitet, vattenmärkning och mer.
### Kräver Groupdocs.Viewer för .NET internetanslutning?
Nej, Groupdocs.Viewer för .NET fungerar lokalt i din .NET-miljö och kräver ingen internetanslutning för dokumentvisning.
### Finns teknisk support tillgänglig för Groupdocs.Viewer för .NET?
 Ja, teknisk support är tillgänglig via[Groupdocs forum](https://forum.groupdocs.com/c/viewer/9), där du kan ställa frågor, rapportera problem och interagera med communityn.
### Kan jag prova Groupdocs.Viewer för .NET innan jag köper?
 Ja, du kan börja med en gratis provperiod med det medföljande[testversion](https://releases.groupdocs.com/).