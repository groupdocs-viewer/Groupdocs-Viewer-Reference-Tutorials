---
date: '2026-04-01'
description: Lär dig hur du delar upp CAD-ritningar i rutor med GroupDocs Viewer för
  Java, vilket ökar renderingsprestandan och förenklar hantering av stora filer.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Hur man delar CAD-ritningar i rutor med GroupDocs Viewer
type: docs
url: /sv/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Hur man delar upp CAD-ritningar i rutor med GroupDocs Viewer

Om du undrar **hur man delar upp CAD**-filer i mindre, mer hanterbara delar, har du kommit till rätt ställe. I den här handledningen går vi igenom de exakta stegen som behövs för att dela upp stora CAD-ritningar i rutor med hjälp av **GroupDocs Viewer for Java**. I slutet har du en färdig lösning som förbättrar renderingshastigheten, minskar minnesförbrukningen och gör det enklare att visa ritningar i webb‑ eller mobilapplikationer.

![Dela CAD-ritningar med GroupDocs.Viewer för Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Snabba svar
- **Vad innebär “splitting CAD”?** Det delar upp en massiv ritning i mindre bilder (rutor) som laddas snabbare och förbrukar mindre minne.  
- **Vilket format används för rutorna?** PNG-filer genereras som standard, men andra format stöds via Viewer‑alternativ.  
- **Behöver jag en licens?** En gratis provlicens fungerar för utveckling; en betald licens krävs för produktion.  
- **Kan jag ändra rutornas storlek?** Ja – justera beräkningarna för `tileWidth` och `tileHeight` efter dina behov.  
- **Är detta tillvägagångssätt trådsäkert?** Att rendera varje ruta i sin egen `Viewer`‑instans med try‑with‑resources är säkert för samtidig körning.

## Vad är “how to split CAD”?
Splitting CAD avser att dela upp en enda, ofta enorm, CAD-ritning i flera rektangulära sektioner (rutor). Varje ruta renderas oberoende, vilket gör att du bara laddar de delar som en användare faktiskt behöver – perfekt för webbkartor, dokumentportaler och mobila visare.

## Varför använda GroupDocs Viewer för Java?
GroupDocs Viewer erbjuder färdig support för över 100 filformat, inklusive DWG, DXF och DWF. Dess tile‑API låter dig ange exakta koordinater, så att du kan rendera exakt det område du är intresserad av utan att först bearbeta hela filen. Detta sparar CPU‑cykler, minskar bandbredden och ger en smidigare användarupplevelse.

## Förutsättningar
- **Bibliotek**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Any recent Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse, eller en annan Java‑kompatibel IDE.  
- **Byggverktyg**: Maven (andra byggverktyg fungerar så länge beroendet är tillagt).  

## Konfigurera GroupDocs.Viewer för Java
Lägg till GroupDocs‑arkivet och beroendet i din `pom.xml`:

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
GroupDocs Viewer erbjuder en gratis provlicens för utvärdering:

- **Free Trial**: Besök [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) för att ladda ner biblioteket.  
- **Temporary License**: Ansök på [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Full License**: Köp en produktionslicens på [Purchase Page](https://purchase.groupdocs.com/buy).

### Grundläggande initiering
Skapa en enkel `Viewer`‑instans för att verifiera att biblioteket laddas korrekt:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Steg‑för‑steg‑guide för att dela upp CAD-ritningar i rutor

### Steg 1: Definiera utdatamappen
Vi kommer att lagra varje ruta som en separat PNG‑fil. Att använda en hjälpfunktion håller sökvägslogiken ren och återanvändbar.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Steg 2: Konfigurera visningsalternativ
Ställ in renderingsformatet till PNG och instruera visaren att inte förladda varje sida (vilket sparar minne).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Steg 3: Beräkna rutdimensioner
Först hämtar vi ritningens ursprungliga bredd och höjd, och delar sedan upp den i fyra lika stora kvadranter.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Steg 4: Rendera och spara rutorna
Lägg till de beräknade rutorna i renderingsalternativen och låt `Viewer` generera PNG‑filerna.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Felsökningstips
- **Build path** – Säkerställ att GroupDocs‑JAR‑filerna finns på classpath.  
- **Permissions** – Utdatamappen måste vara skrivbar för Java‑processen.  
- **Exceptions** – Om du ser `ViewerException`, dubbelkolla att DWG‑filen inte är korrupt och att rätt licens har tillämpats.

## Vanliga användningsfall för att dela upp CAD‑rutor
1. **Web Mapping** – Ladda endast den synliga delen av en planritning när en användare panorerar/zoomar.  
2. **Document Management** – Spara varje ruta separat för snabbare förhandsgranskning.  
3. **Mobile Viewing** – Minska bandbredden genom att ladda ner bara de rutor som behövs för den aktuella skärmen.

## Prestandaöverväganden
- **Tile Size** – Större rutor innebär färre filer men långsammare rendering; hitta en balans baserat på dina UI‑behov.  
- **Memory Monitoring** – Använd Javas profileringsverktyg (t.ex. VisualVM) för att övervaka heap‑användning när du bearbetar mycket stora ritningar.  
- **Resource Cleanup** – Mönstret try‑with‑resources som visas ovan frigör automatiskt inhemska resurser.

## Vanliga frågor

**Q: Kan jag dela upp andra filtyper (PDF, bilder) i rutor med samma tillvägagångssätt?**  
A: Ja. GroupDocs Viewer stöder många format; du behöver bara använda motsvarande options‑klass (t.ex. `PdfViewOptions`).

**Q: Hur ändrar jag bildkvaliteten på utdata?**  
A: Justera `viewOptions.setResolution(int dpi)` eller ställ in komprimeringsinställningar på `PngOptions`‑objektet.

**Q: Min applikation får slut på minne på mycket stora DWG‑filer—vad kan jag göra?**  
A: Minska rutdimensionerna, öka JVM‑heapen (`-Xmx`), eller rendera rutor sekventiellt i separata `Viewer`‑instanser.

**Q: Är det möjligt att rendera rutor asynkront?**  
A: Absolut. Packa varje renderingsanrop i en `CompletableFuture` eller använd en executor‑service för att parallellisera arbetsbelastningen.

**Q: Behöver jag en separat licens för varje ruta?**  
A: Nej. En enda giltig GroupDocs Viewer‑licens täcker alla renderingsoperationer i din applikation.

## Resurser
- [Dokumentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase a License](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-04-01  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs