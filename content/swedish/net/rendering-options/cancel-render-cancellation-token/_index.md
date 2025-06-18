---
"description": "Integrera Groupdocs.Viewer för .NET sömlöst i dina .NET-projekt för effektiv dokumentvisning."
"linktitle": "Avbryt rendering med avbokningstoken"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Avbryt rendering med avbokningstoken"
"url": "/sv/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# Avbryt rendering med avbokningstoken

## Introduktion
Groupdocs.Viewer för .NET är ett kraftfullt verktyg utformat för att förenkla dokumentvisning och -bearbetning i .NET-applikationer. Oavsett om du arbetar med PDF-filer, Microsoft Office-dokument eller andra vanliga format, erbjuder detta bibliotek robust funktionalitet för att sömlöst integrera dokumentvisningsfunktioner i dina .NET-projekt.
## Förkunskapskrav
Innan du börjar integrera Groupdocs.Viewer för .NET, se till att du har följande förutsättningar på plats:
1. Installation: Ladda ner och installera Groupdocs.Viewer för .NET-biblioteket från den medföljande filen [nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
   
2. Licens: Erhåll en licens från [Gruppdokument](https://purchase.groupdocs.com/buy) för att frigöra bibliotekets fulla potential. Alternativt kan du börja med en gratis provperiod med hjälp av [tillfällig licens](https://purchase.groupdocs.com/temporary-license/).
   
3. Utvecklingsmiljö: Se till att du har en kompatibel utvecklingsmiljö konfigurerad, inklusive Visual Studio eller annan .NET IDE som du väljer.

## Importera namnrymder
För att kunna använda Groupdocs.Viewer för .NET effektivt måste du importera nödvändiga namnrymder till ditt projekt. Följ dessa steg:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Låt oss nu dela upp det givna exemplet i flera steg för bättre förståelse och implementering:
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Det här steget anger katalogen där de renderade dokumentsidorna ska lagras.
## Steg 2: Definiera format för sidfilens sökväg
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Här definierar vi formatet för filsökvägarna för enskilda dokumentsidor.
## Steg 3: Initiera CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource används för att generera CancellationToken-instanser som kan användas för att avbryta asynkrona operationer.
## Steg 4: Hämta CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Det här steget hämtar token från CancellationTokenSource, som kommer att användas för att avbryta renderingsåtgärden.
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
Här initierar vi renderingen av dokumentsidor asynkront med hjälp av Task.Run(). Viewer-instansen skapas med den angivna dokumentfilen (SAMPLE_DOCX) och renderingsalternativ konfigureras. Renderingsprocessen startas sedan med hjälp av View-metoden i Viewer-klassen.
## Steg 6: Ställ in renderingstidsgräns
```csharp
cancellationTokenSource.CancelAfter(10);
```
Det här steget ställer in en timeout på 10 millisekunder för renderingsåtgärden. Om åtgärden överskrider denna timeout avbryts den automatiskt.
## Steg 7: Visa meddelande om framgång
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Slutligen visas ett meddelande som anger att dokumentet har renderats.

## Slutsats
den här handledningen har vi gått igenom grunderna i att integrera Groupdocs.Viewer för .NET i dina projekt. Genom att följa stegen som beskrivs ovan kan du sömlöst integrera dokumentvisningsfunktioner i dina .NET-applikationer, vilket förbättrar användarupplevelsen och produktiviteten.
## Vanliga frågor
### Är Groupdocs.Viewer för .NET kompatibelt med alla dokumentformat?
Groupdocs.Viewer för .NET stöder en mängd olika dokumentformat, inklusive PDF, Microsoft Office-dokument, bilder och mer.
### Kan jag anpassa utseendet på de renderade dokumentsidorna?
Ja, du kan anpassa olika aspekter av renderingsprocessen, inklusive sidstorlek, kvalitet, vattenstämpel och mer.
### Kräver Groupdocs.Viewer för .NET internetanslutning?
Nej, Groupdocs.Viewer för .NET fungerar lokalt i din .NET-miljö och kräver ingen internetanslutning för dokumentvisning.
### Finns teknisk support tillgänglig för Groupdocs.Viewer för .NET?
Ja, teknisk support finns tillgänglig via [Groupdocs-forum](https://forum.groupdocs.com/c/viewer/9), där du kan ställa frågor, rapportera problem och interagera med communityn.
### Kan jag prova Groupdocs.Viewer för .NET innan jag köper?
Ja, du kan börja med en gratis provperiod med hjälp av den medföljande [testversion](https://releases.groupdocs.com/).