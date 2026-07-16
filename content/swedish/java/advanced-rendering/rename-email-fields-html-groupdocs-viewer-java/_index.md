---
date: '2026-03-24'
description: Lär dig hur du konverterar e‑post till HTML och byter namn på e‑postfält
  med GroupDocs Viewer för Java. Denna guide visar hur du renderar e‑post som HTML
  med anpassade rubriker.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Konvertera e‑post till HTML och byt namn på fält – GroupDocs Viewer Java
type: docs
url: /sv/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Konvertera e‑post till HTML & Byt namn på fält – GroupDocs Viewer Java

Om du behöver **convert email to HTML** medan du ger e‑posthuvudena ett anpassat utseende, är du på rätt plats. I den här handledningen går vi igenom de exakta stegen för att byta namn på e‑postfält, **convert email to HTML**, och anpassa e‑posthuvuden med hjälp av GroupDocs.Viewer för Java. I slutet har du en ren HTML‑representation med de rubriknamn du föredrar, vilket gör resultatet enklare att läsa och integrera i dina applikationer.

![Rename Email Fields When Converting Emails to HTML with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Vad du kommer att lära dig
- Hur du använder GroupDocs.Viewer för Java för att **convert email to HTML**.  
- Tekniker för att **rename email fields** såsom “From”, “To”, “Sent” och “Subject”.  
- Bästa praxis för att konfigurera Maven och licensiering.  
- Verkliga scenarier där **customizing email headers** tillför värde.

## Snabba svar
- **What does “convert email to HTML” mean?** Det betyder att rendera en e‑postfil (MSG/EML) som ett webb‑klart HTML‑dokument.  
- **Which library handles the conversion?** GroupDocs.Viewer för Java (v25.2+).  
- **Do I need a license?** En provversion fungerar för utvärdering; en full licens krävs för produktion.  
- **Can I change any header name?** Ja, alla standard‑e‑posthuvuden kan ommappas via `fieldTextMap`.  
- **Is the output HTML or embedded resources?** Du kan välja inbäddade resurser för en enda självständig fil.

## Vad betyder “convert email to HTML” i samband med GroupDocs.Viewer?
Att konvertera e‑post till HTML innebär att ta en rå e‑postfil och skapa en HTML‑sida som visar meddelandetexten tillsammans med dess metadata. När du också **rename email fields**, ersätts standardetiketterna (t.ex. “From”) med anpassad text (t.ex. “Sender”), vilket hjälper dig att matcha företags‑terminologi eller förbättra UI‑konsistens.

## Varför konvertera e‑post till HTML och byta namn på e‑postfält?
- **Consistent branding:** Anpassa resultatet till ditt företags språk.  
- **Improved searchability:** Anpassade rubriker kan indexeras mer effektivt i arkiveringssystem.  
- **Better UI integration:** Skräddarsy HTML‑snutten så att den passar sömlöst in i webbportaler eller support‑instrumentpaneler.

## Förutsättningar

### Nödvändiga bibliotek, versioner och beroenden
- **GroupDocs.Viewer for Java** – version 25.2 eller senare.  
- **Java Development Kit (JDK)** – version 8+.

### Krav för miljöinställning
- **Maven** för beroendehantering.  
- En IDE såsom IntelliJ IDEA, Eclipse eller VS Code.

### Kunskapsförutsättningar
Grundläggande kunskaper i Java och Maven hjälper dig att följa med snabbt.

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
- **Free Trial:** Ladda ner en gratis provversion från [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** Skaffa en tillfällig licens för att utforska alla funktioner utan begränsningar på [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** För fortsatt användning, överväg att köpa en licens via [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Grundläggande initiering och konfiguration
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

## Så konverterar du e‑post till HTML och byter namn på fält – Steg‑för‑steg

### 1. Ange sökvägen för utdata‑katalogen
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
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` paketerar CSS/JS i HTML‑filen, medan `setFieldTextMap` tillämpar de anpassade rubriknamnen.*

### 5. Rendera e‑posten till HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Ersätt `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` med den faktiska sökvägen till din MSG‑fil.*

#### Felsökningstips
- Verifiera att utdata‑katalogen är skrivbar.  
- Säkerställ att indata‑MSG‑filen finns och att sökvägen är korrekt.  
- Använd samma GroupDocs.Viewer‑version (25.2) som deklarerad i Maven.

## Praktiska tillämpningar
1. **Custom Email Reports:** Anpassa e‑posthuvuden till företags‑terminologi för tydligare rapporter.  
2. **Email Archiving Systems:** Förbättra sökbarheten genom att använda standardiserade rubriknamn.  
3. **Customer Support Platforms:** Presentera ärenden med personliga rubriketiketter för bättre agentupplevelse.

## Prestandaöverväganden
- Avsluta `Viewer`‑objekt med try‑with‑resources för att snabbt frigöra minne.  
- Profilera stora batcher och överväg att bearbeta e‑post i parallella strömmar om det behövs.

## Slutsats
Du vet nu **how to convert email to HTML** samtidigt som du **renaming email fields** och **customizing email headers** med GroupDocs.Viewer för Java. Denna teknik ger dig full kontroll över presentationen av e‑postmetadata i HTML‑utdata.

### Nästa steg
- Experimentera med ytterligare fältmappningar (t.ex. CC, BCC).  
- Utforska andra renderingsformat såsom PDF eller PNG.  
- Besök [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) för djupare API‑insikter.

## Vanliga frågor

**Q: Fungerar detta tillvägagångssätt med andra e‑postformat som EML?**  
A: Ja, GroupDocs.Viewer stödjer både MSG‑ och EML‑filer; samma fält‑mappningslogik gäller.

**Q: Kan jag generera HTML utan inbäddade resurser?**  
A: Du kan använda `HtmlViewOptions.forExternalResources(...)` om du föredrar separata CSS/JS‑filer.

**Q: Vilken version av GroupDocs.Viewer testades?**  
A: Koden testades med GroupDocs.Viewer **25.2**.

**Q: Är det möjligt att ändra teckensnitt eller stil för de anpassade rubrikerna?**  
A: Stil kan appliceras via CSS efter rendering, eller så kan du injicera anpassad CSS med `HtmlViewOptions.getResourcesPath()`.

**Q: Hur hämtar jag programatiskt den genererade HTML‑filens sökväg?**  
A: Filvägen följer mönstret definierat i `pageFilePathFormat`; du kan konstruera den med `String.format` och sidnumret.

## Resurser
- **Documentation:** Omfattande guider finns på [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Detaljerad API‑information finns på [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Hämta den senaste versionen via [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Last Updated:** 2026-03-24  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs