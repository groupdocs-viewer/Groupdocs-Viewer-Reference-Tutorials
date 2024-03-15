---
title: Rendera CMX-bilder
linktitle: Rendera CMX-bilder
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du enkelt renderar CMX-bilder till olika format med GroupDocs.Viewer för .NET. Förbättra din dokumenthantering.
type: docs
weight: 13
url: /sv/net/image-rendering/render-cmx-images/
---
## Introduktion
När det gäller dokumenthantering och manipulation är rendering av bilder från olika format en central uppgift. GroupDocs.Viewer för .NET förenklar denna process genom att tillhandahålla omfattande funktioner för att rendera CMX-bilder till olika format som HTML, JPG, PNG och PDF. Denna handledning guidar dig genom steg-för-steg-processen för att rendera CMX-bilder med GroupDocs.Viewer för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1.  GroupDocs.Viewer for .NET Library: Ladda ner och installera GroupDocs.Viewer for .NET-biblioteket från[här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Ha en fungerande utvecklingsmiljö inrättad med .NET framework.
3. CMX-bildfil: Skaffa en CMX-bildfil som du vill rendera.

## Importera namnområden
Innan du fortsätter, se till att importera de nödvändiga namnområdena för att komma åt GroupDocs.Viewer-funktioner i din .NET-applikation:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Rendering till HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Definiera utdatakatalog: Ställ in katalogen där du vill lagra de renderade HTML-filerna.
- Ange filsökvägsformat: Definiera formatet för HTML-utdatafilerna.
- Instantiate Viewer Object: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- HTML-renderingsalternativ: Konfigurera HTML-renderingsalternativ, som att bädda in resurser.
- Rendera CMX till HTML: Anropa View-metoden för visningsobjektet för att rendera CMX-bilden till HTML.
## Rendering till JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definiera utdatakatalog: Ställ in katalogen för lagring av de renderade JPG-filerna.
- Ange filsökvägsformat: Definiera formatet för utdata JPG-filer.
- Instantiate Viewer Object: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- JPG-renderingsalternativ: Konfigurera JPG-renderingsalternativ.
- Rendera CMX till JPG: Anropa View-metoden för visningsobjektet för att rendera CMX-bilden till JPG.
## Renderar till PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definiera utdatakatalog: Ställ in katalogen för lagring av de renderade PNG-filerna.
- Ange filsökvägsformat: Definiera formatet för utdata PNG-filer.
- Instantiate Viewer Object: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- PNG-renderingsalternativ: Konfigurera PNG-renderingsalternativ.
- Rendera CMX till PNG: Anropa View-metoden för visningsobjektet för att rendera CMX-bilden till PNG.
## Rendering till PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definiera utdatakatalog: Ställ in katalogen för lagring av den renderade PDF-filen.
- Ange filsökvägsformat: Definiera formatet för den utgående PDF-filen.
- Instantiate Viewer Object: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- Alternativ för PDF-rendering: Konfigurera alternativ för PDF-rendering.
- Rendera CMX till PDF: Anropa View-metoden för visningsobjektet för att rendera CMX-bilden till PDF.

## Slutsats
Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en robust lösning för att sömlöst rendera CMX-bilder till olika format. Genom att följa stegen som beskrivs i denna handledning kan du enkelt integrera CMX-bildåtergivningsmöjligheter i dina .NET-applikationer, vilket förbättrar effektiviteten i dokumenthanteringen.
## FAQ's
### Kan jag rendera specifika sidor i en CMX-bild?
Ja, du kan rendera specifika sidor genom att ange sidnumret i renderingsalternativen.
### Är GroupDocs.Viewer för .NET kompatibel med alla .NET-ramverk?
Ja, GroupDocs.Viewer för .NET är kompatibel med flera .NET-ramverk, inklusive .NET Core och .NET Framework.
### Stöder GroupDocs.Viewer rendering av krypterade CMX-bilder?
Ja, GroupDocs.Viewer stöder rendering av krypterade CMX-bilder med lämpliga dekrypteringsnycklar.
### Kan jag anpassa renderingsalternativen för olika utdataformat?
Absolut, GroupDocs.Viewer erbjuder omfattande alternativ för att anpassa renderingsparametrar baserat på dina krav.
### Finns det ett communityforum för GroupDocs.Viewer-support?
 Ja, du kan söka hjälp och engagera dig i GroupDocs.Viewer-communityt på supportforumet[här](https://forum.groupdocs.com/c/viewer/9).