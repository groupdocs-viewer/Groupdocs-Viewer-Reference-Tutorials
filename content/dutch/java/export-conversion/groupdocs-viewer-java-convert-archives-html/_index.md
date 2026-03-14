---
date: '2026-02-23'
description: Leer hoe u items per pagina instelt, HTML‑resources insluit en archieven
  in batch converteert naar één‑ of meerpagina‑HTML met GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Items per pagina instellen: archieven converteren naar HTML met GroupDocs.Viewer
  Java'
type: docs
url: /nl/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Items per pagina instellen: Archieven converteren naar HTML met GroupDocs.Viewer Java

Archieven zoals ZIP of RAR omzetten naar web‑vriendelijke HTML is een veelvoorkomende behoefte wanneer je documenten direct in een browser wilt delen of bekijken. In deze gids leer je **hoe je items per pagina instelt** tijdens het renderen van archieven, hoe je resources HTML embedt voor een zelf‑containende output, en hoe je archieven efficiënt batch‑converteert met GroupDocs.Viewer Java.

![Archieven converteren naar HTML met GroupDocs.Viewer voor Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Snelle antwoorden
- **Waar regelt “items per pagina instellen” over?** Het bepaalt hoeveel bestanden of mappen uit een archief op elke gegenereerde HTML‑pagina verschijnen.  
- **Kan ik afbeeldingen en CSS direct in de HTML embedden?** Ja – gebruik de `forEmbeddedResources`‑optie om resources HTML te embedden.  
- **Is batch‑conversie mogelijk?** Absoluut; je kunt over een collectie archieven itereren en elk één met dezelfde instellingen renderen.  
- **Heb ik Maven nodig om GroupDocs.Viewer te gebruiken?** Ja, voeg de `maven groupdocs viewer`‑dependency toe zoals hieronder weergegeven.  
- **Welke outputformaten worden ondersteund?** Single‑page HTML Java en multi‑page HTML Java zijn beide beschikbaar.

## Wat is “items per pagina instellen” in GroupDocs.Viewer?
De **items per pagina instellen**‑instelling behoort tot de archive‑renderopties. Ze vertelt de viewer hoeveel archief‑items (bestanden of mappen) op elke HTML‑pagina moeten worden weergegeven wanneer je een multi‑page HTML‑document genereert. Het aanpassen van deze waarde helpt je de paginagrootte en navigatiesnelheid in balans te houden, vooral bij grote archieven.

## Waarom resources HTML embedden?
Resources (afbeeldingen, CSS, fonts) direct in het HTML‑bestand embedden creëert één draagbaar document dat kan worden geopend zonder externe bestanden. Dit is ideaal voor e‑mailbijlagen, offline weergave, of het insluiten van de output in andere webpagina’s.

## Vereisten

- **Benodigde bibliotheken:** Include GroupDocs.Viewer versie 25.2 of later.  
- **Omgeving:** Java Development Kit (JDK) geïnstalleerd en geconfigureerd.  
- **Kennis:** Basis Java en Maven‑dependency‑beheer.  

## Maven GroupDocs Viewer Setup

Voeg de GroupDocs‑repository en de viewer‑dependency toe aan je `pom.xml`:

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
GroupDocs.Viewer biedt een **gratis proeflink**, een tijdelijke licentie, of een volledige aankoopoptie. Kies de optie die past bij je projectplanning.

### Basisinitialisatie
Na de Maven‑setup, haal de viewer in je code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Hoe archieven renderen naar Single‑Page HTML

### Stap 1: Output‑directory definiëren
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Stap 2: Bestandsnaam voor Single‑Page output instellen
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Stap 3: De Viewer initialiseren
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Stap 4: Renderopties configureren (embed resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Stap 5: Renderen als één pagina
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Hoe archieven renderen naar Multi‑Page HTML en items per pagina instellen

### Stap 1: De output‑directory opnieuw gebruiken
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Stap 2: Bestandsnaamsjabloon definiëren voor meerdere pagina’s
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Stap 3: De Viewer opnieuw initialiseren
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Stap 4: Multi‑Page‑opties configureren (embed resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Stap 5: Items per pagina instellen (primaire zoekterm in actie)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktische toepassingen

- **Document Management Systemen:** Voeg archief‑previewfunctionaliteit toe zonder extra viewers te installeren.  
- **Webportalen:** Bied gebruikers een snelle, geen‑download manier om gebundelde documenten te verkennen.  
- **Samenwerkingstools:** Laat teams gedeelde archieven direct in de browser inspecteren.

## Prestatie‑overwegingen

- **Resource‑beheer:** Houd het geheugenverbruik in de gaten; overweeg de JVM‑garbage‑collector af te stemmen voor grote batches.  
- **Batch‑conversie van archieven:** Loop door een lijst met archiefbestanden en roep dezelfde renderlogica aan om de doorvoer te maximaliseren.  
- **Caching‑strategie:** Sla gerenderde HTML op in een cache als hetzelfde archief vaak wordt opgevraagd.

## Veelgestelde vragen

**Q: Wat is GroupDocs.Viewer Java?**  
A: Een veelzijdige bibliotheek voor het renderen van documenten—incl. archieven—naar formaten zoals HTML, PDF en afbeeldingen.

**Q: Hoe kan ik een gratis proefversie van GroupDocs.Viewer verkrijgen?**  
A: Bezoek de [free trial link](https://releases.groupdocs.com/viewer/java/) om te downloaden en te testen.

**Q: Kan ik andere documenttypen dan archieven converteren?**  
A: Ja, de viewer ondersteunt PDF’s, Word, Excel en nog veel meer formaten.

**Q: Wat moet ik doen als het renderen traag is?**  
A: Verminder het aantal items per pagina, schakel streaming in, of verwerk archieven in kleinere batches.

**Q: Waar kan ik hulp of ondersteuning krijgen?**  
A: Neem contact op via het [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Is het mogelijk om CSS en afbeeldingen direct in de HTML te embedden?**  
A: Absoluut—gebruik `HtmlViewOptions.forEmbeddedResources` zoals getoond in de voorbeelden.

**Q: Hoe batch‑converteer ik een map met archieven?**  
A: Iterate over elk bestand met een `for`‑loop, waarbij je dezelfde `Viewer`‑ en `HtmlViewOptions`‑configuratie toepast voor elke iteratie.

## Resources

- **Documentatie:** Duik dieper in de functionaliteit met de [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑referentie:** Verken de volledige API op de [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Haal de nieuwste binaries op van de [download page](https://releases.groupdocs.com/viewer/java/).  
- **Aankoop en licenties:** Bekijk de opties op de [purchase page](https://purchase.groupdocs.com/buy).  
- **Ondersteuning en community:** Doe mee aan discussies op het [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Laatst bijgewerkt:** 2026-02-23  
**Getest met:** GroupDocs.Viewer 25.2  
**Auteur:** GroupDocs