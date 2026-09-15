---
date: '2026-09-15'
description: Leer hoe u eml naar html kunt converteren met een aangepast datum‑tijdformaat
  en tijdzone‑offset met GroupDocs.Viewer voor Java—ideaal voor e‑mailarchivering
  en ondersteuningsportalen.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Converteer eml naar html met een aangepast datum‑tijdformaat en tijdzone‑offset
  met GroupDocs.Viewer voor Java. Volg deze stapsgewijze handleiding voor nauwkeurige
  weergave van e‑mail.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: Converteer eml naar html met aangepaste datum‑tijd in java met GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: Converteer eml naar html met aangepaste datum‑tijd in java met GroupDocs.Viewer
type: docs
url: /nl/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EML naar HTML converteren met aangepaste datum/tijd in Java met GroupDocs.Viewer

In moderne support- en archiveringssystemen is **convert eml to html** snel uitvoeren terwijl exacte tijdstempels behouden blijven een onmisbare mogelijkheid. Deze tutorial laat zien hoe je een EML‑e‑mail rendert naar HTML, een **custom datetime format** toepast, en een **timezone offset** instelt met GroupDocs.Viewer voor Java. Aan het einde heb je een herbruikbare code‑fragment die nauwkeurige, web‑klare e‑mailweergaven produceert voor elke **email to html conversion** workflow.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Snelle antwoorden
- **Kan GroupDocs.Viewer EML naar HTML converteren?** Ja – de API rendert EML‑bestanden direct naar HTML zonder externe mailclients.  
- **Heb ik een licentie nodig voor productie?** Een gratis proefversie is voldoende voor testen; een betaalde licentie is vereist voor productie‑implementaties.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of nieuwer wordt volledig ondersteund.  
- **Hoe wijzig ik het weergegeven datumformaat?** Roep `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")` aan.  
- **Kan ik de tijdzone aanpassen?** Ja, gebruik `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## Wat is “convert eml to html”?
`Convert eml to html` is het proces van het omzetten van een EML‑e‑mailbestand naar een HTML‑document voor weergave in een browser. Het converteren van een EML‑bestand naar HTML verandert de ruwe e‑mail (inclusief headers, body en bijlagen) in een web‑vriendelijk formaat dat browsers kunnen weergeven zonder extra plug‑ins. Dit maakt het eenvoudig om e‑mails in webapplicaties, archieven of support‑dashboards in te sluiten.

## Waarom GroupDocs.Viewer voor deze taak gebruiken?
GroupDocs.Viewer ondersteunt **meer dan 50 invoer‑ en uitvoerformaten**, waaronder EML, MSG, PST en PDF, en kan e‑mails van honderden pagina's renderen zonder het volledige bestand in het geheugen te laden. De zero‑dependency engine elimineert de noodzaak voor Outlook of externe parsers, waardoor je volledige controle krijgt over **custom datetime format** en **timezone offset** terwijl het resource‑gebruik laag blijft.

## Vereisten
- GroupDocs.Viewer voor Java ≥ 25.2  
- JDK 8+ en een Java‑IDE (IntelliJ IDEA, Eclipse, VS Code)  
- Maven voor afhankelijkheidsbeheer  

## GroupDocs.Viewer voor Java instellen

### Maven‑configuratie
Voeg de GroupDocs‑repository en de Viewer‑dependency toe aan je `pom.xml`‑bestand.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### Licentie‑verwerving
Begin met een gratis proefversie of vraag een tijdelijke licentie aan voor uitgebreid testen. Schaf een volledige licentie aan voor productiegebruik.

### Basisinitialisatie
Maak een `Viewer`‑instantie die verwijst naar het EML‑bestand dat je wilt converteren.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## EML naar HTML converteren met aangepaste datum/tijd in Java

De volgende stappen leiden je door het renderen van een EML‑bestand naar HTML terwijl een custom datetime format en timezone offset worden toegepast.

### Stap 1: output‑directory en bestandspad instellen
Definieer waar de gegenereerde HTML wordt opgeslagen.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Uitleg:* `Path.of()` maakt een referentie naar de map waar de HTML wordt opgeslagen. `resolve()` voegt de bestandsnaam toe.

### Stap 2: viewer initialiseren met e‑mailbestand
Instantieer de `Viewer`‑klasse voor het doel‑EML‑bestand.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Uitleg:* De `Viewer`‑instantie wijst naar het EML‑bestand dat je wilt converteren.

### Stap 3: HtmlViewOptions configureren
Maak een `HtmlViewOptions`‑object dat afbeeldingen en andere bronnen direct in de HTML‑output bundelt.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Uitleg:* `forEmbeddedResources()` bundelt afbeeldingen en andere bronnen direct in de HTML‑output.

### Stap 4: custom datetime format instellen *(custom datetime java)*
`setDateTimeFormat` stelt het datum‑tijdpatroon in dat wordt gebruikt bij het renderen van e‑mail‑tijdstempels.  
Definieer het patroon dat voor alle tijdstempels in de gerenderde HTML wordt gebruikt.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Uitleg:* Dit patroon toont de maand, dag, jaar, uur, minuut, AM/PM‑aanduiding en de tijdzone‑offset (`zzz`).

### Stap 5: timezone offset instellen *(timezone offset java)*
`setTimeZoneOffset` specificeert de tijdzone die wordt toegepast op alle e‑mail‑tijdstempels.  
Pas tijdstempels aan naar de gewenste tijdzone.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Uitleg:* Past de gerenderde tijdstempels aan naar de gewenste tijdzone. Vervang `"GMT+1"` door een geldige zone‑identifier.

### Hoe e‑mail‑tijdzone in Java aanpassen
Als je de **email timezone** moet aanpassen voorbij eenvoudige offsets — bijvoorbeeld bij het omgaan met zomertijd — kun je het juiste `TimeZone`‑object ophalen via de `java.util.TimeZone`‑API met regio‑ID’s zoals `"Europe/Paris"` of `"America/New_York"` en dit doorgeven aan `setTimeZoneOffset`. Dit zorgt ervoor dat de e‑mail‑tijdstempels altijd de juiste lokale tijd weergeven.

### Stap 6: document renderen
Voer de conversie uit en genereer het uiteindelijke HTML‑bestand.

```java
viewer.view(options);
```
*Uitleg:* Voert de conversie uit en produceert een HTML‑bestand met je custom date‑time instellingen.

## Hoe beïnvloedt het custom datetime format de gerenderde HTML?
Het custom datetime format bepaalt hoe elk e‑mail‑tijdstempel verschijnt in de gegenereerde HTML, wat invloed heeft op leesbaarheid en naleving van locale‑instellingen. Door een patroon zoals `"MMM dd, yyyy hh:mm a zzz"` op te geven, zorg je dat elke datum consistent wordt weergegeven, met de maandafkorting, dag, jaar, uur, minuut, AM/PM‑aanduiding en de expliciete tijdzone‑offset, wat cruciaal is voor wereldwijde support‑teams.

## Welke bestandsformaten ondersteunt GroupDocs.Viewer voor e‑mailrendering?
GroupDocs.Viewer kan **EML, MSG, PST, MBOX en EMLX** bestanden renderen naar HTML, PDF, PNG en JPEG. Het ondersteunt meer dan 50 document‑ en afbeeldingsformaten, waardoor je e‑mails kunt converteren naar elk van de meest gangbare web‑vriendelijke outputformaten zonder extra converters.

## Hoe kan ik meerdere EML‑bestanden batch‑gewijs converteren?
Plaats alle EML‑bestanden in één map, loop door elk bestand met een `for`‑ of `foreach`‑constructie, hergebruik dezelfde `HtmlViewOptions`‑instantie en roep `viewer.view` aan voor elk bestand. Deze aanpak minimaliseert de overhead van objectcreatie en versnelt bulk‑conversies.

## Probleemoplossingstips
- **FileNotFoundException:** Controleer de paden die worden gebruikt in `Viewer` en `Path.of()`.  
- **Incorrect timestamps:** Zorg ervoor dat de `TimeZone`‑ID overeenkomt met je doellocatie.  
- **Missing images:** Controleer of je `HtmlViewOptions.forEmbeddedResources()` hebt gebruikt; anders kunnen externe bronnen weggelaten worden.

## Praktische toepassingen
1. **E‑mailarchivering:** Bewaar doorzoekbare HTML‑snapshots van e‑mails voor compliance‑audits.  
2. **Klantenondersteuningsportalen:** Toon binnenkomende tickets met nauwkeurige lokale tijden voor agenten wereldwijd.  
3. **Juridische documentatie:** Produceer gerechtsklare e‑mailrecords met gestandaardiseerde tijdstempels.

## Prestatie‑overwegingen
- Zet in op een dedicated server voor bulk‑conversies.  
- Houd het Java‑heap‑gebruik in de gaten; verhoog `-Xmx` als je een `OutOfMemoryError` tegenkomt.  
- Cache de gerenderde HTML wanneer dezelfde e‑mail herhaaldelijk wordt opgevraagd om de CPU‑belasting te verminderen.

## Conclusie
Je hebt nu een volledige, productie‑klare methode om **convert eml to html** uit te voeren met een custom datetime format en timezone offset met GroupDocs.Viewer voor Java. Deze oplossing verbetert de leesbaarheid, garandeert nauwkeurige tijdstempels en past naadloos in archiverings-, support- of juridische workflows.

**Volgende stappen:** Verken extra Viewer‑opties zoals custom CSS‑injectie, paginering of PDF‑conversie om de output verder af te stemmen op de behoeften van je applicatie.

## Veelgestelde vragen

**Q: Hoe ga ik om met EML‑bestanden met bijlagen?**  
A: Bijlagen worden automatisch ingebed wanneer je `HtmlViewOptions.forEmbeddedResources()` gebruikt. Je kunt ze ook extraheren via de Viewer‑API als je afzonderlijke bestanden nodig hebt.

**Q: Kan ik de HTML‑template wijzigen of custom CSS toevoegen?**  
A: Ja, na het renderen kun je het gegenereerde HTML‑bestand bewerken of CSS programmatisch injecteren vóór het opslaan.

**Q: Is het mogelijk om meerdere EML‑bestanden in één batch te renderen?**  
A: Plaats de renderlogica in een lus en hergebruik dezelfde `HtmlViewOptions`‑instantie voor elk bestand.

**Q: Wat als ik andere e‑mailformaten zoals MSG moet ondersteunen?**  
A: GroupDocs.Viewer ondersteunt ook MSG, PST en andere e‑mailcontainers — wijzig simpelweg de bestandsextensie in de `Viewer`‑constructor.

**Q: Heb ik een aparte licentie per server nodig?**  
A: Licenties zijn per implementatie; raadpleeg de GroupDocs‑licentiehandleiding voor multi‑server scenario's.

## Resources

- [Documentatie](https://docs.groupdocs.com/viewer/java/)
- [API‑referentie](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Aankoop](https://purchase.groupdocs.com/buy)
- [Gratis proefversie](https://releases.groupdocs.com/viewer/java/)
- [Tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)
- [Supportforum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-09-15  
**Getest met:** GroupDocs.Viewer 25.2 (Java)  
**Auteur:** GroupDocs

## Gerelateerde tutorials

- [E‑mail naar HTML converteren & velden hernoemen – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – Optimaliseer e‑mail‑naar‑PDF rendering met GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [GroupDocs Viewer Java responsieve HTML rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}