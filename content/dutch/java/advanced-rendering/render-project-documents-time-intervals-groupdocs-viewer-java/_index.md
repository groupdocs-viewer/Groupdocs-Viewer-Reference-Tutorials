---
date: '2026-01-15'
description: Leer hoe u GroupDocs Viewer kunt gebruiken om HTML te genereren uit projectdocumenten
  binnen specifieke tijdsintervallen. Deze gids behandelt installatie, code en praktijkvoorbeelden.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Hoe GroupDocs Viewer te gebruiken om projectdocumenten per tijdsintervallen
  te renderen in Java
type: docs
url: /nl/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Hoe GroupDocs Viewer te gebruiken om projectdocumenten per tijdsintervallen te renderen in Java

Als je op zoek bent naar **how to use GroupDocs** om projectplanningen in een gericht tijdvenster te renderen, ben je hier aan het juiste adres. In deze tutorial lopen we het volledige proces door—van Maven‑configuratie tot het genereren van HTML uit projectdocumenten—zodat je nauwkeurige tijdlijnweergaven direct in je applicaties kunt insluiten.

![Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Snelle Antwoorden
- **Wat doet de functie?** Het rendert alleen het gedeelte van een Microsoft Project‑bestand dat tussen een start‑ en einddatum valt.  
- **Welk uitvoerformaat wordt gebruikt?** HTML met ingesloten resources, perfect voor webintegratie.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan ik het datumbereik tijdens runtime wijzigen?** Ja—pas de `setStartDate` en `setEndDate` waarden aan in de rendering‑opties.  
- **Wordt dit ondersteund op alle Java‑versies?** Werkt met Java 8+ zolang je GroupDocs.Viewer 25.2 of nieuwer gebruikt.

## Wat betekent “How to Use GroupDocs” in deze context?
GroupDocs Viewer is een Java‑bibliotheek die meer dan 100 bestandsformaten converteert naar web‑vriendelijke weergaven. Wanneer je **how to use GroupDocs** voor projectbestanden gebruikt, krijg je de mogelijkheid om planningsgegevens te extraheren, visualiseren en delen zonder dat Microsoft Project aan de clientzijde nodig is.

## Waarom projectdocumenten renderen met tijdsintervallen?
- **Gerichte analyse:** Toon alleen de fase waarin je geïnteresseerd bent (bijv. Q3 2024).  
- **Prestaties:** Een kleinere HTML‑output betekent snellere paginaladingen.  
- **Integratie:** Integreer tijdlijnweergaven in dashboards, rapportageportalen of aangepaste PM‑tools.  

## Vereisten

- **GroupDocs.Viewer for Java** versie 25.2 of hoger.  
- Java Development Kit (JDK) 8 of nieuwer.  
- Een IDE zoals IntelliJ IDEA of Eclipse.  
- Basiskennis van Maven.  

## GroupDocs.Viewer voor Java instellen

### Maven‑afhankelijkheid

Add the repository and dependency to your `pom.xml`:

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

### Stappen voor het verkrijgen van een licentie

1. **Free Trial** – Download een proefversie van de [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Verkrijg een tijdelijke licentie voor uitgebreid testen via [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Voor onbeperkt productiegebruik koop je een licentie op de [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Basis Viewer‑initialisatie

De volgende snippet toont hoe je een `Viewer`‑instance maakt die naar een Microsoft Project‑bestand (`.mpp`) wijst:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Stapsgewijze implementatie‑gids

### 1. Definieer de uitvoermap

Create a folder where the generated HTML pages will be saved:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Waarom?* Het georganiseerd houden van gerenderde bestanden maakt het makkelijker om ze vanaf een webserver te serveren of in een UI in te sluiten.

### 2. Initialiseert de Viewer met uw projectbestand

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Waarom?* Het laden van het document bereidt de interne parser voor en maakt project‑specifieke metadata toegankelijk.

### 3. Haal weergave‑informatie op voor projectbestanden

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Waarom?* `ProjectManagementViewInfo` geeft je de start‑ en einddatums van de planning, die je later gebruikt om de render‑scope te beperken.

### 4. Configureer HTML‑renderopties (Genereer HTML uit project)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Waarom?* Het instellen van `StartDate` en `EndDate` vertelt GroupDocs om **HTML uit project**‑gegevens alleen binnen dat venster te **genereren**.

### 5. Voer het renderproces uit

```java
viewer.view(viewOptions);
```

*Waarom?* Deze aanroep produceert een reeks zelfstandige HTML‑pagina's die het geselecteerde tijdssegment van je projectplanning weergeven.

## Veelvoorkomende valkuilen & probleemoplossing

- **Onjuiste bestands‑paden** – Controleer dubbel dat zowel het bron‑`.mpp`‑bestand als de uitvoermap bestaan.  
- **Niet‑ondersteund bestandstype** – Zorg ervoor dat het document een ondersteund Project‑formaat is (bijv. `.mpp`, `.mpt`).  
- **Licentiefouten** – Een proeflicentie kan render‑limieten opleggen; schakel over naar een volledige licentie voor onbeperkt gebruik.  

## Praktische toepassingen

1. **Projecttijdlijnanalyse** – Toon belanghebbenden alleen de huidige fase.  
2. **Geautomatiseerde rapportage** – Genereer tijd‑gebonden HTML‑rapporten voor wekelijkse statusupdates.  
3. **Integratie met dashboards** – Integreer de gerenderde pagina's in BI‑tools of aangepaste portals.  
4. **Archivering** – Bewaar een web‑vriendelijke snapshot van de planning van een project voor toekomstig gebruik.  

## Prestatietips

- Gebruik de *embedded resources* optie om elke HTML‑pagina zelf‑bevat te houden, waardoor HTTP‑verzoeken worden verminderd.  
- Overweeg bij zeer grote projecten om te renderen in kleinere datum‑chunks om het geheugenverbruik laag te houden.  
- Ruim tijdelijke bestanden op na het serveren om schijfruimte‑opblazen te voorkomen.  

## Conclusie

Je weet nu **how to use GroupDocs** Viewer om projectdocumenten binnen een specifiek tijdsinterval te renderen en **HTML uit project**‑gegevens te **genereren** in Java. Deze mogelijkheid stroomlijnt tijdlijnvisualisaties, verbetert de rapportage‑efficiëntie en integreert soepel met moderne webapplicaties.

### Volgende stappen
- Verken extra Viewer‑functies zoals watermerken, wachtwoordbeveiliging of aangepaste CSS‑styling.  
- Combineer deze render‑pipeline met een REST‑API om on‑demand tijdlijnweergaven te leveren.  

## Veelgestelde vragen

**Q: Welke bestandsformaten ondersteunt GroupDocs.Viewer?**  
A: GroupDocs.Viewer ondersteunt een breed scala aan formaten, waaronder Microsoft Project (MPP), PDF, Word, Excel, PowerPoint en nog veel meer.

**Q: Hoe begin ik met een gratis proefversie van GroupDocs.Viewer?**  
A: Je kunt de proefversie downloaden van [here](https://releases.groupdocs.com/viewer/java/).

**Q: Kan ik documenten renderen zonder resources in te sluiten?**  
A: Ja, je kunt een andere HTML‑weergave‑optie kiezen die externe resources referereert in plaats van ze in te sluiten.

**Q: Wat als mijn document te groot is om te renderen?**  
A: Overweeg het document op te splitsen in kleinere secties of alleen het benodigde datumbereik te renderen, zoals hierboven getoond.

**Q: Hoe ga ik om met render‑fouten?**  
A: Controleer alle configuratie‑instellingen, zorg dat je een geldige licentie hebt, en raadpleeg de GroupDocs‑documentatie voor gedetailleerde foutcodes.

## Resources
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-01-15  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs