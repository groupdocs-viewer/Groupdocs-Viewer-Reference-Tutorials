---
date: '2026-03-24'
description: Leer hoe je EML naar HTML kunt converteren met een aangepast datum‑tijdformaat
  en de tijdzone‑offset kunt instellen in Java met GroupDocs.Viewer. Ideaal voor e‑mailarchivering
  en supportsystemen.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Converteer EML naar HTML met aangepaste datum/tijd in Java met GroupDocs.Viewer
type: docs
url: /nl/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Converteer EML naar HTML met Aangepaste DateTime in Java met GroupDocs.Viewer

In de hedendaagse snel veranderende digitale wereld is het kunnen **convert EML to HTML** snel en met de juiste datum‑tijd presentatie essentieel voor archivering, supportportalen en wettelijke naleving. Deze tutorial leidt je door het renderen van e‑mailberichten naar HTML terwijl een **custom datetime format** en een **timezone offset** worden toegepast met GroupDocs.Viewer voor Java. Aan het einde heb je een herbruikbare oplossing die tijdstempels nauwkeurig en leesbaar houdt, perfect voor elke **email to HTML Java** workflow.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Wat je zult leren**
- Hoe GroupDocs.Viewer in een Java‑project in te stellen  
- Hoe e‑mails naar HTML te renderen met ingebedde resources  
- Hoe de **customize the date‑time format** van je e‑mailberichten (custom datetime java)  
- Hoe de **set the timezone offset** voor correcte tijdstempels (timezone offset java)  

## Snelle antwoorden
- **Kan GroupDocs.Viewer EML naar HTML converteren?** Ja, het rendert EML‑bestanden direct naar HTML.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor testen; een betaalde licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8 of nieuwer.  
- **Hoe wijzig ik het weergegeven datumformaat?** Gebruik `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Kan ik de tijdzone aanpassen?** Ja, met `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## Wat is “convert EML to HTML”?
Het converteren van een EML‑bestand naar HTML transformeert de ruwe e‑mail (inclusief headers, body en bijlagen) naar een web‑vriendelijk formaat dat browsers kunnen weergeven zonder extra plug‑ins. Dit maakt het eenvoudig om e‑mails in webapplicaties, archieven of support‑dashboards in te sluiten.

## Waarom GroupDocs.Viewer voor deze taak gebruiken?
- **Zero‑dependency rendering** – geen Outlook of externe mail‑parsers nodig.  
- **Built‑in support for embedded resources** (afbeeldingen, bijlagen).  
- **Fine‑grained control** over datum‑tijd opmaak en tijdzone‑afhandeling.  

## Vereisten

- **GroupDocs.Viewer for Java** versie 25.2 of hoger.  
- **Java Development Kit (JDK)** 8+ en een IDE (IntelliJ IDEA, Eclipse, etc.).  
- Basiskennis van Java en vertrouwdheid met Maven.

## GroupDocs.Viewer voor Java instellen

### Maven‑configuratie
Voeg de GroupDocs‑repository en afhankelijkheid toe aan je `pom.xml`:

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

### Licentie‑acquisitie
Begin met een gratis proefversie of vraag een tijdelijke licentie aan voor uitgebreid testen. Schaf een volledige licentie aan voor productiegebruik.

### Basisinitialisatie
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Converteer EML naar HTML met Aangepaste DateTime in Java

De volgende stap‑voor‑stap gids laat zien hoe je **convert EML to HTML** kunt uitvoeren terwijl je een aangepast datetime‑formaat en tijdzone‑offset toepast.

### Stap 1: Output‑map en bestands‑pad instellen
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Uitleg:* `Path.of()` maakt een referentie naar de map waar de HTML wordt opgeslagen. `resolve()` voegt de bestandsnaam toe.

### Stap 2: Viewer initialiseren met e‑mailbestand
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Uitleg:* De `Viewer`‑instantie wijst naar het EML‑bestand dat je wilt converteren.

### Stap 3: HtmlViewOptions configureren
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Uitleg:* `forEmbeddedResources()` bundelt afbeeldingen en andere resources direct in de HTML‑output.

### Stap 4: Aangepast DateTime‑formaat instellen *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Uitleg:* Dit patroon toont de maand, dag, jaar, uur, minuut, AM/PM‑markering en de tijdzone‑offset (`zzz`).

### Stap 5: Tijdzone‑offset instellen *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Uitleg:* Past de gerenderde tijdstempels aan naar de gewenste tijdzone. Vervang `"GMT+1"` door een geldige zone‑identifier.

### Hoe e‑mailtijdzone in Java aan te passen
Als je de **adjust email timezone** moet aanpassen buiten eenvoudige offsets—bijvoorbeeld bij het verwerken van zomertijd—kun je het juiste `TimeZone`‑object ophalen via de `java.util.TimeZone`‑API met regio‑ID's zoals `"Europe/Paris"` of `"America/New_York"` en dit doorgeven aan `setTimeZoneOffset`. Dit zorgt ervoor dat de e‑mailtijdstempels altijd de correcte lokale tijd weergeven.

### Stap 6: Document renderen
```java
viewer.view(options);
```
*Uitleg:* Voert de conversie uit en produceert een HTML‑bestand met je aangepaste datum‑tijd instellingen.

## Probleemoplossingstips
- **FileNotFoundException:** Controleer de paden die in `Viewer` en `Path.of()` worden gebruikt.  
- **Incorrect timestamps:** Verifieer dat de `TimeZone`‑ID overeenkomt met je doelregio.  
- **Missing images:** Zorg ervoor dat je `HtmlViewOptions.forEmbeddedResources()` hebt gebruikt; anders worden externe resources mogelijk niet opgenomen.

## Praktische toepassingen
1. **Email Archiving:** Sla doorzoekbare HTML‑snapshots van e‑mails op voor naleving.  
2. **Customer Support Portals:** Toon binnenkomende tickets met nauwkeurige lokale tijden.  
3. **Legal Documentation:** Maak gerechtsklare e‑mailrecords met gestandaardiseerde tijdstempels.

## Prestatie‑overwegingen
- Zet in op een dedicated server voor bulk‑conversies.  
- Houd het Java‑heap‑gebruik in de gaten; verhoog `-Xmx` bij een `OutOfMemoryError`.  
- Cache de gerenderde HTML wanneer dezelfde e‑mail herhaaldelijk wordt opgevraagd.

## Conclusie
Je hebt nu een complete, productie‑klare methode om **convert EML to HTML** uit te voeren met een aangepast datetime‑formaat en tijdzone‑offset met GroupDocs.Viewer voor Java. Dit verbetert de leesbaarheid, zorgt voor nauwkeurige tijdstempels en past naadloos in archiverings‑ of support‑workflows.

**Volgende stappen:** Verken extra Viewer‑opties zoals CSS‑styling, paginering of PDF‑conversie om de output verder aan te passen aan je behoeften.

## Veelgestelde vragen

**Q: Hoe ga ik om met EML‑bestanden met bijlagen?**  
A: Bijlagen worden automatisch ingebed wanneer je `HtmlViewOptions.forEmbeddedResources()` gebruikt. Je kunt ze ook extraheren via de Viewer‑API indien nodig.

**Q: Kan ik de HTML‑template wijzigen of aangepaste CSS toevoegen?**  
A: Ja, na het renderen kun je het gegenereerde HTML‑bestand bewerken of CSS programmatisch injecteren vóór het opslaan.

**Q: Is het mogelijk om meerdere EML‑bestanden in één batch te renderen?**  
A: Plaats de renderlogica in een lus en hergebruik dezelfde `HtmlViewOptions`‑instantie voor elk bestand.

**Q: Wat als ik andere e‑mailformaten zoals MSG moet ondersteunen?**  
A: GroupDocs.Viewer ondersteunt ook MSG, PST en andere e‑mailcontainers—verander simpelweg de bestandsextensie in de `Viewer`‑constructor.

**Q: Heb ik een aparte licentie per server nodig?**  
A: Licenties zijn per implementatie; raadpleeg de GroupDocs‑licentiegids voor multi‑server scenario's.

## Bronnen

- [Documentatie](https://docs.groupdocs.com/viewer/java/)
- [API‑referentie](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Aankoop](https://purchase.groupdocs.com/buy)
- [Gratis proefversie](https://releases.groupdocs.com/viewer/java/)
- [Tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)
- [Supportforum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-03-24  
**Getest met:** GroupDocs.Viewer 25.2 (Java)  
**Auteur:** GroupDocs