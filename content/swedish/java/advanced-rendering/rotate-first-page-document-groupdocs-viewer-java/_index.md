---
date: '2026-01-18'
description: Lär dig hur du roterar en sida 90 grader i Java med GroupDocs Viewer,
  inklusive installation, kod och prestandatips.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Rotera sidan 90 grader med GroupDocs Viewer för Java
type: docs
url: /sv/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Rotera sida 90 grader med GroupDocs Viewer för Java

När du behöver **rotera sida 90 grader** i ett dokument—oavsett om det är en PDF, Word‑fil eller kalkylblad—sparar det att göra det programmässigt tid och eliminerar manuella fel. I den här avancerade guiden går vi igenom de exakta stegen för att rotera den första sidan i vilket stödjat dokument som helst med **GroupDocs Viewer för Java**. I slutet har du ett återanvändbart kodsnutt som du kan lägga in i dina egna projekt.

![Rotera den första sidan i ett dokument med GroupDocs.Viewer för Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Snabba svar
- **Vad betyder “rotate page 90 degrees”?** Det vrider den valda sidan medurs ett kvart varv.  
- **Vilket bibliotek hanterar rotationen?** GroupDocs Viewer för Java tillhandahåller `rotatePage`‑metoden.  
- **Kan jag rotera PDF‑sidor med Java?** Ja—använd samma `rotatePage`‑anrop; det fungerar för PDF, DOCX, XLSX och mer.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en betald licens krävs för produktion.  
- **Är operationen minnesintensiv?** Inte när du stänger `Viewer`‑instansen omedelbart; se prestandatipsen nedan.

## Vad är “rotate page 90 degrees”?
Att rotera en sida 90 grader omorienterar sidan från stående till liggande (eller vice‑versa) utan att ändra det underliggande innehållet. Detta är särskilt praktiskt för presentationer, utskrift av enbart liggande grafik, eller korrigering av skannade dokument som fångades sidledes.

## Varför rotera sidor med GroupDocs Viewer för Java?
GroupDocs Viewer abstraherar komplexiteten i att hantera dussintals filformat. Det låter dig applicera sidnivå‑transformeringar—som rotation—utan att ändra den ursprungliga filen. API‑et är flytande, trådsäkert och fungerar på alla Java 8+‑miljöer.

## Förutsättningar

- **GroupDocs.Viewer for Java** (senaste versionen)
- **JDK 8** eller nyare
- **Maven** (eller Gradle) för beroendehantering
- En IDE såsom IntelliJ IDEA eller Eclipse
- Grundläggande kunskap om Java I/O

## Installera GroupDocs.Viewer för Java

Lägg till GroupDocs‑arkivet och beroendet i din `pom.xml`. Detta kodsnutt är oförändrad från den ursprungliga handledningen:

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
- **Free trial** – ladda ner från GroupDocs‑sajten.  
- **Temporary license** – begär om du behöver en förlängd utvärderingsperiod.  
- **Full license** – köp för produktionsdistributioner.

### Grundläggande Viewer‑initialisering
Följande kod visar det minsta sättet att skapa en `Viewer`‑instans. Behåll den exakt som den visas:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Steg‑för‑steg‑implementering: Rotera den första sidan 90 grader

### 1. Importera de nödvändiga paketen
Dessa importeringar ger dig åtkomst till PDF‑renderingsalternativ och rotations‑enum.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definiera utdata‑platser och skapa Viewer‑instansen
Byt ut platshållar‑sökvägarna mot dina faktiska kataloger.

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
`rotatePage`‑metoden tar sidnumret (1‑baserat) och ett `Rotation`‑enum‑värde.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Rendera dokumentet
Slutligen, anropa `view` för att generera den roterade PDF‑filen.

```java
viewer.view(viewOptions);
```

#### Så fungerar det
- **PdfViewOptions** talar om för Viewer att skriva ut en PDF‑fil.  
- **rotatePage(int, Rotation)** roterar endast den sida du anger, resten förblir orörd.  
- Metoden stödjer `ON_90_DEGREE`, `ON_180_DEGREE` och `ON_270_DEGREE`.

## Vanliga problem och lösningar

| Symptom | Trolig orsak | Lösning |
|---------|--------------|-----|
| **FileNotFoundException** | Felaktig sökväg eller saknad mapp | Verifiera att `YOUR_OUTPUT_DIRECTORY` och `YOUR_DOCUMENT_DIRECTORY` finns och är läsbara. |
| **Unsupported file format** | Försök att rotera ett format som inte stöds av Viewer | Kontrollera sidan [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Använder fel sidnummer (0‑baserat) | Kom ihåg att `rotatePage` använder **1‑baserad** indexering. |
| **Out‑of‑memory errors on large docs** | Renderar många stora filer i en enda tråd | Processa dokument sekventiellt eller använd en trådpott med begränsad samtidighet. |

## Praktiska tillämpningar

1. **Presentationjusteringar** – Konvertera en stående bild till liggande i farten.  
2. **Masskorrigering av dokument** – Automatisera rättning av skannade PDF‑filer som fångades sidledes.  
3. **Utskriftsklar output** – Säkerställ att liggande grafik skrivs ut korrekt på stående papper.

## Prestandatips

- **Stäng resurser omedelbart** – `try‑with‑resources`‑blocket frigör automatiskt `Viewer`.  
- **Batch‑behandling** – När du hanterar många filer, återanvänd en enda `Viewer`‑instans per tråd för att minska overhead.  
- **Övervaka minne** – För dokument större än 100 MB, överväg att strömma utdata till disk istället för att hålla den i minnet.

## Vanliga frågor

**Q: Kan jag rotera flera sidor samtidigt?**  
A: Ja—anropa `rotatePage()` för varje sidnummer du behöver rotera.

**Q: Finns det ett sätt att ångra rotationen efter rendering?**  
A: Inte direkt. Du skulle behöva rendera dokumentet igen utan rotationsalternativen.

**Q: Vilka filformat stödjer sidrotation i GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX och många andra format som listas i den officiella dokumentationen.

**Q: Hur kan jag rotera sidor i en mängd dokument automatiskt?**  
A: Omge koden med en loop som itererar över en samling av filsökvägar och tillämpar samma `rotatePage`‑logik på varje.

**Q: Vad är bästa praxis för att hantera fel under rotation?**  
A: Omge användningen av Viewer i ett `try‑catch`‑block, logga undantaget och fortsätt eventuellt med nästa fil.

## Resurser

- **Dokumentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API‑referens**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Nedladdning**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Köp**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Gratis provversion**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Tillfällig licens**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Senast uppdaterad:** 2026-01-18  
**Testad med:** GroupDocs Viewer 25.2 för Java  
**Författare:** GroupDocs  

---