---
date: '2026-01-15'
description: Lär dig hur du renderar spårade ändringar i Word och visar dokumentrevisioner
  i Word‑filer med GroupDocs.Viewer för Java. Följ den här steg‑för‑steg‑guiden för
  utvecklare.
keywords:
- render tracked changes Word docs GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- Java document rendering
title: Rendera spårade ändringar i Word‑dokument med GroupDocs.Viewer för Java
type: docs
url: /sv/java/advanced-rendering/render-tracked-changes-word-docs-groupdocs-viewer-java/
weight: 1
---

# Rendera spårade ändringar i Word‑dokument med GroupDocs.Viewer för Java

Om du behöver **rendera spårade ändringar i Word** i din Java‑applikation, har du kommit till rätt ställe. I den här guiden visar vi hur du visar varje revision, insättning och borttagning som finns i en Word‑fil, och omvandlar den till ren, navigerbar HTML. Oavsett om du bygger en dokumentgranskningsportal, ett juridiskt ärendehanteringssystem eller någon lösning som måste **visa Word‑dokumentrevisioner**, så går den här tutorialen igenom hela processen—från miljöinställning till slutlig rendering.

![Render Tracked Changes in Word Documents with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-tracked-changes-in-word-documents-java.png)

## Snabba svar
- **Vad betyder “render word tracked changes”?** Det konverterar en Word‑fils revisionsmarkering till en visuell HTML‑representation.  
- **Vilket bibliotek hanterar detta?** GroupDocs.Viewer för Java.  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en full licens tar bort alla begränsningar.  
- **Vilken Java‑version krävs?** Java 8 eller nyare.  
- **Kan jag inaktivera rendering av spårade ändringar?** Ja—sätt `setRenderTrackedChanges(false)` i visningsalternativen.

## Vad är “render word tracked changes”?
Att rendera spårade ändringar i Word innebär att ta revisionsdata som lagras i en `.docx`‑fil (insättningar, borttagningar, kommentarer osv.) och producera ett visningsbart format—vanligtvis HTML—där dessa ändringar visuellt markeras. Detta låter slutanvändare se exakt vad som har ändrats utan att öppna Microsoft Word.

## Varför använda GroupDocs.Viewer för att visa Word‑dokumentrevisioner?
GroupDocs.Viewer för Java abstraherar den lågnivå OpenXML‑hanteringen och ger dig ett enda API‑anrop för att generera HTML, PDF eller bilder. Det stödjer också **view word document revisions** direkt ur lådan, och bevarar formatering, inbäddade resurser och ändringsspårning.

## Förutsättningar
- **GroupDocs.Viewer för Java** bibliotek version 25.2 eller senare.  
- Maven för beroendehantering.  
- Grundläggande Java‑utvecklingsmiljö (IDE, JDK 8+).  

## Konfigurera GroupDocs.Viewer för Java

### Maven‑konfiguration
Add the GroupDocs repository and dependency to your `pom.xml`:

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
Börja med en gratis provversion eller begär en tillfällig utvärderingslicens. När du är redo för produktion, köp en full licens för att låsa upp alla funktioner.

### Grundläggande initiering
Importera de nödvändiga klasserna i din Java‑kod och förbered filsökvägar för in- och utdata.

## Så renderar du spårade ändringar i Word‑dokument

Nedan följer en steg‑för‑steg‑genomgång som speglar den exakta koden du behöver. Kodblocken är oförändrade från den ursprungliga handledningen.

### Steg 1: Definiera sökvägen för utdata‑katalogen
Skapa en mapp där de renderade HTML‑sidorna kommer att sparas.

```java
Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RenderTrackedChanges");
```

### Steg 2: Ange formatet för att spara varje sida
Ställ in ett namnformat för varje genererad HTML‑fil.

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

### Steg 3: Konfigurera visningsalternativ
Aktivera inbäddade resurser och slå på rendering av spårade ändringar.

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getWordProcessingOptions().setRenderTrackedChanges(true);
```

### Steg 4: Skapa en Viewer‑instans och rendera
Läs in Word‑dokumentet som innehåller spårade ändringar och generera HTML‑utdata.

```java
try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SAMPLE_DOCX_WITH_TRACKED_CHANGES"))) {
    viewer.view(viewOptions);
}
```

## Vanliga problem och lösningar
- **Felaktiga filsökvägar** – Dubbelkolla att `YOUR_OUTPUT_DIRECTORY` och `YOUR_DOCUMENT_DIRECTORY` pekar på befintliga mappar.  
- **Ej stödd dokumentformat** – Säkerställ att filen är en `.docx` eller `.doc` som GroupDocs.Viewer stödjer.  
- **Saknad licens** – Utan en giltig licens kan biblioteket begränsa renderingsfunktionerna.

## Praktiska tillämpningar
1. **Dokumentgranskningssystem** – Visa granskare exakt vad som lagts till eller tagits bort.  
2. **Juridisk ärendehantering** – Markera ändringar i kontrakt eller inlagor.  
3. **Akademiskt samarbete** – Visualisera bidrag från flera författare.

## Prestandaöverväganden
- Bearbeta ett begränsat antal dokument samtidigt för att hålla minnesanvändningen låg.  
- Använd effektiva katalogstrukturer för att minska I/O‑belastning.  
- Håll biblioteket uppdaterat; nyare versioner innehåller prestandaoptimeringar.

## Slutsats
Du har nu en komplett, produktionsklar metod för att **rendera spårade ändringar i Word** och **visa Word‑dokumentrevisioner** med GroupDocs.Viewer för Java. Integrera dessa steg i din applikation, så ger du användarna en kraftfull, interaktiv dokumentgranskningsupplevelse.

## Vanliga frågor

1. **Vad är den lägsta Java‑versionen som krävs?**  
   Java 8 eller senare rekommenderas generellt för kompatibilitet med moderna bibliotek som GroupDocs.Viewer.  
2. **Kan jag rendera dokument utan spårade ändringar?**  
   Ja, inaktivera helt enkelt `setRenderTrackedChanges(true)` i dina konfigurationsalternativ.  
3. **Hur hanterar jag stora dokument effektivt?**  
   Överväg att dela upp stora filer i mindre sektioner eller använda pagineringsmetoder för att hantera resursanvändning på ett effektivt sätt.  
4. **Vilka licensalternativ finns för GroupDocs.Viewer?**  
   Du kan börja med en gratis provversion, välja en tillfällig utvärderingslicens eller köpa en full licens baserat på ditt projekts behov.  
5. **Finns det support om jag stöter på problem?**  
   Ja, du kan få support via GroupDocs‑forumet och de officiella dokumentationsresurserna.

## Resurser
- [Dokumentation](https://docs.groupdocs.com/viewer/java/)
- [API‑referens](https://reference.groupdocs.com/viewer/java/)
- [Nedladdning](https://releases.groupdocs.com/viewer/java/)
- [Köp](https://purchase.groupdocs.com/buy)
- [Gratis provversion](https://releases.groupdocs.com/viewer/java/)
- [Tillfällig licens](https://purchase.groupdocs.com/temporary-license/)
- [Support](https://forum.groupdocs.com/c/viewer/9)

---

**Senast uppdaterad:** 2026-01-15  
**Testad med:** GroupDocs.Viewer for Java 25.2  
**Författare:** GroupDocs