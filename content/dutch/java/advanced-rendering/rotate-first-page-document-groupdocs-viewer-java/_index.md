---
date: '2026-01-18'
description: Leer hoe je een pagina 90 graden draait in Java met GroupDocs Viewer,
  inclusief installatie, code en prestatie‑tips.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Pagina 90 graden roteren met GroupDocs Viewer voor Java
type: docs
url: /nl/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Draai pagina 90 graden met GroupDocs Viewer voor Java

Wanneer je **pagina 90 graden moet draaien** in een document—of het nu een PDF, Word‑bestand of spreadsheet is—bespaart het programmatisch doen tijd en elimineert het handmatige fouten. In deze geavanceerde gids lopen we de exacte stappen door om de eerste pagina van elk ondersteund document te draaien met behulp van **GroupDocs Viewer for Java**. Aan het einde heb je een herbruikbare code‑fragment die je in je eigen projecten kunt gebruiken.

![Draai de eerste pagina van een document met GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Snelle antwoorden
- **Wat betekent “rotate page 90 degrees”?** Het draait de geselecteerde pagina met de klok mee een kwartslag.  
- **Welke bibliotheek verwerkt de rotatie?** GroupDocs Viewer for Java biedt de `rotatePage`‑methode.  
- **Kan ik PDF‑pagina's draaien met Java?** Ja—gebruik dezelfde `rotatePage`‑aanroep; deze werkt voor PDF, DOCX, XLSX en meer.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een betaalde licentie is vereist voor productie.  
- **Is de bewerking geheugenintensief?** Niet wanneer je de `Viewer`‑instantie direct sluit; zie de prestatietips hieronder.

## Wat is “rotate page 90 degrees”?
Het draaien van een pagina 90 graden herschikt de pagina van portret naar landschap (of omgekeerd) zonder de onderliggende inhoud te wijzigen. Dit is vooral handig voor presentaties, het afdrukken van uitsluitend landschaps‑grafieken, of het corrigeren van gescande documenten die scheef zijn vastgelegd.

## Waarom pagina's draaien met GroupDocs Viewer voor Java?
GroupDocs Viewer abstraheert de complexiteit van het verwerken van tientallen bestandsformaten. Het stelt je in staat paginaniveau‑transformaties toe te passen—zoals rotatie—terwijl het originele bestand ongewijzigd blijft. De API is vloeiend, thread‑veilig en werkt op elke Java 8+ runtime.

## Vereisten

- **GroupDocs.Viewer for Java** (nieuwste versie)
- **JDK 8** of nieuwer
- **Maven** (of Gradle) voor afhankelijkheidsbeheer
- Een IDE zoals IntelliJ IDEA of Eclipse
- Basiskennis van Java I/O

## GroupDocs.Viewer voor Java instellen

Voeg de GroupDocs‑repository en afhankelijkheid toe aan je `pom.xml`. Deze code‑fragment is ongewijzigd ten opzichte van de originele tutorial:

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
De volgende code toont de minimale manier om een `Viewer`‑instantie te maken. Houd het exact zoals weergegeven:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Stapsgewijze implementatie: Draai de eerste pagina 90 graden

### 1. Importeer de benodigde pakketten
Deze imports geven je toegang tot PDF‑renderopties en de rotatie‑enum.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definieer uitvoerlokaties en maak de Viewer
Vervang de placeholder‑paden door je eigen directories.

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
Roep tenslotte `view` aan om de gedraaide PDF te genereren.

```java
viewer.view(viewOptions);
```

#### Hoe het werkt
- **PdfViewOptions** vertelt de Viewer om een PDF‑bestand uit te voeren.  
- **rotatePage(int, Rotation)** draait alleen de opgegeven pagina, de rest blijft onaangeroerd.  
- De methode ondersteunt `ON_90_DEGREE`, `ON_180_DEGREE` en `ON_270_DEGREE`.

## Veelvoorkomende problemen en oplossingen

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| **FileNotFoundException** | Onjuist pad of ontbrekende map | Controleer of `YOUR_OUTPUT_DIRECTORY` en `YOUR_DOCUMENT_DIRECTORY` bestaan en leesbaar zijn. |
| **Unsupported file format** | Proberen een formaat te draaien dat niet door Viewer wordt ondersteund | Controleer de [GroupDocs Viewer supported formats] pagina. |
| **No rotation visible** | Het verkeerde paginanummer gebruiken (0‑gebaseerd) | Onthoud dat `rotatePage` **1‑gebaseerde** indexering gebruikt. |
| **Out‑of‑memory errors on large docs** | Veel grote bestanden renderen in één thread | Verwerk documenten opeenvolgend of gebruik een thread‑pool met beperkte gelijktijdigheid. |

## Praktische toepassingen

1. **Aanpassingen van presentaties** – Converteer een portret‑dia naar landschap in één keer.  
2. **Bulk‑documentcorrectie** – Automatiseer het corrigeren van gescande PDF’s die scheef zijn vastgelegd.  
3. **Print‑klare output** – Zorg ervoor dat landschaps‑grafieken correct afdrukken op portret‑georiënteerd papier.

## Prestatietips

- **Sluit bronnen direct** – Het `try‑with‑resources`‑blok verwijdert automatisch de `Viewer`.  
- **Batchverwerking** – Bij het verwerken van veel bestanden, hergebruik één `Viewer`‑instantie per thread om overhead te verminderen.  
- **Monitor geheugen** – Voor documenten groter dan 100 MB, overweeg de output naar schijf te streamen in plaats van in het geheugen te houden.

## Veelgestelde vragen

**Q: Kan ik meerdere pagina's tegelijk draaien?**  
A: Ja—roep `rotatePage()` aan voor elk paginanummer dat je wilt draaien.

**Q: Is er een manier om de rotatie ongedaan te maken na het renderen?**  
A: Niet direct. Je zou het document opnieuw moeten renderen zonder de rotatie‑opties.

**Q: Welke bestandsformaten ondersteunen paginadraaien in GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX en vele andere formaten die in de officiële documentatie staan vermeld.

**Q: Hoe kan ik pagina's in een batch documenten automatisch draaien?**  
A: Plaats de code in een lus die over een collectie bestands‑paden iterereert, en pas dezelfde `rotatePage`‑logica toe op elk.

**Q: Wat is de beste praktijk voor het afhandelen van fouten tijdens het draaien?**  
A: Plaats het gebruik van de Viewer in een `try‑catch`‑blok, log de uitzondering, en ga eventueel door met het verwerken van het volgende bestand.

## Bronnen

- **Documentatie**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API‑referentie**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Aankoop**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Gratis proefversie**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Tijdelijke licentie**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Ondersteuning**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

**Laatst bijgewerkt:** 2026-01-18  
**Getest met:** GroupDocs Viewer 25.2 for Java  
**Auteur:** GroupDocs