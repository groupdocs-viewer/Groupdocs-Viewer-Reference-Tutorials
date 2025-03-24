---
title: Rendera lager i CAD-ritningar
linktitle: Rendera lager i CAD-ritningar
second_title: GroupDocs.Viewer .NET API
description: Återge CAD-ritningar sömlöst i .NET-applikationer med GroupDocs.Viewer för .NET. Utforska renderingsalternativ, anpassa lager och mer.
weight: 13
url: /sv/net/rendering-cad-drawings/render-layers-cad/
---

# Rendera lager i CAD-ritningar

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt verktyg som gör det möjligt för utvecklare att sömlöst integrera dokumentåtergivningsmöjligheter i sina .NET-applikationer. Oavsett om du behöver rendera CAD-ritningar, PDF-filer, Microsoft Office-dokument eller mer, erbjuder GroupDocs.Viewer en heltäckande lösning.
## Förutsättningar
Innan du börjar använda GroupDocs.Viewer för .NET, se till att du har följande förutsättningar:
- Grundläggande förståelse för programmeringsspråket C#.
- .NET-utvecklingsmiljö konfigurerad på din maskin.
-  GroupDocs.Viewer för .NET installerat. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).
-  Tillgång till GroupDocs.Viewer för .NET-dokumentationen för referens, som finns[här](https://tutorials.groupdocs.com/viewer/net/).

## Importera namnområden
För att börja använda GroupDocs.Viewer för .NET måste du importera de nödvändiga namnområdena i ditt projekt. Följ dessa steg:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Låt oss dela upp exemplet i flera steg:
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Initiera Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Kodblockeringen fortsätter...
}
```
## Steg 4: Ställ in HTML-vyalternativ
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
## Steg 6: Gör dokumentet
```csharp
viewer.View(options);
```
## Steg 7: Mata ut plats för renderat dokument
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Med GroupDocs.Viewer för .NET blir rendering av CAD-ritningar i dina .NET-applikationer en sömlös process. Genom att följa stegen som beskrivs i den här guiden kan du enkelt integrera dokumentåtergivningsmöjligheter i dina projekt.
## FAQ's
### Är GroupDocs.Viewer kompatibel med alla typer av CAD-ritningar?
Ja, GroupDocs.Viewer stöder rendering av ett brett utbud av CAD-ritningsformat, inklusive DWG och DXF.
### Kan jag anpassa renderingsalternativen för CAD-ritningar?
Absolut, GroupDocs.Viewer erbjuder olika anpassningsalternativ, som att ange lager att rendera eller ställa in utdataformat.
### Kräver GroupDocs.Viewer en internetanslutning för att rendera dokument?
Nej, GroupDocs.Viewer utför rendering lokalt utan behov av en internetanslutning.
### Finns det en gratis testversion tillgänglig för GroupDocs.Viewer för .NET?
 Ja, du kan få tillgång till en gratis provversion av GroupDocs.Viewer för .NET[här](https://releases.groupdocs.com/).
### Var kan jag få support för GroupDocs.Viewer för .NET?
 För teknisk hjälp eller frågor kan du besöka forumet GroupDocs.Viewer[här](https://forum.groupdocs.com/c/viewer/9).