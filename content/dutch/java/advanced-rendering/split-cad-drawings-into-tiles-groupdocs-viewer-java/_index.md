---
date: '2026-04-01'
description: Leer hoe u CAD-tekeningen in tegels kunt splitsen met GroupDocs Viewer
  voor Java, waardoor de renderprestaties worden verbeterd en het verwerken van grote
  bestanden wordt vereenvoudigd.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Hoe CAD-tekeningen in tegels te splitsen met GroupDocs Viewer
type: docs
url: /nl/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Hoe CAD‑tekeningen in tegels te splitsen met GroupDocs Viewer

Als je je afvraagt **hoe CAD**‑bestanden in kleinere, beter hanteerbare stukken te splitsen, ben je hier aan het juiste adres. In deze tutorial lopen we de exacte stappen door die nodig zijn om grote CAD‑tekeningen in tegels te splitsen met **GroupDocs Viewer for Java**. Aan het einde heb je een kant‑klaar oplossing die de renderingssnelheid verbetert, het geheugenverbruik vermindert en het makkelijker maakt om tekeningen weer te geven in web‑ of mobiele applicaties.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Snelle antwoorden
- **Wat bereikt “splitsen van CAD”?** Het breekt een enorme tekening op in kleinere afbeeldingen (tegels) die sneller laden en minder geheugen verbruiken.  
- **Welk formaat wordt gebruikt voor de tegels?** PNG‑bestanden worden standaard gegenereerd, maar andere formaten worden ondersteund via Viewer‑opties.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een betaalde licentie is vereist voor productie.  
- **Kan ik de tegelgrootte wijzigen?** Ja – pas de berekeningen van `tileWidth` en `tileHeight` aan naar jouw behoeften.  
- **Is deze aanpak thread‑safe?** Het renderen van elke tegel in een eigen `Viewer`‑instantie met try‑with‑resources is veilig voor gelijktijdige uitvoering.

## Wat betekent “splitsen van CAD”?
Splitsen van CAD verwijst naar het verdelen van één, vaak enorme, CAD‑tekening in meerdere rechthoekige secties (tegels). Elke tegel wordt onafhankelijk gerenderd, waardoor je alleen de delen kunt laden die een gebruiker daadwerkelijk nodig heeft — perfect voor webkaarten, documentportalen en mobiele viewers.

## Waarom GroupDocs Viewer voor Java gebruiken?
GroupDocs Viewer biedt kant‑en‑klaar ondersteuning voor meer dan 100 bestandsformaten, waaronder DWG, DXF en DWF. De tile‑API stelt je in staat exacte coördinaten op te geven, zodat je precies het gebied kunt renderen dat je nodig hebt zonder eerst het hele bestand te verwerken. Dit bespaart CPU‑cycli, vermindert bandbreedte en levert een soepelere gebruikerservaring.

## Voorvereisten
- **Bibliotheken**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Elke recente Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse, of een andere Java‑compatibele IDE.  
- **Build‑tool**: Maven (andere build‑tools werken zolang de afhankelijkheid is toegevoegd).  

## GroupDocs.Viewer voor Java instellen
Voeg de GroupDocs‑repository en afhankelijkheid toe aan je `pom.xml`:

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
GroupDocs.Viewer biedt een gratis proeflicentie voor evaluatie:

- **Gratis proefversie**: Bezoek [GroupDocs Gratis Proefversie](https://releases.groupdocs.com/viewer/java/) om de bibliotheek te downloaden.  
- **Tijdelijke licentie**: Vraag aan op de [Pagina Tijdelijke Licentie](https://purchase.groupdocs.com/temporary-license/).  
- **Volledige licentie**: Koop een productie‑licentie op de [Aankooppagina](https://purchase.groupdocs.com/buy).

### Basisinitialisatie
Maak een eenvoudige `Viewer`‑instantie aan om te verifiëren dat de bibliotheek correct wordt geladen:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Stapsgewijze handleiding om CAD‑tekeningen in tegels te splitsen

### Stap 1: Definieer de uitvoermap
We slaan elke tegel op als een afzonderlijk PNG‑bestand. Het gebruik van een hulpfunctie houdt de padlogica overzichtelijk en herbruikbaar.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Stap 2: Configureer weergave‑opties
Stel het renderformaat in op PNG en geef de viewer door om niet elke pagina vooraf te laden (wat geheugen bespaart).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Stap 3: Bereken tegelafmetingen
Eerst verkrijgen we de oorspronkelijke breedte en hoogte van de tekening, vervolgens splitsen we deze in vier gelijke kwadranten.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Stap 4: Render en sla de tegels op
Voeg de berekende tegels toe aan de renderopties en laat de `Viewer` de PNG‑bestanden genereren.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Tips voor probleemoplossing
- **Build‑pad** – Zorg ervoor dat de GroupDocs‑JAR‑bestanden op het classpath staan.  
- **Machtigingen** – De uitvoermap moet beschrijfbaar zijn voor het Java‑proces.  
- **Uitzonderingen** – Als je `ViewerException` ziet, controleer dan dubbel of het DWG‑bestand niet corrupt is en of de juiste licentie is toegepast.

## Veelvoorkomende gebruikssituaties voor het splitsen van CAD‑tegels
1. **Web‑mapping** – Laad alleen het zichtbare gedeelte van een plattegrond terwijl een gebruiker pan/zoomt.  
2. **Documentbeheer** – Sla elke tegel afzonderlijk op voor snellere preview‑generatie.  
3. **Mobiel bekijken** – Verminder bandbreedte door alleen de tegels te downloaden die nodig zijn voor het huidige scherm.

## Prestatie‑overwegingen
- **Tegelgrootte** – Grotere tegels betekenen minder bestanden maar langzamere rendering; vind een balans op basis van je UI‑behoeften.  
- **Geheugenmonitoring** – Gebruik Java‑profileringstools (bijv. VisualVM) om het heap‑gebruik te observeren bij het verwerken van zeer grote tekeningen.  
- **Resource‑opschoning** – Het hierboven getoonde try‑with‑resources‑patroon maakt native resources automatisch vrij.

## Veelgestelde vragen

**V: Kan ik andere bestandstypen (PDF, afbeeldingen) in tegels splitsen met dezelfde aanpak?**  
A: Ja. GroupDocs Viewer ondersteunt veel formaten; je hoeft alleen de bijbehorende options‑klasse te gebruiken (bijv. `PdfViewOptions`).

**V: Hoe wijzig ik de kwaliteit van de uitvoerafbeelding?**  
A: Pas `viewOptions.setResolution(int dpi)` aan of stel compressie‑instellingen in op het `PngOptions`‑object.

**V: Mijn applicatie raakt zonder geheugen bij zeer grote DWG‑bestanden — wat kan ik doen?**  
A: Verklein de tegelafmetingen, vergroot de JVM‑heap (`-Xmx`), of render tegels sequentieel in afzonderlijke `Viewer`‑instanties.

**V: Is het mogelijk om tegels asynchroon te renderen?**  
A: Absoluut. Wikkel elke tegel‑renderaanroep in een `CompletableFuture` of gebruik een executor‑service om de werklast te paralleliseren.

**V: Heb ik een aparte licentie nodig voor elke tegel?**  
A: Nee. Eén geldige GroupDocs Viewer‑licentie dekt alle renderbewerkingen binnen je applicatie.

## Bronnen
- [Documentatie](https://docs.groupdocs.com/viewer/java/)
- [API‑referentie](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Koop een licentie](https://purchase.groupdocs.com/buy)
- [Gratis proefversie](https://releases.groupdocs.com/viewer/java/)
- [Tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)
- [Supportforum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-04-01  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs  

---