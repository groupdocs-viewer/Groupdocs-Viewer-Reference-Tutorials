---
date: '2026-07-19'
description: Leer hoe u PST naar HTML en andere formaten zoals JPG, PNG, PDF kunt
  converteren met GroupDocs.Viewer for Java. Deze gids behandelt alle benodigde stappen
  en configuraties.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Converteer PST snel naar HTML met GroupDocs.Viewer for Java. Leer
  stap‑voor‑stap hoe u ook kunt exporteren naar JPG, PNG en PDF in een productieklare
  gids.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Converteer PST naar HTML met GroupDocs.Viewer for Java – Snelle e-mailexport
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Converteer PST naar HTML, JPG, PNG, PDF met GroupDocs.Viewer for Java
type: docs
url: /nl/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# PST converteren naar HTML, JPG, PNG, PDF met GroupDocs.Viewer voor Java

Bent u op zoek naar **pst naar html converteren** of andere formaten zoals JPG, PNG of PDF? Met de krachtige GroupDocs.Viewer for Java bibliotheek is deze taak eenvoudig en efficiënt. In deze tutorial leert u hoe u Outlook PST/OST‑bestanden kunt renderen naar web‑vriendelijke HTML, afbeeldingsbestanden of een enkele PDF, waardoor uw e‑mailarchieven gemakkelijk te delen en op te slaan zijn.

![PST/OST converteren naar HTML, JPG, PNG, PDF met GroupDocs.Viewer voor Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Wat u zult leren**
- Hoe GroupDocs.Viewer voor Java in een Maven‑project in te stellen.  
- Stap‑voor‑stap instructies om **java pst converteren** bestanden naar HTML, JPG, PNG en PDF.  
- Configuratietips voor optimale prestaties en veelvoorkomende valkuilen.

## Snelle antwoorden
- **Welke bibliotheek verwerkt PST-conversie?** GroupDocs.Viewer for Java.  
- **Kan ik PST direct naar PDF converteren?** Ja, met `PdfViewOptions`.  
- **Is een licentie vereist voor productie?** Een geldige GroupDocs‑licentie is nodig.  
- **Welke Java‑versie wordt ondersteund?** JDK 8 of hoger.  
- **Moet ik bijlagen handmatig extraheren?** Nee, de viewer rendert ze automatisch.

## Wat is GroupDocs.Viewer voor Java?
GroupDocs.Viewer voor Java is een server‑side API die meer dan 100 document‑ en e‑mailformaten laadt en deze rendert naar HTML, afbeelding of PDF‑output zonder externe software. Het verwerkt PST‑bestanden tot 2 GB terwijl het geheugengebruik onder 200 MB blijft.

## Hoe pst naar html converteren met GroupDocs.Viewer voor Java?

Laad het PST‑bestand met `new Viewer("source.pst")`, configureer `HtmlViewOptions` om naar een uitvoermap te wijzen, en roep `viewer.view(htmlOptions)` aan. De API extraheert elke e‑mail, behoudt opmaak, bijlagen en metadata, en schrijft een aparte HTML‑pagina per bericht — alles in één methode‑aanroep.

### Waarom kiezen voor GroupDocs.Viewer?
- **High‑fidelity rendering** – 99,9 % van de e‑mailinhoud (inclusief rich‑text‑lichamen, tabellen en ingesloten afbeeldingen) wordt nauwkeurig gereproduceerd.  
- **Meerdere uitvoerformaten** – Eén API‑aanroep kan HTML, JPG, PNG of PDF genereren, met meer dan 50 exportopties.  
- **Geen externe afhankelijkheden** – Geen Outlook, Exchange Server of converters van derden nodig; alles draait binnen uw Java‑runtime.

## Vereisten

- **GroupDocs.Viewer for Java** – versie 25.2 of hoger.  
- **Java Development Kit (JDK)** – 8 of nieuwer.  
- Maven voor afhankelijkheidsbeheer.  
- Basiskennis van Java en vertrouwdheid met Maven.

## GroupDocs.Viewer voor Java instellen

`Viewer` is de kernklasse in GroupDocs.Viewer voor Java die een document laadt en rendert naar het gekozen formaat. Voeg de GroupDocs‑repository en afhankelijkheid toe aan uw `pom.xml`:

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
- **Gratis proefversie** – verken alle functies zonder kosten.  
- **Tijdelijke licentie** – verleng de evaluatietijd indien nodig.  
- **Volledige licentie** – vereist voor productie‑implementaties.

### Basisinitialisatie

`Viewer`‑instanties zijn lichtgewicht; u kunt één instantie hergebruiken voor veel bestanden om de overhead van objectcreatie te minimaliseren.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Implementatie‑gids

De volgende secties leiden u door het renderen van PST/OST‑bestanden naar elk ondersteund formaat.

### PST/OST‑documenten renderen naar HTML

#### Stap 1: Uitvoermap instellen
Definieer een map waarin de HTML‑pagina's worden weggeschreven. GroupDocs maakt een sub‑map voor elke e‑mail om assets georganiseerd te houden.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Stap 2: Load‑opties configureren
`LoadOptions` stelt u in staat om wachtwoordafhandeling, time‑outs voor resource‑laden en selectieve paginarendering op te geven. Een time‑out van 30 seconden werkt goed voor de meeste serveromgevingen.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Stap 3: HTML‑viewopties definiëren
`HtmlViewOptions` specificeert de uitvoermap, resource‑afhandeling en optionele CSS‑instellingen voor HTML‑conversie.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Stap 4: Viewer initialiseren en HTML renderen
Maak een `Viewer`‑object, geef het PST‑bestandspad door, en roep `view` aan met de `HtmlViewOptions`. De API doorloopt automatisch alle berichten in de PST en genereert een nette HTML‑hiërarchie.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### PST/OST‑documenten renderen naar JPG

#### Stap 1: Uitvoermap instellen
Maak een speciale map voor JPG‑snapshots; elke e‑mail wordt één of meer afbeeldingsbestanden afhankelijk van de lengte.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Stap 2: Load‑opties configureren
Dezelfde `LoadOptions` die voor HTML werd gebruikt, kan hier opnieuw worden gebruikt, waardoor consistente wachtwoordafhandeling over formaten heen wordt gegarandeerd.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Stap 3: JPG‑viewopties definiëren
`JpgViewOptions` regelt beeldresolutie, kwaliteit en uitvoermap voor JPEG‑conversie.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Stap 4: Viewer initialiseren en JPG renderen
Gebruik `viewer.view(jpgOptions)` om hoogwaardige JPEG‑bestanden te genereren die klaar zijn voor web‑preview.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### PST/OST‑documenten renderen naar PNG

#### Stap 1: Uitvoermap instellen
PNG‑output is nuttig wanneer u verliesvrije kwaliteit nodig heeft voor archivering of OCR‑verwerking.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Stap 2: Load‑opties configureren
Geen extra instellingen zijn vereist naast de wachtwoord‑ en time‑out‑configuratie.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Stap 3: PNG‑viewopties definiëren
`PngViewOptions` stelt u in staat een transparante achtergrond en uitvoermap in te stellen voor verliesvrije PNG‑afbeeldingen.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Stap 4: Viewer initialiseren en PNG renderen
Instantieer `viewer.view(pngOptions)` om PNG‑snapshots van elke e‑mail te produceren.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST‑documenten renderen naar PDF

#### Stap 1: Uitvoermap instellen
Een enkel PDF‑bestand per PST vereenvoudigt juridische‑review‑workflows en vermindert opslag‑overhead.

CODE_BLOCK_PLACEHOLDER_14_END

#### Stap 2: Load‑opties configureren
Bij conversie naar PDF wilt u mogelijk `setEmbedFonts(true)` inschakelen om visuele getrouwheid op elk apparaat te garanderen.

CODE_BLOCK_PLACEHOLDER_15_END

#### Stap 3: PDF‑viewopties definiëren
`PdfViewOptions` laat u compressieniveau kiezen, lettertypen insluiten, en de uitvoernaam voor PDF‑conversie instellen.

CODE_BLOCK_PLACEHOLDER_16_END

#### Stap 4: Viewer initialiseren en PDF renderen
Maak `PdfViewOptions`, kies eventueel een compressieniveau, en roep `viewer.view(pdfOptions)` aan. De API voegt alle e‑mails samen tot één doorzoekbaar PDF‑document.

CODE_BLOCK_PLACEHOLDER_17_END

## Praktische toepassingen

- **E‑mailarchivering:** Zet grote PST‑archieven om in doorzoekbare HTML of PDF voor naleving.  
- **Documentbeheersystemen:** Sla geconverteerde bestanden op in systemen die alleen PDF, PNG of JPG accepteren.  
- **Samenwerkingsplatformen:** Deel geconverteerde e‑mails als afbeeldingen in Slack of Teams.  
- **Juridische beoordeling:** Voorzie rechtbanken van PDF‑versies van e‑mailbewijsmateriaal.  
- **Back‑upstrategieën:** Houd lichtgewicht PNG‑ of JPG‑snapshots van kritieke berichten.

## Prestatie‑overwegingen

- **Resourcebeheer:** Hergebruik `Viewer`‑instanties bij het verwerken van meerdere bestanden om overhead te verminderen.  
- **Geheugentuning:** Pas `loadOptions.setResourceLoadingTimeout` aan op basis van servercapaciteit.  
- **Asynchrone verwerking:** Schakel conversie uit naar achtergrondthreads voor responsieve UI’s.

## Veelgestelde vragen

**Q: Hoe kan ik **pst naar pdf** converteren met dezelfde codebasis?**  
A: Gebruik `PdfViewOptions` zoals getoond in de PDF‑rendersectie; de rest van de code blijft identiek.

**Q: Kan GroupDocs.Viewer versleutelde PST‑bestanden verwerken?**  
A: Ja, geef het wachtwoord door via `LoadOptions.setPassword("yourPassword")` vóór het renderen.

**Q: Wat is het verschil tussen **java pst converteren** naar PNG versus JPG?**  
A: PNG behoudt verliesvrije kwaliteit, ideaal voor screenshots, terwijl JPG kleinere bestandsgroottes biedt voor e‑mail‑previews.

**Q: Is er een manier om **pst**‑bestanden in bulk te converteren?**  
A: Omhul de renderlogica in een lus die over een map met PST‑bestanden iterereert; hergebruik dezelfde `Viewer`‑configuratie voor elk bestand.

**Q: Ondersteunt de API het converteren van PST‑bestanden groter dan 1 GB?**  
A: Ja, GroupDocs.Viewer streamt data en kan bestanden tot 2 GB verwerken zonder het volledige archief in het geheugen te laden.

## Conclusie

U heeft nu een volledige, productie‑klare gids om **pst naar html** te **converteren**, JPG, PNG en PDF te gebruiken met GroupDocs.Viewer voor Java. Door de bovenstaande stappen te volgen kunt u e‑mailconversie integreren in elke Java‑gebaseerde workflow, de toegankelijkheid verbeteren en voldoen aan compliance‑vereisten.

---

**Laatst bijgewerkt:** 2026-07-19  
**Getest met:** GroupDocs.Viewer for Java 25.2  
**Auteur:** GroupDocs

## Gerelateerde tutorials

- [NSF converteren naar PDF, HTML, JPG, PNG met GroupDocs.Viewer voor Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [odf html java converteren – ODF naar HTML, JPG, PNG, PDF met GroupDocs.Viewer voor Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Hoe DOCX naar HTML converteren met GroupDocs.Viewer voor Java: Een stap‑voor‑stap gids](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)