---
date: '2026-09-25'
description: Lär dig hur du skapar html‑vy för mpp med GroupDocs Viewer för Java,
  renderar projektdokument efter tidsintervaller med steg‑för‑steg‑kod.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Skapa html‑vy för mpp med GroupDocs Viewer för Java för att rendera
  Microsoft Project‑filer efter specifika tidsintervaller. Följ steg‑för‑steg‑installation,
  licensiering och kodexempel för exakt tidslinjevisualisering.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Skapa html‑vy för mpp med GroupDocs Viewer för Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Skapa html‑vy för mpp med GroupDocs Viewer (Java)
type: docs
url: /sv/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Hur man använder GroupDocs Viewer för att rendera projektdokument efter tidsintervall i Java

I den här handledningen kommer du att lära dig hur du **skapar html view mpp** med GroupDocs Viewer för Java, vilket gör att du kan rendera endast de delar av en Microsoft Project‑fil som faller inom ett specifikt start‑ och slutdatumsintervall. Vi går igenom Maven‑inställning, licensiering och de exakta API‑anropen du behöver för att bädda in precisa tidslinjevyer direkt i dina applikationer.

![Rendera projektdokument efter tidsintervall med GroupDocs.Viewer för Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

För en förhandsgranskning, se [Rendera projektdokument efter tidsintervall med GroupDocs.Viewer för Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Snabba svar
- **Vad gör funktionen?** Den renderar endast den del av en Microsoft Project‑fil som faller mellan ett start‑ och slutdatum.  
- **Vilket utdataformat används?** HTML med inbäddade resurser, perfekt för webbintegration.  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en full licens krävs för produktion.  
- **Kan jag ändra datumintervallet vid körning?** Ja—justera `setStartDate` och `setEndDate` värdena i renderingsalternativen.  
- **Stöds detta på alla Java‑versioner?** Fungerar med Java 8+ så länge du använder GroupDocs.Viewer 25.2 eller nyare.

## Vad är create html view mpp?
`create html view mpp` är processen att konvertera en Microsoft Project‑fil (`.mpp` eller `.mpt`) till en uppsättning HTML‑sidor som representerar schemat. GroupDocs Viewer utför konverteringen på serversidan, så du kan visa tidslinjen i vilken webbläsare som helst utan att installera Microsoft Project.

## Varför rendera projektdokument med tidsintervall?
Att rendera endast det nödvändiga tidsintervallet minskar storleken på den genererade HTML‑koden, snabbar upp sidladdning och låter dig fokusera på den specifika projektfas du behöver analysera. Denna riktade vy är idealisk för instrumentpaneler, statusrapporter eller inbäddning i anpassade PM‑verktyg där fullständig projektdata skulle vara överväldigande.

## Förutsättningar
- **GroupDocs.Viewer for Java** version 25.2 eller högre.  
- Java Development Kit (JDK) 8 eller nyare.  
- En IDE såsom IntelliJ IDEA eller Eclipse.  
- Grundläggande kunskaper i Maven.  

## Konfigurera GroupDocs.Viewer för Java

### Maven‑beroende

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

### Steg för att skaffa licens

1. **Gratis provversion** – Ladda ner en provversion från [GroupDocs nedladdningssida](https://releases.groupdocs.com/viewer/java/).  
2. **Tillfällig licens** – Skaffa en tillfällig licens för utökad testning via [temporär‑licenssidan](https://purchase.groupdocs.com/temporary-license/).  
3. **Köp** – För obegränsad produktionsanvändning, köp en licens på [GroupDocs köpsida](https://purchase.groupdocs.com/buy).

## Grundläggande visningsinitialisering

`Viewer` är huvudklassen i GroupDocs.Viewer för Java som laddar ett dokument och tillhandahåller renderingsfunktioner.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Hämta vyinformation för projektfiler

`ProjectManagementViewInfo` tillhandahåller metadata om en Microsoft Project‑fil, inklusive dess övergripande schema start‑ och slutdatum.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Konfigurera HTML‑renderingsalternativ (generera HTML från projekt)

`HtmlViewOptions` konfigurerar hur GroupDocs renderar HTML, vilket låter dig ange datumintervall, bädda in resurser och anpassa utseendet.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Utför renderingsprocessen

`viewer.render` utför konverteringen baserat på angivna alternativ och skriver de resulterande HTML‑filerna till mål‑mappen.

```java
viewer.view(viewOptions);
```

## Vanliga fallgropar & felsökning
- **Felaktiga filsökvägar** – Dubbelkolla att både källfilen `.mpp` och mål‑katalogen finns.  
- **Ej stödd filtyp** – Säkerställ att dokumentet är i ett stödd Project‑format (t.ex. `.mpp`, `.mpt`).  
- **Licensfel** – En provlicens kan ha renderingsbegränsningar; byt till en full licens för obegränsad användning.  

## Praktiska tillämpningar
1. **Projekt‑tidslinjeanalys** – Visa intressenter endast den aktuella fasen.  
2. **Automatiserad rapportering** – Generera tidsbundna HTML‑rapporter för veckovisa statusuppdateringar.  
3. **Integration med instrumentpaneler** – Bädda in de renderade sidorna i BI‑verktyg eller anpassade portaler.  
4. **Arkivering** – Spara en webvänlig ögonblicksbild av ett projekts schema för framtida referens.  

## Prestandatips
- Använd alternativet *embedded resources* för att hålla varje HTML‑sida självständig, vilket minskar HTTP‑förfrågningar.  
- För mycket stora projekt, överväg att rendera i mindre datumdelar för att hålla minnesanvändningen låg. Att rendera ett ettårs‑intervall kan minska HTML‑storleken med upp till 80 % jämfört med en full‑projektexport, vilket minskar laddningstiden från flera sekunder till under en sekund på vanliga servrar.  
- Rensa temporära filer efter att de har levererats för att undvika diskuppblåsthet.  

## Slutsats
Du vet nu **hur du använder GroupDocs** Viewer för att rendera projektdokument inom ett specifikt tidsintervall och **generera HTML från projekt**‑data i Java. Denna funktion förenklar tidslinjevisualiseringar, förbättrar rapporteringseffektiviteten och integreras smidigt med moderna webbapplikationer.

### Nästa steg
- Utforska ytterligare Viewer‑funktioner såsom vattenstämpling, lösenordsskydd eller anpassad CSS‑styling.  
- Kombinera denna renderingspipeline med ett REST‑API för att leverera tidslinjevyer på begäran.  

## Vanliga frågor
**Q: Vilka filformat stöder GroupDocs.Viewer?**  
A: GroupDocs.Viewer stöder över 100 inmatningsformat, inklusive PDF, DOCX, XLSX, PPTX och Microsoft Project‑filer, vilket möjliggör universell dokumentvisualisering.

**Q: Hur kommer jag igång med en gratis provversion av GroupDocs.Viewer?**  
A: Du kan ladda ner provversionen från [GroupDocs Viewer Java nedladdningssida](https://releases.groupdocs.com/viewer/java/).

**Q: Kan jag rendera dokument utan att bädda in resurser?**  
A: Ja, du kan välja ett annat HTML‑vyalternativ som refererar till externa resurser istället för att bädda in dem.

**Q: Vad händer om mitt dokument är för stort för rendering?**  
A: Överväg att dela upp dokumentet i mindre sektioner eller rendera endast det nödvändiga datumintervallet, som demonstrerat ovan.

**Q: Hur hanterar jag renderingsfel?**  
A: Verifiera alla konfigurationsinställningar, säkerställ att du har en giltig licens och konsultera GroupDocs‑dokumentationen för detaljerade felkoder.

## Resurser
- **Dokumentation**: [GroupDocs Viewer Java-dokumentation](https://docs.groupdocs.com/viewer/java/)
- **API-referens**: [GroupDocs API-referens](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs nedladdningar](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Köp GroupDocs-licens](https://purchase.groupdocs.com/buy)
- **Free trial**: [Prova den gratis versionen](https://releases.groupdocs.com/viewer/java/)
- **Temporary license**: [Skaffa en tillfällig licens](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs-forum](https://forum.groupdocs.com/c/viewer/9)

---

**Senast uppdaterad:** 2026-09-25  
**Testad med:** GroupDocs.Viewer 25.2 for Java  
**Författare:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Relaterade handledningar

- [Hur man renderar MS Project‑filer som HTML, JPG, PNG och PDF med anteckningar med GroupDocs.Viewer för Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [MS Project HTML‑export: Justera tidsenheter via GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Groupdocs Viewer Java responsiv HTML‑rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)