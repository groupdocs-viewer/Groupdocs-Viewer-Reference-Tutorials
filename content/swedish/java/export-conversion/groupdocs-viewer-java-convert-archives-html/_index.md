---
date: '2026-08-03'
description: Lär dig hur du konverterar zip till html med GroupDocs.Viewer Java, sätter
  objekt per sida, embed resources html och batch convert archives effektivt.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Lär dig hur du konverterar zip till html med GroupDocs.Viewer Java,
  sätter objekt per sida, embed resources html och batch convert archives effektivt.
  Följ step‑by‑step code och performance tips.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Konvertera zip till html och ange objekt per sida med GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
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

# Konvertera zip till html och ange objekt per sida med GroupDocs.Viewer Java

I många webbapplikationer behöver du visa innehållet i ett ZIP- eller RAR-arkiv direkt i en webbläsare. Med GroupDocs.Viewer för Java kan du **convert zip to html** i ett enda steg, kontrollera hur många arkivposter som visas på varje sida, bädda in alla stödjande bilder och CSS, och till och med batch‑processa dussintals arkiv. Denna handledning guidar dig genom hela arbetsflödet, från Maven‑inställning till flersidig rendering, och förklarar varför varje inställning är viktig för prestanda och användbarhet.

![Konvertera arkiv till HTML med GroupDocs.Viewer för Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Snabba svar
- **Vad styr “set items per page”?** Det bestämmer hur många filer eller mappar från ett arkiv som visas på varje genererad HTML‑sida.  
- **Kan jag bädda in bilder och CSS direkt i HTML?** Ja – använd `forEmbeddedResources`‑alternativet för att bädda in resurser i HTML.  
- **Är batch‑konvertering möjlig?** Absolut; du kan loopa över en samling arkiv och rendera var och en med samma inställningar.  
- **Behöver jag Maven för att använda GroupDocs.Viewer?** Ja, lägg till `groupdocs-viewer`‑Maven‑beroendet som visas nedan.  
- **Vilka utdataformat stöds?** En‑sides HTML och flersidig HTML är båda tillgängliga, och biblioteket stöder 50+ inmatningsarkivtyper.

## Vad är “set items per page” i GroupDocs.Viewer?
Inställningen **set items per page** tillhör alternativen för arkivrendering. Den talar om för visaren hur många arkivposter (filer eller mappar) som ska visas på varje HTML‑sida när du genererar ett flersidigt HTML‑dokument. Att justera detta värde hjälper dig att balansera sidstorlek och navigeringshastighet, särskilt för stora arkiv.

## Varför bädda in resurser i HTML?
Att bädda in resurser (bilder, CSS, typsnitt) direkt i HTML‑filen skapar ett enda, portabelt dokument som kan öppnas utan externa filer. Detta är idealiskt för e‑postbilagor, offline‑visning eller för att bädda in resultatet i andra webbsidor. Detta tillvägagångssätt förenklar även distribution eftersom inga externa resursvägar behöver hanteras.

## Förutsättningar
- **Nödvändiga bibliotek:** Include GroupDocs.Viewer version 25.2 or later.  
- **Miljö:** Java Development Kit (JDK) installed and configured.  
- **Kunskap:** Basic Java and Maven dependency management.  

## Maven GroupDocs Viewer‑inställning
Lägg till GroupDocs‑arkivet och visardependenserna i din `pom.xml`:

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
GroupDocs.Viewer erbjuder en **gratis provlänk**, en tillfällig licens eller ett fullständigt köpalternativ. Välj den som passar ditt projekts tidslinje.

### Grundläggande initiering
Efter Maven‑inställningen, inför visaren i din kod:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Hur man renderar arkiv till en‑sidig html
Viewer är kärnklassen som laddar ett dokument eller arkiv för rendering.

För att generera en enda HTML‑fil som innehåller hela arkivet, skapa en `Viewer`‑instans för ZIP‑filen och använd `HtmlViewOptions.forEmbeddedResources()` för att bädda in alla bilder, CSS och typsnitt. Rendering av arkivet med dessa alternativ producerar en självständig sida som är lämplig för e‑post eller offline‑användning.

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

### Steg 4: Konfigurera renderingsalternativ (bädda in resurser i html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Steg 5: Rendera som en enda sida
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Hur man renderar arkiv till flersidig html och anger objekt per sida
`HtmlViewOptions` konfigurerar hur visaren renderar HTML‑utdata, inklusive paginering och resursinbäddning.

För att dela ett arkiv i flera sidor, skapa `HtmlViewOptions.forEmbeddedResources()` och ange önskad sidstorlek med `options.setItemsPerPage(20)`. Visaren kommer att generera separata HTML‑filer, var och en visar upp till det angivna antalet poster, vilket förbättrar navigeringen för stora arkiv och säkerställer snabbare laddning.

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

### Steg 4: Konfigurera flersidiga alternativ (bädda in resurser i html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Steg 5: Ange objekt per sida (primärt nyckelord i handlingen)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktiska tillämpningar
- **Document management systems:** Lägg till förhandsgranskning av arkiv utan att installera extra visare.  
- **Web portals:** Erbjud användare ett snabbt, utan nedladdning‑sätt att utforska samlade dokument.  
- **Collaboration tools:** Låt team inspektera delade arkiv direkt i webbläsaren.

## Prestandaöverväganden
- **Resource management:** Håll minnesanvändning låg genom att bearbeta arkiv i strömmar; visaren kan hantera arkiv upp till 500 MB utan att ladda hela filen i minnet.  
- **Batch convert archives:** Loopa igenom en lista med arkivfiler och anropa samma renderingslogik för att maximera genomströmning.  
- **Caching strategy:** Spara renderad HTML i en cache om samma arkiv ofta begärs, vilket minskar återupprepad bearbetningstid med upp till 70 %.

## Vanliga frågor
**Q: Vad är GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java är ett server‑side‑bibliotek som renderar över 50 dokument‑ och arkivformat—inklusive ZIP och RAR—till HTML, PDF eller bildfiler utan att kräva externa applikationer.

**Q: Hur kan jag få en gratis provversion av GroupDocs.Viewer?**  
A: Besök den [gratis provlänken](https://releases.groupdocs.com/viewer/java/) för att ladda ner och testa.

**Q: Kan jag konvertera andra dokumenttyper förutom arkiv?**  
A: Ja, visaren stöder PDF‑filer, Word, Excel, PowerPoint och 35+ ytterligare format.

**Q: Vad ska jag göra om renderingen är långsam?**  
A: Minska antalet objekt per sida, aktivera strömning, eller bearbeta arkiv i mindre batcher för att förbättra hastigheten.

**Q: Var kan jag få hjälp eller support?**  
A: Kontakta via [supportforumet](https://forum.groupdocs.com/c/viewer/9).

**Q: Är det möjligt att bädda in CSS och bilder direkt i HTML?**  
A: Absolut—använd `HtmlViewOptions.forEmbeddedResources` som visas i exemplen.

**Q: Hur batch‑konverterar jag en mapp med arkiv?**  
A: Iterera över varje fil med en `for`‑loop, och tillämpa samma `Viewer`‑ och `HtmlViewOptions`‑konfiguration för varje iteration.

## Resurser
- **Documentation:** Fördjupa dig i funktionaliteten med [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API reference:** Utforska hela API:n på [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Hämta de senaste binärerna från [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and licensing:** Granska alternativ på [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and community:** Gå med i diskussioner på [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Senast uppdaterad:** 2026-08-03  
**Testat med:** GroupDocs.Viewer 25.2  
**Författare:** GroupDocs

## Relaterade handledningar
- [Hur man konverterar zip till HTML och renderar zip‑mappar i Java med GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [konvertera zip till pdf med GroupDocs.Viewer Java - Anpassade filnamn](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Hur man konverterar DOCX till HTML med GroupDocs.Viewer för Java: En steg‑för‑steg‑guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)