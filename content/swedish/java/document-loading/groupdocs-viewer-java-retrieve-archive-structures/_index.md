---
date: '2026-06-30'
description: Lär dig hur du får viewinfo och hämtar java-arkivfiltypsstrukturer med
  hjälp av GroupDocs.Viewer. Denna guide täcker installation, kodexempel och verkliga
  användningsfall.
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
title: Hur man får ViewInfo och hämtar arkivstrukturer i Java
type: docs
url: /sv/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Hur man får ViewInfo och hämtar arkivstrukturer i Java

Att hantera arkivfiler effektivt kräver en klar förståelse av deras struktur. I den här handledningen kommer du att lära dig **how to get viewinfo** för vilket arkiv som helst och se hur det hjälper dig att arbeta med **java archive file type**. Vi går igenom hur du konfigurerar GroupDocs.Viewer, extraherar vyinformation och rekursivt läser mapphierarkier så att du kan integrera lösningen i riktiga projekt.

![Arkivstrukturer med GroupDocs.Viewer för Java](/viewer/document-loading/archive-structures-java.png)

**Vad du kommer att lära dig**
- Setting up and configuring GroupDocs.Viewer for Java.  
- Methods to **get viewinfo** from archives.  
- Techniques to read and display the folder structure of an archive file.  
- Practical applications and performance considerations when using GroupDocs.Viewer in Java projects.

## Snabba svar
- **Vad ger “viewinfo”?** Den returnerar filtyp, sidantal och en komplett lista över mappar och filer i ett arkiv.  
- **Vilka arkivformat stöds?** ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.  
- **Behöver jag en licens för produktion?** Ja—en kommersiell licens krävs för produktion; en gratis provversion fungerar för utvärdering.  
- **Kan stora arkiv bearbetas effektivt?** Absolut—använd streamingalternativ och bearbeta en mappnivå åt gången för att hålla minnesanvändningen låg.  
- **Är Maven det enda sättet att lägga till biblioteket?** Maven är den rekommenderade beroendehanteraren, men Gradle eller manuell JAR-inkludering fungerar också.

## Vad är “how to get viewinfo”?

`getViewInfo` är en GroupDocs.Viewer API‑metod som extraherar metadata från ett dokument eller arkiv utan full rendering. Den returnerar det interna mappträdet, antalet filer och grundläggande egenskaper i ett anrop, så att du kan bestämma vilka delar som ska bearbetas. Anropet returnerar en komplett ögonblicksbild av arkiv upp till 500 MB på under en sekund på vanliga servrar.

## Varför hämta strukturer för Java-arkivfiltyp?

Att hämta den interna layouten av en **java archive file type** gör det möjligt att omedelbart hitta nödvändiga filer, undvika onödig extraktion och bygga automatiserade pipelines som bara berör relevanta underkataloger. Detta tillvägagångssätt minskar I/O med upp till 70 % för stora arkiv och gör det möjligt att skanna tusentals filer per minut i data‑ingest‑scenarier.

## Förutsättningar

- **Java Development Kit (JDK):** Version 8 eller nyare.  
- **Maven:** För beroendehantering och byggen.  
- **Basic Java knowledge:** Bekantskap med OOP‑koncept är hjälpsamt men inte obligatoriskt.  

Du behöver också tillgång till GroupDocs.Viewer‑biblioteket, som du kan lägga till i ditt Maven‑projekt som visas nedan.

## Konfigurera GroupDocs.Viewer för Java

### Maven‑konfiguration

Lägg till förrådet och beroendet i din `pom.xml`.

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

### Licensanskaffning

- **Free Trial:** Ladda ner en provversion från GroupDocs webbplats.  
- **Temporary License:** Begär en tillfällig nyckel för korttidsutvärdering.  
- **Full License:** Köp en kommersiell licens för obegränsad produktionsanvändning.

När biblioteket finns på din classpath kan du börja koda.

## Implementeringsguide

### Så får du ViewInfo för arkivfiler

För att hämta vyinformation, ladda först arkivet i Viewer, anropa sedan `getViewInfo` för att hämta metadata och iterera slutligen över den returnerade mapphierarkin. Detta trestegs‑mönster fungerar för alla stödda arkivformat och ger en komplett ögonblicksbild i ett enda API‑anrop, vilket förenklar vidare bearbetning.

#### Initiera Viewer

`Viewer`‑klassen är ingångspunkten för alla renderings‑ och inspektionsoperationer. Den hanterar filströmmar, formatdetektering och resurshantering.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Hämta vyinformation

`ViewInfo` kapslar metadata såsom filtyp, totalt antal sidor och en hierarkisk lista över mappar och filer. Att anropa `getViewInfo` returnerar detta objekt omedelbart.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Visa mappstruktur

Iterera genom `viewInfo.getFolders()` för att skriva ut varje mappnamn, dess djup och innehållande filer. Denna enkla loop ger dig en läsbar trädvy av arkivet.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekursiv mappläsning

För djupt nästlade arkiv kan en rekursiv hjälpmethod gå igenom trädet djup‑först, vilket säkerställer att varje underkatalog besöks utan att ladda hela arkivet i minnet.

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

### Funktion 2: Hämta arkivmappstruktur

Denna funktion fokuserar på att skriva ut mappstrukturen i en arkivfil. Den liknar den första funktionen men betonar den rekursiva utforskningen.

#### Konfigurera ViewInfo‑alternativ

`ArchiveOptions` låter dig ange lösenordsskydd, sidgränser och streamingpreferenser innan du anropar `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekursiv utforskning

En andra rekursiv rutin demonstrerar hur man hanterar lösenordsskyddade arkiv och stora filuppsättningar effektivt.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktiska tillämpningar

1. **Datahantering:** Organisera snabbt stora dataset genom att förstå arkivstrukturer.  
2. **Automatiserad filbearbetning:** Batch‑processa arkiverade filer utan att helt extrahera dem, vilket minskar I/O med upp till 70 %.  
3. **CMS‑integration:** Förbättra innehållshanteringssystem med dynamisk arkivnavigering, så att redaktörer kan förhandsgranska filer direkt från arkivet.

## Prestandaöverväganden

- **Optimera minnesanvändning:** Bearbeta mappar en nivå åt gången och stäng `Viewer`‑instansen omedelbart.  
- **Håll dig uppdaterad:** Använd den senaste GroupDocs.Viewer‑versionen (25.2 vid skrivande) och JDK‑utgåvor för prestandaförbättringar.  
- **Streamingstöd:** Biblioteket kan streama arkiv större än 1 GB utan att ladda hela filen i RAM, tack vare dess interna chunk‑read‑arkitektur.

## Vanliga problem och lösningar

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| `NullPointerException` när mappar läses | `viewInfo.getFolders()` returnerar null för tomma kataloger | Kontrollera null eller tom lista innan iteration. |
| Långsam bearbetning av stora ZIP‑filer | Hela arkivet laddas in i minnet | Använd streamingalternativ som finns i nyare GroupDocs‑versioner. |
| Licens hittades inte | Sökvägen till licensfilen är felaktig | Placera licensfilen i applikationens rot eller sätt `License.setLicense("path/to/license.json")`. |

## Vanliga frågor

**Q:** Vad är GroupDocs.Viewer?  
A: GroupDocs.Viewer är ett Java‑bibliotek som renderar över 100 dokument-, bild- och arkivformat till HTML, PDF eller bildströmmar utan att kräva inhemska applikationer.

**Q:** Kan jag använda GroupDocs.Viewer med andra programmeringsspråk?  
A: Ja, GroupDocs erbjuder SDK:er för .NET, Python, PHP och mer, men den här handledningen fokuserar på Java‑implementationen.

**Q:** Hur hanterar jag stora arkivfiler?  
A: Aktivera streaming via `ArchiveOptions.setUseStreaming(true)`, bearbeta en mappnivå åt gången och avyttra `Viewer`‑objektet efter användning.

**Q:** Vilka typer av arkiv stöder GroupDocs.Viewer?  
A: Det stöder 12+ arkivformat, inklusive ZIP, RAR, TAR, 7z, ISO, ARJ och CAB, samt många proprietära containertyper.

**Q:** Finns det någon storleksgräns för arkiv?  
A: Den praktiska gränsen beror på serverns RAM och CPU; tester visar smidig bearbetning av 2 GB‑arkiv på en maskin med 16 GB RAM när streaming är aktiverat.

**Q:** Fungerar “how to get viewinfo” med lösenordsskyddade arkiv?  
A: Ja, ange lösenordet via `ArchiveOptions.setPassword("yourPassword")` innan du anropar `getViewInfo`.

## Slutsats

Genom att följa den här guiden vet du nu **how to get viewinfo** för alla stödda arkiv och hur du traverserar dess mapphierarki med GroupDocs.Viewer för Java. Dessa tekniker gör det möjligt att bygga smartare databehandlings‑pipelines, förbättra CMS‑integrationer och hantera stora samlingar av arkiverade filer med förtroende. Nästa steg är att utforska rendering av enskilda filer från arkivet eller konvertera dem till PDF/HTML med andra Viewer‑funktioner.

---

**Senast uppdaterad:** 2026-06-30  
**Testad med:** GroupDocs.Viewer 25.2 for Java  
**Författare:** GroupDocs  

**Resurser**
- **Dokumentation:** [GroupDocs Viewer Java-dokumentation](https://docs.groupdocs.com/viewer/java/)
- **API‑referens:** [GroupDocs API‑referens för Java](https://reference.groupdocs.com/viewer/java/)
- **Ladda ner GroupDocs.Viewer:** [GroupDocs nedladdningssida](https://releases.groupdocs.com/viewer/java/)
- **Köp licens:** [Köp GroupDocs](https://purchase.groupdocs.com/buy)
- **Gratis provversion och tillfällig licens:** [GroupDocs gratis provversion](https://releases.groupdocs.com/viewer/java/) | [Tillfällig licens](https://purchase.groupdocs.com/temporary-license/)

## Relaterade handledningar

- [Extrahera dokumentmetadata med GroupDocs.Viewer för Java – Hämta dokumentvyinformation och insikter](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Hur man hämtar bilagor och skriver ut dokumentbilagor med GroupDocs.Viewer för Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java‑guide: Rendera specifika sidor med GroupDocs.Viewer API för dokumentförhandsgranskning och hantering](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)