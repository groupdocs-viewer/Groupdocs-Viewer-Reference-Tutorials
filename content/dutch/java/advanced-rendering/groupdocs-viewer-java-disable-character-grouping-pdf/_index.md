---
date: '2026-03-22'
description: Leer hoe je HTML uit PDF kunt genereren en karaktergroepering kunt uitschakelen
  met GroupDocs Viewer voor Java voor een nauwkeurige weergave van tekst.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: HTML genereren uit PDF & Groeperen uitschakelen – GroupDocs Java
type: docs
url: /nl/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# HTML genereren vanuit PDF en Groeperen uitschakelen met GroupDocs Viewer voor Java

In veel projecten moet je **HTML genereren vanuit PDF** terwijl je elk glyph precies op de juiste plaats houdt. Dit is vooral het geval bij complexe scripts, oude talen of juridische documenten waarbij één verkeerd geplaatst teken de betekenis kan veranderen. In deze tutorial lopen we je stap voor stap door het volledige proces van het renderen van PDF's naar HTML met GroupDocs Viewer voor Java en laten we je zien **hoe je groeperen uitschakelt** zodat elk teken wordt behandeld als een onafhankelijk element.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Snelle Antwoorden
- **Wat doet “disable grouping”?** Het dwingt de renderer elk teken als een onafhankelijk element te behandelen, waardoor de exacte lay-out behouden blijft.  
- **Welke API-optie regelt dit?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Heb ik een licentie nodig?** Een proefversie werkt voor testen, maar een volledige licentie is vereist voor productie.  
- **Kan ik tegelijkertijd HTML genereren vanuit PDF?** Ja—gebruik `HtmlViewOptions` om HTML-output te maken terwijl groeperen wordt uitgeschakeld.  
- **Is deze functie beperkt tot PDF's?** Het is voornamelijk voor PDF's, maar de viewer ondersteunt veel andere formaten.

## Introductie

Bij het werken met PDF-documenten is precisie in rendering cruciaal—vooral bij complexe tekststructuren zoals hiërogliefen of talen die een nauwkeurige tekenrepresentatie vereisen. De functie “Character Grouping” veroorzaakt vaak problemen door tekens onjuist te groeperen, wat leidt tot misinterpretatie van de documentinhoud. Dit kan bijzonder problematisch zijn voor gebruikers die een exacte replicatie van de tekstlay-out van hun documenten nodig hebben.

### Voorvereisten

- **Libraries & Dependencies**: Je hebt GroupDocs.Viewer voor Java versie 25.2 of later nodig.  
- **Environment Setup**: Zorg ervoor dat je een Java Development Kit (JDK) geïnstalleerd hebt en dat je IDE is ingesteld om met Maven-projecten te werken.  
- **Knowledge Prerequisites**: Basiskennis van Java-programmeren, vooral het omgaan met bestandspaden en het gebruiken van externe libraries.

## Hoe HTML genereren vanuit PDF met GroupDocs Viewer

HTML genereren vanuit PDF is een twee‑stappenproces: configureer de viewer en render vervolgens het document. Het belangrijkste is om character grouping uit te schakelen vóór het renderen, zodat de HTML-output de oorspronkelijke PDF‑lay-out teken‑voor‑teken weerspiegelt.

### GroupDocs.Viewer voor Java instellen

#### Installatie via Maven

Eerst moet je de benodigde bibliotheek in je project integreren. Voeg de volgende configuratie toe aan je `pom.xml`:

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

#### Licentie‑acquisitie

Om GroupDocs.Viewer volledig te benutten, overweeg je een licentie aan te schaffen:
- **Free Trial**: Begin met de gratis proefversie om functies te testen.  
- **Temporary License**: Vraag een tijdelijke licentie aan als je meer tijd nodig hebt.  
- **Purchase**: Voor langdurige projecten is het aan te raden een licentie aan te schaffen.

#### Basisinitialisatie en -configuratie

Hieronder staat een kant‑en‑klaar snippet dat de volledige workflow toont—van het instellen van de outputmap tot het renderen van de PDF als HTML terwijl character grouping wordt uitgeschakeld:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Implementatiegids

#### Functie: Character Grouping uitschakelen

Hieronder splitsen we elke regel van het voorbeeld zodat je begrijpt **waarom** we het doen en **hoe** het bijdraagt aan het genereren van HTML vanuit PDF zonder ongewenste teken‑samenvoeging.

##### Stap 1: Outputdirectory definiëren  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Waarom?** Dit zorgt ervoor dat je gerenderde HTML‑bestanden in een speciale map worden opgeslagen, waardoor ze later gemakkelijk te vinden en te beheren zijn.

##### Stap 2: Bestandspadformaat configureren  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Waarom?** Het gebruik van een placeholder (`{0}`) laat de viewer een apart HTML‑bestand voor elke PDF‑pagina maken, waardoor de output georganiseerd blijft.

##### Stap 3: HTML View Options initialiseren  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Waarom?** Ingebedde resources bundelen afbeeldingen, lettertypen en CSS direct met elke HTML‑pagina, wat ideaal is voor web‑gebaseerde viewers of e‑learningplatformen.

##### Stap 4: Character Grouping uitschakelen  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Waarom?** Dit is de cruciale regel die de renderengine vertelt **niet** om aangrenzende tekens te combineren, waardoor gegarandeerd wordt dat de gegenereerde HTML de exacte glyph‑plaatsing van de bron‑PDF weerspiegelt.

##### Stap 5: Document renderen  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Waarom?** Het omhullen van de `Viewer` in een try‑with‑resources‑blok garandeert dat alle native resources automatisch worden vrijgegeven, waardoor geheugenlekken in langdurige applicaties worden voorkomen.

### Java HTML genereren vanuit PDF zonder Groeperen

De klasse `HtmlViewOptions` stelt je in staat om **HTML genereren vanuit PDF** te produceren terwijl elk teken afzonderlijk blijft. Dit is vooral handig wanneer je de gerenderde pagina's wilt embedden in een webportaal of een e‑learningplatform waar exacte glyph‑plaatsing van belang is.

### Veelvoorkomende problemen en oplossingen

- **FileNotFoundException** – Controleer het pad dat je doorgeeft aan `new Viewer(...)` nogmaals. Gebruik absolute paden of `Path.of(...)` voor duidelijkheid.  
- **Write Permissions** – Zorg ervoor dat de outputdirectory schrijfbaar is voor het Java‑proces; op Linux moet je mogelijk de maprechten aanpassen (`chmod 775`).  
- **Version Mismatch** – De `setDisableCharsGrouping`‑optie is beschikbaar vanaf versie 25.2. Controleer of je `pom.xml` de juiste versie aangeeft.

### Praktische toepassingen

1. **Language Preservation** – Ideaal voor het renderen van documenten in Chinees, Japans, Arabisch of oude scripts waarbij de tekenafstand betekenis draagt.  
2. **Legal & Financial Documents** – Garandeert exacte tekstreplicatie voor compliance‑intensieve documenten.  
3. **Educational Resources** – Perfect voor leerboeken die complexe diagrammen, annotaties of meertalige inhoud bevatten.

### Prestatieoverwegingen

- **Optimize Resource Usage** – Grote PDF's kunnen veel geheugen verbruiken. Overweeg om pagina's in batches te verwerken en `Viewer`‑instanties tijdig te verwijderen.  
- **Java Memory Management** – Stem de JVM‑heap af (`-Xmx2g` of hoger) als je verwacht multi‑honderd‑pagina PDF's te verwerken.  
- **Parallel Rendering** – Voor bulkconversies kun je aparte threads starten, elk met een eigen `Viewer`‑instantie, om multi‑core CPU's te benutten.

## Veelgestelde vragen

**Q:** *Waarom zou ik character grouping überhaupt moeten uitschakelen?*  
**A:** Het uitschakelen van groeperen voorkomt dat de renderer tekens samenvoegt die tot verschillende glyphs behoren, wat essentieel is voor scripts waarbij spatiëring en volgorde betekenis overbrengen.

**Q:** *Is de `setDisableCharsGrouping`‑instelling alleen van toepassing op HTML-output?*  
**A:** Nee, het beïnvloedt de onderliggende PDF‑renderengine, dus elk outputformaat (HTML, PNG, JPEG, enz.) zal de wijziging weergeven.

**Q:** *Kan ik deze instelling combineren met aangepaste lettertypen?*  
**A:** Ja—laad je aangepaste lettertypen vóór het initialiseren van `Viewer`, en de groeperingsregel blijft van toepassing.

**Q:** *Heeft het uitschakelen van groeperen invloed op de prestaties?*  
**A:** Een beetje, omdat de engine elk teken afzonderlijk verwerkt, maar de impact is minimaal voor de meeste documenten.

**Q:** *Is er een manier om groeperen per pagina in of uit te schakelen?*  
**A:** Momenteel is de optie globaal per `PdfOptions`‑instantie; je zou aparte `Viewer`‑instanties nodig hebben voor verschillende pagina's als je gemengd gedrag wilt.

## Bronnen

- [GroupDocs Documentatie](https://docs.groupdocs.com/viewer/java/)
- [API Referentie](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs Viewer downloaden](https://releases.groupdocs.com/viewer/java/)
- [Licentie aanschaffen](https://purchase.groupdocs.com/buy)
- [Gratis proefversie](https://releases.groupdocs.com/viewer/java/)
- [Aanvraag tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Supportforum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-03-22  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs