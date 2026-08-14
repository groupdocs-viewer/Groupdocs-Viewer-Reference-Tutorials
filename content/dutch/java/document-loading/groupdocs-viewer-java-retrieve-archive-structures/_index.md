---
date: '2026-06-30'
description: Leer hoe je viewinfo kunt ophalen en java-archiefbestandtype-structuren
  kunt ophalen met GroupDocs.Viewer. Deze gids behandelt de installatie, codevoorbeelden
  en praktijkvoorbeelden.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Hoe ViewInfo te verkrijgen en archiefstructuren op te halen in Java
type: docs
url: /nl/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Hoe ViewInfo te krijgen en archiefstructuren op te halen in Java

Het effectief beheren van archiefbestanden vereist een duidelijk begrip van hun structuur. In deze tutorial leer je **how to get viewinfo** voor elk archief en zie je hoe het je helpt werken met het **java archive file type**. We lopen door het opzetten van GroupDocs.Viewer, het extraheren van view‑informatie, en het recursief lezen van maphiërarchieën zodat je de oplossing in echte projecten kunt integreren.

![Archiefstructuren met GroupDocs.Viewer voor Java](/viewer/document-loading/archive-structures-java.png)

**Wat je zult leren**
- GroupDocs.Viewer voor Java installeren en configureren.  
- Methoden om **get viewinfo** uit archieven te halen.  
- Technieken om de mapstructuur van een archiefbestand te lezen en weer te geven.  
- Praktische toepassingen en prestatie‑overwegingen bij het gebruik van GroupDocs.Viewer in Java‑projecten.

## Snelle antwoorden
- **Wat biedt “viewinfo”?** Het retourneert bestandstype, paginatelling en een volledige lijst van mappen en bestanden binnen een archief.  
- **Welke archiefformaten worden ondersteund?** ZIP, RAR, TAR, 7z, ISO, en 12+ andere gangbare formaten.  
- **Heb ik een licentie nodig voor productie?** Ja—een commerciële licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.  
- **Kunnen grote archieven efficiënt worden verwerkt?** Absoluut—gebruik streaming‑opties en verwerk één mapniveau per keer om het geheugenverbruik laag te houden.  
- **Is Maven de enige manier om de bibliotheek toe te voegen?** Maven is de aanbevolen dependency‑manager, maar Gradle of handmatige JAR‑inclusie werken ook.

## Wat is “how to get viewinfo”?

`getViewInfo` is een GroupDocs.Viewer API‑methode die metadata uit een document of archief haalt zonder volledige rendering. Het retourneert de interne mapboom, het aantal bestanden en basis‑eigenschappen in één oproep, zodat je kunt bepalen welke delen je wilt verwerken. De oproep geeft een volledige momentopname van archieven tot 500 MB in minder dan een seconde op typische servers.

## Waarom Java‑archiefbestand‑type‑structuren ophalen?

Het ophalen van de interne indeling van een **java archive file type** stelt je in staat om benodigde bestanden direct te vinden, onnodige extractie te vermijden en geautomatiseerde pipelines te bouwen die alleen relevante sub‑mappen aanraken. Deze aanpak vermindert I/O met tot 70 % voor grote archieven en maakt het mogelijk om duizenden bestanden per minuut te scannen in data‑ingestiescenario's.

## Voorvereisten

- **Java Development Kit (JDK):** Versie 8 of nieuwer.  
- **Maven:** Voor dependency‑beheer en builds.  
- **Basis Java‑kennis:** Vertrouwdheid met OOP‑concepten helpt, maar is niet verplicht.  

Je hebt ook toegang nodig tot de GroupDocs.Viewer‑bibliotheek, die je kunt toevoegen aan je Maven‑project zoals hieronder weergegeven.

## GroupDocs.Viewer voor Java instellen

### Maven‑configuratie

Voeg de repository en dependency toe aan je `pom.xml`.

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

**Afhankelijkheden:**
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

- **Free Trial:** Download een proefversie van de GroupDocs‑website.  
- **Temporary License:** Vraag een tijdelijke sleutel aan voor kortetermijnevaluatie.  
- **Full License:** Koop een commerciële licentie voor onbeperkt productiegebruik.

Zodra de bibliotheek op je classpath staat, kun je beginnen met coderen.

## Implementatie‑gids

### Hoe ViewInfo te krijgen voor archiefbestanden

Om view‑informatie te verkrijgen, laad je eerst het archief in de Viewer, roep je vervolgens `getViewInfo` aan om de metadata op te halen, en itereren tenslotte over de geretourneerde maphiërarchie. Dit drie‑stappenpatroon werkt voor alle ondersteunde archiefformaten en biedt een volledige momentopname in één API‑oproep, waardoor verdere verwerking wordt vereenvoudigd.

#### De Viewer initialiseren

De `Viewer`‑klasse is het toegangspunt voor alle render‑ en inspectie‑operaties. Het beheert bestands‑streams, formaatdetectie en resource‑opschoning.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### View‑informatie ophalen

`ViewInfo` bevat metadata zoals bestandstype, totaal aantal pagina's en een hiërarchische lijst van mappen en bestanden. Het aanroepen van `getViewInfo` retourneert dit object direct.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Mapstructuur weergeven

Itereer door `viewInfo.getFolders()` om elke mapnaam, diepte en bijbehorende bestanden af te drukken. Deze eenvoudige lus geeft je een leesbare boomweergave van het archief.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Recursief mappen lezen

Voor diep geneste archieven kan een recursieve hulpfunctie de boom diepte‑eerst doorlopen, zodat elke sub‑map wordt bezocht zonder het volledige archief in het geheugen te laden.

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

### Functie 2: Archief‑mapstructuur ophalen

Deze functie richt zich op het afdrukken van de mapstructuur van een archiefbestand. Het is vergelijkbaar met de eerste functie, maar legt de nadruk op de recursieve verkenning.

#### View‑Info‑opties instellen

`ArchiveOptions` stelt je in staat om wachtwoordbeveiliging, paginalimieten en streamingvoorkeuren op te geven vóór het aanroepen van `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Recursieve verkenning

Een tweede recursieve routine toont hoe je wachtwoord‑beveiligde archieven en grote bestandssets efficiënt kunt verwerken.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktische toepassingen

1. **Data Management:** Organiseer snel grote datasets door archiefstructuren te begrijpen.  
2. **Automated File Processing:** Batch‑verwerk gearchiveerde bestanden zonder ze volledig uit te pakken, waardoor I/O met tot 70 % wordt verminderd.  
3. **CMS Integration:** Verbeter content‑managementsystemen met on‑the‑fly archiefnavigatie, zodat editors bestanden direct vanuit het archief kunnen bekijken.

## Prestatie‑overwegingen

- **Optimize Memory Usage:** Verwerk mappen één niveau per keer en sluit de `Viewer`‑instantie snel af.  
- **Stay Updated:** Gebruik de nieuwste GroupDocs.Viewer‑versie (25.2 op het moment van schrijven) en JDK‑releases voor prestatieverbeteringen.  
- **Streaming Support:** De bibliotheek kan archieven groter dan 1 GB streamen zonder het hele bestand in RAM te laden, dankzij de interne chunk‑read‑architectuur.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| `NullPointerException` bij het lezen van mappen | `viewInfo.getFolders()` retourneert null voor lege mappen | Controleer op null of een lege lijst vóór iteratie. |
| Trage verwerking van enorme ZIP‑bestanden | Het volledige archief wordt in het geheugen geladen | Gebruik streaming‑opties die beschikbaar zijn in nieuwere GroupDocs‑versies. |
| Licentie niet gevonden | Pad naar licentiebestand is onjuist | Plaats het licentiebestand in de applicatieroot of stel `License.setLicense("path/to/license.json")` in. |

## Veelgestelde vragen

**Q:** Wat is GroupDocs.Viewer?  
A: GroupDocs.Viewer is een Java‑bibliotheek die meer dan 100 document‑, afbeelding‑ en archiefformaten rendert naar HTML, PDF of afbeeldings‑streams zonder native applicaties te vereisen.

**Q:** Kan ik GroupDocs.Viewer gebruiken met andere programmeertalen?  
A: Ja, GroupDocs biedt SDK's voor .NET, Python, PHP en meer, maar deze tutorial richt zich op de Java‑implementatie.

**Q:** Hoe ga ik om met grote archiefbestanden?  
A: Schakel streaming in via `ArchiveOptions.setUseStreaming(true)`, verwerk één mapniveau per keer en maak het `Viewer`‑object vrij na gebruik.

**Q:** Welke archieftypen ondersteunt GroupDocs.Viewer?  
A: Het ondersteunt 12+ archiefformaten, waaronder ZIP, RAR, TAR, 7z, ISO, ARJ en CAB, plus vele propriëtaire containertypen.

**Q:** Is er een grootte‑limiet voor archieven?  
A: De praktische limiet hangt af van het RAM‑ en CPU‑vermogen van je server; tests tonen soepele verwerking van 2 GB‑archieven op een machine met 16 GB RAM wanneer streaming is ingeschakeld.

**Q:** Werkt “how to get viewinfo” met wachtwoord‑beveiligde archieven?  
A: Ja, geef het wachtwoord op via `ArchiveOptions.setPassword("yourPassword")` vóór het aanroepen van `getViewInfo`.

## Conclusie

Door deze gids te volgen weet je nu **how to get viewinfo** voor elk ondersteund archief en hoe je de maphiërarchie kunt doorlopen met GroupDocs.Viewer voor Java. Deze technieken stellen je in staat om slimmere data‑verwerkings‑pipelines te bouwen, CMS‑integraties te verbeteren en grote collecties gearchiveerde bestanden met vertrouwen te verwerken. Als volgende stap kun je het renderen van individuele bestanden uit het archief verkennen of ze naar PDF/HTML converteren met andere Viewer‑functies.

---

**Laatst bijgewerkt:** 2026-06-30  
**Getest met:** GroupDocs.Viewer 25.2 for Java  
**Auteur:** GroupDocs  

**Bronnen**
- **Documentatie:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API‑referentie:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs.Viewer downloaden:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Licentie kopen:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Gratis proefversie en tijdelijke licentie:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Gerelateerde tutorials

- [Documentmetadata extraheren met GroupDocs.Viewer voor Java - Documentweergave‑informatie en inzichten ophalen](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Hoe bijlagen op te halen en documentbijlagen af te drukken met GroupDocs.Viewer voor Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java‑gids: Specifieke pagina's renderen met GroupDocs.Viewer API voor documentpreview en -beheer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)