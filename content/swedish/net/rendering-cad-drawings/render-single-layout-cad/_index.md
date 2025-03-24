---
title: Gör enkel layout i CAD-ritningar
linktitle: Gör enkel layout i CAD-ritningar
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar en enkel layout i CAD-ritningar med GroupDocs.Viewer för .NET. Enkla steg för sömlös integration i dina .NET-applikationer.
weight: 14
url: /sv/net/rendering-cad-drawings/render-single-layout-cad/
---
## Introduktion
Inom området .NET-utveckling är hantering och visning av CAD-ritningar ett vanligt krav. GroupDocs.Viewer för .NET förenklar denna uppgift genom att tillhandahålla en heltäckande lösning för att rendera CAD-ritningar i .NET-applikationer. I den här handledningen kommer vi att fördjupa oss i att rendera en enskild layout i CAD-ritningar med GroupDocs.Viewer för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
- Grundläggande förståelse för C# programmeringsspråk och .NET framework.
- Visual Studio installerat på ditt system.
-  GroupDocs.Viewer för .NET-bibliotek laddas ner och refereras till i ditt projekt. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).
- Kännedom om CAD-filformat och deras strukturer.

## Importera namnområden
Importera först de nödvändiga namnrymden till din C#-kod för att komma åt GroupDocs.Viewer-funktioner.

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
## Steg 2: Definiera sidfilssökvägsformat
Definiera formatet för filsökvägen för varje renderad sida.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Instantiera Viewer Object
Skapa en instans av Viewer-klassen som tillhandahålls av GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Steg 4: Konfigurera HTML-vyalternativ
Konfigurera alternativ för att rendera HTML-utdata med inbäddade resurser.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Steg 5: Ange CAD-layoutnamn
Ange namnet på den CAD-layout du vill rendera.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Steg 6: Återge CAD-ritning
Anropa View-metoden för Viewer-objektet med de angivna alternativen.
```csharp
viewer.View(options);
```
## Steg 7: Visa framgångsmeddelande
Informera användaren om den framgångsrika renderingen av källdokumentet.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Att rendera CAD-ritningar, särskilt när det gäller layouter, kan vara en skrämmande uppgift. Men med GroupDocs.Viewer för .NET blir processen sömlös och effektiv. Genom att följa stegen som beskrivs i denna handledning kan du enkelt rendera en enda layout i CAD-ritningar i dina .NET-applikationer.
## FAQ's
### Kan jag rendera flera layouter samtidigt med GroupDocs.Viewer för .NET?
Ja, GroupDocs.Viewer för .NET stöder rendering av flera layouter från CAD-ritningar.
### Är GroupDocs.Viewer kompatibel med olika CAD-filformat?
Absolut, GroupDocs.Viewer stöder ett brett utbud av CAD-filformat, inklusive DWG, DXF, DGN och mer.
### Kan jag anpassa renderingsalternativen för CAD-ritningar?
Ja, GroupDocs.Viewer erbjuder omfattande alternativ för att anpassa renderingsinställningarna enligt dina krav.
### Finns det en gratis testversion tillgänglig för GroupDocs.Viewer för .NET?
 Ja, du kan utforska funktionerna i GroupDocs.Viewer med en gratis provperiod tillgänglig[här](https://releases.groupdocs.com/).
### Var kan jag få support för GroupDocs.Viewer för .NET?
 För frågor eller hjälp kan du besöka forumet GroupDocs.Viewer[här](https://forum.groupdocs.com/c/viewer/9).