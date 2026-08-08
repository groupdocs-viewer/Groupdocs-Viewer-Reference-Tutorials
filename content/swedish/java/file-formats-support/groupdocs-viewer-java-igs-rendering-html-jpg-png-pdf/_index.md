---
date: '2026-08-08'
description: Lär dig hur du konverterar IGS till PDF, HTML, JPG och PNG med GroupDocs.Viewer
  för Java. Step‑by‑step guide, prerequisites, och troubleshooting för Java developers.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Konvertera IGS till PDF, HTML, JPG och PNG med GroupDocs.Viewer för
  Java. Detailed setup, code snippets, och troubleshooting för Java developers.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Konvertera IGS till PDF, HTML, JPG & PNG med GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Konvertera IGS till PDF, HTML, JPG & PNG med GroupDocs.Viewer Java
type: docs
url: /sv/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Konvertera IGS till PDF, HTML, JPG & PNG med GroupDocs.Viewer Java

Om du behöver **konvertera IGS till PDF** (eller till HTML, JPG, PNG) direkt från en Java‑applikation, har du kommit till rätt ställe. I den här handledningen går vi igenom allt du behöver—från att installera biblioteket till att rendera 3‑D‑modellen i det format som passar ditt projekt. Du kommer att förstå varför GroupDocs.Viewer är ett solidt val för snabba, pålitliga konverteringar och du får färdiga kodsnuttar som du kan klistra in i din egen lösning.

![Konvertera IGS‑filer till HTML, JPG, PNG och PDF med GroupDocs.Viewer för Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Snabba svar
- **Kan jag konvertera IGS till PDF med Java?** Ja, använd `PdfViewOptions` tillsammans med `Viewer`‑API:t.  
- **Vilka utdataformat stöds?** HTML, JPG, PNG och PDF hanteras alla nativt.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs; en gratis provversion låter dig testa huvudfunktionerna.  
- **Vilken Java‑version krävs?** JDK 8 eller högre; biblioteket fungerar också på Java 11, 17 och senare.  
- **Är Maven det enda sättet att lägga till biblioteket?** Nej, du kan också använda Gradle eller manuellt lägga till JAR‑filerna i din classpath.

## Vad är konvertering av IGS till PDF?
Att konvertera IGS till PDF innebär att omvandla en neutral 3‑D‑CAD‑fil till ett statiskt, universellt visningsbart dokument. Detta gör det möjligt att dela designvisualiseringar med intressenter som saknar CAD‑verktyg, bädda in renderingen i rapporter eller arkivera modellen för efterlevnadsändamål.

## Varför använda GroupDocs.Viewer för IGS‑konverteringar?
GroupDocs.Viewer bearbetar IGS‑filer utan att kräva någon extern CAD‑programvara. Det stöder **50+ in‑ och utdataformat**, kan rendera sammansättningar som innehåller **hundratals delar** samtidigt som minnesanvändningen hålls under **200 MB**, och levererar resultat på under **2 sekunder** för typiska modeller på en standardserver. Dessa kvantifierade fördelar gör det till ett högpresterande, kostnadseffektivt val för företags‑pipeline.

## Förutsättningar
- **GroupDocs.Viewer för Java** ≥ 25.2 (den senaste stabila versionen).  
- **JDK 8+** installerat och konfigurerat i din IDE (IntelliJ IDEA, Eclipse, NetBeans osv.).  
- Grundläggande kunskap om Maven (valfritt men rekommenderas för beroendehantering).

## Konfigurera GroupDocs.Viewer för Java

### Maven‑beroende
Lägg till GroupDocs‑arkivet och Viewer‑beroendet i din `pom.xml`:

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

### Licensförvärv
GroupDocs.Viewer offers three licensing options:
- **Gratis provversion** – begränsad användning, perfekt för snabba proof‑of‑concept‑tester.  
- **Tillfällig licens** – fullständigt funktionspaket för en kort utvärderingsperiod, idealisk för pilotprojekt.  
- **Kommersiell licens** – obegränsad produktionsanvändning, inkluderar prioriterat stöd och uppdateringar.

### Grundläggande viewer‑initialisering
Klassen `Viewer` är ingångspunkten för alla renderingsoperationer. Den laddar källfilen, analyserar formatet och exponerar metoder för att producera önskat resultat.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendera IGS till HTML

### Hur konverterar man IGS till HTML?
Läs in IGS‑filen med en `Viewer`‑instans och skicka ett `HtmlViewOptions`‑objekt som bäddar in alla nödvändiga resurser. Anropet returnerar en enda HTML‑fil som innehåller den fullständiga 3‑D‑vyn, vilket gör det enkelt att bädda in i webbsidor. Du kan också anpassa renderingen genom att ställa in alternativ som sidstorlek, bakgrundsfärg och om interaktiva kontroller ska inkluderas.  
`HtmlViewOptions` konfigurerar hur HTML‑utdata genereras, inklusive resursembedding och sidlayout.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendera IGS till JPG

### Hur konverterar man IGS till JPG?
Skapa ett `JpgViewOptions`‑objekt, konfigurera önskad upplösning och komprimeringskvalitet, och låt `Viewer` generera rasterbilder för varje sida av modellen. De genererade JPG‑filerna kan sparas till en angiven katalog, och du kan justera kvalitetsparametern för att balansera filstorlek mot visuell trohet, vilket är användbart för miniatyrer eller högupplösta utskrifter.  
`JpgViewOptions` specificerar inställningar för JPG‑bildgenerering såsom upplösning, kvalitet och utskriftskatalog.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendera IGS till PNG

### Hur konverterar man IGS till PNG?
`PngViewOptions`‑klassen låter dig skapa förlustfria bilder med valfri transparens. Detta format är idealiskt för att överlagra modellen på färgade bakgrunder i marknadsföringsmaterial. Du kan också definiera upplösning och bakgrundsfärg för att matcha dina varumärkesriktlinjer, vilket säkerställer enhetligt utseende över alla genererade tillgångar.  
`PngViewOptions` definierar parametrar för PNG‑rendering, inklusive upplösning, transparens och bakgrundsfärg.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendera IGS till PDF

### Hur konverterar man IGS till PDF?
Använd `PdfViewOptions` för att skapa en paginerad PDF som bevarar den visuella layouten av 3‑D‑modellen. Du kan också bädda in typsnitt och kontrollera sidstorlek för att uppfylla företagets varumärkesriktlinjer. Ytterligare inställningar låter dig specificera bildkvalitet, komprimeringsnivå och om en innehållsförteckning ska inkluderas för flersidiga sammansättningar.  
`PdfViewOptions` styr PDF‑skapandet, vilket möjliggör konfiguration av sidstorlek, bildkvalitet och typsnitts‑embedding.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Praktiska tillämpningar
- **Webbportaler** – bädda in HTML‑renderade modeller direkt i produktkonfiguratorer, så att kunder kan rotera och zooma utan att installera plugins.  
- **Marknadsföringsmaterial** – generera högupplösta JPG/PNG‑bilder för broschyrer, presentationsbilder och inlägg på sociala medier.  
- **Teknisk dokumentation** – inkludera PDF‑renderingar av CAD‑modeller i användarmanualer, vilket säkerställer att ingenjörer kan visa design offline.  
- **Kvalitetssäkring** – automatisera skapandet av miniatyrer för tusentals IGS‑filer, vilket påskyndar arbetsflöden för visuell inspektion.

## Vanliga problem & lösningar

| Problem | Lösning |
|-------|----------|
| **Mapp för utdata hittades inte** | Verifiera sökvägen som skickas till `Path outputDirectory` och säkerställ att Java‑processen har skrivrättigheter till mål‑katalogen. |
| **Tomma sidor i PDF** | Bekräfta att käll‑IGS‑filen inte är korrupt; öppna den först i en inbyggd CAD‑visare. |
| **Långsam rendering för stora sammansättningar** | Öka JVM‑heapen (`-Xmx2g` eller mer) och överväg att rendera sida‑för‑sida med `viewer.getPageCount()` för att bearbeta i delar. |
| **Saknade typsnitt i PDF** | Använd `PdfViewOptions` för att bädda in nödvändiga typsnitt eller installera de saknade typsnitten på servern som hostar konverteringstjänsten. |

## Vanliga frågor

**Q: Kan jag konvertera flera IGS‑filer i ett enda körning?**  
A: Ja. Iterera över en samling av filsökvägar och anropa den lämpliga `view`‑metoden för varje fil inom samma `Viewer`‑instans.

**Q: Är det möjligt att anpassa PDF‑sidstorleken?**  
A: Absolut. `PdfViewOptions` erbjuder `setPageSize(PageSize.A4)`, `PageSize.Letter` och anpassade dimensioner via `setCustomSize(width, height)`.

**Q: Behöver jag en separat licens för varje utdataformat?**  
A: Nej. En enda GroupDocs.Viewer‑licens täcker alla stödda format, inklusive HTML, JPG, PNG och PDF.

**Q: Hur stor kan en IGS‑fil vara innan prestandan försämras?**  
A: Biblioteket hanterar pålitligt filer upp till **500 MB**; för modeller större än 200 MB, allokera extra JVM‑minne och överväg att rendera i batchar.

**Q: Kan jag rendera endast en specifik vy eller orientering?**  
A: GroupDocs.Viewer renderar standardorienteringen som definierats i IGS‑filen. För anpassade vyer, förbehandla filen med ett CAD‑verktyg eller justera modellen innan konvertering.

---

**Senast uppdaterad:** 2026-08-08  
**Testad med:** GroupDocs.Viewer 25.2 för Java  
**Författare:** GroupDocs

## Relaterade handledningar

- [konvertera cdr till html, jpg, png, pdf med GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Hur man konverterar pdf till html och optimerar bildkvalitet i Java med GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)