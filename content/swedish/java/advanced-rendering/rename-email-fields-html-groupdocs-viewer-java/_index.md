---
date: '2026-01-05'
description: Lär dig hur du byter namn på e‑postfält, konverterar e‑post till HTML
  och anpassar e‑postrubriker med GroupDocs.Viewer för Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Hur man byter namn på e‑postfält när man renderar e‑post till HTML med GroupDocs.Viewer
  Java
type: docs
url: /sv/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Hur man byter namn på e‑postfält när man renderar e‑post till HTML med GroupDocs.Viewer Java

Undrar du **hur man byter namn på e‑post**‑fält när du konverterar ett e‑postmeddelande till HTML? I den här guiden går vi igenom de exakta stegen för att byta namn på e‑postfält, **konvertera e‑post till HTML** och **anpassa e‑posthuvuden** med GroupDocs.Viewer för Java. I slutet har du en ren HTML‑representation med dina föredragna rubriknamn, vilket gör utskriften lättare att läsa och integrera i dina applikationer.

![Byt namn på e‑postfält när du konverterar e‑post till HTML med GroupDocs.Viewer för Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Vad du kommer att lära dig
- Hur man använder GroupDocs.Viewer för Java för att **konvertera e‑post till HTML**.  
- Tekniker för att **byta namn på e‑postfält** såsom “From”, “To”, “Sent” och “Subject”.  
- Bästa praxis för att konfigurera Maven och licensiering.  
- Verkliga scenarier där **anpassning av e‑posthuvuden** ger mervärde.

## Snabba svar
- **Vad betyder “how to rename email”?** Det avser att mappa standarde‑posthuvudsnamn till anpassade etiketter under rendering.  
- **Vilket bibliotek hanterar konverteringen?** GroupDocs.Viewer för Java (v25.2+).  
- **Behöver jag en licens?** En provversion fungerar för utvärdering; en full licens krävs för produktion.  
- **Kan jag ändra något huvudnamn?** Ja, alla standarde‑posthuvuden kan ommappas via `fieldTextMap`.  
- **Är utdata HTML eller inbäddade resurser?** Du kan välja inbäddade resurser för en enda självständig fil.

## Vad betyder “How to Rename Email” i sammanhanget med GroupDocs.Viewer?
Att byta namn på e‑postfält innebär att ersätta standardetiketterna (t.ex. “From”) med anpassad text (t.ex. “Sender”) när e‑posten renderas till HTML. Detta är användbart för att anpassa utskriften till företagets terminologi eller förbättra slutanvändarens läsbarhet.

## Varför konvertera e‑post till HTML och anpassa e‑posthuvuden?
- **Konsekvent varumärkesprofil:** Matcha din organisations språk i all kommunikation.  
- **Förbättrad sökbarhet:** Anpassade huvuden kan indexeras mer effektivt i arkiveringssystem.  
- **Bättre UI‑integration:** Anpassa HTML‑snutten så att den sömlöst passar in i webbportaler eller support‑instrumentpaneler.

## Förutsättningar

### Nödvändiga bibliotek, versioner och beroenden
- **GroupDocs.Viewer för Java** – version 25.2 eller senare.  
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

## Implementeringsguide

### Byta namn på e‑postfält – Steg för steg

#### 1. Ställ in sökvägen för utdata‑katalogen
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Ersätt `"YOUR_OUTPUT_DIRECTORY"` med den mapp där du vill spara HTML‑filerna.*

#### 2. Definiera format för sidfilens sökväg
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` kommer att ersättas med sidnumret under rendering.*

#### 3. Skapa en mappning av e‑postfält till nya namn
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

#### 4. Konfigurera HTML‑visningsalternativ
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` paketerar CSS/JS i HTML‑filen, medan `setFieldTextMap` tillämpar de anpassade huvudnamnen.*

#### 5. Rendera e‑posten till HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Ersätt `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` med den faktiska sökvägen till din MSG‑fil.*

#### Felsökningstips
- Verifiera att utdata‑katalogen är skrivbar.  
- Säkerställ att indata‑MSG‑filen finns och att sökvägen är korrekt.  
- Använd samma GroupDocs.Viewer‑version (25.2) som deklarerats i Maven.

## Praktiska tillämpningar
1. **Anpassade e‑postrapporter:** Anpassa e‑posthuvuden till företagets terminologi för tydligare rapporter.  
2. **E‑postarkiveringssystem:** Förbättra sökbarheten genom att använda standardiserade huvudnamn.  
3. **Kundsupportplattformar:** Presentera ärenden med personliga huvudetiketter för bättre agentupplevelse.

## Prestandaöverväganden
- Avsluta `Viewer`‑objekt med try‑with‑resources för att snabbt frigöra minne.  
- Profilera stora batcher och överväg att bearbeta e‑post i parallella strömmar om så behövs.

## Slutsats
Du vet nu **hur man byter namn på e‑post**‑fält medan du **konverterar e‑post till HTML** och **anpassar e‑posthuvuden** med GroupDocs.Viewer för Java. Denna teknik ger dig full kontroll över presentationen av e‑postmetadata i HTML‑utdata.

### Nästa steg
- Experimentera med ytterligare fältmappningar (t.ex. CC, BCC).  
- Utforska andra renderingsformat såsom PDF eller PNG.  
- Besök [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) för djupare API‑insikter.

## FAQ‑sektion
1. **Kan jag byta namn på alla e‑posthuvuden med den här metoden?**  
   - Ja, du kan mappa vilket standarde‑posthuvud som helst till ett nytt namn enligt dina krav.  
2. **Är det möjligt att använda GroupDocs.Viewer utan licens?**  
   - En provversion finns tillgänglig för testning, men en fullutrustad version kräver en giltig licens.  
3. **Hur hanterar jag stora volymer av e‑post effektivt med GroupDocs.Viewer?**  
   - Överväg batch‑behandling och optimera systemresurser för att hantera större datamängder effektivt.  
4. **Kan jag integrera denna lösning i en befintlig Java‑applikation?**  
   - Absolut, integrationen är enkel med Maven‑beroenden.  
5. **Var kan jag hitta support om jag stöter på problem?**  
   - Besök [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) för community‑ och officiell hjälp.

## Vanliga frågor

**Q: Fungerar detta tillvägagångssätt med andra e‑postformat som EML?**  
A: Ja, GroupDocs.Viewer stödjer både MSG‑ och EML‑filer; samma fält‑mappningslogik gäller.

**Q: Kan jag generera HTML utan inbäddade resurser?**  
A: Du kan använda `HtmlViewOptions.forExternalResources(...)` om du föredrar separata CSS/JS‑filer.

**Q: Vilken version av GroupDocs.Viewer testades?**  
A: Koden testades med GroupDocs.Viewer **25.2**.

**Q: Är det möjligt att ändra teckensnitt eller stil för de anpassade huvudena?**  
A: Stil kan appliceras via CSS efter rendering, eller så kan du injicera anpassad CSS med `HtmlViewOptions.getResourcesPath()`.

**Q: Hur hämtar jag programatiskt den genererade HTML‑filens sökväg?**  
A: Filvägen följer mönstret definierat i `pageFilePathFormat`; du kan konstruera den med `String.format` och sidnumret.

## Resurser
- **Documentation:** Omfattande guider finns på [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Detaljerad API‑information finns på [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Få den senaste versionen via [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Senast uppdaterad:** 2026-01-05  
**Testad med:** GroupDocs.Viewer 25.2  
**Författare:** GroupDocs