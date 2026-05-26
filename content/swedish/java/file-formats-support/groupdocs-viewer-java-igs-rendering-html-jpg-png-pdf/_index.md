---
date: '2026-02-23'
description: Lär dig hur du konverterar IGS till PDF, HTML, JPG och PNG med GroupDocs.Viewer
  för Java. Följ den här steg‑för‑steg‑guiden med färdiga kodexempel som kan köras
  direkt.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Konvertera IGS till PDF, HTML, JPG och PNG med GroupDocs.Viewer Java
type: docs
url: /sv/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Konvertera IGS till PDF, HTML, JPG & PNG med GroupDocs.Viewer Java

Om du behöver **convert IGS to PDF** (eller till HTML, JPG, PNG) direkt från en Java‑applikation, har du kommit till rätt ställe. I den här handledningen går vi igenom allt du behöver—från att konfigurera biblioteket till att rendera 3‑D‑modellen i det format som passar ditt projekt. Du får se varför GroupDocs.Viewer är ett solidt val för snabba, pålitliga konverteringar och får praktisk kod som du kan lägga in i din egen lösning.

![Konvertera IGS-filer till HTML, JPG, PNG och PDF med GroupDocs.Viewer för Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Snabba svar
- **Kan jag konvertera IGS till PDF med Java?** Ja, med GroupDocs.Viewer’s `PdfViewOptions`.
- **Vilka utdataformat stöds?** HTML, JPG, PNG och PDF.
- **Behöver jag en licens för produktion?** En kommersiell licens krävs; en gratis provperiod är tillgänglig för testning.
- **Vilken Java‑version krävs?** JDK 8 eller högre.
- **Är Maven det enda sättet att lägga till biblioteket?** Nej, du kan också använda Gradle eller manuellt inkludera JAR‑filen.

## Vad betyder “convert IGS to PDF”?
Att konvertera IGS (ett neutralt filformat för 3‑D‑CAD‑data) till PDF innebär att omvandla en komplex 3‑D‑modell till ett statiskt, allmänt visningsbart dokument. Detta är användbart för att dela designer med intressenter som inte har CAD‑verktyg.

## Varför använda GroupDocs.Viewer för IGS‑konverteringar?
- **Zero‑code CAD rendering** – biblioteket sköter den tunga delen av att tolka IGS‑formatet.
- **Multiple output options** – ett API‑anrop kan producera HTML, JPG, PNG eller PDF.
- **Cross‑platform** – fungerar på alla operativsystem som stödjer Java.
- **Performance‑focused** – snabb rendering även för stora sammansättningar.

## Förutsättningar
- **GroupDocs.Viewer for Java** ≥ 25.2
- **JDK 8+** installerad och konfigurerad i din IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.)
- Grundläggande Maven‑kunskap (valfritt men rekommenderas)

## Så här installerar du GroupDocs.Viewer för Java

### Maven‑beroende
Lägg till GroupDocs‑förrådet och Viewer‑beroendet i din `pom.xml`:

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
GroupDocs.Viewer offers:
- **Free trial** – begränsad användning, bra för snabba tester.  
- **Temporary license** – full funktionalitet under en kort utvärderingsperiod.  
- **Commercial license** – obegränsad produktionsanvändning.

### Grundläggande Viewer‑initialisering
Kodsnutten nedan visar hur du skapar en `Viewer`‑instans som pekar på din IGS‑fil:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendera IGS till HTML

### Hur konverterar man IGS till HTML?
HTML‑utdata ger dig en interaktiv, webbläsarvänlig vy av 3‑D‑modellen.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Key point:** `HtmlViewOptions.forEmbeddedResources()` bäddar in alla nödvändiga resurser (CSS, bilder) direkt i HTML‑filen, vilket gör den portabel.

## Rendera IGS till JPG

### Hur konverterar man IGS till JPG?
JPG‑bilder är perfekta för miniatyrer eller snabba förhandsvisningar.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Du kan justera `JpgViewOptions` för att styra upplösning och komprimeringskvalitet.

## Rendera IGS till PNG

### Hur konverterar man IGS till PNG?
PNG stödjer transparens, vilket är praktiskt för att överlagra modellen på olika bakgrunder.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Experimentera med `PngViewOptions` för att hitta den bästa balansen mellan filstorlek och visuell kvalitet.

## Rendera IGS till PDF

### Hur konverterar man IGS till PDF?
PDF är det föredragna formatet för att dela detaljerad design‑dokumentation. Detta avsnitt adresserar direkt huvudnyckelordet **convert IGS to PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` låter dig styra sidlayout, bildkvalitet och om teckensnitt ska bäddas in.

## Praktiska tillämpningar
- **Web portals** – bädda in HTML‑renderade modeller direkt i produktkonfiguratorer.  
- **Marketing assets** – generera högupplösta JPG/PNG‑bilder för broschyrer.  
- **Technical documentation** – inkludera PDF‑renderingar av CAD‑modeller i användarmanualer.  
- **Quality assurance** – automatisera generering av miniatyrer för stora satser av IGS‑filer.

## Vanliga problem & lösningar

| Issue | Solution |
|-------|----------|
| **Mappen för utdata hittades inte** | Verifiera sökvägen som skickas till `Path outputDirectory` och säkerställ att Java‑processen har skrivbehörighet. |
| **Tomma sidor i PDF** | Se till att IGS‑filen inte är korrupt; försök öppna den i en CAD‑visare först. |
| **Långsam rendering för stora sammansättningar** | Öka JVM‑heapen (`-Xmx2g` eller mer) och överväg att rendera sida‑för‑sida med `viewer.getPageCount()` om det behövs. |
| **Saknade teckensnitt i PDF** | Använd `PdfViewOptions` för att bädda in nödvändiga teckensnitt eller installera de saknade teckensnitten på servern. |

## Vanliga frågor

**Q: Kan jag konvertera flera IGS‑filer i ett och samma kör?**  
A: Ja. Loopa igenom en lista med filsökvägar och anropa den lämpliga `view`‑metoden för varje.

**Q: Är det möjligt att anpassa PDF‑sidstorlek?**  
A: Absolut. `PdfViewOptions` erbjuder `setPageSize(PageSize.A4)` och liknande metoder.

**Q: Behöver jag en separat licens för varje utdataformat?**  
A: Nej. En enda GroupDocs.Viewer‑licens täcker alla stödjade format.

**Q: Hur stor kan en IGS‑fil vara innan prestandan försämras?**  
A: Biblioteket hanterar filer upp till flera hundra megabyte, men du kan behöva allokera mer JVM‑minne för mycket stora modeller.

**Q: Kan jag rendera endast en specifik vy eller orientering?**  
A: GroupDocs.Viewer renderar standardvyn. För anpassade orienteringar, förbehandla IGS‑filen med ett CAD‑verktyg innan konvertering.

---

**Senast uppdaterad:** 2026-02-23  
**Testad med:** GroupDocs.Viewer 25.2 for Java  
**Författare:** GroupDocs