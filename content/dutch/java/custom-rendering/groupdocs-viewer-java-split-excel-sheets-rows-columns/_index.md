---
date: '2026-06-15'
description: Leer hoe je Excel naar PDF kunt converteren met Java en Excel-bladen
  kunt splitsen op rijen en kolommen met GroupDocs Viewer. Inclusief installatie,
  code en best practices.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Excel naar PDF converteren met Java & Bladen splitsen op rijen en kolommen
type: docs
url: /nl/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel naar PDF Java converteren & Bladen splitsen op rijen en kolommen (Java)

Grote Excel-werkboeken bevatten vaak meer gegevens dan comfortabel op één scherm of afdrukpagina weergegeven kan worden. **convert excel to pdf java** is een veelvoorkomende eis wanneer je een statisch, deelbaar formaat nodig hebt, terwijl **splitsen van Excel-bladen op rijen en kolommen** de gegevens gemakkelijker maakt om te consumeren in web‑ of afdruklay‑outs. In deze gids lopen we beide taken door met **GroupDocs Viewer for Java**, laten we zien hoe je paginering configureert en geven we best‑practice tips voor prestaties en probleemoplossing.

![Excelbladen splitsen op rijen en kolommen met GroupDocs.Viewer voor Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Excelbladen splitsen op rijen en kolommen met GroupDocs.Viewer voor Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** GroupDocs Viewer for Java.  
- **Kan ik zowel op rijen als kolommen splitsen?** Ja – je kunt rijen‑per‑pagina en kolommen‑per‑pagina samen definiëren.  
- **Heb ik een licentie nodig?** Een proef‑ of tijdelijke licentie werkt voor ontwikkeling; een volledige licentie is vereist voor productie.  
- **Welke uitvoerformaten worden ondersteund?** HTML (ingesloten bronnen) wordt getoond; PDF kan met dezelfde opties worden gegenereerd.  
- **Is Maven vereist?** Maven is de aanbevolen manier om afhankelijkheden te beheren.  
- **Kan ik ook Excel naar PDF converteren?** Absoluut – schakel `HtmlViewOptions` over naar `PdfViewOptions` en hergebruik dezelfde pagineringsinstellingen.

## Wat is “How to Split Excel”?
Een Excel‑blad splitsen betekent een enkel werkblad verdelen over meerdere pagina’s of bestanden op basis van een vast aantal rijen, kolommen of beide. Deze techniek is handig wanneer je gepagineerde rapporten wilt maken, gegevens in webpagina’s wilt insluiten of afdrukbare secties wilt genereren zonder het volledige werkboek in één keer te laden.

## Waarom GroupDocs Viewer voor Java gebruiken?
GroupDocs Viewer verwerkt spreadsheets in één enkele doorgang en pagineert ze automatisch, waardoor handmatige berekeningen overbodig zijn. **Snelle weergave verwerkt een 250‑pagina‑XLSX‑werkboek in minder dan 2 seconden op een typische 2‑core server**, en **de bibliotheek ondersteunt meer dan 50 invoer‑ en uitvoerformaten**, waaronder XLS, XLSX, CSV, PDF en HTML. Hij draait op elk JVM‑compatibel platform — Windows, Linux, macOS, Docker‑containers of cloud‑gebaseerde serverless‑omgevingen — zodat je hem kunt integreren waar je Java‑applicatie ook leeft.

## Voorvereisten
- Java 17 of hoger geïnstalleerd.  
- Een IDE zoals IntelliJ IDEA of Eclipse.  
- Maven voor afhankelijkheidsbeheer.  
- Basiskennis van Java en vertrouwdheid met het verwerken van Excel‑bestanden.

### Vereiste bibliotheken, versies en afhankelijkheden
Voeg de GroupDocs‑repository en de viewer‑afhankelijkheid toe aan je `pom.xml`:

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
Vraag een gratis proefversie, tijdelijke licentie of koop een volledige licentie aan via [GroupDocs](https://purchase.groupdocs.com/buy).

## Hoe Excel naar PDF Java converteren?

De `Viewer`‑klasse is het kernonderdeel van GroupDocs Viewer dat een document laadt en rendermethoden biedt voor verschillende uitvoerformaten. `SpreadsheetOptions` stelt je in staat pagineringsinstellingen zoals rijen‑per‑pagina en kolommen‑per‑pagina voor spreadsheet‑rendering te regelen.

Laad je Excel‑bestand met `new Viewer("source.xlsx")`, configureer `SpreadsheetOptions` voor paginering en roep `viewer.view(pdfOptions, stream)` aan – die ene oproep converteert het werkboek naar een PDF terwijl de door jou ingestelde rij‑/kolomlimieten gerespecteerd worden. De conversie behoudt formules, afbeeldingen en celstijlen, waardoor een getrouwe PDF‑replica ontstaat die klaar is voor distributie.

## Hoe Excelbladen splitsen op rijen

Splitsen op rijen creëert een reeks HTML‑pagina’s, elk met een vast aantal rijen (bijv. 15). Deze aanpak is ideaal voor dashboards die een beperkt aantal records per weergave tonen. De viewer genereert afzonderlijke HTML‑bestanden zoals `page_0.html`, `page_1.html`, enz., elk met het opgegeven aantal rijen. Dit maakt het eenvoudig om alleen het benodigde gedeelte in een web‑interface te laden, waardoor bandbreedte en render‑tijd verminderen.

### Definitie‑anker
`Viewer` is de kernklasse van GroupDocs Viewer die een document laadt en het renderen naar het gekozen uitvoerformaat orkestreert.

### Stapsgewijze implementatie

#### Stap 1: Padinstellingen en Viewer initialiseren
Definieer eerst waar de gesplitste pagina’s moeten worden opgeslagen en maak een `Viewer`‑instantie voor het bron‑werkboek.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Stap 2: Rijen per pagina configureren
Geef de viewer aan hoeveel rijen elke pagina moet bevatten.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Stap 3: Document renderen
Render het werkboek ten slotte met de door jou gedefinieerde opties.

```java
viewer.view(viewOptions);
```

## Hoe Excelbladen splitsen op rijen en kolommen

Soms moet een enkele pagina een matrix van rijen **en** kolommen tonen (bijv. 15 rijen × 7 kolommen). Dit geeft volledige controle over de lay‑out van elke HTML‑pagina. De resulterende pagina’s tonen een rechthoekig blok cellen, bijvoorbeeld rijen 1‑15 en kolommen A‑G op de eerste pagina, rijen 16‑30 en kolommen H‑N op de volgende. Deze raster‑stijl paginering is nuttig voor het maken van afdrukbare rapporten die passen op standaard papierformaten.

### Definitie‑anker
`SpreadsheetOptions` configureert hoeveel rijen en kolommen op elke gegenereerde pagina verschijnen.

### Stapsgewijze implementatie

#### Stap 1: Padinstellingen en Viewer initialiseren
De opzet is gelijk aan het voorbeeld alleen‑rijen, alleen de bestandsnaam verandert.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Stap 2: Rijen en kolommen per pagina configureren
Specificeer beide dimensies om een raster‑stijl splitsing te creëren.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Stap 3: Document renderen
Render met dezelfde `view`‑aanroep.

```java
viewer.view(options);
```

## Praktische toepassingen
- **Generate Excel report Java**: Zet grote financiële modellen om in een reeks gepagineerde HTML‑rapporten.  
- **GroupDocs Viewer Excel**: Integreer gesplitste pagina’s direct in een webportaal voor interactieve gegevensverkenning.  
- **Render Excel HTML Java**: Serveer de gegenereerde HTML‑pagina’s via een servlet of Spring‑controller voor snelle client‑side weergave.  

## Prestatie‑overwegingen
- **Geheugengebruik** – Grote werkboeken kunnen aanzienlijke heap‑ruimte verbruiken; overweeg de JVM‑optie `-Xmx` te verhogen.  
- **Chunk‑grootte** – Kies rij‑/kolom‑aantallen die een balans bieden tussen paginagrootte en render‑snelheid.  
- **Versie‑updates** – Houd GroupDocs Viewer up‑to‑date om te profiteren van prestatie‑verbeteringen; de nieuwste 25.2‑release verbetert de rendersnelheid tot 30 % ten opzichte van 24.x.

## Veelvoorkomende problemen & foutopsporing
| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| `OutOfMemoryError` | Een zeer groot blad renderen met te veel rijen per pagina | Verminder `countRowsPerPage` of vergroot de JVM‑heap |
| Lege uitvoerbestanden | Onjuist bestandspad of ontbrekende schrijfrechten | Controleer of `outputDirectory` bestaat en schrijfbaar is |
| HTML‑bronnen worden niet geladen | `forEmbeddedResources` gebruiken maar bestanden vanaf een andere basis‑URL serveren | Serveer de volledige output‑map of schakel over naar `forExternalResources` |

## Veelgestelde vragen

**Q: Kan ik een PDF genereren in plaats van HTML?**  
A: Ja. Vervang `HtmlViewOptions` door `PdfViewOptions` en behoud dezelfde `SpreadsheetOptions`‑configuratie.

**Q: Is het mogelijk om te splitsen op basis van celinhoud in plaats van vaste rijen/kolommen?**  
A: Inhoudsgebaseerd splitsen is niet ingebouwd in GroupDocs Viewer, maar je kunt het werkboek vooraf verwerken met Apache POI om afzonderlijke bladen te maken voordat je rendert.

**Q: Ondersteunt GroupDocs Viewer oudere Excel‑formaten (XLS)?**  
A: Absoluut. De viewer verwerkt XLS, XLSX, CSV en andere spreadsheet‑formaten.

**Q: Hoe kan ik de gegenereerde HTML in een Spring MVC‑view insluiten?**  
A: Serveer de output‑map als statische bron en verwijs naar de gegenereerde `page_0.html`, `page_1.html`, enz. vanuit je Thymeleaf‑ of JSP‑templates.

**Q: Welke licentie heb ik nodig voor commerciële inzet?**  
A: Een volledige productie‑licentie van GroupDocs is vereist; proef‑licenties zijn alleen voor evaluatie.

## Bronnen
- **Documentatie**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API‑referentie**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Koop GroupDocs‑licentie**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Gratis proefversie**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Tijdelijke licentie verkrijgen**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Ondersteuningsforum**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-06-15  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs  

---

## Gerelateerde tutorials

- [Verborgen rijen en kolommen renderen in Java‑spreadsheets met GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Lege rijen overslaan bij renderen in Java met GroupDocs.Viewer: Een prestatie‑gids](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Uitgebreide gids: Excel 2003 XML converteren naar HTML/JPG/PNG/PDF met GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)