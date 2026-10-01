---
date: '2026-09-30'
description: Leer hoe je een pagina 90 graden kunt roteren in Java met GroupDocs Viewer,
  inclusief installatie, code en performance tips.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Roteer een pagina 90 graden in Java met GroupDocs Viewer. Stapsgewijze
  handleiding, performance tips en praktijkvoorbeelden voor ontwikkelaars.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Pagina 90 graden roteren met GroupDocs Viewer voor Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Pagina 90 graden roteren met GroupDocs Viewer voor Java
type: docs
url: /nl/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# Pagina 90 graden roteren met GroupDocs Viewer voor Java

If you need to **rotate page 90 degrees** in a document—whether it’s a PDF, Word file, or spreadsheet—doing it programmatically in Java saves time, removes manual errors, and lets you embed the operation into automated pipelines. In this advanced guide you’ll learn how to rotate the first page of any supported document using **GroupDocs Viewer for Java**, why this capability matters in real‑world projects, and how to keep the process lightweight and memory‑efficient.

![De eerste pagina van een document roteren met GroupDocs.Viewer voor Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Snelle antwoorden
- **Wat betekent “rotate page 90 degrees”?** Het draait de geselecteerde pagina met de klok mee een kwartslag.  
- **Welke bibliotheek verzorgt de rotatie?** GroupDocs Viewer voor Java biedt de `rotatePage`‑methode.  
- **Kan ik PDF‑pagina's roteren met Java?** Ja—gebruik dezelfde `rotatePage`‑aanroep; het werkt voor PDF, DOCX, XLSX en meer.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een betaalde licentie is vereist voor productie.  
- **Is de bewerking geheugenintensief?** Niet wanneer je de `Viewer`‑instantie snel sluit; zie de prestatietips hieronder.

## Wat is “rotate page 90 degrees”?
Rotating a page 90 degrees re‑orients the page from portrait to landscape (or vice‑versa) without changing the underlying content. This is handy for presentations, printing landscape‑only graphics, or correcting scanned documents that were captured sideways. The rotation is applied at render time, leaving the original file unchanged.

## Waarom pagina's programmatisch roteren met GroupDocs Viewer voor Java?
GroupDocs Viewer supports **50+ input and output formats**—including PDF, DOCX, PPTX, XLSX, and many image types—so you can render any document without external converters. The API is fluent, thread‑safe, and runs on any Java 8+ runtime, making it a reliable choice for enterprise‑grade automation that must handle dozens of file types consistently.

## Vereisten

- GroupDocs Viewer voor Java (nieuwste versie)
- JDK 8 of nieuwer
- Maven (of Gradle) voor afhankelijkheidsbeheer
- Een IDE zoals IntelliJ IDEA of Eclipse
- Basiskennis van Java I/O

## Installatie van GroupDocs.Viewer voor Java

Add the GroupDocs repository and dependency to your `pom.xml`. This snippet is unchanged from the original tutorial:

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
- **Gratis proefversie** – download van de GroupDocs‑site.  
- **Tijdelijke licentie** – vraag aan indien je een verlengde evaluatieperiode nodig hebt.  
- **Volledige licentie** – aanschaffen voor productie‑implementaties.

### Basis Viewer‑initialisatie
The `Viewer` class is the entry point that loads a document and exposes rendering and transformation methods. Keep the code exactly as shown:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Hoe PDF‑pagina roteren met Java en GroupDocs Viewer
Load the target file with `Viewer`, specify the page number, and call `rotatePage`. The method works for PDF, DOCX, PPTX, XLSX and any other format supported by the library. After rotation, you can render the document to a new PDF or stream it directly to the client, ensuring the original file remains untouched.

## Stapsgewijze implementatie: de eerste pagina 90 graden roteren

### 1. Importeer de benodigde pakketten
`PdfViewOptions` tells the Viewer to output a PDF file, while the `Rotation` enum defines the angle. Both classes belong to the `com.groupdocs.viewer.options` package.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definieer uitvoerlocaties en maak de Viewer aan
Replace the placeholder paths with your actual directories. The `Viewer` constructor accepts a `File` object that points to the source document.

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

### 3. Configureer PDF‑viewopties en pas de rotatie toe
The `rotatePage(int, Rotation)` method takes a **1‑based** page index and a `Rotation` enum value. In this example we use `Rotation.ON_90_DEGREE` to turn the first page clockwise.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Render het document
Calling `view` with the configured options writes the rotated PDF to the output folder.

```java
viewer.view(viewOptions);
```

#### Hoe het werkt
- **PdfViewOptions** stuurt de Viewer om een PDF‑outputbestand te genereren.  
- **rotatePage(int, Rotation)** roteert alleen de opgegeven pagina, terwijl alle andere pagina's ongewijzigd blijven.  
- De methode ondersteunt drie rotatie‑constanten: `ON_90_DEGREE`, `ON_180_DEGREE` en `ON_270_DEGREE`.

## Veelvoorkomende problemen en oplossingen

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| **FileNotFoundException** | Onjuist pad of ontbrekende map | Controleer of `YOUR_OUTPUT_DIRECTORY` en `YOUR_DOCUMENT_DIRECTORY` bestaan en leesbaar zijn. |
| **Unsupported file format** | Poging om een formaat te roteren dat niet door Viewer wordt ondersteund | Bekijk de pagina [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Gebruik van het verkeerde paginanummer (0‑gebaseerd) | Onthoud dat `rotatePage` **1‑gebaseerde** indexering gebruikt. |
| **Out‑of‑memory errors on large docs** | Veel grote bestanden renderen in één thread | Verwerk documenten opeenvolgend of gebruik een thread‑pool met beperkte gelijktijdigheid. |

## Praktische toepassingen

1. **Presentatie‑aanpassingen** – Converteer een staande dia on-the-fly naar liggend voor betere visuele impact.  
2. **Bulk‑documentcorrectie** – Automatiseer het corrigeren van gescande PDF’s die scheef zijn vastgelegd, waardoor uren handmatig werk worden bespaard.  
3. **Print‑klaar output** – Zorg ervoor dat liggende afbeeldingen correct afdrukken op staand papier zonder handmatige rotatie in de printerdriver.

## Prestatietips

- **Sluit bronnen snel** – Het `try‑with‑resources`‑blok verwijdert automatisch de `Viewer`, waardoor geheugen vrijkomt.  
- **Batchverwerking** – Hergebruik één `Viewer`‑instantie per thread om initialisatie‑overhead te verminderen.  
- **Monitor geheugen** – Voor documenten groter dan 100 MB, stream de output naar schijf in plaats van het hele bestand in het geheugen te houden; GroupDocs Viewer kan 200 MB‑bestanden verwerken met minder dan 250 MB RAM.

## Veelgestelde vragen

**V: Kan ik meerdere pagina's tegelijk roteren?**  
A: Ja—roep `rotatePage()` aan voor elk paginanummer dat je wilt roteren, of in een lus of door calls te chainen.

**V: Is er een manier om de rotatie ongedaan te maken na het renderen?**  
A: Niet direct. Je zou het document opnieuw moeten renderen zonder de rotatie‑opties.

**V: Welke bestandsformaten ondersteunen paginarotatie in GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, en vele andere formaten die in de officiële documentatie staan vermeld.

**V: Hoe kan ik pagina's in een batch van documenten automatisch roteren?**  
A: Plaats de rotatielogica in een lus die over een collectie bestands‑paden iterereert, en pas dezelfde `rotatePage`‑configuratie toe op elk bestand.

**V: Wat is de beste praktijk voor het afhandelen van fouten tijdens rotatie?**  
A: Plaats het gebruik van de Viewer in een `try‑catch`‑blok, log de details van de uitzondering, en ga eventueel door met het verwerken van het volgende bestand om te voorkomen dat één fout de hele batch stopt.

## Bronnen

- **Documentatie**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API‑referentie**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Aankoop**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Gratis proefversie**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Tijdelijke licentie**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Ondersteuning**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-09-30  
**Getest met:** GroupDocs Viewer 25.2 voor Java  
**Auteur:** GroupDocs

## Gerelateerde tutorials

- [Hoe specifieke PDF‑pagina's roteren met GroupDocs.Viewer voor Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Document laden vanaf URL in Java – GroupDocs.Viewer tutorial](/viewer/java/document-loading/)
- [GroupDocs Viewer Java Documentweergaven](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)