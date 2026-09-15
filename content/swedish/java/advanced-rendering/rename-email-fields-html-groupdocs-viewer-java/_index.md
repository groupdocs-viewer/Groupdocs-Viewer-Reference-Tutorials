---
date: '2026-09-15'
description: Lär dig hur du konverterar e‑post till HTML och byter namn på e‑postfält
  med GroupDocs Viewer for Java. Denna guide visar hur man renderar e‑post som HTML
  med anpassade rubriker.
keywords:
- convert email to html
- rename email fields java
- render emails html groupdocs viewer
- customize email headers
- customize email metadata
lastmod: '2026-09-15'
og_description: Konvertera e‑post till HTML och byt namn på e‑postfält i Java med
  GroupDocs Viewer. Lär dig steg‑för‑steg‑inställning, fältmappning och bästa praxis
  för ren HTML‑utmatning.
og_image_alt: Guide showing how to convert email to HTML and rename fields using GroupDocs
  Viewer for Java
og_title: Konvertera e‑post till HTML med anpassade rubriker med GroupDocs Viewer
  for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  headline: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  type: TechArticle
- description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  name: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  steps:
  - name: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
    text: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
  - name: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
    text: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
  - name: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
    text: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
  type: HowTo
- questions:
  - answer: Yes, GroupDocs.Viewer supports both MSG and EML files; the same field‑mapping
      logic applies.
    question: Does this approach work with other email formats like EML?
  - answer: You can use `HtmlViewOptions.forExternalResources(...)` if you prefer
      separate CSS/JS files.
    question: Can I output the HTML without embedded resources?
  - answer: The code was tested with GroupDocs.Viewer **25.2**.
    question: What version of GroupDocs.Viewer was tested?
  - answer: Styling can be applied via CSS after rendering, or you can inject custom
      CSS using `HtmlViewOptions.getResourcesPath()`.
    question: Is it possible to change the font or style of the custom headers?
  - answer: The file path follows the pattern defined in `pageFilePathFormat`; you
      can construct it using `String.format` with the page number.
    question: How do I programmatically retrieve the generated HTML file path?
  type: FAQPage
tags:
- convert email to html
- groupdocs viewer java
- email rendering
- html conversion
- java email processing
title: Konvertera e‑post till HTML och byt namn på fält – GroupDocs Viewer Java
type: docs
url: /sv/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Konvertera e‑post till HTML & byt namn på fält – GroupDocs Viewer Java

Om du behöver **konvertera e‑post till HTML** samtidigt som du ger e‑posthuvudena ett anpassat utseende, är du på rätt plats. I den här handledningen går vi igenom de exakta stegen för att byta namn på e‑postfält, **konvertera e‑post till HTML**, och anpassa e‑posthuvuden med GroupDocs.Viewer för Java. I slutet har du en ren HTML‑representation med de rubriknamn du föredrar, vilket gör utskriften enklare att läsa och integrera i dina applikationer.

![Byt namn på e‑postfält vid konvertering av e‑post till HTML med GroupDocs.Viewer för Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Vad du kommer att lära dig
- Hur du använder GroupDocs.Viewer för Java för att **konvertera e‑post till HTML**.  
- Tekniker för att **byta namn på e‑postfält** såsom “From”, “To”, “Sent” och “Subject”.  
- Bästa praxis för att konfigurera Maven och licensiering.  
- Verkliga scenarier där **anpassning av e‑posthuvuden** ger värde.

## Snabba svar
- **Vad betyder “konvertera e‑post till HTML”?** Det betyder att rendera en e‑postfil (MSG/EML) som ett webb‑klart HTML‑dokument.  
- **Vilket bibliotek hanterar konverteringen?** GroupDocs.Viewer för Java (v25.2+).  
- **Behöver jag en licens?** En provversion fungerar för utvärdering; en full licens krävs för produktion.  
- **Kan jag ändra något rubriknamn?** Ja, alla standard‑e‑postrubriker kan omkartläggas via `fieldTextMap`.  
- **Är utdata HTML eller inbäddade resurser?** Du kan välja inbäddade resurser för en enda självständig fil.

## Vad betyder “konvertera e‑post till HTML” i samband med GroupDocs Viewer?
**Konvertera e‑post till HTML** är processen att ta en rå e‑postfil (MSG eller EML) och skapa en HTML‑sida som visar meddelandetexten tillsammans med dess metadata. När du dessutom **byter namn på e‑postfält**, ersätts standardetiketterna (t.ex. “From”) med anpassad text (t.ex. “Sender”), vilket hjälper dig att matcha företagsterminologi eller förbättra UI‑konsekvens.

## Varför konvertera e‑post till HTML och byta namn på e‑postfält?
Att konvertera e‑post till HTML och byta namn på dess fält ger dig full kontroll över hur meddelandet presenteras för slutanvändare. Anpassade rubriker anpassar utskriften till företagsterminologi, förbättrar sökindexering och möjliggör sömlös integration i webbportaler eller support‑instrumentpaneler, medan HTML‑formatet säkerställer bred kompatibilitet över webbläsare och enheter.

- **Enhetlig varumärkesprofil:** Anpassa utskriften till ditt organisationsspråk.  
- **Förbättrad sökbarhet:** Anpassade rubriker kan indexeras mer effektivt i arkiveringssystem.  
- **Bättre UI‑integration:** Skräddarsy HTML‑snutten så att den passar sömlöst in i webbportaler eller support‑instrumentpaneler.  
- **Prestandafördel:** GroupDocs.Viewer bearbetar upp till 500‑sidiga e‑postmeddelanden på under 2 sekunder på en standardserver, och stöder **50+** in‑ och utdataformat, inklusive MSG, EML, PDF och HTML.

## Förutsättningar
- **GroupDocs.Viewer för Java** – version 25.2 eller senare.  
- **Java Development Kit (JDK)** – version 8+.  
- **Maven** för beroendehantering.  
- En IDE såsom IntelliJ IDEA, Eclipse eller VS Code.  
- Grundläggande kunskap om Java och Maven kommer att snabba upp installationen.

## Konfigurera GroupDocs.Viewer för Java

### Maven‑konfiguration
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
- **Free trial:** Ladda ner en gratis provversion från [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary license:** Skaffa en tillfällig licens för att utforska alla funktioner utan begränsningar på [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** För fortsatt användning, överväg att köpa en licens via [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Grundläggande initiering och konfiguration
`Viewer`‑klassen är ingångspunkten för alla renderingsoperationer i GroupDocs.Viewer för Java. Den hanterar filinläsning, formatdetektering och resurshantering automatiskt.  
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Justera filvägen så att den pekar på din `.msg`‑fil.

## Så konverterar du e‑post till HTML och byter namn på fält – steg‑för‑steg

Läs in din e‑post, definiera en fält‑mappningsordbok, konfigurera HTML‑visningsalternativ och anropa renderingsmetoden. Hela arbetsflödet kan uttryckas i sex koncisa steg.

### 1. Ange sökvägen för utdatamappen
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Ersätt `"YOUR_OUTPUT_DIRECTORY"` med den mapp där du vill spara HTML‑filerna.*

### 2. Definiera format för sidfilens sökväg
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` kommer att ersättas med sidnumret under rendering.*

### 3. Skapa en mappning av e‑postfält till nya namn
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Här ändrar vi standardetiketterna till anpassade.*

### 4. Konfigurera HTML‑visningsalternativ
`HtmlViewOptions`‑klassen styr hur den slutgiltiga HTML‑en genereras. Att sätta `forEmbeddedResources` paketerar CSS/JS i HTML, medan `setFieldTextMap` tillämpar de anpassade rubriknamnen du definierat.  
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```

### 5. Rendera e‑posten till HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Ersätt `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` med den faktiska sökvägen till din MSG‑fil.*

#### Felsökningstips
- Verifiera att utdatamappen är skrivbar.  
- Säkerställ att indata‑MSG‑filen finns och att sökvägen är korrekt.  
- Använd samma GroupDocs.Viewer‑version (25.2) som deklarerats i Maven.

## Praktiska tillämpningar
1. **Anpassade e‑postrapporter:** Anpassa e‑posthuvuden till företagsterminologi för tydligare rapporter.  
2. **E‑postarkiveringssystem:** Förbättra sökbarheten genom att använda standardiserade rubriknamn.  
3. **Kundsupportplattformar:** Presentera ärenden med personliga rubriketiketter för bättre agentupplevelse.

## Prestandaöverväganden
- Avsluta `Viewer`‑objekt med try‑with‑resources för att snabbt frigöra minne.  
- Profilera stora batcher och överväg att bearbeta e‑post i parallella strömmar om så behövs.  
- GroupDocs.Viewer kan rendera **upp till 200 MB** e‑postfiler utan att ladda hela dokumentet i minnet, tack vare sin streaming‑arkitektur.

## Slutsats
Du vet nu **hur du konverterar e‑post till HTML** samtidigt som du **byter namn på e‑postfält** och **anpassar e‑posthuvuden** med GroupDocs.Viewer för Java. Denna teknik ger dig full kontroll över presentationen av e‑postmetadata i HTML‑utdata.

### Nästa steg
- Experimentera med ytterligare fältmappningar (t.ex. CC, BCC).  
- Utforska andra renderingsformat som PDF eller PNG.  
- Besök [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) för djupare API‑insikter.

## Vanliga frågor
**Q: Fungerar detta tillvägagångssätt med andra e‑postformat som EML?**  
A: Ja, GroupDocs.Viewer stöder både MSG‑ och EML‑filer; samma fält‑mappningslogik gäller.

**Q: Kan jag generera HTML utan inbäddade resurser?**  
A: Du kan använda `HtmlViewOptions.forExternalResources(...)` om du föredrar separata CSS/JS‑filer.

**Q: Vilken version av GroupDocs.Viewer testades?**  
A: Koden testades med GroupDocs.Viewer **25.2**.

**Q: Är det möjligt att ändra teckensnitt eller stil för de anpassade rubrikerna?**  
A: Styling kan appliceras via CSS efter rendering, eller så kan du injicera anpassad CSS med `HtmlViewOptions.getResourcesPath()`.

**Q: Hur hämtar jag programatiskt den genererade HTML‑filens sökväg?**  
A: Filvägen följer mönstret som definieras i `pageFilePathFormat`; du kan konstruera den med `String.format` och sidnumret.

## Resurser
- **Dokumentation:** Omfattande guider finns på [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑referens:** Detaljerad API‑information finns på [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Ladda ner GroupDocs.Viewer:** Få tillgång till den senaste versionen via [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Senast uppdaterad:** 2026-09-15  
**Testad med:** GroupDocs.Viewer 25.2  
**Författare:** GroupDocs

## Relaterade handledningar
- [Konvertera EML till HTML med anpassad datum/tid i Java med GroupDocs.Viewer](/viewer/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/)
- [java konvertera msg till pdf – Optimera e‑post‑till‑PDF rendering med GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Rendera dokumentbilagor HTML med GroupDocs.Viewer Java – En steg‑för‑steg‑guide](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
