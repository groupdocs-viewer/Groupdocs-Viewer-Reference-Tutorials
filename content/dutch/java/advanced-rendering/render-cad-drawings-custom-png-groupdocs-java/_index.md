---
date: '2026-01-08'
description: Leer hoe u CAD‑tekeningen kunt renderen naar PNG‑afbeeldingen van hoge
  kwaliteit met aangepaste afmetingen en achtergrondkleuren met GroupDocs.Viewer voor
  Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Hoe CAD-tekeningen renderen als PNG met aangepaste grootte en achtergrondkleur
  met GroupDocs.Viewer voor Java
type: docs
url: /nl/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Hoe CAD-tekeningen renderen als PNG met aangepaste grootte en achtergrondkleur met GroupDocs.Viewer voor Java

Problemen met het converteren van uw CAD-tekeningen naar afbeeldingen van hoge kwaliteit terwijl u specifieke afmetingen en esthetiek behoudt? In deze tutorial laten we u zien **hoe CAD te renderen** bestanden als PNG's met aangepaste grootte en achtergrondkleur, zodat u precies het gewenste uiterlijk krijgt voor rapporten, presentaties of webvoorbeelden.

## Snelle antwoorden
- **Wat betekent “how to render CAD”?** Het verwijst naar het converteren van CAD‑bestanden (bijv. DWG) naar afbeeldingsformaten zoals PNG met behulp van code.  
- **Kan ik een aangepaste breedte instellen?** Ja – gebruik `CadOptions.forRenderingByWidth(int width)`.  
- **Hoe wijzig ik de achtergrond?** Roep `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` aan.  
- **Welke bibliotheek is vereist?** GroupDocs.Viewer voor Java (versie 25.2 of later).  
- **Heb ik een licentie nodig?** Een tijdelijke of aangeschafte licentie verwijdert de evaluatielimieten.

![CAD-tekeningen renderen als PNG met aangepaste grootte en achtergrondkleur met GroupDocs.Viewer voor Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Hoe CAD-tekeningen renderen – Overzicht
Deze sectie breidt het primaire doel uit: **hoe CAD** tekeningen naar PNG‑bestanden te renderen terwijl u grootte en achtergrond beheert. We lopen de volledige configuratie, code‑fragmenten en praktische tips door.

## Wat u zult leren
- GroupDocs.Viewer voor Java instellen in uw project  
- **DWG naar PNG converteren** met aangepaste afmetingen  
- **Achtergrondkleur PNG instellen** tijdens het renderen voor een gepolijste uitstraling  
- Praktijkvoorbeelden waarin aangepaste rendering waarde toevoegt  

## Vereisten

### Vereiste bibliotheken en afhankelijkheden
- Java Development Kit (JDK) 8+  
- Maven voor afhankelijkheidsbeheer  

### Omgevingsinstellingen
- IDE zoals IntelliJ IDEA of Eclipse  
- Basiskennis van Java  

### Kennisvereisten
- Vertrouwdheid met het omgaan met bestanden in Java  

## GroupDocs.Viewer voor Java instellen
Voeg de GroupDocs-repository en afhankelijkheid toe aan uw Maven `pom.xml`:

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

### Licentie verkrijgen
Verkrijg een tijdelijke of volledige licentie om evaluatiebeperkingen te verwijderen.

### Basisinitialisatie en configuratie
Maak een `Viewer`‑instantie die naar uw CAD‑bestand wijst:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Implementatiegids

### Functie 1: CAD-tekeningen renderen met aangepaste afbeeldingsgrootte en achtergrondkleur
#### Overzicht
Deze functie stelt u in staat **DWG naar PNG te converteren** terwijl u de afbeeldingsbreedte en achtergrondkleur opgeeft.

#### Stapsgewijze implementatie

##### Vereiste pakketten importeren
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Stel de uitvoermap en bestandsnaamindeling in
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Viewer initialiseren met aangepaste renderopties
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Uitleg van parameters**  
- `PngViewOptions` – definieert het uitvoerformaat en de naamgeving.  
- `forRenderingByWidth(int width)` – stelt de aangepaste afbeeldingsbreedte in.  
- `setBackgroundColor(Color color)` – **past achtergrondkleur toe** bij het renderen van de PNG.

#### Tips voor probleemoplossing
- Controleer of de uitvoermap bestaat; maak deze aan indien nodig.  
- Controleer het pad van het invoerbestand en de rechten.  

### Functie 2: Achtergrondkleur instellen in renderopties
#### Overzicht
Hier richten we ons op **achtergrondkleur PNG instellen** om de visuele consistentie te verbeteren.

#### Stapsgewijze implementatie

##### Vereiste pakketten importeren
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Renderopties configureren met achtergrondkleur
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Belangrijke configuratie‑opties**  
- Pas `forRenderingByWidth(int width)` aan voor verschillende afmetingen.  
- Gebruik een `Color`‑constante of een aangepaste `new Color(r,g,b)` voor op maat gemaakte achtergronden.  

## Praktische toepassingen

### 1. Technische documentatie
Aangepaste rendering zorgt ervoor dat technische tekeningen voldoen aan de bedrijfsstijlrichtlijnen.

### 2. Architecturale visualisatie
Presenteer blauwdrukken met een schone achtergrond die overeenkomt met presentaties.

### 3. Productie‑prototyping
Genereer nauwkeurige PNG‑bestanden voor snelle prototyping‑workflows.

### Integratiemogelijkheden
Combineer deze renderpipeline met documentbeheersystemen om de generatie van visuele assets te automatiseren.

## Prestatie‑overwegingen

### Prestaties optimaliseren
- **Batchverwerking:** Render meerdere CAD‑bestanden in een lus.  
- **Resourcebeheer:** Pas de JVM‑heap‑grootte aan voor grote tekeningen.

### Richtlijnen voor resourcegebruik
Monitor CPU en geheugen; geef `Viewer`‑instanties direct vrij.

### Best practices voor Java‑geheugenbeheer
- Gebruik try‑with‑resources (zoals getoond) om `Viewer` automatisch te sluiten.  
- Vermijd het langer vasthouden van grote `Path`‑objecten dan nodig.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oplossing |
|----------|-----------|
| **Uitvoermap niet gevonden** | Maak de map van tevoren aan of voeg `Files.createDirectories(outputDirectory);` toe |
| **Lege afbeelding** | Zorg ervoor dat `cadOptions.setBackgroundColor` wordt ingesteld na `forRenderingByWidth`. |
| **Out‑of‑memory fouten** | Verhoog de `-Xmx` JVM‑optie of verwerk bestanden in kleinere batches. |

## Veelgestelde vragen

**Q: Kan ik andere CAD‑formaten renderen naast DWG?**  
A: Ja, GroupDocs.Viewer ondersteunt DXF, DWF en verschillende andere CAD‑bestandstypen.

**Q: Hoe gebruik ik een aangepaste RGB‑kleur in plaats van een vooraf gedefinieerde constante?**  
A: Maak een nieuwe `Color`‑instantie, bijv. `new Color(123, 45, 67)` en geef deze door aan `setBackgroundColor`.

**Q: Is het mogelijk om alleen een specifieke layout of laag te renderen?**  
A: U kunt layout‑ of laagopties specificeren via `CadOptions` voordat u `viewer.view` aanroept.

**Q: Ondersteunt de bibliotheek transparante achtergronden?**  
A: Stel de achtergrondkleur in op `new Color(0,0,0,0)` voor volledige transparantie als het doel­formaat dit ondersteunt.

**Q: Welke versie van GroupDocs.Viewer is vereist?**  
A: De tutorial gebruikt versie 25.2, maar nieuwere versies behouden dezelfde API.

## Conclusie
U weet nu **hoe CAD** tekeningen te renderen naar PNG‑bestanden met aangepaste afmetingen en achtergrondkleuren met GroupDocs.Viewer voor Java. Pas deze technieken toe om professioneel uitziende visuele assets te creëren voor engineering, architectuur of productie‑workflows.

### Volgende stappen
- Experimenteer met verschillende afbeeldingsbreedtes en kleuren.  
- Integreer de rendercode in een batch‑verwerkingsservice.  
- Ontdek extra Viewer‑opties zoals PDF-conversie of multi‑page rendering.

---

**Laatst bijgewerkt:** 2026-01-08  
**Getest met:** GroupDocs.Viewer 25.2 voor Java  
**Auteur:** GroupDocs