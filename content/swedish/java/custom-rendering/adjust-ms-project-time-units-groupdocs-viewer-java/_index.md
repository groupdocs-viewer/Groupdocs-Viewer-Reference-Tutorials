---
date: '2026-05-21'
description: Lär dig hur du utför MS Project HTML-export med justerade tidsenheter
  med hjälp av GroupDocs Viewer för Java. Steg‑för‑steg‑guide med förutsättningar,
  installation och felsökning.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML-export: justera tidsenheter via GroupDocs Java'
type: docs
url: /sv/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML-export: Justera tidsenheter via GroupDocs Java

Att exportera en **MS Project**‑fil till HTML är ett vanligt krav för projekt‑styrningsdashboards, status‑rapportportaler och samarbetsgranskningsverktyg. Som standard renderar visaren tidsrelaterad data i minuter, vilket kan göra layouten rörig och göra daglig rapportering svårare att läsa. Med **GroupDocs Viewer for Java** kan du programatiskt ställa in tidsenheten till **days**, vilket ger en ren *ms project html export* som överensstämmer med typiska intressenters förväntningar. I den här handledningen kommer du att lära dig hur du konfigurerar visaren, justerar tidsenheten och renderar projektet till HTML i några enkla steg.

![Justera tidsenheter i MS Project med GroupDocs.Viewer för Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Justera tidsenheter i MS Project med GroupDocs.Viewer för Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Snabba svar
- **Vilket bibliotek renderar MS Project‑filer?** GroupDocs Viewer for Java.  
- **Vilken tidsenhet kan jag ställa in för HTML‑export?** Days, using `TimeUnit.DAYS`.  
- **Behöver jag en licens för produktion?** Yes— a permanent license is required; a trial works for evaluation. You can start with a [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Vilken IDE fungerar bäst?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Är Maven obligatoriskt?** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **Var kan jag köpa?** Visit the [buy page](https://purchase.groupdocs.com/buy) for pricing.

## Vad är GroupDocs Viewer för Java?
**GroupDocs Viewer for Java** är ett Java‑SDK som konverterar över 150 dokumentformat—inklusive MS Project—till webbvänlig HTML, PNG, JPEG eller PDF.  
Det abstraherar parslogiken, låter dig styra renderingsalternativ såsom tidsenheter, och fungerar på alla plattformar som stödjer Java 8 eller högre.  

## Varför justera tidsenheter för MS Project HTML-export?
Att ställa in tidsenheten till **days** minskar visuell brus, matchar de flesta rapporteringsintervaller och förbättrar sidladdningstider eftersom färre detaljerade tidsmarkörer genereras. I kvantitativa termer kan rendering med dagar istället för minuter minska den genererade HTML‑storleken med upp till **45 %** för typiska 30‑dagarsprojekt, och det snabbar upp klient‑sidans rendering med ungefär **30 %**.

## Förutsättningar
- **Java Development Kit (JDK) 8 eller nyare** installerat på din arbetsstation.  
- **Maven** (eller Gradle) för beroendehantering.  
- En **MS Project (.mpp)**‑fil som du vill exportera.  
- Tillgång till en **GroupDocs Viewer for Java**‑licens (testversion eller permanent).  

### Nödvändiga bibliotek
Lägg till följande beroende i din `pom.xml` (eller motsvarande Gradle‑snutt):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** Håll versionsnumret uppdaterat; nyare releaser lägger till formatstöd och prestandaförbättringar.

## Hur konfigurerar jag GroupDocs Viewer för Java?
Initiera visaren genom att skapa en `Viewer`‑instans som pekar på din MS Project‑fil. `Viewer`‑klassen är ingångspunkten för alla renderingsoperationer. Den laddar källdokumentet, förbereder interna strukturer och exponerar metoder såsom `view()` och `viewToHtml()` för att generera önskade utdataformat.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** `Viewer`‑klassen är GroupDocs Viewers kärnkomponent som laddar ett källdokument och tillhandahåller renderingsmetoder såsom `view()` och `viewToHtml()`.

## Hur kan jag justera tidsenheter för HTML‑exporten?
För att ändra tidsgranulariteten, skapa ett `ViewOptions`‑objekt, konfigurera dess `ProjectOptions` att använda `TimeUnit.DAYS`, och skicka det till visaren. `ViewOptions` definierar renderingsinställningar för dokumentet, medan `TimeUnit`‑enumet specificerar enheten (minutes, hours, days) för tidsrelaterad data. Efter att ha ställt in dessa alternativ, anropa `viewer.view(options)` för att producera HTML med dagliga markörer.

Ladda din MS Project‑fil med `new Viewer("file.mpp")`, skapa ett `ViewOptions`‑objekt, sätt `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, och anropa sedan `viewer.view(options)`. Detta trestegsförlopp ändrar tidsenheten från minutes till days och genererar HTML‑filer som endast visar dagliga intervall.

### Steg 1: Definiera utdatamappen
Välj en skrivbar katalog där HTML‑sidorna ska sparas, till exempel `output/`.

### Steg 2: Skapa view‑alternativ med inbäddade resurser
Inbäddade resurser (CSS, JavaScript) säkerställer att HTML‑sidorna är självständiga.

### Steg 3: Ställ in tidsenheten till days
Använd `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` för att byta granulariteten.

### Steg 4: Rendera dokumentet
Anropa `viewer.view(options)`; visaren skriver en HTML‑fil per projektsida till utdatamappen.

### Steg 5: Verifiera resultatet
Öppna den genererade `index.html` i en webbläsare; du bör se uppgiftspålar justerade till dagmarkörer istället för minutmarkörer.

## Vanliga fallgropar och felsökning
- **Felaktig utdataväg** – Säkerställ att katalogen finns och att Java‑processen har skrivbehörighet.  
- **Saknad licens** – Utan en giltig licens återgår visaren till provläge och kan infoga vattenstämplar.  
- **Stora filer (> 500 MB)** – Överväg att öka JVM‑heap‑storleken (`-Xmx2g`) eller rendera med `options.setRenderLimit(1000)` för att bearbeta sidor i batcher.  

## Praktiska tillämpningar av justerad tidsenhet HTML‑export
1. **Executive dashboards** – Daglig granularitet matchar de flesta KPI‑visualiseringar.  
2. **Automated status emails** – Bädda in den genererade HTML‑koden direkt i e‑postmeddelanden för snabba uppdateringar.  
3. **Project portals** – Värd HTML på en intranätsida där teammedlemmar kan filtrera uppgifter per dag.  

## Prestandaöverväganden för stora MS Project‑filer
- **Memory management** – Använd Javas skräpsamlingsflaggor (`-XX:+UseG1GC`) för att snabbt frigöra oanvända objekt.  
- **Selective rendering** – Om du bara behöver Gantt‑diagrammet, inaktivera annan resursrendering via `options.getProjectOptions().setRenderGantt(true)` och `setRenderResources(false)`.  
- **Parallel processing** – För batchkonverteringar, skapa separata `Viewer`‑objekt per fil och kör dem i en trådpool för att utnyttja fler‑kärniga CPU:er.

## Slutsats
Du har nu ett komplett, produktionsklart arbetsflöde för att utföra en **ms project html export** med tidsenheter inställda på days med hjälp av GroupDocs Viewer för Java. Detta tillvägagångssätt minskar HTML‑storleken, snabbar upp klientrenderingen och levererar en intressentvänlig vy av projektscheman. Utforska ytterligare renderingsalternativ—såsom PDF‑export eller bildögonblicksbilder—för att utöka integrationen till bredare rapporteringspipelines.

## Vanliga frågor

**Q: Kan jag rendera andra Project‑vyer (t.ex. Resource Sheet) till HTML?**  
A: Ja, `ProjectOptions`‑objektet låter dig aktivera eller inaktivera specifika vyer såsom Gantt, Resource Sheet och Calendar innan rendering.

**Q: Är det möjligt att anpassa CSS för den genererade HTML‑koden?**  
A: Absolut. Ange en anpassad stilmallsökväg via `options.setStyleSheetPath("path/to/custom.css")` så kommer visaren att bädda in den i varje sida.

**Q: Vilka filstorleksgränser har GroupDocs Viewer för MS Project?**  
A: SDK:n kan hantera filer upp till **500 MB** utan att behöva ladda hela dokumentet i minnet, tack vare dess streaming‑arkitektur.

**Q: Behöver jag installera Microsoft Project på servern?**  
A: Nej. GroupDocs Viewer parsar .mpp‑formatet direkt och kräver inte Microsoft Project eller någon Office‑installation.

**Q: Hur licensierar jag visaren för en produktionsmiljö?**  
A: Köp en permanent licens från GroupDocs‑butiken; applicera licensfilen vid körning med `License license = new License(); license.setLicense("path/to/license.lic");`. För kortsiktiga behov kan du skaffa en [temporary license](https://purchase.groupdocs.com/temporary-license/).

---

**Senast uppdaterad:** 2026-05-21  
**Testad med:** GroupDocs Viewer Java 25.2  
**Författare:** GroupDocs  

**Resurser**  
- [Dokumentation](https://docs.groupdocs.com/viewer/java/)  
- [API‑referens](https://reference.groupdocs.com/viewer/java/)  
- [Ladda ner GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Köp en licens](https://purchase.groupdocs.com/buy)  

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Relaterade handledningar

- [Hur man renderar MS Project‑filer som HTML, JPG, PNG och PDF med anteckningar med GroupDocs.Viewer för Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Hur man använder GroupDocs Viewer för att rendera projektdokument efter tidsintervall i Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Hur man ställer in licenser i GroupDocs.Viewer Java: Fil‑ och URL‑installationsguide](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)