---
date: '2026-02-05'
description: Lär dig hur du får viewinfo och hämtar strukturer för Java‑arkivfiltyper
  med GroupDocs.Viewer. Denna guide täcker installation, kodexempel och verkliga användningsfall.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Hur man får ViewInfo och hämtar arkivstrukturer i Java
type: docs
url: /sv/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Så får du ViewInfo och hämtar arkivstrukturer i Java

Att hantera arkivfiler effektivt kräver en tydlig förståelse för deras struktur. I den här handledningen lär du dig **hur du får viewinfo** för vilket arkiv som helst och ser hur det hjälper dig att arbeta med **java-arkivfiltypen**. Vi går igenom hur du konfigurerar GroupDocs.Viewer, extraherar vyinformation och läser mapphierarkier rekursivt så att du kan integrera lösningen i riktiga projekt.

![Arkivstrukturer med GroupDocs.Viewer för Java](/viewer/document-loading/archive-structures-java.png)

**Vad du kommer att lära dig**
- Installera och konfigurera GroupDocs.Viewer för Java.  
- Metoder för att **få viewinfo** från arkiv.  
- Tekniker för att läsa och visa mappstrukturen i en arkivfil.  
- Praktiska tillämpningar och prestandaöverväganden när du använder GroupDocs.Viewer i Java‑projekt.

## Snabba svar
- **Vad ger “viewinfo”?** Den returnerar filtyp, sidantal och listor över arkivmappar.  
- **Vilka arkiv stöds?** ZIP, RAR, TAR och andra vanliga format.  
- **Behöver jag en licens?** En gratis provperiod fungerar för utvärdering; en kommersiell licens krävs för produktion.  
- **Kan jag bearbeta stora arkiv?** Ja – använd streaming och korrekt minneshantering som visas senare.  
- **Krävs Maven?** Maven är det rekommenderade sättet att hantera GroupDocs.Viewer‑beroendet.

## Vad är “how to get viewinfo”?
`getViewInfo` är en metod i GroupDocs.Viewer‑API:et som extraherar metadata om ett dokument eller arkiv utan att rendera hela innehållet. För arkiv avslöjar den den interna mappträdet, vilket låter dig bestämma vilka delar som ska renderas eller bearbetas vidare.

## Varför hämta strukturer för Java‑arkivfiltyper?
Att förstå den interna layouten för en **java-arkivfiltyp** (t.ex. ZIP, RAR) låter dig:
- Snabbt hitta nödvändiga filer utan att extrahera allt.  
- Bygga automatiserade pipelines som bara bearbetar relevanta underkataloger.  
- Integrera arkivnavigering i innehållshanterings‑ eller data‑ingestionssystem.

## Förutsättningar

- **Java Development Kit (JDK):** Version 8 eller senare.  
- **Maven:** För beroendehantering och byggen.  
- **Grundläggande Java‑kunskaper:** Bekantskap med OOP‑koncept är hjälpsamt men inte obligatoriskt.

Du behöver också tillgång till GroupDocs.Viewer‑biblioteket, som du kan lägga till i ditt Maven‑projekt enligt nedan.

## Installera GroupDocs.Viewer för Java

### Maven‑konfiguration

Lägg till repository och beroende i din `pom.xml`.

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

- **Gratis provperiod:** Ladda ner en provversion från GroupDocs webbplats.  
- **Tillfällig licens:** Begär en tillfällig nyckel för korttidsutvärdering.  
- **Full licens:** Köp en kommersiell licens för obegränsad produktionsanvändning.

När biblioteket finns på din classpath kan du börja koda.

## Implementeringsguide

### Så får du ViewInfo för arkivfiler

Det här avsnittet visar de exakta stegen för att anropa `getViewInfo` och läsa mapphierarkin.

#### Initiera Viewern

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Hämta vyinformation

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Visa mappstruktur

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekursiv mappläsning

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

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekursiv utforskning

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktiska tillämpningar

1. **Datahantering:** Snabbt organisera stora dataset genom att förstå arkivstrukturer.  
2. **Automatiserad filbearbetning:** Batch‑processa arkiverade filer utan att extrahera dem helt.  
3. **CMS‑integration:** Förbättra innehållshanteringssystem med dynamisk arkivnavigering.

## Prestandaöverväganden

- **Optimera minnesanvändning:** Bearbeta mappar en nivå i taget och stäng `Viewer`‑instansen omedelbart.  
- **Håll dig uppdaterad:** Använd den senaste versionen av GroupDocs.Viewer och JDK‑utgåvor för prestandaförbättringar.

## Vanliga problem och lösningar

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| `NullPointerException` när mappar läses | `viewInfo.getFolders()` returnerar null för tomma kataloger | Kontrollera om listan är null eller tom innan du itererar. |
| Långsam bearbetning av stora ZIP‑filer | Hela arkivet laddas in i minnet | Använd streaming‑alternativ som finns i nyare GroupDocs‑versioner. |
| Licens hittades inte | Licensfilens sökväg är felaktig | Placera licensfilen i applikationens rot eller ange `License.setLicense("path/to/license.json")`. |

## Vanliga frågor

**Q: Vad är GroupDocs.Viewer?**  
A: Det är ett kraftfullt Java‑bibliotek för att rendera dokument, inklusive arkiv, till format som HTML, bild och PDF.

**Q: Kan jag använda GroupDocs.Viewer med andra programmeringsspråk?**  
A: Ja, GroupDocs erbjuder SDK:er för flera plattformar, men den här handledningen fokuserar på Java‑implementationen.

**Q: Hur hanterar jag stora arkivfiler?**  
A: Använd effektiva minneshanteringsmetoder och överväg att dela upp arkiven vid behov.

**Q: Vilka typer av arkiv stöder GroupDocs.Viewer?**  
A: Det stöder en mängd olika format inklusive ZIP, RAR, TAR och flera andra.

**Q: Finns det någon gräns för hur stora arkiv jag kan bearbeta?**  
A: Gränserna beror på ditt systems resurser. Testa i din målmiljö för att fastställa praktiska gränser.

**Q: Fungerar “how to get viewinfo” med lösenordsskyddade arkiv?**  
A: Ja, du kan ange lösenordet via `ArchiveOptions.setPassword("yourPassword")` innan du anropar `getViewInfo`.

## Slutsats

Genom att följa den här guiden vet du nu **hur du får viewinfo** för alla stödda arkiv och hur du traverserar deras mapphierarki med GroupDocs.Viewer för Java. Dessa tekniker ger dig möjlighet att bygga smartare dataprocesserings‑pipelines, förbättra CMS‑integrationer och hantera stora samlingar av arkiverade filer med förtroende. Nästa steg är att utforska rendering av enskilda filer från arkivet eller konvertera dem till PDF/HTML med andra Viewer‑funktioner.

---

**Senast uppdaterad:** 2026-02-05  
**Testad med:** GroupDocs.Viewer 25.2 for Java  
**Författare:** GroupDocs  

**Resurser**
- **Dokumentation:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API‑referens:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Ladda ner GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Köp licens:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Gratis provperiod och tillfällig licens:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)