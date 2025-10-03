---
"description": "Lär dig hur du renderar en enda layout i CAD-ritningar med GroupDocs.Viewer för .NET. Enkla steg för sömlös integration i dina .NET-applikationer."
"linktitle": "Rendera en enda layout i CAD-ritningar"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera en enda layout i CAD-ritningar"
"url": "/sv/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# Rendera en enda layout i CAD-ritningar

## Introduktion
Inom .NET-utveckling är hantering och visning av CAD-ritningar ett vanligt krav. GroupDocs.Viewer för .NET förenklar denna uppgift genom att tillhandahålla en omfattande lösning för att rendera CAD-ritningar i .NET-applikationer. I den här handledningen ska vi fördjupa oss i att rendera en enda layout i CAD-ritningar med GroupDocs.Viewer för .NET.
## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förkunskaper:
- Grundläggande förståelse för programmeringsspråket C# och .NET framework.
- Visual Studio installerat på ditt system.
- GroupDocs.Viewer för .NET-biblioteket har laddats ner och handledningar finns i ditt projekt. Du kan ladda ner det från [här](https://releases.groupdocs.com/viewer/net/).
- Bekantskap med CAD-filformat och deras strukturer.

## Importera namnrymder
Importera först de nödvändiga namnrymderna till din C#-kod för att få åtkomst till GroupDocs.Viewer-funktionerna.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Steg 1: Definiera utdatakatalog
Ange katalogen där du vill att den renderade utdata ska sparas.
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera format för sidfilens sökväg
Definiera formatet för filsökvägen för varje renderad sida.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Instansiera Viewer-objekt
Skapa en instans av Viewer-klassen som tillhandahålls av GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Steg 4: Konfigurera HTML-visningsalternativ
Konfigurera alternativ för att rendera HTML-utdata med inbäddade resurser.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Steg 5: Ange CAD-layoutnamn
Ange namnet på den CAD-layout du vill rendera.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Steg 6: Rendera CAD-ritning
Anropa View-metoden för Viewer-objektet med de angivna alternativen.
```csharp
viewer.View(options);
```
## Steg 7: Visa meddelande om framgång
Informera användaren om att källdokumentet har renderats.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Att rendera CAD-ritningar, särskilt när det gäller layouter, kan vara en svår uppgift. Med GroupDocs.Viewer för .NET blir processen dock smidig och effektiv. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt rendera en enda layout i CAD-ritningar i dina .NET-applikationer.
## Vanliga frågor
### Kan jag rendera flera layouter samtidigt med GroupDocs.Viewer för .NET?
Ja, GroupDocs.Viewer för .NET stöder rendering av flera layouter från CAD-ritningar.
### Är GroupDocs.Viewer kompatibel med olika CAD-filformat?
Absolut, GroupDocs.Viewer stöder ett brett utbud av CAD-filformat, inklusive DWG, DXF, DGN och mer.
### Kan jag anpassa renderingsalternativen för CAD-ritningar?
Ja, GroupDocs.Viewer erbjuder omfattande alternativ för att anpassa renderingsinställningarna efter dina behov.
### Finns det en gratis testversion av GroupDocs.Viewer för .NET?
Ja, du kan utforska funktionerna i GroupDocs.Viewer med en gratis provperiod tillgänglig. [här](https://releases.groupdocs.com/).
### Var kan jag få support för GroupDocs.Viewer för .NET?
För frågor eller hjälp kan du besöka GroupDocs.Viewer-forumet. [här](https://forum.groupdocs.com/c/viewer/9).