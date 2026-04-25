---
date: '2026-02-05'
description: Leer hoe u viewinfo kunt ophalen en structuren van Java‑archiefbestanden
  kunt ophalen met GroupDocs.Viewer. Deze gids behandelt de installatie, codevoorbeelden
  en praktijkvoorbeelden.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Hoe ViewInfo te verkrijgen en archiefstructuren op te halen in Java
type: docs
url: /nl/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Hoe ViewInfo op te halen en archiefstructuren op te halen in Java

Het effectief beheren van archiefbestanden vereist een duidelijk begrip van hun structuur. In deze tutorial leer je **hoe viewinfo op te halen** voor elk archief en zie je hoe dit je helpt werken met het **java-archiefbestandtype**. We lopen door het instellen van GroupDocs.Viewer, het extraheren van view‑informatie, en het recursief lezen van maphiërarchieën zodat je de oplossing in echte projecten kunt integreren.

![Archiefstructuren met GroupDocs.Viewer voor Java](/viewer/document-loading/archive-structures-java.png)

**Wat je leert**
- Het instellen en configureren van GroupDocs.Viewer voor Java.  
- Methoden om **viewinfo op te halen** uit archieven.  
- Technieken om de mapstructuur van een archiefbestand te lezen en weer te geven.  
- Praktische toepassingen en prestatie‑overwegingen bij het gebruik van GroupDocs.Viewer in Java‑projecten.

## Snelle antwoorden
- **Wat levert “viewinfo” op?** Het geeft bestandstype, paginatelling en archiefmap‑overzichten terug.  
- **Welke archieven worden ondersteund?** ZIP, RAR, TAR en andere gangbare formaten.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Kan ik grote archieven verwerken?** Ja – gebruik streaming en juiste geheugenbeheer zoals later getoond.  
- **Is Maven vereist?** Maven is de aanbevolen manier om de GroupDocs.Viewer‑afhankelijkheid te beheren.

## Wat is “hoe viewinfo op te halen”?
`getViewInfo` is een methode in de GroupDocs.Viewer API die metadata over een document of archief extraheert zonder de volledige inhoud te renderen. Voor archieven onthult het de interne mapstructuur, waardoor je kunt bepalen welke delen je wilt renderen of verder verwerken.

## Waarom Java‑archiefbestandtype‑structuren ophalen?
Het begrijpen van de interne indeling van een **java-archiefbestandtype** (bijv. ZIP, RAR) stelt je in staat om:
- Snel de benodigde bestanden te vinden zonder alles uit te pakken.  
- Geautomatiseerde pipelines te bouwen die alleen relevante sub‑mappen verwerken.  
- Archiefnavigatie te integreren in content‑management‑ of data‑ingestsystemen.

## Voorvereisten

- **Java Development Kit (JDK):** Versie 8 of hoger.  
- **Maven:** Voor afhankelijkheidsbeheer en builds.  
- **Basiskennis van Java:** Vertrouwdheid met OOP-concepten helpt, maar is niet verplicht.

Je hebt ook toegang nodig tot de GroupDocs.Viewer‑bibliotheek, die je kunt toevoegen aan je Maven‑project zoals hieronder weergegeven.

## GroupDocs.Viewer voor Java instellen

### Maven‑configuratie

Voeg de repository en afhankelijkheid toe aan je `pom.xml`.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Licentie‑acquisitie

- **Gratis proefversie:** Download een proefversie van de GroupDocs‑website.  
- **Tijdelijke licentie:** Vraag een tijdelijke sleutel aan voor kortetermijnevaluatie.  
- **Volledige licentie:** Koop een commerciële licentie voor onbeperkt productiegebruik.

Zodra de bibliotheek op je classpath staat, kun je beginnen met coderen.

## Implementatie‑gids

### Hoe ViewInfo op te halen voor archiefbestanden

Deze sectie toont de exacte stappen om `getViewInfo` aan te roepen en de maphiërarchie te lezen.

#### Viewer initialiseren

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### View‑informatie ophalen

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Mapstructuur weergeven

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Recursief mappen lezen

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Functie 2: Archiefmapstructuur ophalen

Deze functie richt zich op het afdrukken van de mapstructuur van een archiefbestand. Het is vergelijkbaar met de eerste functie, maar legt de nadruk op recursieve verkenning.

#### View‑Info‑opties instellen

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Recursieve verkenning

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktische toepassingen

1. **Gegevensbeheer:** Organiseer snel grote datasets door archiefstructuren te begrijpen.  
2. **Geautomatiseerde bestandsverwerking:** Batch‑verwerk gearchiveerde bestanden zonder ze volledig uit te pakken.  
3. **CMS‑integratie:** Verbeter content‑management‑systemen met on‑the‑fly archiefnavigatie.

## Prestatie‑overwegingen

- **Geheugengebruik optimaliseren:** Verwerk mappen één niveau per keer en sluit de `Viewer`‑instantie direct af.  
- **Blijf up‑to‑date:** Gebruik de nieuwste GroupDocs.Viewer‑versie en JDK‑releases voor prestatieverbeteringen.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| `NullPointerException` bij het lezen van mappen | `viewInfo.getFolders()` retourneert null voor lege mappen | Controleer op null of een lege lijst voordat je iterereert. |
| Trage verwerking van enorme ZIP‑bestanden | Het volledige archief wordt in het geheugen geladen | Gebruik streaming‑opties die beschikbaar zijn in nieuwere GroupDocs‑versies. |
| Licentie niet gevonden | Pad naar licentiebestand is onjuist | Plaats het licentiebestand in de root van de applicatie of stel `License.setLicense("path/to/license.json")` in. |

## Veelgestelde vragen

**Q: Wat is GroupDocs.Viewer?**  
A: Het is een krachtige Java‑bibliotheek voor het renderen van documenten, inclusief archieven, naar formaten zoals HTML, afbeelding en PDF.

**Q: Kan ik GroupDocs.Viewer gebruiken met andere programmeertalen?**  
A: Ja, GroupDocs biedt SDK's voor meerdere platforms, maar deze tutorial richt zich op de Java‑implementatie.

**Q: Hoe ga ik om met grote archiefbestanden?**  
A: Gebruik efficiënte geheugenbeheerpraktijken en overweeg archieven op te splitsen indien nodig.

**Q: Welke soorten archieven ondersteunt GroupDocs.Viewer?**  
A: Het ondersteunt diverse formaten, waaronder ZIP, RAR, TAR en andere.

**Q: Is er een limiet aan de grootte van archieven die ik kan verwerken?**  
A: De limieten hangen af van de bronnen van je systeem. Test in je doelomgeving om praktische limieten te bepalen.

**Q: Werkt “hoe viewinfo op te halen” met met wachtwoord beveiligde archieven?**  
A: Ja, je kunt het wachtwoord opgeven via `ArchiveOptions.setPassword("yourPassword")` voordat je `getViewInfo` aanroept.

## Conclusie

Door deze gids te volgen weet je nu **hoe viewinfo op te halen** voor elk ondersteund archief en hoe je de maphiërarchie kunt doorlopen met GroupDocs.Viewer voor Java. Deze technieken stellen je in staat om slimmere data‑verwerkings‑pipelines te bouwen, CMS‑integraties te verbeteren en grote collecties van gearchiveerde bestanden met vertrouwen te verwerken. Vervolgens kun je verkennen hoe je individuele bestanden uit het archief rendert of ze converteert naar PDF/HTML met andere Viewer‑functies.

---

**Laatst bijgewerkt:** 2026-02-05  
**Getest met:** GroupDocs.Viewer 25.2 voor Java  
**Auteur:** GroupDocs  

**Bronnen**
- **Documentatie:** [GroupDocs Viewer Java Documentatie](https://docs.groupdocs.com/viewer/java/)
- **API‑referentie:** [GroupDocs API‑referentie voor Java](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs.Viewer downloaden:** [GroupDocs Downloadpagina](https://releases.groupdocs.com/viewer/java/)
- **Licentie kopen:** [GroupDocs kopen](https://purchase.groupdocs.com/buy)
- **Gratis proefversie en tijdelijke licentie:** [GroupDocs Gratis proefversie](https://releases.groupdocs.com/viewer/java/) | [Tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)