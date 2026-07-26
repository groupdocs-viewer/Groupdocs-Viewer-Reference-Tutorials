---
date: '2026-03-29'
description: Leer hoe je een pagina 90 graden draait in Java met GroupDocs Viewer,
  inclusief installatie, code en prestatietips.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Pagina 90 graden roteren met GroupDocs Viewer voor Java
type: docs
url: /nl/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Pagina 90 graden roteren met GroupDocs Viewer voor Java

Wanneer je **pagina 90 graden moet roteren** in een document—of het nu een PDF, Word‑bestand of spreadsheet is—bespaart het programmatisch uitvoeren tijd en elimineert handmatige fouten. In deze geavanceerde gids lopen we de exacte stappen door om de eerste pagina van elk ondersteund document te roteren met **GroupDocs Viewer voor Java**. Aan het einde heb je een herbruikbare code‑fragment die je in je eigen projecten kunt gebruiken.  
We bespreken ook waarom het roteren van pagina's in Java belangrijk is, veelvoorkomende scenario's waarin deze techniek uitblinkt, en hoe je de bewerking lichtgewicht houdt.

![Eerste pagina van een document roteren met GroupDocs.Viewer voor Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Snelle antwoorden
- **Wat betekent “pagina 90 graden roteren”?** Het draait de geselecteerde pagina met de klok mee een kwart omwenteling.  
- **Welke bibliotheek verzorgt de rotatie?** GroupDocs Viewer voor Java biedt de `rotatePage`‑methode.  
- **Kan ik PDF‑pagina's roteren met Java?** Ja—gebruik dezelfde `rotatePage`‑aanroep; hij werkt voor PDF, DOCX, XLSX en meer.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een betaalde licentie is vereist voor productie.  
- **Is de bewerking geheugenintensief?** Niet wanneer je de `Viewer`‑instantie direct sluit; zie de prestatietips hieronder.

## Wat is “pagina 90 graden roteren”?
Het roteren van een pagina 90 graden herschikt de pagina van staand naar liggend (of omgekeerd) zonder de onderliggende inhoud te wijzigen. Dit is vooral handig voor presentaties, het afdrukken van uitsluitend liggende afbeeldingen, of het corrigeren van gescande documenten die scheef zijn vastgelegd.

## Waarom pagina's programmatisch roteren met GroupDocs Viewer voor Java?
GroupDocs Viewer abstraheert de complexiteit van het verwerken van tientallen bestandsformaten. Het stelt je in staat paginaniveau‑transformaties toe te passen—zoals rotatie—terwijl het oorspronkelijke bestand intact blijft. De API is vloeiend, thread‑veilig en werkt op elke Java 8+ runtime, waardoor het een betrouwbare keuze is voor automatisering op ondernemingsniveau.

## Vereisten

- **GroupDocs.Viewer voor Java** (nieuwste versie)
- **JDK 8** of nieuwer
- **Maven** (of Gradle) voor afhankelijkheidsbeheer
- Een IDE zoals IntelliJ IDEA of Eclipse
- Basiskennis van Java I/O

## GroupDocs.Viewer voor Java instellen

Voeg de GroupDocs‑repository en afhankelijkheid toe aan je `pom.xml`. Deze codefragment is ongewijzigd ten opzichte van de originele tutorial:

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
- **Tijdelijke licentie** – vraag aan als je een verlengde evaluatieperiode nodig hebt.  
- **Volledige licentie** – aanschaffen voor productie‑implementaties.

### Basis Viewer‑initialisatie
De volgende code toont de minimale manier om een `Viewer`‑instantie te maken. Houd het exact zoals weergegeven:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Hoe PDF‑pagina roteren met Java en GroupDocs Viewer
Hoewel de API met veel formaten werkt, is PDF het meest voorkomende gebruiksscenario voor paginarotatie. Dezelfde `rotatePage`‑methode wordt gebruikt, dus je hoeft alleen de viewer naar een PDF‑bestand te wijzen en het paginanummer op te geven.

## Stapsgewijze implementatie: Eerste pagina 90 graden roteren

### 1. Importeer de vereiste pakketten
Deze imports geven je toegang tot PDF‑renderopties en de rotatie‑enum.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definieer uitvoerlocaties en maak de Viewer
Vervang de tijdelijke paden door je eigen mappen.

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
De `rotatePage`‑methode neemt het paginanummer (1‑gebaseerd) en een `Rotation`‑enumwaarde.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Render het document
Roep tenslotte `view` aan om de geroteerde PDF te genereren.

```java
viewer.view(viewOptions);
```

#### Hoe het werkt
- **PdfViewOptions** vertelt de Viewer om een PDF‑bestand uit te voeren.  
- **rotatePage(int, Rotation)** roteert alleen de opgegeven pagina, de rest blijft onaangeroerd.  
- De methode ondersteunt `ON_90_DEGREE`, `ON_180_DEGREE` en `ON_270_DEGREE`.

## Veelvoorkomende problemen en oplossingen

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| **FileNotFoundException** | Onjuist pad of ontbrekende map | Controleer of `YOUR_OUTPUT_DIRECTORY` en `YOUR_DOCUMENT_DIRECTORY` bestaan en leesbaar zijn. |
| **Unsupported file format** | Proberen een formaat te roteren dat niet door Viewer wordt ondersteund | Controleer de [ondersteunde formaten van GroupDocs Viewer] pagina. |
| **No rotation visible** | Het verkeerde paginanummer gebruiken (0‑gebaseerd) | Onthoud dat `rotatePage` **1‑gebaseerde** indexering gebruikt. |
| **Out‑of‑memory errors on large docs** | Veel grote bestanden in één thread renderen | Verwerk documenten opeenvolgend of gebruik een thread‑pool met beperkte gelijktijdigheid. |

## Praktische toepassingen

1. **Aanpassingen van presentaties** – Converteer een staande dia direct naar liggend.  
2. **Bulkdocumentcorrectie** – Automatiseer het corrigeren van gescande PDF's die scheef zijn vastgelegd.  
3. **Print‑klaar output** – Zorg ervoor dat liggende afbeeldingen correct afdrukken op staand papier.

## Prestatietips

- **Sluit bronnen direct** – Het `try‑with‑resources`‑blok verwijdert automatisch de `Viewer`.  
- **Batchverwerking** – Bij het verwerken van veel bestanden, hergebruik één `Viewer`‑instantie per thread om overhead te verminderen.  
- **Monitor geheugen** – Voor documenten groter dan 100 MB, overweeg de output naar schijf te streamen in plaats van in het geheugen te houden.

## Veelgestelde vragen

**Q: Kan ik meerdere pagina's tegelijk roteren?**  
A: Ja—roep `rotatePage()` aan voor elk paginanummer dat je wilt roteren.

**Q: Is er een manier om de rotatie ongedaan te maken na het renderen?**  
A: Niet rechtstreeks. Je zou het document opnieuw moeten renderen zonder de rotatie‑opties.

**Q: Welke bestandsformaten ondersteunen paginarotatie in GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX en vele andere formaten die in de officiële documentatie staan vermeld.

**Q: Hoe kan ik pagina's in een batch documenten automatisch roteren?**  
A: Plaats de code in een lus die over een collectie bestands‑paden itereren, en pas dezelfde `rotatePage`‑logica toe op elk.

**Q: Wat is de beste praktijk voor het afhandelen van fouten tijdens rotatie?**  
A: Plaats het gebruik van de Viewer in een `try‑catch`‑blok, log de uitzondering, en ga eventueel door met het verwerken van het volgende bestand.

## Bronnen

- **Documentatie**: [GroupDocs Viewer Java Documentatie](https://docs.groupdocs.com/viewer/java/)  
- **API‑referentie**: [GroupDocs API Referentie](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Download GroupDocs Viewer voor Java](https://releases.groupdocs.com/viewer/java/)  
- **Aankoop**: [Koop een licentie](https://purchase.groupdocs.com/buy)  
- **Gratis proefversie**: [Probeer gratis](https://releases.groupdocs.com/viewer/java/)  
- **Tijdelijke licentie**: [Vraag tijdelijke licentie aan](https://purchase.groupdocs.com/temporary-license/)  
- **Ondersteuning**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** GroupDocs Viewer 25.2 voor Java  
**Auteur:** GroupDocs