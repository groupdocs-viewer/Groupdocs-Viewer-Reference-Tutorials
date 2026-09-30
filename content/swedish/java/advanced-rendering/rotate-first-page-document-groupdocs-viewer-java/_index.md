---
date: '2026-09-30'
description: Lär dig hur du roterar en sida 90 grader i Java med GroupDocs Viewer,
  inklusive installation, kod och prestandatips.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Rotera sidan 90 grader i Java med GroupDocs Viewer. Steg‑för‑steg‑guide,
  prestandatips och verkliga användningsfall för utvecklare.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Rotera sidan 90 grader med GroupDocs Viewer för Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Rotera sidan 90 grader med GroupDocs Viewer för Java
type: docs
url: /sv/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rotera sidan 90 grader med GroupDocs Viewer för Java

Om du behöver **rotera sidan 90 grader** i ett dokument—oavsett om det är en PDF, Word‑fil eller kalkylblad—så sparar ett programatiskt tillvägagångssätt i Java tid, eliminerar manuella fel och låter dig integrera operationen i automatiserade pipelines. I den här avancerade guiden lär du dig hur du roterar den första sidan i vilket stödformat som helst med **GroupDocs Viewer för Java**, varför denna funktion är viktig i verkliga projekt och hur du håller processen lättviktig och minnes‑effektiv.

![Rotera den första sidan i ett dokument med GroupDocs.Viewer för Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Snabba svar
- **Vad betyder “rotate page 90 degrees”?** Den vrider den valda sidan medurs ett kvarts varv.  
- **Vilket bibliotek hanterar rotationen?** GroupDocs Viewer för Java tillhandahåller metoden `rotatePage`.  
- **Kan jag rotera PDF‑sidor med Java?** Ja—använd samma `rotatePage`‑anrop; det fungerar för PDF, DOCX, XLSX och mer.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en betald licens krävs för produktion.  
- **Är operationen minnesintensiv?** Inte när du stänger `Viewer`‑instansen omedelbart; se prestandatipsen nedan.

## Vad är “rotate page 90 degrees”?
Att rotera en sida 90 grader omorienterar sidan från stående till liggande (eller tvärtom) utan att ändra det underliggande innehållet. Detta är praktiskt för presentationer, utskrift av enbart liggande grafik eller korrigering av skannade dokument som fångats snett. Rotation appliceras vid renderingen och lämnar originalfilen oförändrad.

## Varför rotera sidor programatiskt med GroupDocs Viewer för Java?
GroupDocs Viewer stödjer **50+ in‑ och utdataformat**—inklusive PDF, DOCX, PPTX, XLSX och många bildtyper—så att du kan rendera vilket dokument som helst utan externa konverterare. API‑et är flytande, trådsäkert och körs på vilken Java 8+‑runtime som helst, vilket gör det till ett pålitligt val för företags‑automation som måste hantera dussintals filtyper konsekvent.

## Förutsättningar

- GroupDocs Viewer för Java (senaste versionen)
- JDK 8 eller nyare
- Maven (eller Gradle) för beroendehantering
- En IDE såsom IntelliJ IDEA eller Eclipse
- Grundläggande kunskap om Java I/O

## Installera GroupDocs.Viewer för Java

Lägg till GroupDocs‑arkivet och beroendet i din `pom.xml`. Detta kodexempel är oförändrat från den ursprungliga handledningen:

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
- **Gratis provversion** – ladda ner från GroupDocs webbplats.  
- **Tillfällig licens** – begär om du behöver en förlängd utvärderingsperiod.  
- **Full licens** – köp för produktionsdistributioner.

### Grundläggande Viewer‑initialisering
Klassen `Viewer` är startpunkten som laddar ett dokument och exponerar renderings‑ och transformationsmetoder. Behåll koden exakt som visad:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Hur man roterar PDF‑sida i Java med GroupDocs Viewer
Läs in målfilen med `Viewer`, ange sidnumret och anropa `rotatePage`. Metoden fungerar för PDF, DOCX, PPTX, XLSX och alla andra format som stöds av biblioteket. Efter rotation kan du rendera dokumentet till en ny PDF eller strömma det direkt till klienten, vilket säkerställer att originalfilen förblir orörd.

## Steg‑för‑steg-implementation: rotera den första sidan 90 grader

### 1. Importera de nödvändiga paketen
`PdfViewOptions` talar om för Viewer att skriva ut en PDF‑fil, medan enum‑typen `Rotation` definierar vinkeln. Båda klasserna tillhör paketet `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definiera utdata‑platser och skapa Viewer
Byt ut platshållar‑sökvägarna mot dina faktiska kataloger. `Viewer`‑konstruktorn accepterar ett `File`‑objekt som pekar på källdokumentet.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Konfigurera PDF‑visningsalternativ och tillämpa rotationen
Metoden `rotatePage(int, Rotation)` tar ett **1‑baserat** sidindex och ett `Rotation`‑enum‑värde. I detta exempel använder vi `Rotation.ON_90_DEGREE` för att vrida den första sidan medurs.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Rendera dokumentet
Genom att anropa `view` med de konfigurerade alternativen skrivs den roterade PDF‑filen till utmatningsmappen.

```java
viewer.view(viewOptions);
```

#### Så fungerar det
- **PdfViewOptions** styr Viewer att generera en PDF‑utdatafil.  
- **rotatePage(int, Rotation)** roterar endast den angivna sidan, medan alla andra sidor förblir oförändrade.  
- Metoden stödjer tre rotationskonstanter: `ON_90_DEGREE`, `ON_180_DEGREE` och `ON_270_DEGREE`.

## Vanliga problem och lösningar
| Symptom | Trolig orsak | Lösning |
|---------|--------------|-----|
| **FileNotFoundException** | Felaktig sökväg eller saknad mapp | Verifiera att `YOUR_OUTPUT_DIRECTORY` och `YOUR_DOCUMENT_DIRECTORY` finns och är läsbara. |
| **Unsupported file format** | Försöker rotera ett format som inte stöds av Viewer | Kontrollera sidan [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Använder fel sidnummer (0‑baserat) | Kom ihåg att `rotatePage` använder **1‑baserad** indexering. |
| **Out‑of‑memory errors on large docs** | Renderar många stora filer i en enda tråd | Processa dokument sekventiellt eller använd en trådpool med begränsad samtidighet. |

## Praktiska tillämpningar

1. **Presentationjusteringar** – Konvertera en stående bild till liggande i realtid för bättre visuell effekt.  
2. **Masskorrektion av dokument** – Automatisera korrigering av skannade PDF‑filer som fångats snett, vilket sparar timmar av manuellt arbete.  
3. **Utskriftsklar output** – Säkerställ att liggande grafik skrivs ut korrekt på stående papper utan manuell rotation i skrivardrivrutinen.

## Prestandatips

- **Stäng resurser omedelbart** – `try‑with‑resources`‑blocket frigör automatiskt `Viewer`, vilket frigör minne.  
- **Batch‑behandling** – Återanvänd en enda `Viewer`‑instans per tråd för att minska initieringskostnaden.  
- **Övervaka minne** – För dokument större än 100 MB, strömma utdata till disk istället för att hålla hela filen i minnet; GroupDocs Viewer kan bearbeta 200 MB‑filer med under 250 MB RAM.

## Vanliga frågor

**Q: Kan jag rotera flera sidor samtidigt?**  
A: Ja—anropa `rotatePage()` för varje sidnummer du behöver rotera, antingen i en loop eller genom att kedja anrop.

**Q: Finns det ett sätt att ångra rotationen efter rendering?**  
A: Inte direkt. Du måste rendera dokumentet igen utan rotationsalternativen.

**Q: Vilka filformat stödjer sidrotation i GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX och många andra format som listas i den officiella dokumentationen.

**Q: Hur kan jag rotera sidor i en mängd dokument automatiskt?**  
A: Packa rotationslogiken i en loop som itererar över en samling av filsökvägar och tillämpar samma `rotatePage`‑konfiguration på varje fil.

**Q: Vad är bästa praxis för att hantera fel under rotation?**  
A: Omge Viewer‑användningen med ett `try‑catch`‑block, logga undantagsdetaljerna och fortsätt eventuellt med nästa fil för att undvika att ett enstaka fel stoppar hela batchen.

## Resurser

- **Dokumentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API‑referens**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Ladda ner**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Köp en licens**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Prova gratis**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Begär tillfällig licens**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Senast uppdaterad:** 2026-09-30  
**Testad med:** GroupDocs Viewer 25.2 för Java  
**Författare:** GroupDocs

## Relaterade handledningar

- [Hur man roterar specifika PDF‑sidor med GroupDocs.Viewer för Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Ladda dokument från URL i Java – GroupDocs.Viewer‑handledning](/viewer/java/document-loading/)
- [GroupDocs Viewer Java Dokumentvyer](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}