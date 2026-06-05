---
date: '2026-06-05'
description: Leer hoe je Excel kunt converteren naar HTML, JPG, PNG en PDF met GroupDocs.Viewer
  Java. Deze stapsgewijze gids behandelt de installatie, renderopties en praktijkvoorbeelden.
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: Hoe Excel te converteren naar HTML, JPG, PNG en PDF met GroupDocs.Viewer Java
type: docs
url: /nl/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# Hoe Excel naar HTML, JPG, PNG en PDF converteren met GroupDocs.Viewer Java

Het converteren van Excel naar HTML is een veelvoorkomende eis wanneer je spreadsheet‑gegevens op het web wilt weergeven terwijl je rij‑ en kolom‑koppen behoudt. In deze tutorial leer je hoe GroupDocs.Viewer voor Java **convert excel to html** vereenvoudigt, evenals hoe je dezelfde werkmap rendert naar JPG-, PNG- en PDF‑formaten. We lopen de vereisten, bibliotheekconfiguratie en elk renderingsscenario door met duidelijke, productie‑klare code‑fragmenten.

## Snelle antwoorden
- **Kan GroupDocs.Viewer Excel naar meerdere formaten renderen?** Ja – HTML, JPG, PNG en PDF worden direct ondersteund.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een permanente licentie is vereist voor productie.  
- **Worden rij‑ en kolom‑koppen behouden?** Stel `setRenderHeadings(true)` in op de weergave‑opties om ze op te nemen.  
- **Welke Java‑versie is vereist?** Java 8 of hoger; de bibliotheek is compatibel met Java 11, 17 en later.  
- **Is de conversie snel voor grote werkmappen?** GroupDocs.Viewer kan 200‑pagina‑spreadsheets verwerken in minder dan een seconde op typische serverhardware.

## Wat betekent “convert excel to html”?
**Convert excel to html** betekent het omzetten van een Excel‑werkmap naar een web‑klaar HTML‑document terwijl de oorspronkelijke lay-out, formules en kopteksten behouden blijven. Dit maakt naadloze integratie van spreadsheets in webpagina’s of portals mogelijk zonder dat de eindgebruiker Excel geïnstalleerd hoeft te hebben.

## Waarom GroupDocs.Viewer Java gebruiken voor Excel‑rendering?
GroupDocs.Viewer Java ondersteunt **meer dan 50 invoer‑ en uitvoerformaten**, waaronder DOCX, XLSX, PPTX, HTML, JPG, PNG en PDF. Het verwerkt werkmappen van meerdere honderden pagina’s zonder het volledige bestand in het geheugen te laden, en levert conversiesnelheden tot **10 × sneller** dan veel open‑source alternatieven. De bibliotheek biedt ook fijnmazige controle over renderopties zoals de zichtbaarheid van kopteksten, paginagrootte en beeldkwaliteit.

## Vereisten

- **Java Development Kit (JDK) 8+** geïnstalleerd en geconfigureerd in je IDE (IntelliJ IDEA, Eclipse, enz.).
- **Maven** voor afhankelijkheidsbeheer.
- Basiskennis van Java‑syntaxis en Maven’s `pom.xml`.
- Een actieve **GroupDocs.Viewer Java**‑licentie (proef of permanent).

### Vereiste bibliotheken en afhankelijkheden
Voeg de GroupDocs.Viewer Java‑afhankelijkheid toe aan je `pom.xml`:

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

### Omgevingsconfiguratie
- Controleer dat `java -version` 1.8 of nieuwer retourneert.
- Open je favoriete IDE en maak een Maven‑project aan.

Laten we beginnen met de vereisten die nodig zijn voordat we aan de implementatie beginnen.

![Excel‑bestanden converteren naar HTML, JPG, PNG en PDF met GroupDocs.Viewer voor Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## GroupDocs.Viewer Java instellen

### Installatie‑informatie
Neem de hierboven getoonde Maven‑afhankelijkheid op in de `pom.xml` van je project. Na het uitvoeren van `mvn clean install` is de bibliotheek beschikbaar op je classpath.

### Stappen voor het verkrijgen van een licentie
1. **Gratis proefversie:** Download de proefversie van [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
2. **Tijdelijke licentie:** Verkrijg een tijdelijke licentie voor uitgebreid testen via [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
3. **Aankoop:** Verkrijg een volledige licentie voor productiegebruik op [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Basisinitialisatie
De `Viewer`‑klasse is het toegangspunt voor alle render‑operaties. Het initialiseren ervan is eenvoudig:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

Dit maakt een `Viewer`‑instantie aan die is gekoppeld aan een lokaal licentiebestand, klaar om Excel‑bestanden te verwerken.

## Implementatie‑gids

Hieronder behandelen we elk renderdoel. Voor elk formaat importeren we eerst **de vereiste klassen**, vervolgens **stellen we de uitvoermap in**, en tot slot **configureren we de weergave‑opties** met `setRenderHeadings(true)` om rij‑/kolom‑koppen te behouden.

### Spreadsheet renderen naar HTML
**Hoe converteer ik een Excel‑werkmap naar HTML met GroupDocs.Viewer Java?**  
Om een Excel‑werkmap naar HTML te converteren, laad je het bestand met de Viewer, maak je een HtmlViewOptions‑instantie, schakel je het renderen van kopteksten in, en roep je de view‑methode aan. Het proces schrijft elk werkblad naar afzonderlijke HTML‑bestanden, waarbij celopmaak, formules en de oorspronkelijke lay-out behouden blijven voor een nauwkeurige weergave op het web.

#### Stapsgewijze implementatie
**1. Vereiste bibliotheken importeren**  
HtmlViewOptions configureert hoe de werkmap naar HTML wordt gerenderd, met mogelijkheden voor aanpassing van kopteksten, stijlen en paginalay-out.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. Uitvoermap instellen**  
Geef een map op waar de gegenereerde HTML‑pagina’s naartoe worden geschreven.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. Viewer initialiseren en opties configureren**  
Maak een `Viewer`‑instantie, stel `setRenderHeadings(true)` in, en roep `view` aan.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Uitleg:** `HtmlViewOptions` regelt de HTML‑output. Het inschakelen van `setRenderHeadings(true)` zorgt ervoor dat de eerste rij en kolom (meestal kopteksten) verschijnen in de resulterende HTML, waardoor de gegevens direct begrijpelijk zijn.

### Spreadsheet renderen naar JPG
**Hoe kan ik een Excel‑blad renderen als een JPG‑afbeelding met inbegrepen kopteksten?**  
Het renderen van een Excel‑blad als JPG omvat het initialiseren van de Viewer met de werkmap, het construeren van een JpgViewOptions‑object, het instellen van renderHeadings op true, en het aanroepen van view. De bibliotheek rastert elke pagina op de opgegeven DPI, waardoor hoge‑resolutie JPG‑bestanden ontstaan die de visuele structuur en kopteksten van de spreadsheet behouden.

#### Stapsgewijze implementatie
**1. Vereiste bibliotheken importeren**  
JpgViewOptions definieert instellingen voor het renderen van werkbladen als JPG‑afbeeldingen, inclusief DPI, kwaliteit en zichtbaarheid van kopteksten.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. Uitvoermap instellen**  
Geef aan waar de JPG‑bestanden worden opgeslagen.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. Viewer initialiseren en opties configureren**  
Maak de viewer, stel het renderen van kopteksten in, en voer de conversie uit.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Uitleg:** `JpgViewOptions` stelt je in staat DPI en kwaliteit te regelen. Met `setRenderHeadings(true)` behouden de resulterende afbeeldingen de header‑rijen en -kolommen van de spreadsheet, wat essentieel is voor rapporten en presentaties.

### Spreadsheet renderen naar PNG
**Wat is het proces om Excel naar PNG te converteren terwijl kolom‑kopteksten behouden blijven?**  
Om PNG‑afbeeldingen uit een Excel‑bestand te produceren, gebruik je de Viewer om de werkmap te openen, maak je een PngViewOptions‑instantie, schakel je het renderen van kopteksten in, en voer je view uit. PNG‑output biedt verliesloze kwaliteit, behoudt alle celstijlen en header‑rijen, waardoor het ideaal is voor archivering of verdere beeldverwerking.

#### Stapsgewijze implementatie
**1. Vereiste bibliotheken importeren**  
PngViewOptions regelt het renderen van werkbladen naar PNG‑afbeeldingen, met verliesloze compressie en koptekstopties.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. Uitvoermap instellen**  
Kies een map voor de PNG‑output.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. Viewer initialiseren en opties configureren**  
Maak de viewer, schakel het renderen van kopteksten in, en roep `view` aan.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Uitleg:** Door `setRenderHeadings(true)` aan te roepen, bevatten de PNG‑bestanden de oorspronkelijke header‑rijen en -kolommen van de spreadsheet, waardoor context behouden blijft voor downstream‑gebruikers.

### Spreadsheet renderen naar PDF
**Hoe converteer ik een Excel‑bestand naar PDF met zichtbare rij‑ en kolom‑koppen?**  
Het converteren van Excel naar PDF is eenvoudig: maak een Viewer‑instantie met het bronbestand, configureer een PdfViewOptions‑object om kopteksten te renderen, en roep view aan. De resulterende PDF weerspiegelt de lay-out van de werkmap, inclusief rij‑ en kolom‑koppen, en ondersteunt vector‑graphics voor scherpe afdrukken en distributie.

#### Stapsgewijze implementatie
**1. Vereiste bibliotheken importeren**  
PdfViewOptions specificeert PDF‑generatieparameters zoals paginagrootte, marges en het renderen van kopteksten.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. Uitvoermap instellen**  
Geef de bestemmingsmap op voor het PDF‑document.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. Viewer initialiseren en opties configureren**  
Maak een `Viewer`, schakel het renderen van kopteksten in, en voer de conversie uit.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Uitleg:** Het instellen van `setRenderHeadings(true)` op `PdfViewOptions` garandeert dat de eerste rij/kolom in de uiteindelijke PDF verschijnen, waardoor het document klaar is voor afdrukken of archivering.

## Praktische toepassingen
Praktijksituaties waarin **convert excel to html**, **excel to pdf java**, of **convert spreadsheet to image** van onschatbare waarde zijn:

1. **Zakelijke rapportage:** Genereer HTML‑dashboards of PDF‑rapporten uit financiële modellen zonder handmatig kopiëren‑en‑plakken.  
2. **Datavisualisatie:** Integreer JPG/PNG‑momentopnames van spreadsheets in presentaties, zodat kopteksten de kijker direct context geven.  
3. **Documentarchivering:** Bewaar Excel‑werkmappen als PDF’s voor compliance, terwijl de oorspronkelijke lay-out en kopteksten behouden blijven.  
4. **Webportalen:** Lever HTML‑versies van spreadsheets direct in browsers, waardoor interactieve filtering met JavaScript mogelijk is.

## Veelgestelde vragen

**V: Kan ik met een wachtwoord beveiligde Excel‑bestanden converteren?**  
A: Ja. Geef het wachtwoord door aan de `Viewer`‑constructor, en de bibliotheek zal de werkmap ontcijferen vóór het renderen.

**V: Ondersteunt GroupDocs.Viewer macro‑ingeschakelde werkmappen (.xlsm)?**  
A: Absoluut. De viewer behandelt macro’s als data; ze worden genegeerd tijdens het renderen, wat een veilige conversie garandeert.

**V: Wat is de maximale ondersteunde bestandsgrootte?**  
A: De bibliotheek kan bestanden tot **2 GB** verwerken zonder het volledige document in het geheugen te laden, dankzij de streaming‑architectuur.

**V: Is het mogelijk om alleen een specifiek werkblad te renderen?**  
A: Ja. Gebruik `ViewOptions.setPageNumber(pageIndex)` om een enkel blad te targeten bij het genereren van HTML, JPG, PNG of PDF.

**V: Hoe regel ik de beeldkwaliteit voor JPG‑output?**  
A: Stel `JpgViewOptions.setQuality(90)` (waarde 0‑100) in om bestandsgrootte en visuele kwaliteit in balans te brengen.

## Conclusie
Je hebt nu een volledige, productie‑klare gids voor **convert excel to html**, **excel to pdf java**, en **convert spreadsheet to image** met GroupDocs.Viewer Java. Door de bovenstaande stappen te volgen kun je spreadsheet‑rendering integreren in elke Java‑backend, waardoor HTML‑rapporten, hoge‑resolutie‑afbeeldingen of archief‑PDF’s met automatisch bewaarde kopteksten worden geleverd.

---

**Laatst bijgewerkt:** 2026-06-05  
**Getest met:** GroupDocs.Viewer Java 23.12  
**Auteur:** GroupDocs

## Gerelateerde tutorials
- [Hoe DOCX naar HTML converteren met GroupDocs.Viewer voor Java: Een stap‑voor‑stap gids](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Responsieve HTML-rendering met GroupDocs.Viewer voor Java: Een uitgebreide gids](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – ODF naar HTML, JPG, PNG, PDF converteren met GroupDocs.Viewer voor Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)