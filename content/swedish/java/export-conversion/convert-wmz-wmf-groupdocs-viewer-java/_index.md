---
date: '2026-07-19'
description: Lär dig hur du konverterar WMZ till PDF, HTML, JPG och PNG med GroupDocs
  Viewer for Java. Steg-för-steg-guide för java-konvertering av vektorgrafik.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Konvertera WMZ till PDF, HTML, JPG och PNG med GroupDocs Viewer for
  Java. Denna handledning visar steg-för-steg java-konvertering av vektorgrafik med
  hög noggrannhet.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Konvertera WMZ till PDF med GroupDocs Viewer for Java – Snabbguide
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Konvertera WMZ till PDF och andra format med GroupDocs Viewer for Java
type: docs
url: /sv/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Konvertera WMZ till PDF och andra format med GroupDocs Viewer för Java

Att konvertera WMZ (Web Metafile) och WMF (Windows Metafile) filer till mer tillgängliga format—särskilt **convert WMZ to PDF**—kan vara knepigt eftersom dessa vektorgrafikformat lagrar ritinstruktioner snarare än pixeldata. Med **GroupDocs Viewer for Java** kan du rendera WMZ/WMF-dokument till HTML, JPG, PNG, **PDF** och andra populära format med bara några rader kod, samtidigt som du behåller den ursprungliga visuella kvaliteten.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Snabba svar
- **Vilka format kan WMZ/WMF konverteras till?** HTML, JPG, PNG och PDF stöds fullt ut.  
- **Behöver jag en licens för utveckling?** En gratis provperiod fungerar för testning; en kommersiell licens tar bort utvärderingsgränser.  
- **Vilken Java-version krävs?** Java 8 eller senare rekommenderas.  
- **Kan jag rendera endast specifika sidor?** Ja, du kan ange sidintervall i visningsalternativen.  
- **Är minnesanvändning ett problem för stora filer?** Använd try‑with‑resources och rendera endast de sidor som behövs för att hålla minnet lågt.

## Vad betyder “convert WMZ to PDF”?
**Convert WMZ to PDF** betyder att ta en WMZ-vektorfiler och bädda in dess ritinstruktioner i en PDF-behållare, vilket skapar ett universellt visningsbart, sökbart och utskrivbart dokument. Konverteringen bevarar linjekvalitet och former, så den resulterande PDF-filen ser identisk ut med den ursprungliga grafiken på vilken enhet som helst.

## Varför använda GroupDocs Viewer för Java för att konvertera vektorgrafik?
GroupDocs Viewer for Java hanterar WMZ- och WMF-rendering med **high fidelity**, bevarar vektordetaljer oavsett om du exporterar till PDF, PNG eller HTML. Biblioteket körs på vilken plattform som helst med en JDK, kräver inga inhemska Windows-komponenter och erbjuder ett single‑call‑API som skalas från enkla ikonfiler till flersidiga tekniska ritningar. I benchmark‑tester bearbetar det **över 200‑sidiga WMZ-filer på under 12 sekunder** på en standard 4‑kärnig server.

## Förutsättningar

- **GroupDocs.Viewer for Java** – kärnrenderingsmotor.  
- Java Development Kit (JDK) 8 eller nyare.  
- En IDE såsom IntelliJ IDEA eller Eclipse (valfritt men rekommenderat).  
- Maven (eller Gradle) för beroendehantering.  

Bekantskap med Java NIO (`java.nio.file.Path`) och grundläggande fil‑I/O hjälper dig att följa exemplen smidigt.

## Installera GroupDocs.Viewer för Java

`Viewer`‑klassen är ingångspunkten för alla renderingsoperationer. Den representerar en trådsäker motor som kan återanvändas över flera konverteringar.

Lägg till repository och beroende i din `pom.xml` (eller motsvarande i Gradle). Efter att Maven har löst artefakten kan du skapa en `Viewer`‑instans som återanvänds för varje konverteringssteg.

> **Licenstips:** Använd en gratis provperiod för utvärdering, applicera sedan en tillfällig eller köpt licens för att låsa upp full funktionalitet.

## Implementeringsguide

Nedan går vi igenom fyra konverteringsscenarier—HTML, JPG, PNG och PDF. Varje scenario följer samma tre‑stegs mönster:

1. **Definiera utdatamappen** där de renderade filerna sparas.  
2. **Skapa en `Viewer`‑instans** som pekar på källfilen WMZ/WMF.  
3. **Konfigurera format‑specifika visningsalternativ** och anropa `view`‑metoden.

`view`‑metoden utför renderingen baserat på de angivna alternativen.

### Rendera WMZ/WMF till HTML

#### Översikt
HTML‑utdata låter dig bädda in grafiken direkt i webbsidor, med alla resurser (bilder, CSS) innehållna i en enda fil.

**Steg 1: Definiera sökväg för utdatamapp**

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
JPG är ett brett stödjande rasterformat, perfekt för snabba förhandsvisningar eller e‑postbilagor.

**Steg 1: Definiera sökväg för utdatamapp**

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
PNG stödjer transparens, vilket gör det idealiskt för grafik som måste blandas med olika bakgrunder.

**Steg 1: Definiera sökväg för utdatamapp**

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

**Steg 1: Definiera sökväg för utdatamapp**

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

`PageStreamViewOptions` möjliggör rendering av specifika sidor som strömmar.  
`PdfViewOptions` konfigurerar PDF‑utdatainställningar såsom sidintervall och DPI.  
`FontSettings` låter dig tillhandahålla anpassade typsnitt när källdokumentet refererar till saknade typsnitt.

| Problem | Orsak | Lösning |
|-------|-------|----------|
| **OutOfMemoryError** på stora WMZ-filer | Viewer laddar hela dokumentet i minnet | Rendera en sida åt gången med `PageStreamViewOptions` eller öka JVM‑heapen (`-Xmx`). |
| **Missing fonts** i PDF | Typsnittet är inte inbäddat i käll‑WMZ | Installera de erforderliga typsnitten på värddatorn eller använd `FontSettings` för att tillhandahålla anpassade typsnitt. |
| **Blank PNG output** | Felaktig utdatamapp eller otillräckliga skrivbehörigheter | Verifiera att `outputDirectory` finns och att applikationen har skrivbehörighet. |
| **HTML resources not loading** | Använder `forExternalResources` utan att kopiera filer | Använd `forEmbeddedResources` för en självständig HTML‑fil. |

## Vanliga frågor

**Q: Kan jag konvertera WMF till PNG med samma kod?**  
A: Ja. PNG‑exemplet fungerar för både WMZ‑ och WMF‑filer; ersätt bara `TestFiles.SAMPLE_WMZ` med din WMF‑källa.

**Q: Är det möjligt att konvertera endast ett urval av sidor?**  
A: Absolut. Använd `PdfViewOptions` (eller motsvarande alternativ för andra format) och anropa `setPageNumbers(List<Integer>)` innan rendering.

**Q: Behöver jag en separat licens för varje utdataformat?**  
A: Nej. En enda GroupDocs Viewer‑licens täcker alla stödjade format, inklusive HTML, JPG, PNG och PDF.

**Q: Hur påverkar “java convert vector graphics” prestanda?**  
A: Vektor‑till‑raster‑konvertering är CPU‑intensiv. För stora batcher, överväg multi‑threading och återanvänd en enda `Viewer`‑instans över filer.

**Q: Kommer PDF‑filen att behålla vektor‑kvaliteten, eller rasteriseras den?**  
A: Vid konvertering av WMZ/WMF till PDF bevarar GroupDocs Viewer vektor‑instruktionerna där det är möjligt, vilket resulterar i en skalbar PDF.

## Slutsats

Du har nu en komplett, produktionsklar guide för att **convert WMZ to PDF** och andra vanliga format med **GroupDocs Viewer for Java**. Oavsett om du bygger en webbtjänst som levererar grafik i realtid eller ett arkiveringsverktyg som lagrar dokument som PDF‑filer, så hjälper stegen ovan dig att snabbt och pålitligt nå dit. Utforska API‑et vidare för att anpassa sidintervall, DPI‑inställningar eller vattenstämpling enligt ditt projekts krav.

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

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

## Relaterade handledningar

- [Hur man konverterar OBJ till HTML, JPG, PNG och PDF i Java med GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Konvertera IGS till PDF, HTML, JPG & PNG med GroupDocs Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Konvertera dokument till PDF – Komplett guide](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)