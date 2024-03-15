---
title: Vänd och rotera sidor
linktitle: Vänd och rotera sidor
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du integrerar Groupdocs.Viewer för .NET i dina applikationer för sömlös dokumentrendering, vändning och rotation.
type: docs
weight: 12
url: /sv/net/rendering-options/flip-rotate-pages/
---
## Introduktion
den här handledningen kommer vi att fördjupa oss i funktionerna i Groupdocs.Viewer för .NET, speciellt med fokus på att vända och rotera sidor. Groupdocs.Viewer för .NET är ett kraftfullt verktyg utformat för att rendera dokument i olika format inom .NET-applikationer. Oavsett om du utvecklar ett dokumenthanteringssystem eller behöver integrera dokumentvisningsmöjligheter i din programvara, erbjuder Groupdocs.Viewer för .NET en effektiv lösning.
## Förutsättningar
Innan vi börjar, se till att du har ställt in följande förutsättningar:
### Installerar Groupdocs.Viewer för .NET
 För att använda Groupdocs.Viewer för .NET måste du installera paketet via NuGet Package Manager. Du kan hitta detaljerade installationsanvisningar i[dokumentation](https://reference.groupdocs.com/viewer/net/).

## Importera namnområden
Se till att du har de nödvändiga namnrymden importerade i ditt projekt för att använda Groupdocs.Viewer för .NET effektivt.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss dela upp processen att vända och rotera sidor med Groupdocs.Viewer för .NET i enkla steg:
## Steg 1: Ställ in utdatakatalog och filsökväg
Definiera katalogen där du vill att utdatafilen ska sparas och ange utdatafilens sökväg.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Steg 2: Initiera Viewer Object
Skapa en instans av Viewer-klassen genom att skicka sökvägen till dokumentet du vill visa.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Steg 3: Konfigurera visningsalternativ
Ställ in visningsalternativen, som att ange utdatafilformatet och eventuella ytterligare inställningar som sidrotation.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Steg 4: Gör dokumentet
Anropa View-metoden för Viewer-objektet och skicka vyalternativen.
```csharp
viewer.View(viewOptions);
```
## Steg 5: Visa framgångsmeddelande
Informera användaren om att dokumentet har renderats och ange utdatakatalogen för verifiering.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Sammanfattningsvis erbjuder Groupdocs.Viewer för .NET kraftfulla funktioner för att rendera dokument, inklusive att vända och rotera sidor. Genom att följa stegen som beskrivs i den här självstudien kan du sömlöst integrera dessa funktioner i dina .NET-applikationer, vilket förbättrar dokumentvisningsupplevelsen för dina användare.
## FAQ's
### Är Groupdocs.Viewer för .NET kompatibel med alla dokumentformat?
Ja, Groupdocs.Viewer för .NET stöder ett brett utbud av dokumentformat, inklusive DOCX, PDF, PPTX och mer.
### Kan jag anpassa visningsalternativen utöver att vända och rotera sidor?
Absolut, Groupdocs.Viewer för .NET erbjuder olika anpassningsalternativ för att visa dokument, så att du kan skräddarsy upplevelsen efter dina krav.
### Finns det en gratis testversion tillgänglig för Groupdocs.Viewer för .NET?
 Ja, du kan använda en gratis provversion av Groupdocs.Viewer för .NET genom att besöka[hemsida](https://releases.groupdocs.com/).
### Hur kan jag få support för Groupdocs.Viewer för .NET?
 Du kan söka hjälp och engagera dig i samhället genom[Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).
### Var kan jag få en tillfällig licens för Groupdocs.Viewer för .NET?
 Tillfälliga licenser för Groupdocs.Viewer för .NET kan erhållas från[köpsidan](https://purchase.groupdocs.com/temporary-license/).