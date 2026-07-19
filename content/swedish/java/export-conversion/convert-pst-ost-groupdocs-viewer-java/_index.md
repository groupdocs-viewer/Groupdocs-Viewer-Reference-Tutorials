---
date: '2026-07-19'
description: Lär dig hur du konverterar pst till html och andra format som JPG, PNG,
  PDF med GroupDocs.Viewer for Java. Den här guiden täcker alla steg och nödvändiga
  konfigurationer.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Konvertera PST till HTML snabbt med GroupDocs.Viewer for Java. Lär
  dig steg för steg hur du även exporterar till JPG, PNG och PDF i en produktionsklar
  guide.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Konvertera PST till HTML med GroupDocs.Viewer for Java – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Konvertera PST till HTML, JPG, PNG, PDF med GroupDocs.Viewer for Java
type: docs
url: /sv/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Konvertera PST till HTML, JPG, PNG, PDF med GroupDocs.Viewer för Java

Letar du efter att **konvertera pst till html** eller andra format som JPG, PNG eller PDF? Med det kraftfulla GroupDocs.Viewer för Java-biblioteket är denna uppgift enkel och effektiv. I den här handledningen kommer du att lära dig hur du renderar Outlook PST/OST-filer till webb‑vänlig HTML, bildfiler eller en enda PDF, vilket gör dina e‑postarkiv enkla att dela och arkivera.

![Konvertera PST/OST till HTML, JPG, PNG, PDF med GroupDocs.Viewer för Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Konvertera PST/OST till HTML, JPG, PNG, PDF med GroupDocs.Viewer för Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Vad du kommer att lära dig**
- Hur du installerar GroupDocs.Viewer för Java i ett Maven‑projekt.  
- Steg‑för‑steg‑instruktioner för att **java konvertera pst** filer till HTML, JPG, PNG och PDF.  
- Konfigurationstips för optimal prestanda och vanliga fallgropar.

## Snabba svar
- **Vilket bibliotek hanterar PST‑konvertering?** GroupDocs.Viewer för Java.  
- **Kan jag konvertera PST till PDF direkt?** Ja, med `PdfViewOptions`.  
- **Behövs en licens för produktion?** En giltig GroupDocs‑licens krävs.  
- **Vilken Java‑version stöds?** JDK 8 eller högre.  
- **Måste jag extrahera bilagor manuellt?** Nej, visaren renderar dem automatiskt.

## Vad är GroupDocs.Viewer för Java?
GroupDocs.Viewer för Java är ett server‑side API som laddar över 100 dokument‑ och e‑postformat och renderar dem till HTML, bild eller PDF‑utdata utan extern programvara. Det bearbetar PST‑filer upp till 2 GB samtidigt som minnesanvändningen hålls under 200 MB.

## Hur konverterar man pst till html med GroupDocs.Viewer för Java?
Läs in PST‑filen med `new Viewer("source.pst")`, konfigurera `HtmlViewOptions` för att peka på en utdata‑mapp och anropa `viewer.view(htmlOptions)`. API‑et extraherar varje e‑post, bevarar formatering, bilagor och metadata, och skriver en separat HTML‑sida per meddelande — allt i ett enda metodanrop.

### Varför välja GroupDocs.Viewer?
- **High‑fidelity rendering** – 99,9 % av e‑postinnehållet (inklusive rich‑text‑kroppar, tabeller och inbäddade bilder) återges exakt.  
- **Multiple output formats** – Ett API‑anrop kan generera HTML, JPG, PNG eller PDF, med över 50 exportalternativ.  
- **Zero external dependencies** – Ingen Outlook, Exchange Server eller tredjeparts‑konverterare behövs; allt körs i din Java‑runtime.

## Förutsättningar
- **GroupDocs.Viewer för Java** – version 25.2 eller senare.  
- **Java Development Kit (JDK)** – 8 eller nyare.  
- Maven för beroendehantering.  
- Grundläggande kunskaper i Java och erfarenhet av Maven.

## Konfigurera GroupDocs.Viewer för Java
`Viewer` är kärnklassen i GroupDocs.Viewer för Java som laddar ett dokument och renderar det till det valda formatet. Lägg till GroupDocs‑arkivet och beroendet i din `pom.xml`:

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

### Licensanskaffning
- **Free trial** – utforska alla funktioner utan kostnad.  
- **Temporary license** – förläng utvärderingstiden vid behov.  
- **Full license** – krävs för produktionsdistributioner.

### Grundläggande initiering
`Viewer`‑instanser är lätta; du kan återanvända en enda instans för många filer för att minimera objekt‑skapande overhead.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Implementeringsguide
Följande avsnitt guidar dig genom renderingen av PST/OST‑filer till varje stödd format.

### Rendera PST/OST-dokument till HTML
#### Steg 1: Skapa utdata‑katalog
Definiera en mapp där HTML‑sidorna ska skrivas. GroupDocs skapar en underkatalog för varje e‑post för att hålla resurser organiserade.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Steg 2: Konfigurera Load Options
`LoadOptions` låter dig ange lösenordshantering, tidsgränser för resurssökning och selektiv sidrendering. En timeout på 30 sekunder fungerar bra för de flesta servermiljöer.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Steg 3: Definiera HTML‑visningsalternativ
`HtmlViewOptions` specificerar utdata‑mappen, resurshantering och valfria CSS‑inställningar för HTML‑konvertering.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Steg 4: Initiera Viewer och rendera HTML
Skapa ett `Viewer`‑objekt, ange PST‑filens sökväg och anropa `view` med `HtmlViewOptions`. API‑et itererar automatiskt genom alla meddelanden i PST‑filen och genererar en strukturerad HTML‑hierarki.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Rendera PST/OST-dokument till JPG
#### Steg 1: Skapa utdata‑katalog
Skapa en dedikerad mapp för JPG‑ögonblicksbilder; varje e‑post blir en eller flera bildfiler beroende på dess längd.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Steg 2: Konfigurera Load Options
Samma `LoadOptions` som användes för HTML kan återanvändas här, vilket säkerställer konsekvent lösenordshantering över format.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Steg 3: Definiera JPG‑visningsalternativ
`JpgViewOptions` styr bildupplösning, kvalitet och utdata‑mapp för JPEG‑konvertering.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Steg 4: Initiera Viewer och rendera JPG
Använd `viewer.view(jpgOptions)` för att generera högkvalitativa JPEG‑filer redo för webb‑förhandsvisning.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Rendera PST/OST-dokument till PNG
#### Steg 1: Skapa utdata‑katalog
PNG‑utdata är användbart när du behöver förlustfri kvalitet för arkivering eller OCR‑behandling.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Steg 2: Konfigurera Load Options
Inga ytterligare inställningar krävs utöver lösenord och timeout‑konfiguration.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Steg 3: Definiera PNG‑visningsalternativ
`PngViewOptions` låter dig ange en transparent bakgrund och utdata‑mapp för förlustfria PNG‑bilder.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Steg 4: Initiera Viewer och rendera PNG
Instansiera `viewer.view(pngOptions)` för att producera PNG‑ögonblicksbilder av varje e‑post.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendera PST/OST-dokument till PDF
#### Steg 1: Skapa utdata‑katalog
En enda PDF‑fil per PST förenklar juridiska granskningsprocesser och minskar lagringskostnader.

CODE_BLOCK_PLACEHOLDER_14_END

#### Steg 2: Konfigurera Load Options
När du konverterar till PDF kan du vilja aktivera `setEmbedFonts(true)` för att garantera visuell trohet på vilken maskin som helst.

CODE_BLOCK_PLACEHOLDER_15_END

#### Steg 3: Definiera PDF‑visningsalternativ
`PdfViewOptions` låter dig välja komprimeringsnivå, bädda in teckensnitt och ange filnamn för PDF‑konvertering.

CODE_BLOCK_PLACEHOLDER_16_END

#### Steg 4: Initiera Viewer och rendera PDF
Skapa `PdfViewOptions`, välj eventuellt en komprimeringsnivå och anropa `viewer.view(pdfOptions)`. API‑et sammanslår alla e‑postmeddelanden till ett sökbart PDF‑dokument.

CODE_BLOCK_PLACEHOLDER_17_END

## Praktiska tillämpningar
- **Email Archiving:** Omvandla stora PST‑arkiv till sökbar HTML eller PDF för efterlevnad.  
- **Document Management Systems:** Lagra konverterade filer i system som endast accepterar PDF, PNG eller JPG.  
- **Collaboration Platforms:** Dela konverterade e‑postmeddelanden som bilder i Slack eller Teams.  
- **Legal Review:** Tillhandahåll domstolar PDF‑versioner av e‑postbevis.  
- **Backup Strategies:** Behåll lätta PNG‑ eller JPG‑ögonblicksbilder av kritiska meddelanden.

## Prestandaöverväganden
- **Resource Management:** Återanvänd `Viewer`‑instanser när du bearbetar flera filer för att minska overhead.  
- **Memory Tuning:** Justera `loadOptions.setResourceLoadingTimeout` baserat på serverkapacitet.  
- **Asynchronous Processing:** Flytta konverteringen till bakgrundstrådar för responsiva UI:n.  

## Vanliga frågor
**Q: Hur konverterar jag **pst till pdf** med samma kodbas?**  
A: Använd `PdfViewOptions` som visas i PDF‑renderingssektionen; resten av koden förblir identisk.

**Q: Kan GroupDocs.Viewer hantera krypterade PST‑filer?**  
A: Ja, ange lösenordet via `LoadOptions.setPassword("yourPassword")` innan rendering.

**Q: Vad är skillnaden mellan **java konvertera pst** till PNG vs JPG?**  
A: PNG bevarar förlustfri kvalitet, idealiskt för skärmdumpar, medan JPG ger mindre filstorlekar för e‑post‑förhandsvisningar.

**Q: Finns det ett sätt att **hur man konverterar pst** filer i bulk?**  
A: Inkapsla renderingslogiken i en loop som itererar över en katalog med PST‑filer; återanvänd samma `Viewer`‑konfiguration för varje fil.

**Q: Stöder API‑et konvertering av PST‑filer större än 1 GB?**  
A: Ja, GroupDocs.Viewer strömmar data och kan bearbeta filer upp till 2 GB utan att ladda hela arkivet i minnet.

## Slutsats
Du har nu en komplett, produktionsklar guide för att **konvertera pst till html**, JPG, PNG och PDF med GroupDocs.Viewer för Java. Genom att följa stegen ovan kan du integrera e‑postkonvertering i vilket Java‑baserat arbetsflöde som helst, förbättra åtkomst och uppfylla efterlevnadskrav.

---

**Senast uppdaterad:** 2026-07-19  
**Testat med:** GroupDocs.Viewer för Java 25.2  
**Författare:** GroupDocs

## Relaterade handledningar
- [Konvertera NSF till PDF, HTML, JPG, PNG med GroupDocs.Viewer för Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Konvertera ODF till HTML, JPG, PNG, PDF med GroupDocs.Viewer för Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Hur man konverterar DOCX till HTML med GroupDocs.Viewer för Java: En steg‑för‑steg‑guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)