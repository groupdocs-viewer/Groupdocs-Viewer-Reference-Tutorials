---
date: '2026-01-05'
description: Leer hoe u e‑mailvelden kunt hernoemen, e‑mail kunt converteren naar
  HTML en e‑mailheaders kunt aanpassen met GroupDocs.Viewer voor Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Hoe e‑mailvelden te hernoemen bij het renderen van e‑mails naar HTML met GroupDocs.Viewer
  Java
type: docs
url: /nl/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Hoe e‑mailvelden hernoemen bij het renderen van e‑mails naar HTML met GroupDocs.Viewer Java

Vraag je je af **hoe je e‑mail**‑velden kunt hernoemen tijdens het converteren van een e‑mail naar HTML? In deze gids lopen we stap voor stap door hoe je e‑mailvelden hernoemt, **e‑mail naar HTML converteert** en **e‑mail‑headers aanpast** met GroupDocs.Viewer voor Java. Aan het einde heb je een nette HTML‑weergave met jouw gewenste header‑namen, waardoor de output makkelijker leesbaar en te integreren is in je applicaties.

![E‑mailvelden hernoemen bij het converteren van e‑mails naar HTML met GroupDocs.Viewer voor Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Wat je zult leren
- Hoe je GroupDocs.Viewer voor Java gebruikt om **e‑mail naar HTML** te **converteren**.  
- Technieken om **e‑mailvelden** zoals “From”, “To”, “Sent” en “Subject” te **hernoemen**.  
- Best practices voor het instellen van Maven en licenties.  
- Praktijkvoorbeelden waarbij **het aanpassen van e‑mail‑headers** waarde toevoegt.

## Snelle antwoorden
- **Wat betekent “hoe je e‑mail hernoemt”?** Het verwijst naar het toewijzen van aangepaste labels aan de standaard e‑mail‑headernamen tijdens het renderen.  
- **Welke bibliotheek verzorgt de conversie?** GroupDocs.Viewer voor Java (v25.2+).  
- **Heb ik een licentie nodig?** Een proefversie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan ik elke headernaam wijzigen?** Ja, elke standaard e‑mail‑header kan worden gemapt via `fieldTextMap`.  
- **Is de output HTML of ingesloten resources?** Je kunt kiezen voor ingesloten resources voor één enkel zelf‑containend bestand.

## Wat betekent “hoe je e‑mail hernoemt” in de context van GroupDocs.Viewer?
E‑mailvelden hernoemen betekent dat de standaardlabels (bijv. “From”) worden vervangen door aangepaste tekst (bijv. “Afzender”) wanneer de e‑mail wordt gerenderd naar HTML. Dit is handig om de output af te stemmen op de terminologie van je organisatie of de leesbaarheid voor eindgebruikers te verbeteren.

## Waarom e‑mail naar HTML converteren en e‑mail‑headers aanpassen?
- **Consistente branding:** Stem de taal van je organisatie af op alle communicatie.  
- **Verbeterde doorzoekbaarheid:** Aangepaste headers kunnen effectiever worden geïndexeerd in archiveringssystemen.  
- **Betere UI‑integratie:** Pas het HTML‑fragment aan zodat het naadloos past in webportalen of support‑dashboards.

## Vereisten

### Vereiste bibliotheken, versies en afhankelijkheden
- **GroupDocs.Viewer voor Java** – versie 25.2 of hoger.  
- **Java Development Kit (JDK)** – versie 8+.

### Omgevingsinstellingen
- **Maven** voor afhankelijkheidsbeheer.  
- Een IDE zoals IntelliJ IDEA, Eclipse of VS Code.

### Kennisvereisten
Basiskennis van Java en Maven helpt je om snel mee te volgen.

## GroupDocs.Viewer voor Java instellen

### Maven‑configuratie
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
- **Tijdelijke licentie:** Verkrijg een tijdelijke licentie om de volledige functionaliteit zonder beperkingen te verkennen via [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Aankoop:** Voor doorlopend gebruik kun je een licentie aanschaffen via [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Basisinitialisatie en -instelling
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

## Implementatie‑gids

### E‑mailvelden hernoemen – stap‑voor‑stap

#### 1. Output‑directory‑pad instellen
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Vervang `"YOUR_OUTPUT_DIRECTORY"` door de map waarin je de HTML‑bestanden wilt opslaan.*

#### 2. Formaat voor paginabestandspad definiëren
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` wordt tijdens het renderen vervangen door het paginanummer.*

#### 3. Een mapping van e‑mailvelden naar nieuwe namen maken
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
*Hier wijzigen we de standaardlabels naar aangepaste namen.*

#### 4. HTML‑view‑opties configureren
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` bundelt CSS/JS in de HTML, terwijl `setFieldTextMap` de aangepaste header‑namen toepast.*

#### 5. De e‑mail naar HTML renderen
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Vervang `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` door het daadwerkelijke pad naar je MSG‑bestand.*

#### Tips voor probleemoplossing
- Controleer of de output‑directory beschrijfbaar is.  
- Zorg ervoor dat het invoer‑MSG‑bestand bestaat en het pad correct is.  
- Gebruik dezelfde GroupDocs.Viewer‑versie (25.2) als gedeclareerd in Maven.

## Praktische toepassingen
1. **Aangepaste e‑mailrapporten:** Stem e‑mail‑headers af op de terminologie van de organisatie voor duidelijkere rapporten.  
2. **E‑mail‑archiveringssystemen:** Verbeter de doorzoekbaarheid door gestandaardiseerde header‑namen te gebruiken.  
3. **Klantenondersteuningsplatforms:** Presenteer tickets met gepersonaliseerde header‑labels voor een betere agent‑ervaring.

## Prestatie‑overwegingen
- Maak `Viewer`‑objecten vrij met try‑with‑resources om het geheugen snel vrij te geven.  
- Profileer grote batches en overweeg het verwerken van e‑mails in parallelle streams indien nodig.

## Conclusie
Je weet nu **hoe je e‑mail**‑velden kunt hernoemen terwijl je **e‑mail naar HTML** **converteert** en **e‑mail‑headers aanpast** met GroupDocs.Viewer voor Java. Deze techniek geeft je volledige controle over de weergave van e‑mail‑metadata in HTML‑outputs.

### Volgende stappen
- Experimenteer met extra veld‑mappings (bijv. CC, BCC).  
- Verken andere render‑formaten zoals PDF of PNG.  
- Bezoek de [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) voor diepere API‑inzichten.

## FAQ‑sectie
1. **Kan ik alle e‑mail‑headers hernoemen met deze methode?**  
   - Ja, je kunt elke standaard e‑mail‑header naar een nieuwe naam mappen volgens jouw eisen.  
2. **Is het mogelijk GroupDocs.Viewer te gebruiken zonder licentie?**  
   - Een proefversie is beschikbaar voor testen, maar een volledige versie vereist een geldige licentie.  
3. **Hoe verwerk ik grote hoeveelheden e‑mails efficiënt met GroupDocs.Viewer?**  
   - Overweeg batch‑verwerking en optimaliseer systeembronnen om grotere datasets effectief te beheren.  
4. **Kan ik deze oplossing integreren in een bestaande Java‑applicatie?**  
   - Absoluut, integratie is eenvoudig via Maven‑afhankelijkheden.  
5. **Waar vind ik ondersteuning als ik problemen tegenkom?**  
   - Bezoek het [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) voor community‑ en officiële hulp.

## Veelgestelde vragen

**V: Werkt deze aanpak met andere e‑mailformaten zoals EML?**  
A: Ja, GroupDocs.Viewer ondersteunt zowel MSG‑ als EML‑bestanden; dezelfde veld‑mappinglogica is van toepassing.

**V: Kan ik de HTML zonder ingesloten resources outputten?**  
A: Je kunt `HtmlViewOptions.forExternalResources(...)` gebruiken als je losse CSS/JS‑bestanden verkiest.

**V: Welke versie van GroupDocs.Viewer is getest?**  
A: De code is getest met GroupDocs.Viewer **25.2**.

**V: Is het mogelijk het lettertype of de stijl van de aangepaste headers te wijzigen?**  
A: Styling kan na het renderen via CSS worden toegepast, of je kunt aangepaste CSS injecteren met `HtmlViewOptions.getResourcesPath()`.

**V: Hoe haal ik programmatically het gegenereerde HTML‑bestandspad op?**  
A: Het bestandspad volgt het patroon dat is gedefinieerd in `pageFilePathFormat`; je kunt het construeren met `String.format` en het paginanummer.

## Resources
- **Documentatie:** Uitgebreide gidsen zijn beschikbaar op [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑referentie:** Gedetailleerde API‑informatie vind je op [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **GroupDocs.Viewer downloaden:** Toegang tot de nieuwste versie via de [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Laatst bijgewerkt:** 2026-01-05  
**Getest met:** GroupDocs.Viewer 25.2  
**Auteur:** GroupDocs  

---