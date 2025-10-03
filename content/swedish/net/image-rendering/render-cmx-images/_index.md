---
"description": "Lär dig hur du enkelt renderar CMX-bilder till olika format med GroupDocs.Viewer för .NET. Förbättra din dokumenthantering."
"linktitle": "Rendera CMX-bilder"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera CMX-bilder"
"url": "/sv/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# Rendera CMX-bilder

## Introduktion
Inom dokumenthantering och manipulation är rendering av bilder från olika format en central uppgift. GroupDocs.Viewer för .NET förenklar denna process genom att tillhandahålla omfattande funktioner för att rendera CMX-bilder till olika format som HTML, JPG, PNG och PDF. Den här handledningen guidar dig steg för steg genom processen för att rendera CMX-bilder med GroupDocs.Viewer för .NET.

![Rendera CMX-bilder med GroupDocs.Viewer för .NET](/viewer/image-rendering/render-cmx-images.png)

## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förutsättningar på plats:
1. GroupDocs.Viewer för .NET-biblioteket: Ladda ner och installera GroupDocs.Viewer för .NET-biblioteket från [här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Ha en fungerande utvecklingsmiljö konfigurerad med .NET Framework.
3. CMX-bildfil: Hämta en CMX-bildfil som du vill rendera.

## Importera namnrymder
Innan du fortsätter, se till att importera de namnrymder som krävs för att komma åt GroupDocs.Viewer-funktionerna i din .NET-applikation:
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
- Definiera utdatakatalog: Ange katalogen där du vill lagra de renderade HTML-filerna.
- Ange sökvägsformat: Definiera formatet för HTML-utdatafilerna.
- Instansiera Viewer-objekt: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- HTML-renderingsalternativ: Konfigurera HTML-renderingsalternativ, till exempel inbäddning av resurser.
- Rendera CMX till HTML: Anropa View-metoden för viewer-objektet för att rendera CMX-bilden till HTML.
## Rendering till JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definiera utdatakatalog: Ange katalogen för att lagra de renderade JPG-filerna.
- Ange sökvägsformat: Definiera formatet för JPG-filerna som utdata.
- Instansiera Viewer-objekt: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- JPG-renderingsalternativ: Konfigurera JPG-renderingsalternativ.
- Rendera CMX till JPG: Anropa View-metoden för viewer-objektet för att rendera CMX-bilden till JPG.
## Rendering till PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definiera utdatakatalog: Ange katalogen för att lagra de renderade PNG-filerna.
- Ange sökvägsformat: Definiera formatet för PNG-filerna som utdata.
- Instansiera Viewer-objekt: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- PNG-renderingsalternativ: Konfigurera PNG-renderingsalternativ.
- Rendera CMX till PNG: Anropa View-metoden för viewer-objektet för att rendera CMX-bilden till PNG.
## Rendering till PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definiera utdatakatalog: Ange katalogen för att lagra den renderade PDF-filen.
- Ange sökvägsformat: Definiera formatet för PDF-utdatafilen.
- Instansiera Viewer-objekt: Skapa en instans av Viewer-klassen med CMX-bildfilen.
- PDF-renderingsalternativ: Konfigurera PDF-renderingsalternativ.
- Rendera CMX till PDF: Anropa View-metoden för viewer-objektet för att rendera CMX-bilden till PDF.

## Slutsats
Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en robust lösning för att rendera CMX-bilder i olika format sömlöst. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt integrera CMX-bildrenderingsfunktioner i dina .NET-applikationer, vilket förbättrar effektiviteten i dokumenthanteringen.
## Vanliga frågor
### Kan jag rendera specifika sidor av en CMX-bild?
Ja, du kan rendera specifika sidor genom att ange sidnumret i renderingsalternativen.
### Är GroupDocs.Viewer för .NET kompatibelt med alla .NET-ramverk?
Ja, GroupDocs.Viewer för .NET är kompatibelt med flera .NET-ramverk, inklusive .NET Core och .NET Framework.
### Har GroupDocs.Viewer stöd för rendering av krypterade CMX-bilder?
Ja, GroupDocs.Viewer stöder rendering av krypterade CMX-bilder med lämpliga dekrypteringsnycklar.
### Kan jag anpassa renderingsalternativen för olika utdataformat?
Absolut, GroupDocs.Viewer erbjuder omfattande alternativ för att anpassa renderingsparametrar baserat på dina krav.
### Finns det ett communityforum för support av GroupDocs.Viewer?
Ja, du kan söka hjälp och interagera med GroupDocs.Viewer-communityn på supportforumet. [här](https://forum.groupdocs.com/c/viewer/9).