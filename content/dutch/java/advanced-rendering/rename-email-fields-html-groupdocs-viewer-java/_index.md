---
date: '2026-03-24'
description: Leer hoe u e‑mail naar HTML kunt converteren en e‑mailvelden kunt hernoemen
  met GroupDocs Viewer voor Java. Deze gids toont het renderen van e‑mail als HTML
  met aangepaste headers.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: E-mail naar HTML converteren & velden hernoemen – GroupDocs Viewer Java
type: docs
url: /nl/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# E‑mail converteren naar HTML & Velden hernoemen – GroupDocs Viewer Java

Als je **e‑mail wilt converteren naar HTML** en de e‑mailheaders een aangepaste uitstraling wilt geven, ben je op de juiste plek. In deze tutorial lopen we stap voor stap door hoe je e‑mailvelden hernoemt, **e‑mail converteert naar HTML**, en e‑mailheaders aanpast met GroupDocs.Viewer voor Java. Aan het einde heb je een nette HTML‑weergave met de door jou gewenste header‑namen, waardoor de output makkelijker leesbaar en te integreren is in je applicaties.

![E‑mailvelden hernoemen bij het converteren van e‑mails naar HTML met GroupDocs.Viewer voor Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Wat je leert
- Hoe je GroupDocs.Viewer voor Java gebruikt om **e‑mail te converteren naar HTML**.  
- Technieken om **e‑mailvelden te hernoemen** zoals “From”, “To”, “Sent” en “Subject”.  
- Best practices voor het configureren van Maven en licenties.  
- Praktijkvoorbeelden waarbij **het aanpassen van e‑mailheaders** waarde toevoegt.

## Snelle antwoorden
- **Wat betekent “e‑mail converteren naar HTML”?** Het betekent het renderen van een e‑mailbestand (MSG/EML) als een web‑klaar HTML‑document.  
- **Welke bibliotheek voert de conversie uit?** GroupDocs.Viewer voor Java (v25.2+).  
- **Heb ik een licentie nodig?** Een proefversie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan ik elke headernaam wijzigen?** Ja, elke standaard e‑mailheader kan worden herverdeeld via `fieldTextMap`.  
- **Is de output HTML of ingesloten bronnen?** Je kunt ingesloten bronnen kiezen voor één zelf‑bevatend bestand.

## Wat betekent “e‑mail converteren naar HTML” in de context van GroupDocs.Viewer?
E‑mail converteren naar HTML betekent dat je een ruwe e‑mailbestand neemt en er een HTML‑pagina van maakt die de berichtinhoud samen met de metadata weergeeft. Wanneer je bovendien **e‑mailvelden hernoemt**, worden de standaardlabels (bijv. “From”) vervangen door aangepaste tekst (bijv. “Sender”), wat helpt om de bedrijfs‑terminologie te volgen of de UI‑consistentie te verbeteren.

## Waarom e‑mail converteren naar HTML en e‑mailvelden hernoemen?
- **Consistente branding:** Stem de output af op de taal van je organisatie.  
- **Verbeterde doorzoekbaarheid:** Aangepaste headers kunnen effectiever worden geïndexeerd in archiveringssystemen.  
- **Betere UI‑integratie:** Pas het HTML‑fragment aan zodat het naadloos past in webportalen of support‑dashboards.

## Vereisten

### Vereiste bibliotheken, versies en afhankelijkheden
- **GroupDocs.Viewer voor Java** – versie 25.2 of later.  
- **Java Development Kit (JDK)** – versie 8+.

### Omgevingsvereisten
- **Maven** voor afhankelijkheidsbeheer.  
- Een IDE zoals IntelliJ IDEA, Eclipse of VS Code.

### Kennisvereisten
Basiskennis van Java en Maven helpt je om snel mee te volgen.

## GroupDocs.Viewer voor Java instellen

### Maven-configuratie
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

### Stappen voor licentie‑acquisitie
- **Gratis proefversie:** Download een gratis proefversie van [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Tijdelijke licentie:** Verkrijg een tijdelijke licentie om de volledige functies zonder beperkingen te verkennen via [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Aankoop:** Voor doorlopend gebruik kun je overwegen een licentie aan te schaffen via [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Basisinitialisatie en configuratie
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Pas het bestandspad aan zodat het naar je `.msg`‑bestand wijst.

## Hoe e‑mail converteren naar HTML en velden hernoemen – Stap‑voor‑stap

### 1. Stel het uitvoermap‑pad in
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Vervang `"YOUR_OUTPUT_DIRECTORY"` door de map waarin je de HTML‑bestanden wilt opslaan.*

### 2. Definieer het paginabestand‑padformaat
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` wordt tijdens het renderen vervangen door het paginanummer.*

### 3. Maak een mapping van e‑mailvelden naar nieuwe namen
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Hier wijzigen we de standaardlabels naar aangepaste labels.*

### 4. Configureer HTML‑view‑opties
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` bundelt CSS/JS binnen de HTML, terwijl `setFieldTextMap` de aangepaste header‑namen toepast.*

### 5. Render de e‑mail naar HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Vervang `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` door het daadwerkelijke pad naar je MSG‑bestand.*

#### Tips voor probleemoplossing
- Controleer of de uitvoermap schrijfbaar is.  
- Zorg ervoor dat het invoer‑MSG‑bestand bestaat en het pad correct is.  
- Gebruik dezelfde GroupDocs.Viewer‑versie (25.2) als gedeclareerd in Maven.

## Praktische toepassingen
1. **Aangepaste e‑mailrapporten:** Stem e‑mailheaders af op de bedrijfs‑terminologie voor duidelijkere rapporten.  
2. **E‑mailarchiveringssystemen:** Verbeter de doorzoekbaarheid door gestandaardiseerde header‑namen te gebruiken.  
3. **Klantenondersteuningsplatforms:** Presenteer tickets met gepersonaliseerde header‑labels voor een betere agent‑ervaring.

## Prestatie‑overwegingen
- Verwijder `Viewer`‑objecten met try‑with‑resources om het geheugen snel vrij te maken.  
- Profileer grote batches en overweeg het verwerken van e‑mails in parallelle streams indien nodig.

## Conclusie
Je weet nu **hoe je e‑mail kunt converteren naar HTML** terwijl je **e‑mailvelden hernoemt** en **e‑mailheaders aanpast** met GroupDocs.Viewer voor Java. Deze techniek geeft je volledige controle over de weergave van e‑mailmetadata in HTML‑outputs.

### Volgende stappen
- Experimenteer met extra field‑mappings (bijv. CC, BCC).  
- Verken andere renderformaten zoals PDF of PNG.  
- Bezoek [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) voor diepere API‑inzichten.

## Veelgestelde vragen

**Q: Werkt deze aanpak met andere e‑mailformaten zoals EML?**  
A: Ja, GroupDocs.Viewer ondersteunt zowel MSG‑ als EML‑bestanden; dezelfde field‑mapping‑logica is van toepassing.

**Q: Kan ik de HTML outputten zonder ingesloten bronnen?**  
A: Je kunt `HtmlViewOptions.forExternalResources(...)` gebruiken als je aparte CSS/JS‑bestanden verkiest.

**Q: Welke versie van GroupDocs.Viewer is getest?**  
A: De code is getest met GroupDocs.Viewer **25.2**.

**Q: Is het mogelijk om het lettertype of de stijl van de aangepaste headers te wijzigen?**  
A: Styling kan worden toegepast via CSS na het renderen, of je kunt aangepaste CSS injecteren met `HtmlViewOptions.getResourcesPath()`.

**Q: Hoe haal ik programmatisch het gegenereerde HTML‑bestandspad op?**  
A: Het bestandspad volgt het patroon dat is gedefinieerd in `pageFilePathFormat`; je kunt het construeren met `String.format` en het paginanummer.

## Bronnen
- **Documentatie:** Uitgebreide gidsen zijn beschikbaar op [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑referentie:** Gedetailleerde API‑informatie is te vinden op [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **GroupDocs.Viewer downloaden:** Toegang tot de nieuwste versie via de [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Laatst bijgewerkt:** 2026-03-24  
**Getest met:** GroupDocs.Viewer 25.2  
**Auteur:** GroupDocs