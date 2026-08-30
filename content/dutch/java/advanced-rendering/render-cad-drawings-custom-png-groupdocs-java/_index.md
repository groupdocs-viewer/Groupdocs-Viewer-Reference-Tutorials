---
date: '2026-08-30'
description: Leer hoe je DWG naar PNG kunt converteren, de achtergrondkleur in Java
  kunt instellen en de afbeeldingsgrootte kunt aanpassen met GroupDocs.Viewer for
  Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Converteer DWG naar PNG met GroupDocs.Viewer for Java terwijl je een
  aangepaste afbeeldingsbreedte en achtergrondkleur instelt. Deze gids biedt stapsgewijze
  installatie, code‑fragmenten en tips voor probleemoplossing.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: DWG naar PNG converteren met aangepaste grootte, achtergrondkleur in Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Hoe DWG naar PNG te converteren met aangepaste grootte & achtergrondkleur met
  GroupDocs.Viewer for Java
type: docs
url: /nl/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Hoe DWG naar PNG te converteren met aangepaste grootte en achtergrondkleur met GroupDocs.Viewer voor Java

In deze tutorial leer je **hoe je DWG naar PNG kunt converteren** terwijl je de afmetingen en achtergrondkleur van de uitvoer beheerst, met GroupDocs.Viewer voor Java. Of je nu CAD‑tekeningen in een rapport wilt insluiten, miniaturen voor een webportaal wilt genereren, of batch‑rendering wilt automatiseren, de onderstaande stappen geven je volledige controle over het visuele uiterlijk van elk PNG‑bestand.

## Snelle antwoorden
- **Wat betekent “convert DWG to PNG”?** Het is het proces waarbij een DWG CAD‑bestand via code wordt omgezet naar een PNG‑afbeelding, waarbij vector‑details behouden blijven als rasterpixels.  
- **Kan ik een aangepaste breedte instellen?** Ja – roep `CadOptions.forRenderingByWidth(int width)` aan om de exacte pixelbreedte te definiëren die je nodig hebt.  
- **Hoe wijzig ik de achtergrondkleur?** Gebruik `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` vóór het renderen.  
- **Welke bibliotheek is vereist?** GroupDocs.Viewer voor Java (versie 25.2 of nieuwer).  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie verwijdert evaluatielimieten en maakt onbeperkt renderen mogelijk.

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Wat is GroupDocs.Viewer voor Java?
GroupDocs.Viewer voor Java is een server‑side API die meer dan 150 bestandsformaten—waaronder CAD‑bestanden—rendert naar afbeeldingen, PDF‑bestanden of HTML. Het werkt zonder dat er externe software zoals AutoCAD nodig is, waardoor het ideaal is voor geautomatiseerde pipelines.

## Hoe DWG naar PNG te converteren met aangepaste grootte en achtergrondkleur?
Laad het DWG‑bestand met een `Viewer`‑instantie, configureer `CadOptions` voor de gewenste breedte en achtergrond, en roep vervolgens `viewer.view` aan met `PngViewOptions`. Deze drie‑stappen‑stroom behandelt bestands‑I/O, rendering en bestandsnaamgeving in één geheugen‑efficiënte bewerking.

Viewer is de primaire klasse die een document laadt en rendering uitvoert.  
CadOptions configureert CAD‑specifieke instellingen zoals afbeeldingsbreedte en achtergrondkleur.  
PngViewOptions definieert het PNG‑uitvoerformaat en het naamgevingspatroon voor de gerenderde pagina's.

Je kunt nu elke DWG‑tekening renderen naar een PNG met precies de breedte die je opgeeft, en je kunt elke effen kleur (of transparante) achtergrond kiezen die past bij je merk of UI‑thema.

## Waarom een aangepaste achtergrondkleur instellen?
Het instellen van een achtergrondkleur zorgt ervoor dat de gerenderde PNG naadloos opgaat in omliggende UI‑elementen, ongewenste witte marges voorkomt, en tekeningsdetails kan accentueren die anders verloren zouden gaan op een standaard wit canvas. GroupDocs.Viewer ondersteunt elke `java.awt.Color`, inclusief aangepaste RGB‑waarden, waardoor je pixel‑perfecte controle hebt.

java.awt.Color vertegenwoordigt een kleurwaarde die wordt gebruikt voor het renderen van achtergronden.

## Voorvereisten

- **Java Development Kit (JDK) 8+** – de API richt zich op Java 8 en nieuwer.  
- **Maven** – voor afhankelijkheidsbeheer.  
- **IDE** – IntelliJ IDEA, Eclipse, of elke editor die je verkiest.  
- **Basiskennis van Java‑bestandsafhandeling** – om bron‑DWG‑bestanden te lezen en PNG‑uitvoer te schrijven.

## GroupDocs.Viewer voor Java instellen
Voeg de GroupDocs‑repository en de Viewer‑afhankelijkheid toe aan je Maven `pom.xml`:

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
Verkrijg een tijdelijke of volledige licentiesleutel via het GroupDocs‑portaal en plaats het `license.lic`‑bestand in de resources‑map van je project. Dit verwijdert de 20‑pagina evaluatielimiet en ontgrendelt rendering met volledige resolutie.

### Basisinitialisatie en configuratie
Maak een `Viewer`‑instantie die wijst naar de map met je DWG‑bestanden:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Functie 1: CAD‑tekeningen renderen met aangepaste afbeeldingsgrootte en achtergrondkleur

### Hoe de CAD‑achtergrondkleur te wijzigen
Om de CAD‑achtergrondkleur te wijzigen, configureer je het CadOptions‑object vóór het renderen. Stel de gewenste breedte in met `forRenderingByWidth` en pas de nieuwe achtergrond toe met `setBackgroundColor`. De viewer genereert vervolgens PNG‑afbeeldingen die de opgegeven kleur weergeven, waardoor een consistente visuele stijl over alle uitvoerbestanden wordt gegarandeerd.

#### Stapsgewijze implementatie

##### Vereiste pakketten importeren
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Stel de uitvoermap en bestands‑padformaat in
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Initialiseer viewer met aangepaste renderopties
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
- `PngViewOptions` – definieert het PNG‑uitvoerformaat en het naamgevingspatroon.  
- `forRenderingByWidth(int width)` – dwingt de renderer om een afbeelding te produceren waarvan de breedte overeenkomt met de opgegeven pixelwaarde; de hoogte wordt proportioneel geschaald.  
- `setBackgroundColor(Color color)` – overschrijft het standaard witte canvas met de kleur die je kiest, waardoor de visuele consistentie over gegenereerde assets verbetert.

#### Tips voor probleemoplossing
- Zorg ervoor dat de uitvoermap bestaat; gebruik `Files.createDirectories(outputDir)` als deze niet bestaat.  
- Controleer of het pad naar het invoerbestand correct is en dat de applicatie leesrechten heeft.  

## Functie 2: achtergrondkleur instellen in renderopties

### Hoe PNG‑achtergrondkleur in te stellen
Het instellen van de PNG‑achtergrondkleur houdt in dat je een Color‑instantie maakt en deze toewijst aan de CadOptions vóór het renderen. Dit zorgt ervoor dat elke gegenereerde PNG de opgegeven achtergrond gebruikt, passend bij je merkrichtlijnen of UI‑thema. Je kunt vooraf gedefinieerde constanten gebruiken of aangepaste RGB‑waarden definiëren voor nauwkeurige controle.

java.awt.Color vertegenwoordigt een kleurwaarde die wordt gebruikt voor het renderen van achtergronden.

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
- Pas `forRenderingByWidth(int width)` aan voor verschillende afmetingen, zoals 800 px voor web‑miniaturen of 1920 px voor hoge‑resolutie afdrukken.  
- Gebruik elke vooraf gedefinieerde `Color`‑constante (bijv. `Color.LIGHT_GRAY`) of maak een aangepaste instantie met `new Color(r, g, b)` voor precieze branding.  

## Praktische toepassingen

### 1. Technische documentatie
Aangepaste rendering zorgt ervoor dat elke tekening voldoet aan de stijlgids van het bedrijf, waardoor handmatige beeldbewerking na export wordt geëlimineerd.

### 2. Architecturale visualisatie
Presenteer blauwdrukken met een achtergrond die overeenkomt met presentatieslides of klantgerichte portals, waardoor de visuele samenhang verbetert.

### 3. Productie‑prototyping
Genereer PNG‑bestanden voor snelle prototyping‑workflows waarbij downstream‑tools een specifieke afbeeldingsgrootte en achtergrond verwachten.

### Integratiemogelijkheden
Combineer deze render‑pipeline met een document‑managementsysteem (bijv. SharePoint) om automatisch preview‑afbeeldingen te genereren telkens wanneer een DWG‑bestand wordt geüpload.

## Prestatie‑overwegingen

### Prestaties optimaliseren
- **Batchverwerking:** Loop door een map met DWG‑bestanden en render elk bestand opeenvolgend om de opwarmkosten van de JVM te amortiseren.  
- **Resource‑beheer:** Voor grote tekeningen (500+ pagina's) vergroot je de JVM‑heap (`-Xmx2g`) of verwerk je bestanden in kleinere batches om out‑of‑memory‑fouten te voorkomen.

### Richtlijnen voor resource‑gebruik
Monitor CPU‑ en geheugen‑gebruik met tools zoals VisualVM; maak `Viewer`‑instanties snel vrij met try‑with‑resources.

### Best practices voor Java‑geheugenbeheer
- Gebruik try‑with‑resources (zoals getoond) om `Viewer` automatisch te sluiten.  
- Vermijd het behouden van grote `Path`‑objecten langer dan nodig.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oplossing |
|----------|-----------|
| Uitvoermap niet gevonden | Maak de map van tevoren aan of voeg `Files.createDirectories(outputDirectory);` toe. |
| Lege afbeelding | Zorg ervoor dat `cadOptions.setBackgroundColor` wordt aangeroepen na `forRenderingByWidth`. |
| Out‑of‑memory‑fouten | Verhoog de `-Xmx` JVM‑optie of verwerk bestanden in kleinere batches. |

## Veelgestelde vragen

**Q: Kan ik andere CAD‑formaten renderen naast DWG?**  
A: Ja, GroupDocs.Viewer ondersteunt DXF, DWF en verschillende andere CAD‑formaten.

**Q: Hoe gebruik ik een aangepaste RGB‑kleur in plaats van een vooraf gedefinieerde constante?**  
A: Maak een nieuwe `Color` aan met `new Color(123, 45, 67)` en geef deze door aan `setBackgroundColor`.

**Q: Is het mogelijk om alleen een specifieke layout of laag te renderen?**  
A: Je kunt layout‑ of laagopties specificeren via `CadOptions` vóór het aanroepen van `viewer.view`.

**Q: Ondersteunt de bibliotheek transparante achtergronden?**  
A: Stel de achtergrondkleur in op `new Color(0,0,0,0)` voor volledige transparantie als het uitvoerformaat dit ondersteunt.

**Q: Welke versie van GroupDocs.Viewer is vereist?**  
A: De tutorial gebruikt versie 25.2, maar nieuwere releases behouden dezelfde API‑structuur.

---

**Laatst bijgewerkt:** 2026-08-30  
**Getest met:** GroupDocs.Viewer 25.2 voor Java  
**Auteur:** GroupDocs

## Gerelateerde tutorials

- [groupdocs viewer dwg – Hoe specifieke CAD‑tekeningen te renderen in Java met GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render CAD Layers Java met GroupDocs.Viewer – Een volledige gids](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Hoe pdf naar html te converteren en de beeldkwaliteit te optimaliseren in Java met GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)