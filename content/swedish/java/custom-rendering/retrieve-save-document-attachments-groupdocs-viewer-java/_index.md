---
date: '2026-06-30'
description: Lär dig hur du på ett effektivt sätt hämtar och sparar dokumentbilagor
  i Java-applikationer med java file output stream och det kraftfulla GroupDocs.Viewer
  API:et.
keywords:
- java file output stream
- how to save attachment
- GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  headline: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  name: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  steps:
  - name: '**Create a Viewer Instance**'
    text: '**Create a Viewer Instance**'
  - name: '**Retrieve Attachments**'
    text: '**Retrieve Attachments**'
  - name: '**Understanding Parameters and Methods**'
    text: '**Understanding Parameters and Methods**'
  - name: '**Define the Output Directory**'
    text: '**Define the Output Directory**'
  - name: '**Save Attachments**'
    text: '**Save Attachments**'
  - name: '**Explain Parameters and Methods**'
    text: '**Explain Parameters and Methods**'
  - name: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
    text: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
  - name: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
    text: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
  - name: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
    text: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown earlier; the repository URL and version
      are all you need for a quick start.
    question: How do I install GroupDocs.Viewer in my Java project?
  - answer: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG,
      and many image types—so most common business files are covered.
    question: Can GroupDocs.Viewer handle all document types?
  - answer: Verify that the output path is correct, the directory exists, and your
      process has write permissions. Also ensure you’re using `FileOutputStream` correctly
      as shown.
    question: What if I encounter errors while saving attachments?
  - answer: Yes, a valid GroupDocs.Viewer license is required for production deployments.
      A free trial is available for evaluation.
    question: Is a license required for production use?
  - answer: Using `java file output stream` with buffered I/O efficiently handles
      large binaries; monitor memory usage and consider streaming in chunks for files
      larger than 200 MB.
    question: Does this approach work with large attachment files?
  type: FAQPage
title: Hur man hämtar och sparar dokumentbilagor med java file output stream och GroupDocs.Viewer
  för Java
type: docs
url: /sv/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# Hur man hämtar och sparar dokumentbilagor med java file output stream med GroupDocs.Viewer för Java

## Introduktion

Letar du efter ett sätt att programatiskt extrahera och hantera dokumentbilagor i dina Java‑applikationer med **java file output stream**? Med den ökande digitala dokumenthanteringen är det viktigt att ha verktyg som effektivt förenklar dessa processer. Möt GroupDocs.Viewer för Java—din lösning för att sömlöst hämta och spara dokumentbilagor med lätthet.

![Hämta och spara dokumentbilagor med GroupDocs.Viewer för Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[Hämta och spara dokumentbilagor med GroupDocs.Viewer för Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

I den här handledningen kommer vi att utforska hur du kan utnyttja kraften i GroupDocs.Viewer för att hämta bilagor från dokument och spara dem till önskad katalog. Genom att följa med får du praktiska färdigheter i att hantera dokumentdata effektivt i en Java‑miljö, och du får se exakt **hur du sparar bilagor** med den standardiserade `java file output stream`.

## Snabba svar
- **Vad gör java file output stream?** Det skriver byte‑strömmar direkt till filer, vilket möjliggör att binär data (som bilagor) sparas på disk.  
- **Vilket API hämtar bilagor?** `Viewer.getAttachments()` returnerar en lista med metadata för bilagor.  
- **Kan jag ange utmatningsmappen?** Ja—använd `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en betald licens krävs för produktion.  
- **Är detta tillvägagångssätt trådsäkert?** Skapa en separat `Viewer`‑instans per tråd eller synkronisera åtkomst.

## Vad är java file output stream?
`java.io.FileOutputStream` är en kärnklass i Java som skriver råa byte till en fil. Den är det ideala valet när du behöver lagra binärt innehåll såsom e‑postbilagor, bilder eller annan icke‑textdata som extraheras från ett dokument. Den stödjer både små och stora filer effektivt och kan kombineras med buffrade strömmar för bättre prestanda, vilket säkerställer pålitlig lagring av binära payloads på disk.

## Varför använda java file output stream med GroupDocs.Viewer?
Att använda `java.io.FileOutputStream` tillsammans med GroupDocs.Viewer gör det möjligt för utvecklare att skriva bilagors byte‑data direkt till disk utan mellansteg, vilket bevarar den ursprungliga filintegriteten. Detta minskar minnesförbrukningen, snabbar upp bearbetning av stora bilagor och förenklar koden genom att utnyttja standard‑Java‑I/O ihop med de kraftfulla extraktionsfunktionerna i GroupDocs.Viewer.

- **Direkt binärhantering** – Ingen behov av mellankonverteringar; bilagornas byte skrivs exakt som de förekommer i källfilen.  
- **Prestanda** – Strömmade skrivningar minimerar minnesbelastning, särskilt för stora bilagor.  
- **Enkelhet** – API‑et integreras smidigt med standard‑Java‑I/O, vilket gör koden lättläst och underhållbar.

## Förutsättningar
- **Nödvändiga bibliotek och beroenden**: Lägg till GroupDocs.Viewer‑biblioteket i ditt projekt (se Maven‑snutten nedan).  
- **Miljöuppsättning**: En Java‑IDE (IntelliJ IDEA, Eclipse, etc.) med JDK 8+ installerad.  
- **Kunskapsförutsättningar**: Bekantskap med Java‑I/O, särskilt `FileOutputStream`, samt grundläggande Maven‑användning.

## Installera GroupDocs.Viewer för Java
För att komma igång med GroupDocs.Viewer‑API:t i ditt projekt måste du installera det via Maven. Lägg till följande konfiguration i din `pom.xml`‑fil:

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

**Steg för att skaffa licens:**
- **Gratis prov**: Börja med en gratis provversion för att utforska funktionerna.  
- **Tillfällig licens**: Skaffa en tillfällig licens för en förlängd utvärderingsperiod.  
- **Köp**: För produktionsbruk behöver du en köpt licens.

### Grundläggande initiering och konfiguration
När GroupDocs.Viewer har lagts till som beroende i ditt projekt, initiera det i din Java‑applikation. Så här gör du:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Denna grundläggande konfiguration initierar GroupDocs.Viewer och förbereder det för att hämta bilagor.

## Implementeringsguide

### Hämta bilagor med java file output stream
Låt oss gå igenom hur du kan hämta bilagor med GroupDocs.Viewer. Denna funktion låter dig extrahera metadata för varje bilaga som finns i ditt dokument.

#### Översikt
Att hämta bilagor innebär att anropa metoden `getAttachments`, som returnerar en lista med `Attachment`‑objekt som innehåller detaljer som filnamn och storlek. **Attachment** representerar en fil som är inbäddad i källdokumentet, t.ex. en bild eller en inbäddad fil.

#### Implementeringssteg
1. **Skapa en Viewer‑instans**  
   `Viewer` är huvudklassen i GroupDocs.Viewer som laddar och bearbetar dokument för rendering och extraktion. Initiera `Viewer`‑klassen med sökvägen till ditt dokument:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Hämta bilagor**  
   Använd metoden `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Förstå parametrar och metoder**  
   - `Viewer`: Tar en filsökväg eller en ström till dokumentet.  
   - `getAttachments()`: Hämtar en lista med inbäddade filer och ger detaljer som namn.

### Spara dokumentbilagor till en katalog
Nu när du har lärt dig hur du hämtar bilagor, låt oss spara dem till önskad katalog med GroupDocs.Viewer‑API:t och **java file output stream**.

#### Översikt
Denna funktion innebär att varje hämtad bilagefil sparas till en specificerad utmatningskatalog.

#### Implementeringssteg
1. **Definiera utmatningskatalogen**  
   Ställ in en `outputDirectory`‑sökväg där filerna ska sparas:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Spara bilagor**  
   Använd en loop för att spara varje bilaga med metoden `saveAttachment`. **saveAttachment** skriver det binära innehållet från en `Attachment` till ett angivet `OutputStream`.

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Förklara parametrar och metoder**  
   - `saveAttachment`: Tar ett `Attachment`‑objekt och ett fil‑output‑stream för att spara bilagan.  
   - `FileOutputStream`: Hanterar skrivning av data till filer med **java file output stream**‑semantik.

## Hur sparar man en bilaga med java file output stream?
Läs in varje `Attachment`‑objekt, öppna ett `FileOutputStream` för målfilen och strömma bilagans byte‑data direkt till disk. Detta tillvägagångssätt skriver den exakta binära payloaden utan någon transformation och garanterar att den sparade filen matchar den ursprungliga bilagan byte‑för‑byte. För stora bilagor, omslut strömmen med en `BufferedOutputStream` för att förbättra genomströmning och minska I/O‑anrop. **BufferedOutputStream** buffrar skrivningar för att reducera antalet I/O‑operationer, vilket förbättrar prestanda för stora filer.

### Vanliga problem och lösningar
- **Saknade beroenden**: Säkerställ att alla Maven‑beroenden är korrekt tillagda.  
- **Fel i filsökvägar**: Dubbelkolla sökvägar för både dokument och utmatningskataloger.  
- **Åtkomstbehörigheter**: Verifiera att din applikation har nödvändiga läs‑/skrivrättigheter.  

## Praktiska tillämpningar
Att använda GroupDocs.Viewer i Java kan vara ovärderligt i olika scenarier:

1. **E‑postklienter** – Extrahera automatiskt bilagor från e‑postarkiv för bearbetning eller arkivering.  
2. **Dokumenthanteringssystem** – Förbättra DMS genom att hämta och organisera inbäddade filer.  
3. **Juridiska avdelningar** – Extrahera bevisrelaterade bilagor från juridiska dokument på ett säkert sätt.  

Integrationsmöjligheter med CRM, ERP eller anpassade arbetsflödesmotorer kan ytterligare effektivisera affärsprocesser, vilket gör bilagehantering sömlös över avdelningar.

## Prestandaöverväganden
För att optimera prestanda när du använder GroupDocs.Viewer:

- **Optimera filhantering** – Använd buffrade strömmar för stora filer och stäng resurser omedelbart.  
- **Minneshantering** – Frigör `Viewer`‑instanser snabbt (try‑with‑resources) för att undvika minnesläckor.  
- **Kvantifierad nytta** – GroupDocs.Viewer kan bearbeta dokument upp till 500 MB och hantera upp till 200 bilagor per fil samtidigt som minnesanvändningen hålls under 150 MB på en standard‑8 GB JVM.

Genom att följa Java‑bästa praxis får du avsevärt förbättrad effektivitet i din bilage‑bearbetningspipeline.

## Slutsats
Du har nu lärt dig hur du hämtar och sparar dokumentbilagor med **java file output stream** i kombination med GroupDocs.Viewer för Java. Detta kraftfulla API förenklar hanteringen av dokumentdata och är ett oumbärligt verktyg för utvecklare som arbetar med digitala dokument. För att utforska GroupDocs.Viewer ytterligare, experimentera med dess andra funktioner—såsom att rendera sidor, konvertera format eller extrahera text. Har du frågor eller behöver support, tveka inte att kontakta de officiella resurserna.

## Vanliga frågor

**Q: Hur installerar jag GroupDocs.Viewer i mitt Java‑projekt?**  
A: Lägg till Maven‑beroendet som visades tidigare; repository‑URL:en och versionen är allt du behöver för en snabb start.

**Q: Klarar GroupDocs.Viewer alla dokumenttyper?**  
A: Det stödjer över 50 in‑ och utdataformat—including PDF, DOCX, PPTX, MSG, och många bildtyper—så de flesta vanliga affärsfiler täcks.

**Q: Vad gör jag om jag får fel när jag sparar bilagor?**  
A: Kontrollera att utmatningssökvägen är korrekt, att katalogen finns och att processen har skrivbehörighet. Säkerställ också att du använder `FileOutputStream` korrekt enligt exemplet.

**Q: Krävs en licens för produktionsbruk?**  
A: Ja, en giltig GroupDocs.Viewer‑licens krävs för produktionsdistribution. En gratis provversion finns för utvärdering.

**Q: Fungerar detta tillvägagångssätt med stora bilagefiler?**  
A: Genom att använda `java file output stream` med buffrad I/O hanteras stora binära filer effektivt; övervaka minnesanvändning och överväg att strömma i delar för filer större än 200 MB.

---

**Senast uppdaterad:** 2026-06-30  
**Testat med:** GroupDocs.Viewer 25.2  
**Författare:** GroupDocs  

---

## Relaterade handledningar

- [Hur man hämtar bilagor och skriver ut dokumentbilagor med GroupDocs.Viewer för Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Rendera dokumentbilagor till HTML med GroupDocs.Viewer Java: En steg‑för‑steg‑guide](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [Anpassad renderingshanterare Java – GroupDocs Viewer‑handledning](/viewer/java/custom-rendering/)