---
"description": "Rendera CAD-ritningar sömlöst i .NET-applikationer med GroupDocs.Viewer för .NET. Utforska renderingsalternativ, anpassa lager och mer."
"linktitle": "Rendera lager i CAD-ritningar"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera lager i CAD-ritningar"
"url": "/sv/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
type: docs
---
# Rendera lager i CAD-ritningar

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt verktyg som gör det möjligt för utvecklare att sömlöst integrera dokumentrenderingsfunktioner i sina .NET-applikationer. Oavsett om du behöver rendera CAD-ritningar, PDF-filer, Microsoft Office-dokument eller mer, erbjuder GroupDocs.Viewer en heltäckande lösning.
## Förkunskapskrav
Innan du börjar använda GroupDocs.Viewer för .NET, se till att du har följande förutsättningar:
- Grundläggande förståelse för programmeringsspråket C#.
- .NET-utvecklingsmiljö konfigurerad på din dator.
- GroupDocs.Viewer för .NET installerat. Du kan ladda ner det från [här](https://releases.groupdocs.com/viewer/net/).
- Åtkomst till GroupDocs.Viewer för .NET-dokumentationen för handledningar, som finns [här](https://tutorials.groupdocs.com/viewer/net/).

## Importera namnrymder
För att börja använda GroupDocs.Viewer för .NET måste du importera de namnrymder som krävs i ditt projekt. Följ dessa steg:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Låt oss dela upp det givna exemplet i flera steg:
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera format för sidfilens sökväg
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Initiera visningsobjektet
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Kodblocket fortsätter...
}
```
## Steg 4: Ange HTML-visningsalternativ
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Steg 5: Definiera CAD-lager
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Steg 6: Rendera dokument
```csharp
viewer.View(options);
```
## Steg 7: Plats för utdatarenderat dokument
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Med GroupDocs.Viewer för .NET blir rendering av CAD-ritningar i dina .NET-applikationer en sömlös process. Genom att följa stegen som beskrivs i den här guiden kan du enkelt integrera dokumentrenderingsfunktioner i dina projekt.
## Vanliga frågor
### Är GroupDocs.Viewer kompatibel med alla typer av CAD-ritningar?
Ja, GroupDocs.Viewer stöder rendering av en mängd olika CAD-ritningsformat, inklusive DWG och DXF.
### Kan jag anpassa renderingsalternativen för CAD-ritningar?
Absolut, GroupDocs.Viewer erbjuder olika anpassningsalternativ, som att ange lager som ska renderas eller ställa in utdataformat.
### Kräver GroupDocs.Viewer en internetanslutning för att rendera dokument?
Nej, GroupDocs.Viewer utför rendering lokalt utan behov av en internetanslutning.
### Finns det en gratis testversion av GroupDocs.Viewer för .NET?
Ja, du kan få tillgång till en gratis provversion av GroupDocs.Viewer för .NET. [här](https://releases.groupdocs.com/).
### Var kan jag få support för GroupDocs.Viewer för .NET?
För teknisk hjälp eller frågor kan du besöka GroupDocs.Viewer-forumet. [här](https://forum.groupdocs.com/c/viewer/9).