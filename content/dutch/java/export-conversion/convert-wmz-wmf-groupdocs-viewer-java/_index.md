---
date: '2026-02-18'
description: Leer hoe u WMZ- en WMF-bestanden kunt converteren naar PDF, HTML, JPG
  en PNG met GroupDocs Viewer voor Java. Deze gids behandelt GroupDocs Viewer Java
  en Java-conversie van vectorafbeeldingen.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Hoe WMZ te converteren naar PDF en andere formaten met GroupDocs Viewer voor
  Java
type: docs
url: /nl/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Hoe WMZ naar PDF en andere formaten converteren met GroupDocs Viewer voor Java

Het converteren van WMZ (Web Metafile) en WMF (Windows Metafile) bestanden naar meer toegankelijke formaten — vooral **convert WMZ to PDF** — kan lastig zijn omdat deze vectorgrafiekformaten tekengereedschappen opslaan in plaats van pixelgegevens. Met **GroupDocs Viewer for Java** kun je WMZ/WMF‑documenten renderen naar HTML, JPG, PNG, **PDF** en andere populaire formaten met slechts een paar regels code.

![WMZ/WMF-documenten converteren met GroupDocs.Viewer voor Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

In deze tutorial leer je hoe je de bibliotheek instelt, WMZ/WMF‑bestanden rendert naar de gewenste output en veelvoorkomende valkuilen afhandelt. Aan het einde kun je **groupdocs viewer java** integreren in je Java‑applicaties om **java convert vector graphics** snel en betrouwbaar uit te voeren.

## Quick Answers
- **Welke formaten kunnen WMZ/WMF worden geconverteerd?** HTML, JPG, PNG en PDF worden volledig ondersteund.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie verwijdert evaluatielimieten.  
- **Welke Java‑versie is vereist?** Java 8 of later wordt aanbevolen.  
- **Kan ik alleen specifieke pagina's renderen?** Ja, je kunt paginabereiken opgeven in de weergave‑opties.  
- **Is geheugengebruik een zorg bij grote bestanden?** Gebruik try‑with‑resources en render alleen benodigde pagina's om het geheugen laag te houden.

## Wat betekent “convert WMZ to PDF”?

Het converteren van WMZ naar PDF betekent dat je het vector‑gebaseerde WMZ‑bestand neemt en het rastert (of de vectorgegevens behoudt) binnen een PDF‑container. PDF is universeel bekijkbaar, doorzoekbaar en afdrukbaar, waardoor het ideaal is voor het archiveren en delen van WMZ‑graphics.

## Waarom GroupDocs Viewer voor Java gebruiken om vectorgrafieken te converteren?
- **Hoge getrouwheid**: De bibliotheek behoudt de oorspronkelijke tekenkwaliteit, of je nu exporteert naar PDF of PNG.  
- **Geen externe afhankelijkheden**: Geen native Windows‑bibliotheken nodig; alles draait op elk platform met een JDK.  
- **Eenvoudige API**: Eén `Viewer`‑instantie en één `view`‑aanroep verwerken de volledige conversie.  
- **Schaalbaar**: Werkt even goed voor één‑pagina‑iconen en meer‑pagina‑technische tekeningen.

## Prerequisites

### Vereiste bibliotheken
- **GroupDocs.Viewer for Java** – de kern‑renderengine.  
- Java Development Kit (JDK) 8+.

### Omgevingsconfiguratie
- IDE zoals IntelliJ IDEA of Eclipse.  
- Maven voor afhankelijkheidsbeheer (of Gradle als je dat verkiest).

### Kennisvereisten
- Bekendheid met Java‑bestand‑I/O (`java.nio.file.Path`).  
- Basisbegrip van hoe document‑viewers inhoud renderen.

## GroupDocs.Viewer voor Java instellen

Voeg de repository en afhankelijkheid toe aan je `pom.xml`:

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

> **Licentietip:** Gebruik een gratis proefversie voor evaluatie, en pas daarna een tijdelijke of aangeschafte licentie toe om de volledige functionaliteit te ontgrendelen.

Zodra de afhankelijkheid is opgelost, kun je een `Viewer`‑instantie maken die voor elke conversiestap wordt hergebruikt.

## Implementatiegids

We doorlopen vier conversiescenario's: HTML, JPG, PNG en PDF. Elk voorbeeld volgt hetzelfde patroon — een uitvoermap definiëren, `Viewer` instantiëren met het bron‑WMZ‑bestand, de juiste weergave‑opties configureren en `view` aanroepen.

### WMZ/WMF renderen naar HTML

#### Overzicht
HTML‑output stelt je in staat de afbeelding direct in webpagina's in te sluiten, waarbij alle bronnen (afbeeldingen, CSS) in één enkel bestand zijn opgenomen.

**Stap 1: Definieer het pad van de uitvoermap**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Stap 2: Initialiseer Viewer en render naar HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF renderen naar JPG

#### Overzicht
JPG is een breed ondersteund rasterformaat, perfect voor snelle previews of e‑mailbijlagen.

**Stap 1: Definieer het pad van de uitvoermap**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Stap 2: Initialiseer Viewer en render naar JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF renderen naar PNG

#### Overzicht
PNG ondersteunt transparantie, waardoor het ideaal is voor afbeeldingen die moeten mengen met verschillende achtergronden.

**Stap 1: Definieer het pad van de uitvoermap**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Stap 2: Initialiseer Viewer en render naar PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF renderen naar PDF

#### Overzicht
PDF biedt een platform‑onafhankelijk, doorzoekbaar document dat de oorspronkelijke lay-out behoudt.

**Stap 1: Definieer het pad van de uitvoermap**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Stap 2: Initialiseer Viewer en render naar PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **OutOfMemoryError** bij grote WMZ‑bestanden | Viewer laadt het volledige document in het geheugen | Render één pagina per keer met `PageStreamViewOptions` of vergroot de JVM‑heap (`-Xmx`). |
| **Ontbrekende lettertypen** in PDF | Lettertype niet ingebed in bron‑WMZ | Installeer de vereiste lettertypen op de hostmachine of gebruik `FontSettings` om aangepaste lettertypen te leveren. |
| **Lege PNG‑output** | Onjuist uitvoerpad of onvoldoende schrijfrechten | Controleer of `outputDirectory` bestaat en de applicatie schrijfrechten heeft. |
| **HTML‑bronnen laden niet** | Gebruik van `forExternalResources` zonder bestanden te kopiëren | Gebruik `forEmbeddedResources` voor een zelf‑bevatend HTML‑bestand. |

## Veelgestelde vragen

**V: Kan ik WMF naar PNG converteren met dezelfde code?**  
A: Ja. Het PNG‑voorbeeld werkt voor zowel WMZ‑ als WMF‑bestanden; vervang gewoon `TestFiles.SAMPLE_WMZ` door je WMF‑bron.

**V: Is het mogelijk om alleen een deel van de pagina's te converteren?**  
A: Absoluut. Gebruik `PdfViewOptions` (of de overeenkomstige opties voor andere formaten) en roep `setPageNumbers(List<Integer>)` aan vóór het renderen.

**V: Heb ik een aparte licentie nodig voor elk uitvoerformaat?**  
A: Nee. Eén GroupDocs Viewer‑licentie dekt alle ondersteunde formaten, inclusief HTML, JPG, PNG en PDF.

**V: Hoe beïnvloedt “java convert vector graphics” de prestaties?**  
A: Vector‑naar‑raster conversie is CPU‑intensief. Voor grote batches, overweeg multi‑threading en het hergebruiken van één `Viewer`‑instantie over bestanden.

**V: Behoudt de PDF vectorkwaliteit, of wordt deze gerasterd?**  
A: Bij het converteren van WMZ/WMF naar PDF behoudt GroupDocs Viewer waar mogelijk de vectorinstructies, resulterend in een schaalbare PDF.

## Conclusie

Je hebt nu een volledige, productie‑klare gids om **convert WMZ to PDF** en andere veelvoorkomende formaten te gebruiken met **GroupDocs Viewer for Java**. Of je nu een webservice bouwt die afbeeldingen on‑the‑fly levert of een archiveringshulpmiddel dat documenten opslaat als PDF’s, de bovenstaande stappen helpen je snel op weg.

---

**Laatst bijgewerkt:** 2026-02-18  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs