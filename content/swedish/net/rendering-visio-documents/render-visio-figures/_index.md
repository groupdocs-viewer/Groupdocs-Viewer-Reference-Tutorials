---
title: Rendera Visio-figurer
linktitle: Rendera Visio-figurer
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du renderar Visio-figurer med GroupDocs.Viewer för .NET med detta omfattande. Förbättra dokumentvisningsmöjligheterna i dina .NET-applikationer.
type: docs
weight: 10
url: /sv/net/rendering-visio-documents/render-visio-figures/
---
## Introduktion
I dagens digitala tidsålder spelar dokumentåtergivning en avgörande roll i olika applikationer. Oavsett om det gäller att visa dokument på en webbplats eller konvertera dem till olika format, är effektiv rendering avgörande. GroupDocs.Viewer för .NET tillhandahåller en robust lösning för att visa och manipulera dokument i .NET-applikationer. I den här handledningen kommer vi att fördjupa oss i att rendera Visio-figurer med GroupDocs.Viewer för .NET, och dela upp processen i enkla steg.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
1. Miljöinställningar: Se till att du har en arbetsmiljö för .NET-utveckling.
2.  GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från[nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
3. Grundläggande förståelse för C#: Bekanta dig med C#-programmeringsspråkets grunder.
4. Exempel på Visio-dokument: Ha ett exempel på Visio-dokument redo för rendering.

## Importera namnområden
I ditt C#-projekt börjar du med att importera de nödvändiga namnrymden:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Rendering till HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Utdatakatalog: Definiera katalogen där den renderade HTML-koden ska sparas.
- Sidfilssökvägsformat: Ange sökvägsformatet för HTML-sidan.
- Viewer-initiering: Initiera Viewer-objektet med sökvägen till Visio-dokumentet.
- HTML-vyalternativ: Konfigurera alternativ för att rendera HTML.
- Visio-renderingsalternativ: Ställ in alternativ som är specifika för Visio-rendering, som att endast återge figurer och figurbredd.
## 2. Rendering till JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- I likhet med rendering till HTML, konfigurera alternativ för rendering till JPG-format.
## 3. Rendera till PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Konfiguration för rendering till PNG-format följer ett liknande mönster som JPG-rendering.
## 4. Rendering till PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- För att rendera till PDF, konfigurera alternativ som är specifika för PDF-format.

## Slutsats
I den här handledningen har vi undersökt hur man renderar Visio-figurer med GroupDocs.Viewer för .NET. Genom att följa den steg-för-steg-guiden kan du sömlöst integrera dokumentåtergivningsmöjligheter i dina .NET-applikationer, vilket förbättrar användarupplevelsen och produktiviteten.
## FAQ's
### Kan jag anpassa renderingsalternativen för Visio-figurer?
Ja, GroupDocs.Viewer för .NET erbjuder omfattande alternativ för att anpassa renderingen, inklusive figurbredd, endast rendering av figurer och mer.
### Är GroupDocs.Viewer för .NET lämplig för storskalig dokumentrendering?
Absolut, GroupDocs.Viewer för .NET är optimerad för att hantera storskalig dokumentrendering effektivt.
### Stöder GroupDocs.Viewer andra dokumentformat förutom Visio?
Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive PDF, Microsoft Office, AutoCAD och mer.
### Kan jag integrera GroupDocs.Viewer i webbapplikationer?
Ja, GroupDocs.Viewer kan sömlöst integreras i webbapplikationer för dokumentvisning och manipulering.
### Finns det en testversion tillgänglig för testning innan du köper?
Ja, du kan använda en gratis provperiod från[hemsida](https://releases.groupdocs.com/) för att testa funktionerna i GroupDocs.Viewer för .NET.