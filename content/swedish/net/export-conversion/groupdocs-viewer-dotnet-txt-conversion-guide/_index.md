---
"date": "2025-04-25"
"description": "Lär dig hur du konverterar TXT-filer till flera format som HTML, JPG, PNG och PDF med GroupDocs.Viewer för .NET med den här omfattande guiden."
"title": "Konvertera TXT till HTML, JPG, PNG, PDF med GroupDocs.Viewer .NET – en komplett guide"
"url": "/sv/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# Konvertera TXT till flera format med GroupDocs.Viewer .NET

## Introduktion

Vill du enkelt konvertera textdokument till olika format som HTML, JPG, PNG eller PDF? Att hantera dokumentkonverteringar kan vara utmanande, särskilt när du har att göra med flera sidor eller specifika formatkrav. **GroupDocs.Viewer för .NET** förenklar processen att rendera TXT-filer till olika utdataformat, vilket säkerställer att dina data är tillgängliga och visuellt tilltalande.

![Konvertera TXT till HTML, JPG, PNG, PDF med GroupDocs.Viewer för .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

I den här guiden utforskar vi hur man använder GroupDocs.Viewer för .NET för att omvandla TXT-dokument till flersidig HTML, enkelsidig HTML, JPG, PNG och PDF. I slutet kommer du att behärska:
- Konvertera TXT-filer med C# med GroupDocs.Viewer
- Implementera olika renderingsalternativ för dina behov
- Optimera prestanda under konverteringar

Låt oss dyka in i hur du löser dina utmaningar med dokumentkonvertering.

## Förkunskapskrav

Innan vi börjar, se till att du har följande redo:
- **Utvecklingsmiljö**Visual Studio 2019 eller senare.
- **.NET Framework**Version 4.6.1 eller senare.
- **GroupDocs.Viewer för .NET-bibliotek**:
  - Via NuGet-pakethanterarkonsolen: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Använda .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Bekantskap med C#-programmering och grundläggande filoperationer i .NET rekommenderas för att enkelt kunna följa med.

## Konfigurera GroupDocs.Viewer för .NET

### Installation

För att börja, installera **Gruppdokument.Visare** bibliotek med din föredragna pakethanterare:

#### NuGet-pakethanterarkonsolen
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Licensiering

Du kan börja med en **gratis provperiod** eller få en **tillfällig licens** för att utforska GroupDocs.Viewers fulla möjligheter för .NET utan utvärderingsbegränsningar:
- Gratis provperiod: [Ladda ner här](https://releases.groupdocs.com/viewer/net/)
- Tillfällig licens: [Begär här](https://purchase.groupdocs.com/temporary-license/)

För kontinuerlig användning, överväg att köpa en licens direkt från [Gruppdokument](https://purchase.groupdocs.com/buy).

### Grundläggande initialisering

Så här konfigurerar du GroupDocs.Viewer i ditt projekt:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Initiera Viewer-objektet med en TXT-filsökväg.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Din renderingskod kommer att placeras här.
}
```

## Implementeringsguide

Nu ska vi gå in på varje funktion och se hur du kan implementera dem.

### Rendera TXT-dokument till flersidig HTML

#### Översikt
Den här funktionen demonstrerar hur man konverterar ett TXT-dokument till flersidigt HTML-format. Varje sida i textfilen återges som en individuell HTML-fil med inbäddade resurser.

#### Steg 1: Konfigurera tittaren

Skapa en `Viewer` objekt för din käll-TXT-fil:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Initiera visaren med en exempeltextfil.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Fortsätt till steg 2...
```

#### Steg 2: Konfigurera HTML-vyalternativ

Inrätta `HtmlViewOptions` för att rendera varje sida separat:

```csharp
// Konfigurera HTML-visningsalternativ för flersidig rendering.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Rendera dokumentet som flersidig HTML.
viewer.View(options);
}
```

**Förklaring**: Den `ForEmbeddedResources()` Metoden säkerställer att resurser som bilder och stilar bäddas in direkt i HTML-filen, vilket underlättar enkel delning.

### Rendera TXT-dokument till ensidig HTML

#### Översikt
Konvertera ett TXT-dokument till en enda HTML-sida, perfekt för dokument som behöver visas som en sammanhängande webbsida.

#### Steg 1: Konfigurera tittaren

Initiera `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Initiera en ny Viewer-instans för en annan textfil.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Fortsätt till steg 2...
```

#### Steg 2: Konfigurera HTML-alternativ för enstaka sidor

Konfigurera `HtmlViewOptions` med inställningen för ensidig visning aktiverad:

```csharp
// Konfigurera alternativ för rendering till en enda HTML-sida.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Rendera som en enda HTML-sida.
viewer.View(options);
}
```

**Förklaring**: Den `RenderToSinglePage` egenskapen säkerställer att hela innehållet visas på en sida.

### Rendera TXT-dokument till JPG

#### Översikt
Den här funktionen låter dig konvertera ett textdokument till en JPEG-bild, vilket är användbart för visuella presentationer eller arkivering.

#### Steg 1: Konfigurera tittaren

Förbered din `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Initiera tittaren med en exempelfil.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Fortsätt till steg 2...
```

#### Steg 2: Konfigurera JPG-visningsalternativ

Inrätta `JpgViewOptions` för bildrendering:

```csharp
// Konfigurera alternativ för rendering som en JPG-bild.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Rendera dokumentet som en JPEG-fil.
viewer.View(options);
}
```

**Förklaring**: Den `JpgViewOptions` klassen anger hur man renderar och sparar varje sida i dokumentet i JPEG-format.

### Rendera TXT-dokument till PNG

#### Översikt
Konvertera ett textdokument till PNG-format, vilket ger högkvalitativ bildutskrift med stöd för transparens.

#### Steg 1: Konfigurera tittaren

Initiera `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Skapa en visningsinstans för din TXT-fil.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Fortsätt till steg 2...
```

#### Steg 2: Konfigurera PNG-visningsalternativ

Inrätta `PngViewOptions`:

```csharp
// Konfigurera visningsalternativ för rendering som en PNG-bild.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Rendera dokumentet i PNG-format.
viewer.View(options);
}
```

**Förklaring**: Den `PngViewOptions` klassen tillåter att varje sida renderas med transparens, vilket gör den lämplig för lagerbaserad grafik.

### Återge TXT-dokument till PDF

#### Översikt
Den här funktionen är perfekt för att konvertera textdokument till ett universellt tillgängligt PDF-format.

#### Steg 1: Konfigurera tittaren

Förbered din `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Initiera en visningsinstans för din exempeltextfil.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Fortsätt till steg 2...
```

#### Steg 2: Konfigurera PDF-visningsalternativ

Inrätta `PdfViewOptions`:

```csharp
// Konfigurera visningsalternativ för rendering som ett PDF-dokument.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Rendera dokumentet till en PDF-fil.
viewer.View(options);
}
```

**Förklaring**: Den `PdfViewOptions` Klassen specificerar hur man konverterar och sparar dina TXT-filer som PDF-dokument.

## Slutsats

Med GroupDocs.Viewer för .NET är det enkelt att konvertera textdokument till olika format. Den här guiden behandlade hur man konverterar TXT-filer till flersidig HTML, enkelsidig HTML, JPG, PNG och PDF med hjälp av C#. Oavsett om du vill förbättra dokumenttillgängligheten eller kompatibiliteten, erbjuder dessa metoder robusta lösningar.

För ytterligare hjälp eller mer avancerade funktioner, se [officiell GroupDocs.Viewer-dokumentation](https://docs.groupdocs.com/viewer/net/)Lycka till med kodningen!