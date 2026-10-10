---
date: '2026-10-10'
description: Lär dig hur du konverterar zip till html med GroupDocs.Viewer Java, ställer
  in objekt per sida, bäddar in resurser i html och batchkonverterar arkiv effektivt.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: Lär dig hur du konverterar zip till html med GroupDocs.Viewer Java,
  bäddar in resurser, anger objekt per sida och batch‑processar arkiv för snabba,
  portabla webb‑förhandsvisningar.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: Konvertera zip till HTML med paginering i GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Konvertera zip till html och ange objekt per sida med GroupDocs.Viewer Java
type: docs
url: /sv/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera zip till html och ange objekt per sida med GroupDocs.Viewer Java

I många webbapplikationer behöver du visa innehållet i ett ZIP- eller RAR-arkiv direkt i en webbläsare. **Hur man konverterar zip**-filer till HTML med GroupDocs.Viewer för Java är ett vanligt krav, och biblioteket låter dig bädda in bilder, CSS och typsnitt så att resultatet blir en enda, portabel sida. Denna handledning guidar dig genom allt—från Maven‑konfiguration till rendering av flera sidor—och förklarar varför varje alternativ är viktigt för prestanda och användbarhet.

![Konvertera arkiv till HTML med GroupDocs.Viewer för Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Snabba svar
- **Vad styr “set items per page”?** Det bestämmer hur många filer eller mappar från ett arkiv som visas på varje genererad HTML‑sida.  
- **Kan jag bädda in bilder och CSS direkt i HTML?** Ja – använd `forEmbeddedResources`‑alternativet för att bädda in resurser i HTML.  
- **Är batch‑konvertering möjlig?** Absolut; du kan loopa över en samling arkiv och rendera varje med samma inställningar.  
- **Behöver jag Maven för att använda GroupDocs.Viewer?** Ja, lägg till `groupdocs-viewer`‑Maven‑beroendet som visas nedan.  
- **Vilka utdataformat stöds?** En‑sides HTML och flersidigt HTML är båda tillgängliga, och biblioteket stödjer över 50 inmatningsarkivtyper.

## Vad är “set items per page” i GroupDocs.Viewer?
Det talar om för visaren hur många arkivposter (filer eller mappar) som ska visas på varje HTML‑sida när du genererar ett flersidigt dokument. Att justera detta värde hjälper dig att balansera sidstorlek och navigeringshastighet, särskilt för stora arkiv, genom att begränsa mängden data som laddas per sida och minska renderingtiden för slutanvändare.

## Varför bädda in resurser i HTML?
Att bädda in resurser (bilder, CSS, typsnitt) direkt i HTML‑filen skapar ett enda, portabelt dokument som kan öppnas utan externa filer. Detta är idealiskt för e‑postbilagor, offline‑visning eller för att bädda in resultatet i andra webbsidor. Det eliminerar också behovet av att hantera externa tillgångssökvägar.

## Förutsättningar

- **Krävda bibliotek:** Inkludera GroupDocs.Viewer version 25.2 eller senare.  
- **Miljö:** Java Development Kit (JDK) installerat och konfigurerat.  
- **Kunskap:** Grundläggande Java och Maven‑beroendehantering.  

## Maven GroupDocs Viewer‑inställning

Lägg till GroupDocs‑förrådet och viewer‑beroendet i din `pom.xml`:

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
GroupDocs.Viewer erbjuder en **gratis provlänk**, en tillfällig licens eller ett fullständigt köpalternativ. Välj den som passar ditt projekts tidsplan.

## Grundläggande initiering
Klassen `Viewer` är ingångspunkten för rendering av dokument och arkiv. Efter Maven‑inställningen, inför visaren i din kod:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Hur man renderar arkiv till en‑sidig html
`HtmlViewOptions`‑klassen definierar inställningar för HTML‑utdata, såsom inbäddning av resurser. Läs in arkivet, konfigurera HTML‑alternativen för att bädda in resurser och rendera allt till en självständig sida. Detta skapar en enda HTML‑fil som innehåller alla filer, bilder, CSS och typsnitt, klar för offline‑användning eller e‑postbilaga.

**Direkt svar:** Skapa en `Viewer`‑instans för ZIP‑filen, anropa `HtmlViewOptions.forEmbeddedResources()` och anropa `viewer.view(documentPath, options)`. Detta producerar en enda HTML‑fil som innehåller alla filer, bilder, CSS och typsnitt, klar för offline‑användning eller e‑postbilaga.

### Steg 1: Definiera utdatamapp
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Steg 2: Ange filnamn för en‑sidig utdata
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Steg 3: Initiera visaren
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Steg 4: Konfigurera renderingsalternativ (bädda in resurser html)
`HtmlViewOptions`‑klassen definierar inställningar för HTML‑utdata, såsom inbäddning av resurser. Använd `forEmbeddedResources()` för att samla allt i en fil.

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Steg 5: Rendera som en enda sida
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Hur man renderar arkiv till flersidig html och anger objekt per sida
`HtmlViewOptions`‑klassen stödjer också paginering. Genom att anropa `options.setItemsPerPage(N)` instruerar du visaren att dela upp arkivet i flera HTML‑filer, där varje visar upp till **N** poster. Detta tillvägagångssätt förbättrar navigeringshastigheten för stora arkiv samtidigt som varje sida förblir lätt.

**Direkt svar:** Använd `HtmlViewOptions.forEmbeddedResources()`, anropa `options.setItemsPerPage(N)` och rendera arkivet. Visaren kommer att generera separata HTML‑filer—en per sida—varje innehåller upp till **N** poster, vilket snabbar upp navigeringen för stora arkiv.

### Steg 1: Återanvänd utdatamappen
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Steg 2: Definiera filnamnsformat för flera sidor
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Steg 3: Initiera visaren igen
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Steg 4: Konfigurera flersidiga alternativ (bädda in resurser html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Steg 5: Ange objekt per sida (primärt nyckelord i handlingen)
`options.setItemsPerPage(20); // how to convert zip archives with 20 entries per page`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktiska tillämpningar

- **Dokumenthanteringssystem:** Lägg till förhandsgranskning av arkiv utan att installera extra visare.  
- **Webbportaler:** Erbjud användare ett snabbt, utan nedladdning sätt att utforska samlade dokument.  
- **Samarbetsverktyg:** Låt team inspektera delade arkiv direkt i webbläsaren.

## Prestandaöverväganden

- **Resurshantering:** Håll minnesanvändning låg genom att bearbeta arkiv i strömmar; visaren kan hantera arkiv upp till 500 MB utan att ladda hela filen i minnet.  
- **Batch‑konvertera arkiv:** Loop igenom en lista med arkivfiler och anropa samma renderingslogik för att maximera genomströmning.  
- **Cache‑strategi:** Spara renderad HTML i en cache om samma arkiv ofta begärs, vilket minskar återkommande bearbetningstid med upp till 70 %.

## Vanliga frågor

**Q: Vad är GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java är ett server‑sidigt bibliotek som renderar över 50 dokument‑ och arkivformat—inklusive ZIP och RAR—till HTML, PDF eller bildfiler utan att kräva externa applikationer.

**Q: Hur kan jag få en gratis provversion av GroupDocs.Viewer?**  
A: Besök [gratis provlänk](https://releases.groupdocs.com/viewer/java/) för att ladda ner och testa.

**Q: Kan jag konvertera andra dokumenttyper än arkiv?**  
A: Ja, visaren stödjer PDF‑filer, Word, Excel, PowerPoint och över 35 ytterligare format.

**Q: Vad ska jag göra om rendering är långsam?**  
A: Minska antalet objekt per sida, aktivera streaming eller bearbeta arkiv i mindre batcher för att förbättra hastigheten.

**Q: Var kan jag få hjälp eller support?**  
A: Kontakta via [supportforum](https://forum.groupdocs.com/c/viewer/9).

**Q: Är det möjligt att bädda in CSS och bilder direkt i HTML?**  
A: Absolut—använd `HtmlViewOptions.forEmbeddedResources` som visas i exemplen.

**Q: Hur batch‑konverterar jag en mapp med arkiv?**  
A: Iterera över varje fil med en `for`‑loop och tillämpa samma `Viewer`‑ och `HtmlViewOptions`‑konfiguration för varje iteration.

**Q: Var kan jag diskutera problem med andra användare?**  
A: Besök [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) för community‑diskussioner.

## Resurser

- **Dokumentation:** Fördjupa dig i funktionaliteten med [GroupDocs-dokumentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑referens:** Utforska hela API‑et på [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Nedladdning:** Hämta de senaste binärerna från [nedladdningssidan](https://releases.groupdocs.com/viewer/java/).  
- **Köp och licensiering:** Granska alternativ på [köpsidan](https://purchase.groupdocs.com/buy).  
- **Support och community:** Delta i diskussioner på [supportforum](https://forum.groupdocs.com/c/viewer/9).  
- **GroupDocs‑forum:** Få community‑hjälp på [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Senast uppdaterad:** 2026-10-10  
**Testat med:** GroupDocs.Viewer 25.2  
**Författare:** GroupDocs

## Relaterade handledningar

- [Hur man konverterar zip till HTML och renderar zip‑mappar i Java med GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [konvertera zip till pdf med GroupDocs.Viewer Java – Anpassade filnamn](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Hur man konverterar DOCX till HTML med GroupDocs.Viewer för Java: En steg‑för‑steg‑guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}