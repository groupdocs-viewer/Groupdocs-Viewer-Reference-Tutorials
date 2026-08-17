---
date: '2026-08-08'
description: Leer hoe u IGS naar PDF, HTML, JPG en PNG kunt converteren met GroupDocs.Viewer
  voor Java. Stapsgewijze handleiding, vereisten en probleemoplossing voor Java‑ontwikkelaars.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Converteer IGS naar PDF, HTML, JPG en PNG met GroupDocs.Viewer voor
  Java. Gedetailleerde installatie, code‑fragmenten en probleemoplossing voor Java‑ontwikkelaars.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Converteer IGS naar PDF, HTML, JPG en PNG met GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Converteer IGS naar PDF, HTML, JPG en PNG met GroupDocs.Viewer Java
type: docs
url: /nl/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convert IGS naar PDF, HTML, JPG & PNG met GroupDocs.Viewer Java

Als je **IGS naar PDF converteren** (of naar HTML, JPG, PNG) direct vanuit een Java‑applicatie, ben je op de juiste plek. In deze tutorial lopen we alles door wat je nodig hebt—van het installeren van de bibliotheek tot het renderen van het 3‑D‑model in het formaat dat bij je project past. Je begrijpt waarom GroupDocs.Viewer een solide keuze is voor snelle, betrouwbare conversies en je krijgt kant‑klaar code‑fragmenten die je in je eigen oplossing kunt gebruiken.

![IGS-bestanden converteren naar HTML, JPG, PNG en PDF met GroupDocs.Viewer voor Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Snelle antwoorden
- **Kan ik IGS naar PDF converteren met Java?** Ja, gebruik `PdfViewOptions` samen met de `Viewer` API.  
- **Welke uitvoerformaten worden ondersteund?** HTML, JPG, PNG en PDF worden allemaal native ondersteund.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist; een gratis proefversie laat je de kernfuncties testen.  
- **Welke Java‑versie is vereist?** JDK 8 of hoger; de bibliotheek draait ook op Java 11, 17 en later.  
- **Is Maven de enige manier om de bibliotheek toe te voegen?** Nee, je kunt ook Gradle gebruiken of de JAR‑bestanden handmatig aan je classpath toevoegen.

## Wat is IGS naar PDF converteren?
IGS naar PDF converteren betekent een neutraal 3‑D‑CAD‑bestand omzetten naar een statisch, universeel bekijkbaar document. Dit stelt je in staat om ontwerpvisualisaties te delen met belanghebbenden die geen CAD‑tools hebben, de weergave in rapporten in te sluiten, of het model te archiveren voor nalevingsdoeleinden.

## Waarom GroupDocs.Viewer gebruiken voor IGS-conversies?
GroupDocs.Viewer verwerkt IGS‑bestanden zonder dat externe CAD‑software nodig is. Het ondersteunt **meer dan 50 invoer‑ en uitvoerformaten**, kan assemblages met **honderden onderdelen** renderen terwijl het geheugenverbruik onder **200 MB** blijft, en levert resultaten in minder dan **2 seconden** voor typische modellen op een standaard server. Deze gekwantificeerde voordelen maken het een high‑performance, kosteneffectieve keuze voor enterprise‑pijplijnen.

## Voorvereisten
- **GroupDocs.Viewer for Java** ≥ 25.2 (de nieuwste stabiele release).  
- **JDK 8+** geïnstalleerd en geconfigureerd in je IDE (IntelliJ IDEA, Eclipse, NetBeans, enz.).  
- Basiskennis van Maven (optioneel maar aanbevolen voor dependency‑beheer).  

## GroupDocs.Viewer voor Java instellen

### Maven‑dependency
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
GroupDocs.Viewer offers three licensing options:
- **Gratis proefversie** – beperkte gebruik, perfect voor snelle proof‑of‑concept tests.  
- **Tijdelijke licentie** – volledige functionaliteit voor een korte evaluatieperiode, ideaal voor pilotprojecten.  
- **Commerciële licentie** – onbeperkt gebruik in productie, inclusief prioritaire ondersteuning en updates.

### Basisviewer‑initialisatie
The `Viewer` class is the entry point for all rendering operations. It loads the source file, parses the format, and exposes methods to produce the desired output.

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
Laad het IGS‑bestand met een `Viewer`‑instantie en geef een `HtmlViewOptions`‑object door dat alle benodigde assets insluit. De aanroep retourneert één HTML‑bestand dat de volledige 3‑D‑weergave bevat, waardoor het eenvoudig in webpagina’s kan worden ingebed. Je kunt de weergave ook aanpassen door opties in te stellen zoals paginagrootte, achtergrondkleur en of interactieve bedieningselementen moeten worden opgenomen.  
HtmlViewOptions configureert hoe de HTML‑output wordt gegenereerd, inclusief resource‑embedding en paginalay-out.

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

## IGS renderen naar JPG

### Hoe IGS naar JPG converteren?
Maak een `JpgViewOptions`‑object, configureer de gewenste resolutie en compressiekwaliteit, en laat de `Viewer` rasterafbeeldingen genereren voor elke pagina van het model. De gegenereerde JPG‑bestanden kunnen worden opgeslagen in een opgegeven map, en je kunt de kwaliteitsparameter aanpassen om de bestandsgrootte af te stemmen op de visuele nauwkeurigheid, wat handig is voor miniaturen of hoge‑resolutie‑afdrukken.  
JpgViewOptions specificeert instellingen voor JPG‑afbeeldingsgeneratie zoals resolutie, kwaliteit en uitvoermap.

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

## IGS renderen naar PNG

### Hoe IGS naar PNG converteren?
De `PpngViewOptions`‑klasse stelt je in staat verliesvrije afbeeldingen te produceren met optionele transparantie. Dit formaat is ideaal om het model over gekleurde achtergronden in marketingmateriaal te leggen. Je kunt ook de resolutie en achtergrondkleur definiëren om aan je merkrichtlijnen te voldoen, waardoor een consistente uitstraling over alle gegenereerde assets wordt gegarandeerd.  
PngViewOptions definieert parameters voor PNG‑rendering, inclusief resolutie, transparantie en achtergrondkleur.

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

## IGS renderen naar PDF

### Hoe IGS naar PDF converteren?
Gebruik `PdfViewOptions` om een gepagineerde PDF te maken die de visuele lay-out van het 3‑D‑model behoudt. Je kunt ook lettertypen insluiten en de paginagrootte regelen om te voldoen aan de corporate branding‑richtlijnen. Extra instellingen laten je de beeldkwaliteit, compressieniveau en of een inhoudsopgave moet worden opgenomen voor meer‑pagina‑assemblages specificeren.  
PdfViewOptions regelt de PDF‑creatie, waardoor paginagrootte, beeldkwaliteit en lettertype‑embedding kunnen worden geconfigureerd.

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

## Praktische toepassingen
- **Webportalen** – embed HTML‑gerenderde modellen direct in productconfigurators, waardoor klanten kunnen roteren en zoomen zonder plugins te installeren.  
- **Marketing‑assets** – genereer hoge‑resolutie JPG/PNG‑afbeeldingen voor brochures, presentaties en social‑media‑posts.  
- **Technische documentatie** – voeg PDF‑renderingen van CAD‑modellen toe aan gebruikershandleidingen, zodat ingenieurs ontwerpen offline kunnen bekijken.  
- **Kwaliteitsborging** – automatiseer het maken van miniaturen voor duizenden IGS‑bestanden, waardoor visuele inspectieworkflows versnellen.

## Veelvoorkomende problemen & oplossingen

| Probleem | Oplossing |
|----------|-----------|
| **Uitvoermap niet gevonden** | Controleer het pad dat is doorgegeven aan `Path outputDirectory` en zorg ervoor dat het Java‑proces schrijfrechten heeft op de doelmap. |
| **Lege pagina's in PDF** | Bevestig dat het bron‑IGS‑bestand niet corrupt is; open het eerst in een native CAD‑viewer. |
| **Trage rendering voor grote assemblages** | Verhoog de JVM‑heap (`-Xmx2g` of meer) en overweeg rendering pagina‑voor‑pagina met `viewer.getPageCount()` om in delen te verwerken. |
| **Ontbrekende lettertypen in PDF** | Gebruik `PdfViewOptions` om vereiste lettertypen in te sluiten of installeer de ontbrekende lettertypen op de server die de conversiedienst host. |

## Veelgestelde vragen

**V: Kan ik meerdere IGS‑bestanden in één run converteren?**  
A: Ja. Iterate over een collectie bestands‑paden en roep de juiste `view`‑methode aan voor elk bestand binnen dezelfde `Viewer`‑instantie.

**V: Is het mogelijk om de PDF‑paginagrootte aan te passen?**  
A: Absoluut. `PdfViewOptions` biedt `setPageSize(PageSize.A4)`, `PageSize.Letter` en aangepaste afmetingen via `setCustomSize(width, height)`.

**V: Heb ik een aparte licentie nodig voor elk uitvoerformaat?**  
A: Nee. Eén GroupDocs.Viewer‑licentie dekt alle ondersteunde formaten, inclusief HTML, JPG, PNG en PDF.

**V: Hoe groot mag een IGS‑bestand zijn voordat de prestaties afnemen?**  
A: De bibliotheek verwerkt betrouwbaar bestanden tot **500 MB**; voor modellen groter dan 200 MB, wijs extra JVM‑geheugen toe en overweeg batch‑rendering.

**V: Kan ik alleen een specifieke weergave of oriëntatie renderen?**  
A: GroupDocs.Viewer rendert de standaardoriëntatie die in het IGS‑bestand is gedefinieerd. Voor aangepaste weergaven, preprocess het bestand met een CAD‑tool of pas het model aan vóór conversie.

---

**Laatst bijgewerkt:** 2026-08-08  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs

## Gerelateerde tutorials

- [cdr naar html, jpg, png, pdf converteren met GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Hoe pdf naar html converteren en beeldkwaliteit optimaliseren in Java met GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)