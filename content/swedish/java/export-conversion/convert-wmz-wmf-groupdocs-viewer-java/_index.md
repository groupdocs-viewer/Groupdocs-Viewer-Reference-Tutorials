---
date: '2026-02-18'
description: Lär dig hur du konverterar WMZ- och WMF-filer till PDF, HTML, JPG och
  PNG med GroupDocs Viewer för Java. Denna guide täcker GroupDocs Viewer Java och
  Java‑konvertering av vektorgrafik.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Hur man konverterar WMZ till PDF och andra format med GroupDocs Viewer för
  Java
type: docs
url: /sv/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

Check that we didn't miss any shortcodes; none present.

Check code block placeholders remain.

Check image unchanged.

Check links none.

All good.

Now produce final content.# Hur man konverterar WMZ till PDF och andra format med GroupDocs Viewer för Java

Att konvertera WMZ (Web Metafile) och WMF (Windows Metafile) filer till mer tillgängliga format—särskilt **convert WMZ to PDF**—kan vara knepigt eftersom dessa vektorgrafikformat lagrar ritinstruktioner snarare än pixeldata. Med **GroupDocs Viewer for Java** kan du rendera WMZ/WMF-dokument till HTML, JPG, PNG, **PDF** och andra populära format med bara några rader kod.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

I den här handledningen kommer du att lära dig hur du installerar biblioteket, renderar WMZ/WMF-filer till önskad utdata och hanterar vanliga fallgropar. I slutet kommer du att kunna integrera **groupdocs viewer java** i dina Java-applikationer för att **java convert vector graphics** snabbt och pålitligt.

## Snabba svar
- **Vilka format kan WMZ/WMF konverteras till?** HTML, JPG, PNG och PDF stöds fullt ut.  
- **Behöver jag en licens för utveckling?** En gratis provperiod fungerar för testning; en kommersiell licens tar bort utvärderingsgränser.  
- **Vilken Java-version krävs?** Java 8 eller senare rekommenderas.  
- **Kan jag rendera endast specifika sidor?** Ja, du kan ange sidintervall i visningsalternativen.  
- **Är minnesanvändning ett problem för stora filer?** Använd try‑with‑resources och rendera endast de sidor som behövs för att hålla minnet lågt.

## Vad är “convert WMZ to PDF”?
Att konvertera WMZ till PDF innebär att ta den vektorbaserade WMZ-filen och rasterisera den (eller bevara dess vektordata) i en PDF-behållare. PDF är universellt visbart, sökbart och utskrivbart, vilket gör det idealiskt för arkivering och delning av WMZ-grafik.

## Varför använda GroupDocs Viewer för Java för att konvertera vektorgrafik?
- **High fidelity**: Biblioteket bevarar den ursprungliga ritkvaliteten, oavsett om du exporterar till PDF eller PNG.  
- **Zero external dependencies**: Inga externa Windows‑bibliotek behövs; allt körs på vilken plattform som helst med en JDK.  
- **Simple API**: En `Viewer`‑instans och ett enda `view`‑anrop hanterar hela konverteringen.  
- **Scalable**: Fungerar lika bra för enkelsidiga ikoner och flersidiga tekniska ritningar.

## Förutsättningar

### Nödvändiga bibliotek
- **GroupDocs.Viewer for Java** – kärnrenderingsmotorn.  
- Java Development Kit (JDK) 8+.

### Miljöinställning
- IDE såsom IntelliJ IDEA eller Eclipse.  
- Maven för beroendehantering (eller Gradle om du föredrar).

### Kunskapsförutsättningar
- Bekantskap med Java fil‑I/O (`java.nio.file.Path`).  
- Grundläggande förståelse för hur dokumentvisare renderar innehåll.

## Konfigurera GroupDocs.Viewer för Java

Lägg till repository och beroende i din `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

> **Licenstips:** Använd en gratis provperiod för utvärdering, applicera sedan en temporär eller köpt licens för att låsa upp full funktionalitet.

När beroendet är löst kan du skapa en `Viewer`‑instans som kommer att återanvändas för varje konverteringssteg.

## Implementeringsguide

Vi går igenom fyra konverteringsscenarier: HTML, JPG, PNG och PDF. Varje exempel följer samma mönster—definiera en utdatamapp, instansiera `Viewer` med källfilen WMZ, konfigurera lämpliga visningsalternativ och anropa `view`.

### Rendera WMZ/WMF till HTML

#### Översikt
HTML‑utdata låter dig bädda in grafiken direkt i webbsidor, med alla resurser (bilder, CSS) innehållna i en enda fil.

**Steg 1: Definiera utdatamappens sökväg**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Steg 2: Initiera Viewer och rendera till HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendera WMZ/WMF till JPG

#### Översikt
JPG är ett brett stödformat för rasterbilder, perfekt för snabba förhandsvisningar eller e‑postbilagor.

**Steg 1: Definiera utdatamappens sökväg**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Steg 2: Initiera Viewer och rendera till JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendera WMZ/WMF till PNG

#### Översikt
PNG stödjer transparens, vilket gör det idealiskt för grafik som behöver blandas med olika bakgrunder.

**Steg 1: Definiera utdatamappens sökväg**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Steg 2: Initiera Viewer och rendera till PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendera WMZ/WMF till PDF

#### Översikt
PDF erbjuder ett plattformsoberoende, sökbart dokument som behåller den ursprungliga layouten.

**Steg 1: Definiera utdatamappens sökväg**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Steg 2: Initiera Viewer och rendera till PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|----------|
| **OutOfMemoryError** på stora WMZ-filer | Viewer laddar hela dokumentet i minnet | Rendera en sida åt gången med `PageStreamViewOptions` eller öka JVM‑heapen (`-Xmx`). |
| **Missing fonts** i PDF | Typsnittet är inte inbäddat i käll‑WMZ | Installera de nödvändiga typsnitten på värddatorn eller använd `FontSettings` för att tillhandahålla anpassade typsnitt. |
| **Blank PNG output** | Felaktig utdatamapp eller otillräckliga skrivbehörigheter | Verifiera att `outputDirectory` finns och att applikationen har skrivbehörighet. |
| **HTML resources not loading** | Använder `forExternalResources` utan att kopiera filer | Använd `forEmbeddedResources` för en självständig HTML‑fil. |

## Vanliga frågor

**Q: Kan jag konvertera WMF till PNG med samma kod?**  
A: Ja. PNG‑exemplet fungerar för både WMZ- och WMF‑filer; byt bara ut `TestFiles.SAMPLE_WMZ` mot din WMF‑källa.

**Q: Är det möjligt att konvertera endast ett delmängd av sidor?**  
A: Absolut. Använd `PdfViewOptions` (eller motsvarande alternativ för andra format) och anropa `setPageNumbers(List<Integer>)` innan rendering.

**Q: Behöver jag en separat licens för varje utdataformat?**  
A: Nej. En enda GroupDocs Viewer‑licens täcker alla stödjade format, inklusive HTML, JPG, PNG och PDF.

**Q: Hur påverkar “java convert vector graphics” prestandan?**  
A: Vektor‑till‑raster‑konvertering är CPU‑intensiv. För stora batcher, överväg multitrådning och återanvändning av en enda `Viewer`‑instans över filer.

**Q: Kommer PDF‑filen att behålla vektor‑kvaliteten, eller rasteriseras den?**  
A: Vid konvertering av WMZ/WMF till PDF bevarar GroupDocs Viewer vektor‑instruktionerna där det är möjligt, vilket resulterar i en skalbar PDF.

## Slutsats

Du har nu en komplett, produktionsklar guide för att **convert WMZ to PDF** och andra vanliga format med **GroupDocs Viewer for Java**. Oavsett om du bygger en webbtjänst som levererar grafik i realtid eller ett arkiveringsverktyg som lagrar dokument som PDF‑filer, så hjälper stegen ovan dig att snabbt nå dit.

---

**Senast uppdaterad:** 2026-02-18  
**Testad med:** GroupDocs.Viewer 25.2 for Java  
**Författare:** GroupDocs