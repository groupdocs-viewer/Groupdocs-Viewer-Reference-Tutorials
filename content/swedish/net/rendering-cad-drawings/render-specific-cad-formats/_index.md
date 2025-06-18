---
"description": "Lär dig hur du renderar specifika CAD-format som CF2 till HTML, JPG, PNG och PDF med Groupdocs.Viewer för .NET."
"linktitle": "Renderingsspecifika CAD-format (CF2)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderingsspecifika CAD-format (CF2)"
"url": "/sv/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Renderingsspecifika CAD-format (CF2)

## Introduktion
I den här handledningen ska vi utforska hur man renderar specifika CAD-format med Groupdocs.Viewer för .NET. Groupdocs.Viewer är ett kraftfullt dokumentvisnings-API som låter utvecklare visa över 170 dokumenttyper i sina applikationer utan att behöva installera några externa program. Vi kommer specifikt att fokusera på att rendera CAD-format som CF2 till olika utdataformat som HTML, JPG, PNG och PDF.
## Förkunskapskrav
Innan vi går in i handledningen, se till att du har följande förkunskaper:
- Visual Studio installerat på ditt system.
- Groupdocs.Viewer för .NET SDK. Du kan ladda ner det från [här](https://releases.groupdocs.com/viewer/net/).
- Grundläggande kunskaper i programmeringsspråket C#.
## Importera namnrymder
Låt oss först importera de namnrymder som krävs för att rendera CAD-format.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nu ska vi dela upp varje exempel i flera steg:
## Rendera CF2 till HTML
### Steg 1: Definiera utdatakatalogen där den renderade HTML-koden ska sparas.
```csharp
string outputDirectory = "Your Document Directory";
```
### Steg 2: Definiera sökvägsformatet för HTML-utdata.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Steg 3: Initiera Viewer-objektet och ange CF2-indatafilen.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Ställ in ytterligare renderingsalternativ om det behövs
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendera CF2 till JPG
### Steg 1: Definiera sökvägsformatet för JPG-utdata.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Steg 2: Initiera Viewer-objektet och ange CF2-indatafilen.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Ställ in ytterligare renderingsalternativ om det behövs
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendera CF2 till PNG

### Steg 1: Definiera sökvägsformatet för PNG-utdata.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Steg 2: Initiera Viewer-objektet och ange CF2-indatafilen.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Ställ in ytterligare renderingsalternativ om det behövs
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendera CF2 till PDF
### Steg 1: Definiera sökvägsformatet för PDF-utdata.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Steg 2: Initiera Viewer-objektet och ange CF2-indatafilen.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Ställ in ytterligare renderingsalternativ om det behövs
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Slutsats
I den här handledningen har vi lärt oss hur man renderar specifika CAD-format som CF2 med Groupdocs.Viewer för .NET. Genom att följa steg-för-steg-guiden kan du enkelt integrera dokumentrenderingsfunktioner i dina .NET-applikationer.
## Vanliga frågor
### Kan Groupdocs.Viewer rendera andra CAD-format förutom CF2?
Ja, Groupdocs.Viewer stöder ett brett utbud av CAD-format, inklusive DWG, DXF, DGN och fler.
### Är Groupdocs.Viewer lämplig för att rendera dokument i webbapplikationer?
Absolut, Groupdocs.Viewer kan integreras sömlöst i webbapplikationer för att rendera dokument direkt i webbläsaren.
### Kräver Groupdocs.Viewer några externa beroenden för rendering?
Nej, Groupdocs.Viewer är ett fristående API och kräver inga externa beroenden eller programvaruinstallationer.
### Kan jag anpassa renderingsalternativen efter mina behov?
Ja, Groupdocs.Viewer erbjuder olika renderingsalternativ som kan anpassas för att möta dina specifika behov.
### Finns det en testversion av Groupdocs.Viewer?
Ja, du kan få en gratis testversion av Groupdocs.Viewer från [här](https://releases.groupdocs.com/).