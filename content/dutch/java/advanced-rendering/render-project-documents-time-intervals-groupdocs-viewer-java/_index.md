---
date: '2026-03-29'
description: Leer hoe je een html‑weergave van mpp‑bestanden maakt met GroupDocs Viewer
  in Java, waarbij projectdocumenten per tijdsintervallen worden gerenderd met stap‑voor‑stap
  code.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Maak html-weergave mpp met GroupDocs Viewer (Java)
type: docs
url: /nl/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Hoe GroupDocs Viewer te gebruiken om projectdocumenten per tijdsintervallen te renderen in Java

In deze tutorial leer je hoe je **create html view mpp** met GroupDocs Viewer voor Java kunt maken, waardoor je alleen de delen van een Microsoft Project‑bestand kunt renderen die binnen een specifiek tijdsinterval vallen. We lopen door de Maven‑configuratie, code‑instellingen en praktijkvoorbeelden zodat je nauwkeurige tijdlijnweergaven direct in je applicaties kunt insluiten.

![Render projectdocumenten per tijdsintervallen met GroupDocs.Viewer voor Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Snelle antwoorden
- **Wat doet de functie?** Het rendert alleen het gedeelte van een Microsoft Project‑bestand dat tussen een start‑ en einddatum valt.  
- **Welk uitvoerformaat wordt gebruikt?** HTML met ingesloten resources, perfect voor webintegratie.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan ik het datumbereik tijdens runtime wijzigen?** Ja—pas de `setStartDate` en `setEndDate` waarden aan in de renderopties.  
- **Wordt dit ondersteund op alle Java‑versies?** Werkt met Java 8+ zolang je GroupDocs.Viewer 25.2 of nieuwer gebruikt.

## Hoe html view mpp te maken voor projectdocumenten
GroupDocs Viewer kan Microsoft Project‑bestanden (`.mpp`, `.mpt`) omzetten naar HTML‑pagina's. Door de start‑ en einddatums in de renderopties te configureren, beperk je de output tot het tijdssegment dat je nodig hebt, waardoor de bestandsgrootte afneemt en de laadtijd van pagina's versnelt.

## Wat betekent “How to Use GroupDocs” in deze context?
GroupDocs Viewer is een Java‑bibliotheek die meer dan 100 bestandsformaten converteert naar web‑vriendelijke weergaven. Wanneer je **how to use GroupDocs** voor projectbestanden gebruikt, krijg je de mogelijkheid om planningsgegevens te extraheren, visualiseren en delen zonder dat Microsoft Project aan de clientzijde nodig is.

## Waarom projectdocumenten renderen met tijdsintervallen?
- **Gerichte analyse:** Toon alleen de fase die je nodig hebt (bijv. Q3 2024).  
- **Prestaties:** Kleinere HTML‑output betekent snellere paginalading.  
- **Integratie:** Integreer tijdlijnweergaven in dashboards, rapportageportalen of aangepaste PM‑tools.  

## Vereisten
- **GroupDocs.Viewer for Java** versie 25.2 of hoger.  
- Java Development Kit (JDK) 8 of nieuwer.  
- Een IDE zoals IntelliJ IDEA of Eclipse.  
- Basiskennis van Maven.  

## GroupDocs.Viewer voor Java instellen

### Maven‑afhankelijkheid

Voeg de repository en afhankelijkheid toe aan je `pom.xml`:

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

1. **Gratis proefversie** – Download een proefversie van de [downloadpagina van GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Tijdelijke licentie** – Verkrijg een tijdelijke licentie voor uitgebreid testen via [deze link](https://purchase.groupdocs.com/temporary-license/).  
3. **Aankoop** – Voor onbeperkt gebruik in productie, koop een licentie op de [GroupDocs aankooppagina](https://purchase.groupdocs.com/buy).

### Basis Viewer‑initialisatie

De volgende codefragment toont hoe je een `Viewer`‑instantie maakt die naar een Microsoft Project‑bestand (`.mpp`) wijst:

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

Maak een map aan waarin de gegenereerde HTML‑pagina's worden opgeslagen:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Waarom?* Het georganiseerd houden van gerenderde bestanden maakt het makkelijker om ze vanaf een webserver te serveren of in een UI in te sluiten.

### 2. Initialiseer de Viewer met je projectbestand

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Waarom?* Het laden van het document bereidt de interne parser voor en maakt projectspecifieke metadata toegankelijk.

### 3. Haal weergave‑informatie op voor projectbestanden

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Waarom?* `ProjectManagementViewInfo` geeft je de start‑ en einddatums van de planning, die je later gebruikt om de render‑scope te beperken.

### 4. Configureer HTML‑renderopties (HTML genereren vanuit project)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Waarom?* Door `StartDate` en `EndDate` in te stellen, vertelt je GroupDocs om alleen **generate html view mpp** gegevens binnen dat venster te genereren.

### 5. Voer het renderproces uit

```java
viewer.view(viewOptions);
```

*Waarom?* Deze aanroep produceert een reeks zelfstandige HTML‑pagina's die het geselecteerde tijdssegment van je projectplanning weergeven.

## Veelvoorkomende valkuilen & probleemoplossing
- **Onjuiste bestandspaden** – Controleer dubbel of zowel het bron‑`.mpp`‑bestand als de uitvoermap bestaan.  
- **Niet‑ondersteund bestandstype** – Zorg ervoor dat het document een ondersteund Project‑formaat is (bijv. `.mpp`, `.mpt`).  
- **Licentiefouten** – Een proeflicentie kan renderlimieten opleggen; schakel over naar een volledige licentie voor onbeperkt gebruik.  

## Praktische toepassingen
1. **Projecttijdlijnanalyse** – Toon belanghebbenden alleen de huidige fase.  
2. **Geautomatiseerde rapportage** – Genereer tijdgebonden HTML‑rapporten voor wekelijkse statusupdates.  
3. **Integratie met dashboards** – Integreer de gerenderde pagina's in BI‑tools of aangepaste portals.  
4. **Archivering** – Bewaar een web‑vriendelijke snapshot van de projectplanning voor toekomstig gebruik.  

## Prestatie‑tips
- Gebruik de *embedded resources* optie om elke HTML‑pagina zelf‑bevat te houden, waardoor HTTP‑verzoeken worden verminderd.  
- Voor zeer grote projecten, overweeg om te renderen in kleinere datum‑chunks om het geheugenverbruik laag te houden.  
- Verwijder tijdelijke bestanden na het serveren om schijfruimte te besparen.  

## Conclusie
Je weet nu **how to use GroupDocs** Viewer om projectdocumenten binnen een specifiek tijdsinterval te renderen en **generate HTML from project** gegevens in Java te maken. Deze mogelijkheid stroomlijnt tijdlijnvisualisaties, verbetert de rapportage‑efficiëntie en integreert soepel met moderne webapplicaties.

### Volgende stappen
- Verken extra Viewer‑functies zoals watermerken, wachtwoordbeveiliging of aangepaste CSS‑styling.  
- Combineer deze render‑pipeline met een REST‑API om on‑demand tijdlijnweergaven te serveren.  

## Veelgestelde vragen

**Q: Welke bestandsformaten ondersteunt GroupDocs.Viewer?**  
A: GroupDocs.Viewer ondersteunt een breed scala aan formaten, waaronder Microsoft Project (MPP), PDF, Word, Excel, PowerPoint en nog veel meer.

**Q: Hoe begin ik met een gratis proefversie van GroupDocs.Viewer?**  
A: Je kunt de proefversie downloaden van [hier](https://releases.groupdocs.com/viewer/java/).

**Q: Kan ik documenten renderen zonder resources in te sluiten?**  
A: Ja, je kunt een andere HTML‑weergave‑optie kiezen die naar externe resources verwijst in plaats van ze in te sluiten.

**Q: Wat als mijn document te groot is om te renderen?**  
A: Overweeg het document op te splitsen in kleinere secties of alleen het benodigde datumbereik te renderen, zoals hierboven getoond.

**Q: Hoe ga ik om met renderfouten?**  
A: Controleer alle configuratie‑instellingen, zorg dat je een geldige licentie hebt, en raadpleeg de GroupDocs‑documentatie voor gedetailleerde foutcodes.

## Bronnen
- **Documentatie**: [GroupDocs Viewer Java Documentatie](https://docs.groupdocs.com/viewer/java/)
- **API‑referentie**: [GroupDocs API‑referentie](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Aankoop**: [Koop GroupDocs-licentie](https://purchase.groupdocs.com/buy)
- **Gratis proefversie**: [Probeer de gratis versie](https://releases.groupdocs.com/viewer/java/)
- **Tijdelijke licentie**: [Verkrijg een tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)
- **Ondersteuning**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs