---
date: '2026-06-05'
description: Lär dig hur du konverterar docx till jpeg med GroupDocs Viewer för Java,
  inklusive installation, konfiguration och praktisk bildrendering.
keywords:
- convert docx to jpeg
- convert word to image
- GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  headline: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  name: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  steps:
  - name: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
    text: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
  - name: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
    text: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
  - name: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
    text: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
  type: HowTo
- questions:
  - answer: '`DocumentSplitter` allows you to divide a large document into separate
      parts for easier processing. Split the source file into smaller sections using
      `DocumentSplitter` before rendering, or process pages in sequential batches
      to keep memory usage low.'
    question: How do I handle documents larger than 500 pages?
  - answer: Yes, replace `JpgViewOptions` with `PngViewOptions` and adjust the file‑path
      pattern accordingly.
    question: Can I output PNG instead of JPEG?
  - answer: A free trial license works for evaluation and development, but a commercial
      license is required for production deployments.
    question: Is a license mandatory for development builds?
  - answer: Absolutely. Pass the password to the `Viewer` constructor to unlock the
      document before rendering.
    question: Does the library support password‑protected DOCX files?
  - answer: GroupDocs.Viewer for Java is compatible with Java 8, 11, and 17.
    question: What Java versions are supported?
  type: FAQPage
title: Hur man konverterar DOCX till JPEG med GroupDocs Viewer för Java
type: docs
url: /sv/java/rendering-basics/groupdocs-viewer-java-render-docx-to-image/
weight: 1
---

# Konvertera DOCX till JPEG med GroupDocs Viewer för Java

Att konvertera **DOCX till JPEG** låter dig dela dokumentsidor som lätta bilder som visas konsekvent i webbläsare och e‑postklienter. I den här guiden kommer du att se hur du använder **GroupDocs.Viewer for Java** för att omvandla en Word‑fil till högkvalitativa JPEG‑bilder, anpassa dimensioner och hantera resurser effektivt.

![Rendera DOCX till bild med GroupDocs.Viewer för Java](/viewer/rendering-basics/render-docx-to-image.png)

[Rendera DOCX till bild med GroupDocs.Viewer för Java](/viewer/rendering-basics/render-docx-to-image.png)

## Snabba svar
- **Vilket bibliotek hanterar DOCX → JPEG‑konvertering?** GroupDocs.Viewer for Java.  
- **Hur många kodrader behövs?** Endast två rader för att läsa in och rendera filen.  
- **Kan jag ange anpassad bildstorlek?** Ja, via `JpgViewOptions` kan du definiera bredd och höjd.  
- **Krävs en licens för produktion?** En kommersiell licens behövs; en gratis provversion är tillgänglig.  
- **Fungerar det med stora dokument?** Ja, det bearbetar filer upp till 500 sidor samtidigt som minnesanvändningen hålls under 200 MB.

## Vad är “convert docx to jpeg”?
Att konvertera en DOCX‑fil till JPEG skapar en bild per sida, vilket bevarar den ursprungliga layouten, teckensnitten och grafiken. Varje JPEG kan visas i webbläsare, bäddas in i e‑post eller användas som miniatyrbilder. Detta format är lättviktigt, brett stödjande och idealiskt för förhandsgranskning av dokument utan att kräva Microsoft Word eller extra plugins.

## Varför använda GroupDocs Viewer för Java för denna konvertering?
GroupDocs.Viewer stöder **50+ in‑ och utdataformat** och kan rendera dokument upp till **500 sidor** på under **2 sekunder per sida** på standard serverhårdvara. API‑et fungerar utan att Microsoft Office är installerat, vilket garanterar konsekvent layoutbevarande och låg minnesanvändning.

## Förutsättningar
- **Java Development Kit** 8 eller nyare.  
- **Maven** för beroendehantering (eller manuell JAR‑inkludering).  
- **GroupDocs.Viewer for Java**‑biblioteket (nedladdningsbart från den officiella webbplatsen).  
- Grundläggande kunskap om Java‑projektstruktur.

## Installera GroupDocs Viewer för Java

För att lägga till biblioteket i ett Maven‑projekt, infoga följande beroende i din `pom.xml`:

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
GroupDocs erbjuder en gratis provperiod för att utforska funktioner. För utökad användning, skaffa en tillfällig eller köpt licens via deras officiella webbplats.

## Hur konverterar man DOCX till JPEG?

Klassen `Viewer` läser ett dokument och tillhandahåller renderingsfunktioner.  
`JpgViewOptions` konfigurerar JPEG‑utdatainställningar såsom storlek, kvalitet och filnamngivning.

För att konvertera, skapa en instans av `Viewer` med DOCX‑sökvägen, skapa `JpgViewOptions` som pekar på en utdatamapp, ange eventuellt dimensioner och kvalitet, och anropa `viewer.view(options)`. Biblioteket bearbetar varje sida och sparar en JPEG‑fil enligt det angivna namnmönstret.

## Implementeringsguide

### Rendera DOCX till JPEG

Omvandla ett Word‑dokument till JPEG‑bilder för förhandsgranskning eller delningsändamål.

#### Steg‑för‑steg‑implementering

**1. Skapa utdatamapp**  
Definiera mappen där renderade JPEG‑bilder ska sparas:

```java
import com.groupdocs.viewer.Viewer;

public class DocumentRenderer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
            // Configuration and rendering logic goes here
        }
    }
}
```

**2. Specificera filvägsmönster**  
Skapa ett namnmönster som inkluderar sidnumret, t.ex. `page_{0}.jpg`:

```java
import java.nio.file.Path;

// Define output directory using Path API
Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("rendered_document");
```

**3. Konfigurera bildalternativ**  
`JpgViewOptions` låter dig ange bredd, höjd och kvalitet. Till exempel 1024 × 768 pixlar med 90 % kvalitet:

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**4. Rendera dokumentet**  
Använd ett try‑with‑resources‑block för att säkerställa att `Viewer`‑instansen stängs automatiskt, vilket frigör inhemska resurser och förhindrar minnesläckor:

```java
import com.groupdocs.viewer.options.JpgViewOptions;

// Create JpgViewOptions with specified path format
JpgViewOptions viewOptions = new JpgViewOptions(pageFilePathFormat);

// Set custom width and height for each image
viewOptions.setWidth(600);  // Image width in pixels
viewOptions.setHeight(800); // Image height in pixels
```

### Vanliga problem och lösningar
- **Problem med filsökväg** – Verifiera att utdatamappen finns och att applikationen har skrivbehörighet.  
- **Minneshantering** – För dokument med mer än 300 sidor, överväg att bearbeta sidor i batcher och anropa `System.gc()` efter varje batch.  
- **Ej stödda element** – Vissa avancerade Word‑funktioner (t.ex. inbäddade makron) ignoreras under rendering; de påverkar inte den visuella utdata.

## Praktiska tillämpningar

1. **Förhandsgranskning** – Visa dokumentminiatyrer i ett innehållshanteringssystem utan att kräva en helskärmsvisare.  
2. **E‑postbilagor** – Bädda in JPEG‑bilder sida‑för‑sida i e‑post för att undvika begränsningar i bilagestorlek.  
3. **Webbvisning** – Rendera sidor som bilder för snabb laddning på låg‑bandbreddanslutningar.

## Prestandaöverväganden

- **Resurshantering** – Använd alltid try‑with‑resources för att stänga `Viewer`.  
- **Bilddimensioner** – Mindre dimensioner minskar RAM‑användning; välj den minsta storleken som uppfyller kraven på visuell kvalitet.  
- **Asynkron bearbetning** – För masskonverteringar, kör renderingsuppgifter i en separat trådpott för att hålla UI‑responsen.

## Vanliga frågor

**Q: Hur hanterar jag dokument med mer än 500 sidor?**  
A: `DocumentSplitter` låter dig dela ett stort dokument i separata delar för enklare bearbetning. Dela källfilen i mindre sektioner med `DocumentSplitter` innan rendering, eller bearbeta sidor i sekventiella batcher för att hålla minnesanvändningen låg.

**Q: Kan jag exportera PNG istället för JPEG?**  
A: Ja, ersätt `JpgViewOptions` med `PngViewOptions` och justera filvägsmönstret därefter.

**Q: Är en licens obligatorisk för utvecklingsbyggen?**  
A: En gratis provlicens fungerar för utvärdering och utveckling, men en kommersiell licens krävs för produktionsdistributioner.

**Q: Stöder biblioteket lösenordsskyddade DOCX‑filer?**  
A: Absolut. Skicka lösenordet till `Viewer`‑konstruktorn för att låsa upp dokumentet innan rendering.

**Q: Vilka Java‑versioner stöds?**  
A: GroupDocs.Viewer för Java är kompatibel med Java 8, 11 och 17.

## Resurser

- **Dokumentation**: [GroupDocs Viewer Java-dokumentation](https://docs.groupdocs.com/viewer/java/)
- **API‑referens**: [GroupDocs API‑referens](https://reference.groupdocs.com/viewer/java/)
- **Ladda ner GroupDocs.Viewer**: [Nedladdningssida](https://releases.groupdocs.com/viewer/java/)
- **Köp licens**: [Köp GroupDocs](https://purchase.groupdocs.com/buy)
- **Gratis prov**: [Prova GroupDocs gratis](https://releases.groupdocs.com/viewer/java/)
- **Tillfällig licens**: [Skaffa en tillfällig licens](https://purchase.groupdocs.com/temporary-license/)
- **Supportforum**: [GroupDocs supportforum](https://forum.groupdocs.com/c/viewer/9)

---

**Senast uppdaterad:** 2026-06-05  
**Testat med:** GroupDocs.Viewer 23.12 för Java  
**Författare:** GroupDocs

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

## Relaterade handledningar

- [Hur man konverterar DOCX‑filer till PNG med GroupDocs.Viewer för Java](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)
- [Hur man konverterar DOCX till HTML med GroupDocs.Viewer för Java: En steg‑för‑steg‑guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Rendera DOCX‑filer från InputStream i Java med GroupDocs.Viewer](/viewer/java/rendering-basics/render-docx-from-inputstream-groupdocs-viewer-java/)