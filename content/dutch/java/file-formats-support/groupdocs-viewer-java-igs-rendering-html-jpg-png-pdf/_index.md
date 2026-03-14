---
date: '2026-02-23'
description: Leer hoe je IGS kunt converteren naar PDF, HTML, JPG en PNG met GroupDocs.Viewer
  voor Java. Volg deze stapsgewijze handleiding met kant‑klaar code‑voorbeelden.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Converteer IGS naar PDF, HTML, JPG en PNG met GroupDocs.Viewer Java
type: docs
url: /nl/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Converteer IGS naar PDF, HTML, JPG & PNG met GroupDocs.Viewer Java

Als je **IGS naar PDF wilt converteren** (of naar HTML, JPG, PNG) rechtstreeks vanuit een Java‑applicatie, ben je hier aan het juiste adres. In deze tutorial lopen we alles door wat je nodig hebt—van het instellen van de bibliotheek tot het renderen van het 3‑D‑model in het formaat dat bij je project past. Je ziet waarom GroupDocs.Viewer een solide keuze is voor snelle, betrouwbare conversies en krijgt praktische code die je in je eigen oplossing kunt gebruiken.

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Snelle antwoorden
- **Kan ik IGS naar PDF converteren met Java?** Ja, met `PdfViewOptions` van GroupDocs.Viewer.  
- **Welke uitvoerformaten worden ondersteund?** HTML, JPG, PNG en PDF.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist; een gratis proefversie is beschikbaar voor testen.  
- **Welke Java‑versie is vereist?** JDK 8 of hoger.  
- **Is Maven de enige manier om de bibliotheek toe te voegen?** Nee, je kunt ook Gradle of handmatige JAR‑inclusie gebruiken.

## Wat betekent “convert IGS to PDF”?
Het converteren van IGS (een neutraal bestandsformaat voor 3‑D‑CAD‑gegevens) naar PDF betekent het omzetten van een complex 3‑D‑model naar een statisch, breed bekijkbaar document. Dit is handig voor het delen van ontwerpen met belanghebbenden die geen CAD‑tools hebben.

## Waarom GroupDocs.Viewer gebruiken voor IGS‑conversies?
- **Zero‑code CAD rendering** – de bibliotheek neemt het zware werk van het parseren van het IGS‑formaat op zich.  
- **Meerdere uitvoeropties** – één API‑aanroep kan HTML, JPG, PNG of PDF genereren.  
- **Cross‑platform** – werkt op elk besturingssysteem dat Java ondersteunt.  
- **Prestatiegericht** – snelle rendering zelfs voor grote assemblages.

## Vereisten
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** geïnstalleerd en geconfigureerd in je IDE (IntelliJ IDEA, Eclipse, NetBeans, enz.)  
- Basiskennis van Maven (optioneel maar aanbevolen)

## GroupDocs.Viewer voor Java instellen

### Maven‑afhankelijkheid
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`:

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

### Licentie‑acquisitie
GroupDocs.Viewer offers:
- **Gratis proefversie** – beperkte gebruiksduur, ideaal voor snelle tests.  
- **Tijdelijke licentie** – volledige functionaliteit voor een korte evaluatieperiode.  
- **Commerciële licentie** – onbeperkt gebruik in productie.

### Basis Viewer‑initialisatie
The snippet below shows how to create a `Viewer` instance that points to your IGS file:

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

## IGS renderen naar HTML

### Hoe IGS naar HTML converteren?
HTML output gives you an interactive, browser‑friendly view of the 3‑D model.

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

**Belangrijk punt:** `HtmlViewOptions.forEmbeddedResources()` embed alle benodigde assets (CSS, afbeeldingen) direct in het HTML‑bestand, waardoor het draagbaar is.

## IGS renderen naar JPG

### Hoe IGS naar JPG converteren?
JPG images are perfect for thumbnails or quick previews.

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

Je kunt `JpgViewOptions` aanpassen om de resolutie en compressiekwaliteit te regelen.

## IGS renderen naar PNG

### Hoe IGS naar PNG converteren?
PNG supports transparency, which is handy for overlaying the model on different backgrounds.

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

Experimenteer met `PngViewOptions` om de beste balans tussen bestandsgrootte en visuele kwaliteit te krijgen.

## IGS renderen naar PDF

### Hoe IGS naar PDF converteren?
PDF is the go‑to format for sharing detailed design documentation. This section directly addresses the primary keyword **convert IGS to PDF**.

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

`PdfViewOptions` stelt je in staat de paginalay-out, beeldkwaliteit en of lettertypen moeten worden ingesloten te regelen.

## Praktische toepassingen
- **Webportalen** – embed HTML‑gerenderde modellen direct in productconfigurators.  
- **Marketing‑materiaal** – genereer hoge‑resolutie JPG/PNG‑afbeeldingen voor brochures.  
- **Technische documentatie** – voeg PDF‑renderingen van CAD‑modellen toe aan gebruikershandleidingen.  
- **Kwaliteitsborging** – automatiseer het genereren van thumbnails voor grote batches IGS‑bestanden.

## Veelvoorkomende problemen & oplossingen

| Issue | Solution |
|-------|----------|
| **Uitvoermap niet gevonden** | Controleer het pad dat aan `Path outputDirectory` wordt doorgegeven en zorg ervoor dat het Java‑proces schrijfrechten heeft. |
| **Lege pagina's in PDF** | Zorg ervoor dat het IGS‑bestand niet corrupt is; probeer het eerst te openen in een CAD‑viewer. |
| **Trage rendering bij grote assemblages** | Verhoog de JVM‑heap (`-Xmx2g` of meer) en overweeg om pagina voor pagina te renderen met `viewer.getPageCount()` indien nodig. |
| **Ontbrekende lettertypen in PDF** | Gebruik `PdfViewOptions` om vereiste lettertypen in te sluiten of installeer de ontbrekende lettertypen op de server. |

## Veelgestelde vragen

**Q: Kan ik meerdere IGS‑bestanden in één run converteren?**  
A: Ja. Loop door een lijst met bestandspaden en roep de juiste `view`‑methode voor elk bestand aan.

**Q: Is het mogelijk om de PDF‑paginasize aan te passen?**  
A: Zeker. `PdfViewOptions` biedt `setPageSize(PageSize.A4)` en soortgelijke methoden.

**Q: Heb ik een aparte licentie nodig voor elk uitvoerformaat?**  
A: Nee. Eén GroupDocs.Viewer‑licentie dekt alle ondersteunde formaten.

**Q: Hoe groot kan een IGS‑bestand zijn voordat de prestaties afnemen?**  
A: De bibliotheek kan bestanden tot enkele honderden megabytes aan, maar je moet mogelijk meer JVM‑geheugen toewijzen voor zeer grote modellen.

**Q: Kan ik alleen een specifieke weergave of oriëntatie renderen?**  
A: GroupDocs.Viewer rendert de standaardweergave. Voor aangepaste oriëntaties moet je het IGS‑bestand vooraf bewerken met een CAD‑tool vóór conversie.

---

**Laatst bijgewerkt:** 2026-02-23  
**Getest met:** GroupDocs.Viewer 25.2 voor Java  
**Auteur:** GroupDocs