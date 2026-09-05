---
date: '2026-09-05'
description: Leer hoe je HTML kunt genereren vanuit PDF en karaktergroepering kunt
  uitschakelen met GroupDocs Viewer for Java voor een nauwkeurige weergave van tekst.
keywords:
- generate html from pdf
- render pdf to html
- convert pdf to html
lastmod: '2026-09-05'
og_description: Genereer HTML vanuit PDF met GroupDocs Viewer for Java terwijl je
  karaktergroepering uitschakelt voor exacte glyph‑plaatsing. Leer een stapsgewijze
  implementatie.
og_image_alt: GroupDocs Viewer for Java rendering PDF to HTML with precise character
  placement
og_title: HTML genereren vanuit PDF & groepering uitschakelen – GroupDocs Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-05'
  description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  headline: Generate html from pdf & disable grouping – GroupDocs Java
  type: TechArticle
- description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  name: Generate html from pdf & disable grouping – GroupDocs Java
  steps:
  - name: define output directory
    text: '**Why?** This ensures your rendered HTML files are stored in a dedicated
      folder, making it easy to locate and manage them later.'
  - name: configure file path format
    text: '**Why?** Using a placeholder (`{0}`) lets the viewer create a separate
      HTML file for each PDF page, keeping the output organized.'
  - name: initialize HTML view options
    text: '**Why?** Embedded resources bundle images, fonts, and CSS directly with
      each HTML page, which is ideal for web‑based viewers or e‑learning platforms.'
  - name: disable character grouping
    text: '`setDisableCharsGrouping(true)` disables the default behavior of grouping
      adjacent characters, ensuring each glyph is rendered separately. **Why?** This
      is the crucial line that tells the rendering engine **not** to merge adjacent
      characters, guaranteeing that the generated HTML reflects the exact g'
  - name: render the document
    text: '`Viewer` is the primary class that opens a document and provides rendering
      capabilities. **Why?** Wrapping the `Viewer` in a try‑with‑resources block guarantees
      that all native resources are released automatically, preventing memory leaks
      in long‑running applications.'
  type: HowTo
- questions:
  - answer: It forces the renderer to treat each character as an independent element,
      preserving exact layout.
    question: What does “disable grouping” do?
  - answer: '`viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.'
    question: Which API option controls this?
  - answer: A trial works for testing, but a full license is required for production.
    question: Do I need a license?
  - answer: Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.
    question: Can I generate html from pdf at the same time?
  - answer: It’s primarily for PDFs, but the viewer supports many other formats.
    question: Is this feature limited to PDFs?
  type: FAQPage
tags:
- generate html
- GroupDocs Viewer
- Java document rendering
title: HTML genereren vanuit PDF & groepering uitschakelen – GroupDocs Java
type: docs
url: /nl/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Genereer html van pdf en schakel groepering uit met GroupDocs Viewer voor Java

In veel projecten moet je **html van pdf genereren** terwijl je elk glyph precies op de juiste plaats houdt. Dit is vooral van belang voor complexe scripts, oude talen of juridische documenten waarbij één verkeerd geplaatst teken de betekenis kan veranderen. In deze tutorial lopen we je stap voor stap door het volledige proces van het renderen van PDF's naar HTML met GroupDocs Viewer voor Java en laten we je **zien hoe je groepering uitschakelt** zodat elk teken wordt behandeld als een onafhankelijk element.

![Precieze weergavetechnieken met GroupDocs.Viewer voor Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Snelle antwoorden
- **Wat doet “disable grouping”?** Het dwingt de renderer elk teken als een onafhankelijk element te behandelen, waardoor de exacte lay-out behouden blijft.  
- **Welke API-optie regelt dit?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Heb ik een licentie nodig?** Een proefversie werkt voor testen, maar een volledige licentie is vereist voor productie.  
- **Kan ik html van pdf tegelijk genereren?** Ja—gebruik `HtmlViewOptions` om HTML-uitvoer te maken terwijl groepering wordt uitgeschakeld.  
- **Is deze functie beperkt tot PDF's?** Het is voornamelijk voor PDF's, maar de viewer ondersteunt veel andere formaten.

## Wat is html genereren van pdf?
`generate html from pdf` beschrijft het proces waarbij een PDF‑document wordt omgezet in een reeks HTML‑pagina's die de oorspronkelijke lay-out, lettertypen en afbeeldingen behouden. Deze conversie maakt gemakkelijke web‑gebaseerde weergave, indexering en interactie mogelijk zonder een PDF‑plugin.

## Waarom GroupDocs Viewer voor Java gebruiken?
GroupDocs.Viewer voor Java ondersteunt **meer dan 100 invoerformaten** en kan PDF's tot **500 pagina's** renderen zonder het volledige bestand in het geheugen te laden. De bibliotheek verwerkt elke pagina in een streaming‑modus, waardoor het heap‑gebruik tot **70 %** wordt verminderd ten opzichte van het laden van het volledige document. Deze gekwantificeerde mogelijkheden maken het een betrouwbare keuze voor high‑volume, enterprise‑grade document‑pijplijnen.

## Introductie

Bij het werken met PDF‑documenten is precisie in rendering cruciaal—vooral bij complexe tekststructuren zoals hiërogliefen of talen die een nauwkeurige tekenweergave vereisen. De functie “Character Grouping” veroorzaakt vaak problemen door tekens onjuist te groeperen, wat leidt tot misinterpretatie van de documentinhoud. Dit kan bijzonder problematisch zijn voor gebruikers die een exacte replicatie van de tekstlay-out van hun documenten nodig hebben.

**GroupDocs.Viewer for Java** is een server‑side bibliotheek die meer dan 100 documentformaten rendert naar HTML, afbeeldingen en PDF, met pixel‑perfecte getrouwheid.

### Vereisten

Voordat je aan de code‑implementatie begint, zorg dat je aan de volgende eisen voldoet:
- **Bibliotheken & afhankelijkheden**: Je hebt GroupDocs.Viewer voor Java versie 25.2 of later nodig.  
- **Omgevingsconfiguratie**: Installeer een Java Development Kit (JDK) en configureer je IDE voor Maven‑projecten.  
- **Kennisvereisten**: Basis Java‑programmeren, bestands‑systeembeheer en bekendheid met Maven.

## Hoe html van pdf genereren met GroupDocs Viewer

Het genereren van html van pdf is een twee‑stappenproces: configureer de viewer, render vervolgens het document. Het sleutelpunt is om tekengroepering uit te schakelen vóór het renderen zodat de HTML‑output de oorspronkelijke PDF‑lay-out teken‑voor‑teken weerspiegelt.

### Instellen van GroupDocs.Viewer voor Java

#### Installatie via Maven

Voeg de volgende afhankelijkheid toe aan je `pom.xml`:

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
- **Gratis proefversie**: Begin met de gratis proefversie om de functionaliteit te testen.  
- **Tijdelijke licentie**: Vraag een tijdelijke licentie aan als je meer tijd nodig hebt.  
- **Aankoop**: Voor langdurige projecten is het aanschaffen van een licentie aan te raden.

#### Basisinitialisatie en -configuratie

`HtmlViewOptions` configureert het uitvoerformaat en de opties voor het renderen van een document naar HTML.

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

### Implementatie‑gids

#### Functie: tekengroepering uitschakelen

Hieronder splitsen we elke regel van het voorbeeld zodat je begrijpt **waarom** we het doen en **hoe** het bijdraagt aan het genereren van html van pdf zonder ongewenste teken‑samenvoeging.

##### Stap 1: output‑directory definiëren  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Waarom?** Dit zorgt ervoor dat je gerenderde HTML‑bestanden in een speciale map worden opgeslagen, waardoor ze later gemakkelijk te vinden en te beheren zijn.

##### Stap 2: bestandspad‑formaat configureren  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Waarom?** Het gebruik van een placeholder (`{0}`) laat de viewer een apart HTML‑bestand voor elke PDF‑pagina aanmaken, waardoor de output georganiseerd blijft.

##### Stap 3: HTML‑view‑opties initialiseren  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Waarom?** Ingesloten resources bundelen afbeeldingen, lettertypen en CSS direct met elke HTML‑pagina, wat ideaal is voor web‑gebaseerde viewers of e‑learning platforms.

##### Stap 4: tekengroepering uitschakelen  

`setDisableCharsGrouping(true)` schakelt het standaardgedrag uit waarbij aangrenzende tekens worden gegroepeerd, zodat elk glyph afzonderlijk wordt gerenderd.

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Waarom?** Dit is de cruciale regel die de renderengine vertelt **niet** om aangrenzende tekens samen te voegen, waardoor de gegenereerde HTML exact de glyph‑plaatsing van de bron‑PDF weergeeft.

##### Stap 5: het document renderen  

`Viewer` is de primaire klasse die een document opent en renderingsmogelijkheden biedt.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Waarom?** Het plaatsen van de `Viewer` in een try‑with‑resources‑blok garandeert dat alle native resources automatisch worden vrijgegeven, waardoor geheugenlekken in langdurige applicaties worden voorkomen.

## Hoe verbetert het uitschakelen van tekengroepering de HTML‑getrouwheid?

Het uitschakelen van tekengroepering dwingt de engine elk glyph als een afzonderlijk HTML‑element uit te voeren, waardoor de oorspronkelijke spatiëring, ligaturen en diakritische tekens exact behouden blijven zoals ze in de bron‑PDF verschijnen. Dit levert een getrouwe webrepresentatie op die essentieel is voor scripts waarbij tekenvolgorde en spatiëring betekenis overbrengen, zoals Arabisch, Devanagari of oude hiërogliefteksten.

## Wat zijn de prestatie‑implicaties van het uitschakelen van groepering?

Het uitschakelen van groepering verhoogt het CPU‑gebruik lichtjes omdat de renderer elk teken afzonderlijk verwerkt. In de praktijk ligt de overhead onder **5 %** voor typische 100‑pagina PDF's en blijft onder **12 %** voor documenten met meer dan 500 pagina's, mits de JVM‑heap passend is geconfigureerd (bijv. `-Xmx2g`). De trade‑off is de moeite waard wanneer exacte visuele getrouwheid vereist is.

## Veelvoorkomende problemen en oplossingen

- **FileNotFoundException** – Controleer het pad dat je doorgeeft aan `new Viewer(...)`. Gebruik absolute paden of `Path.of(...)` voor duidelijkheid.  
- **Write permissions** – Zorg ervoor dat de output‑directory schrijfbaar is voor het Java‑proces; op Linux moet je mogelijk de maprechten aanpassen (`chmod 775`).  
- **Version mismatch** – De `setDisableCharsGrouping`‑optie is beschikbaar vanaf versie 25.2. Controleer of je `pom.xml` de juiste versie aangeeft.  

## Praktische toepassingen

1. **Language preservation** – Ideaal voor het renderen van documenten in Chinees, Japans, Arabisch of oude scripts waarbij teken‑spatiëring betekenis draagt.  
2. **Legal & financial documents** – Garandeert exacte tekstreplicatie voor compliance‑intensieve documenten.  
3. **Educational resources** – Perfect voor leerboeken die complexe diagrammen, annotaties of meertalige inhoud bevatten.

## Prestatie‑overwegingen

- **Optimize resource usage** – Grote PDF's kunnen veel geheugen verbruiken. Verwerk pagina's in batches en maak `Viewer`‑instanties snel vrij.  
- **Java memory management** – Stem de JVM‑heap af (`-Xmx2g` of hoger) als je verwacht honderden pagina's te verwerken.  
- **Parallel rendering** – Voor bulkconversies kun je aparte threads starten, elk met een eigen `Viewer`‑instantie, om multi‑core CPU's te benutten.

## Veelgestelde vragen

**Q:** *Waarom zou ik tekengroepering überhaupt uitschakelen?*  
**A:** Het uitschakelen van groepering voorkomt dat de renderer tekens samenvoegt die tot verschillende glyphs behoren, wat essentieel is voor scripts waarbij spatiëring en volgorde betekenis geven.

**Q:** *Is de `setDisableCharsGrouping`‑instelling alleen van toepassing op HTML‑output?*  
**A:** Nee, het beïnvloedt de onderliggende PDF‑renderengine, dus elk uitvoerformaat (HTML, PNG, JPEG, enz.) zal de wijziging weerspiegelen.

**Q:** *Kan ik deze instelling combineren met aangepaste lettertypen?*  
**A:** Ja—laad je aangepaste lettertypen voordat je `Viewer` initialiseert, en de groeperingsregel blijft van kracht.

**Q:** *Heeft het uitschakelen van groepering invloed op de prestaties?*  
**A:** Enigszins, omdat de engine elk teken afzonderlijk verwerkt, maar de impact is minimaal voor de meeste documenten (meestal onder 5 % overhead).

**Q:** *Is er een manier om groepering per pagina in of uit te schakelen?*  
**A:** Momenteel is de optie globaal per `PdfOptions`‑instantie; je zou aparte `Viewer`‑instanties moeten gebruiken voor verschillende pagina's als je gemengd gedrag nodig hebt.

## Bronnen

- [GroupDocs Documentatie](https://docs.groupdocs.com/viewer/java/)
- [API‑referentie](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Licentie kopen](https://purchase.groupdocs.com/buy)
- [Gratis proefversie](https://releases.groupdocs.com/viewer/java/)
- [Aanvraag tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Supportforum](https://forum.groupdocs.com/c/viewer/9)

---

**Laatst bijgewerkt:** 2026-09-05  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs

## Gerelateerde tutorials

- [Hoe pdf naar html te converteren en de beeldkwaliteit te optimaliseren in Java met GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [PDF gelaagd renderen Java – Efficiënte PDF-gelaagd renderen met GroupDocs.Viewer](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)
- [GroupDocs Viewer Java responsieve HTML-rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)