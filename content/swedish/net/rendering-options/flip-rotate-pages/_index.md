---
"description": "Lär dig hur du integrerar Groupdocs.Viewer för .NET i dina applikationer för sömlös dokumentrendering, vändning och rotation."
"linktitle": "Vänd och rotera sidor"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Vänd och rotera sidor"
"url": "/sv/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# Vänd och rotera sidor

## Introduktion
den här handledningen kommer vi att fördjupa oss i funktionerna i Groupdocs.Viewer för .NET, med särskilt fokus på att vända och rotera sidor. Groupdocs.Viewer för .NET är ett kraftfullt verktyg utformat för att rendera dokument i olika format inom .NET-applikationer. Oavsett om du utvecklar ett dokumenthanteringssystem eller behöver integrera dokumentvisningsfunktioner i din programvara, erbjuder Groupdocs.Viewer för .NET en effektiv lösning.
## Förkunskapskrav
Innan vi börjar, se till att du har följande förutsättningar konfigurerade:
### Installera Groupdocs.Viewer för .NET
För att använda Groupdocs.Viewer för .NET måste du installera paketet via NuGet Package Manager. Du hittar detaljerade installationsanvisningar i [dokumentation](https://tutorials.groupdocs.com/viewer/net/).

## Importera namnrymder
Se till att du har importerat de nödvändiga namnrymderna i ditt projekt för att kunna använda Groupdocs.Viewer för .NET effektivt.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss dela upp processen att vända och rotera sidor med Groupdocs.Viewer för .NET i enkla steg:
## Steg 1: Ange utdatakatalog och filsökväg
Definiera katalogen där du vill att utdatafilen ska sparas och ange sökvägen till utdatafilen.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Steg 2: Initiera visningsobjektet
Skapa en instans av Viewer-klassen genom att skicka sökvägen till dokumentet du vill visa.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Steg 3: Konfigurera visningsalternativ
Konfigurera visningsalternativen, till exempel att ange utdatafilformatet och eventuella ytterligare inställningar som sidrotation.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Steg 4: Rendera dokument
Anropa View-metoden för Viewer-objektet och skicka view-alternativen.
```csharp
viewer.View(viewOptions);
```
## Steg 5: Visa meddelande om framgång
Informera användaren om att dokumentet har renderats och ange utdatakatalogen för verifiering.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Sammanfattningsvis erbjuder Groupdocs.Viewer för .NET kraftfulla funktioner för att rendera dokument, inklusive att vända och rotera sidor. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera dessa funktioner i dina .NET-applikationer och förbättra dokumentvisningsupplevelsen för dina användare.
## Vanliga frågor
### Är Groupdocs.Viewer för .NET kompatibelt med alla dokumentformat?
Ja, Groupdocs.Viewer för .NET stöder en mängd olika dokumentformat, inklusive DOCX, PDF, PPTX med flera.
### Kan jag anpassa visningsalternativen utöver att vända och rotera sidor?
Absolut, Groupdocs.Viewer för .NET erbjuder olika anpassningsalternativ för att visa dokument, så att du kan skräddarsy upplevelsen efter dina behov.
### Finns det en gratis testversion av Groupdocs.Viewer för .NET?
Ja, du kan få en gratis provversion av Groupdocs.Viewer för .NET genom att besöka [webbplats](https://releases.groupdocs.com/).
### Hur kan jag få support för Groupdocs.Viewer för .NET?
Du kan söka hjälp och engagera dig i samhället genom [Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).
### Var kan jag få en tillfällig licens för Groupdocs.Viewer för .NET?
Tillfälliga licenser för Groupdocs.Viewer för .NET kan erhållas från [köpsida](https://purchase.groupdocs.com/temporary-license/).