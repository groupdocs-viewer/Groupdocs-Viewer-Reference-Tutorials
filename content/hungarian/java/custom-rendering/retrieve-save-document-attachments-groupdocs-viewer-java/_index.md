---
date: '2026-06-30'
description: Ismerje meg, hogyan lehet hatékonyan lekérni és menteni a dokumentum
  mellékleteket Java alkalmazásokban java file output stream és a hatékony GroupDocs.Viewer
  API használatával.
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
title: Hogyan lehet lekérni és menteni a dokumentum mellékleteket java file output
  stream használatával a GroupDocs.Viewer for Java segítségével
type: docs
url: /hu/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# Hogyan lehet lekérni és menteni a dokumentum mellékleteket java file output stream használatával a GroupDocs.Viewer for Java segítségével

## Bevezetés

Szeretné programozottan kinyerni és kezelni a dokumentum mellékleteket Java alkalmazásaiban a **java file output stream** használatával? A digitális dokumentumkezelés növekedésével elengedhetetlen, hogy hatékony eszközök álljanak rendelkezésre ezeknek a folyamatoknak a leegyszerűsítésére. Itt jön képbe a GroupDocs.Viewer for Java – az Ön megoldása a dokumentum mellékletek zökkenőmentes lekéréséhez és mentéséhez.

![Dokumentum mellékletek lekérése és mentése a GroupDocs.Viewer for Java segítségével](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[Dokumentum mellékletek lekérése és mentése a GroupDocs.Viewer for Java segítségével](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

Ebben az útmutatóban bemutatjuk, hogyan használhatja a GroupDocs.Viewer erejét a mellékletek lekérésére a dokumentumokból, és azok mentésére a kívánt könyvtárba. A lépéseket követve gyakorlati tudást szerez a dokumentumadatok hatékony kezeléséről Java környezetben, és pontosan megmutatjuk, **hogyan menthetünk melléklet** fájlokat a szabványos `java file output stream` segítségével.

## Gyors válaszok
- **What does java file output stream do?** Byte áramokat ír közvetlenül fájlokba, lehetővé téve a bináris adatok (például mellékletek) lemezre mentését.  
- **Which API retrieves attachments?** `Viewer.getAttachments()` egy listát ad vissza a melléklet metaadatairól.  
- **Can I specify the output folder?** Igen — használja a `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");` kifejezést.  
- **Do I need a license?** Egy ingyenes próbaidőszak elegendő a kiértékeléshez; a termeléshez fizetett licenc szükséges.  
- **Is this approach thread‑safe?** Hozzon létre külön `Viewer` példányt szálanként, vagy szinkronizálja a hozzáférést.

## Mi az a java file output stream?
`java.io.FileOutputStream` egy alapvető Java osztály, amely nyers bájtokat ír egy fájlba. Ideális választás, ha bináris tartalmat kell tartósan tárolni, például e‑mail mellékleteket, képeket vagy bármilyen nem szöveges adatot, amelyet egy dokumentumból nyertünk ki. Képes kis és nagy fájlok hatékony írására, és kombinálható pufferelt áramokkal a jobb teljesítmény érdekében, biztosítva a bináris payloadok megbízható lemezre írását.

## Miért használjuk a java file output stream-et a GroupDocs.Viewer-rel?
A `java.io.FileOutputStream` és a GroupDocs.Viewer együttes használata lehetővé teszi a fejlesztők számára, hogy a melléklet bájtjait közvetlenül a lemezre írják, anélkül, hogy köztes konverziós lépésekre lenne szükség, ezáltal megőrizve az eredeti fájl integritását. Ez a megközelítés csökkenti a memóriahasználatot, felgyorsítja a nagy mellékletek feldolgozását, és egyszerűsíti a kódot a standard Java I/O és a GroupDocs.Viewer erőteljes kinyerési képességei kombinálásával.

- **Direct binary handling** – Nincs szükség köztes konverziókra; a melléklet bájtjai pontosan úgy kerülnek írásra, ahogy a forrásfájlban szerepelnek.  
- **Performance** – A streamelt írás minimalizálja a memóriaigényt, különösen nagy mellékletek esetén.  
- **Simplicity** – Az API tisztán integrálódik a standard Java I/O-val, így a kód könnyen olvasható és karbantartható.

## Előfeltételek
- **Required Libraries and Dependencies**: Adja hozzá a GroupDocs.Viewer könyvtárat a projektjéhez (lásd a Maven kódrészletet alább).  
- **Environment Setup**: Java IDE (IntelliJ IDEA, Eclipse, stb.) JDK 8+ telepítéssel.  
- **Knowledge Prerequisites**: Ismerje a Java I/O-t, különösen a `FileOutputStream`-ot, valamint az alapvető Maven használatot.

## A GroupDocs.Viewer beállítása Java-hoz
A GroupDocs.Viewer API használatához a projektben Maven‑en keresztül kell telepíteni. Adja hozzá a következő konfigurációt a `pom.xml` fájlhoz:

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

**Licenc megszerzési lépések:**
- **Free Trial**: Kezdje egy ingyenes próbaidőszakkal a funkciók felfedezéséhez.  
- **Temporary License**: Szerezzen ideiglenes licencet a meghosszabbított kiértékeléshez.  
- **Purchase**: Termelésben a vásárolt licenc szükséges.

### Alapvető inicializálás és beállítás
Miután a GroupDocs.Viewer függőségként felkerült a projektbe, inicializálja azt Java‑alkalmazásában. Így néz ki:

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

Ez az alapbeállítás inicializálja a GroupDocs.Viewer‑t, és felkészíti a mellékletek lekérésére.

## Megvalósítási útmutató

### Mellékletek lekérése java file output stream használatával
Ismerje meg, hogyan kérheti le a mellékleteket a GroupDocs.Viewer‑rel. Ez a funkció lehetővé teszi, hogy kinyerje az egyes mellékletek metaadatait a dokumentumból.

#### Áttekintés
A mellékletek lekérése a `getAttachments` metódus hívásával történik, amely `Attachment` objektumok listáját adja vissza, a fájlnév és méret információkkal. Az **Attachment** egy a forrásdokumentumba beágyazott fájlt jelöl, például képet vagy beágyazott fájlt.

#### Megvalósítási lépések
1. **Create a Viewer Instance**  
   A `Viewer` a GroupDocs.Viewer fő osztálya, amely betölti és feldolgozza a dokumentumokat megjelenítés és kinyerés céljából. Inicializálja a `Viewer` osztályt a dokumentum elérési útjával:

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

2. **Retrieve Attachments**  
   Hívja meg a `getAttachments` metódust:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Understanding Parameters and Methods**  
   - `Viewer`: Fájlútvonalat vagy streamet vesz a dokumentumhoz.  
   - `getAttachments()`: Listát ad vissza a csatolt fájlokról, részletekkel, például nevekkel.

### Dokumentum mellékletek mentése könyvtárba
Miután megtanulta a mellékletek lekérését, mentse őket a kívánt könyvtárba a GroupDocs.Viewer API és a **java file output stream** segítségével.

#### Áttekintés
Ez a funkció minden lekért melléklet fájlt egy megadott kimeneti könyvtárba ment.

#### Megvalósítási lépések
1. **Define the Output Directory**  
   Állítson be egy `outputDirectory` útvonalat, ahová a fájlok mentésre kerülnek:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Save Attachments**  
   Használjon egy ciklust, amely minden mellékletet a `saveAttachment` metódussal ment. A **saveAttachment** a `Attachment` bináris tartalmát egy megadott `OutputStream`‑be írja.

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

3. **Explain Parameters and Methods**  
   - `saveAttachment`: Egy `Attachment` objektumot és egy fájl‑output streamet vesz a melléklet mentéséhez.  
   - `FileOutputStream`: Az **java file output stream** szemantika szerint kezeli az adatok fájlba írását.

## Hogyan menthetünk mellékletet java file output stream használatával?
Töltse be az egyes `Attachment` objektumot, nyisson egy `FileOutputStream`‑et a célfájlhoz, és streamelje a melléklet bájtjait közvetlenül a lemezre. Ez a megközelítés a pontos bináris payloadot írja átformálás nélkül, és garantálja, hogy a mentett fájl bájt‑bájt egyezik az eredeti melléklettel. Nagy mellékletek esetén csomagolja a streamet egy `BufferedOutputStream`‑be a throughput javítása és az I/O hívások csökkentése érdekében. A **BufferedOutputStream** puffereli az írásokat, csökkentve az I/O műveletek számát, ezáltal javítva a nagy fájlok teljesítményét.

### Gyakori problémák és megoldások
- **Missing Dependencies**: Győződjön meg róla, hogy minden Maven függőség helyesen hozzá lett adva.  
- **File Path Errors**: Ellenőrizze a dokumentumok és a kimeneti könyvtárak útvonalait.  
- **Access Permissions**: Bizonyosodjon meg arról, hogy az alkalmazásnak megfelelő olvasási/írási jogosultságai vannak.  

## Gyakorlati alkalmazások
A GroupDocs.Viewer Java‑ban számos szituációban felbecsülhetetlenül hasznos:

1. **Email Clients** – Automatikusan kinyerheti a mellékleteket e‑mail archívumokból feldolgozás vagy archiválás céljából.  
2. **Document Management Systems** – A DMS‑t kiegészítheti a mellékletek lekérésével és rendszerezésével.  
3. **Legal Departments** – Biztonságosan kinyerheti a bizonyíték‑kapcsolódó mellékleteket jogi dokumentumokból.  

Az integráció CRM‑mel, ERP‑vel vagy egyedi munkafolyamat‑motorokkal tovább egyszerűsítheti az üzleti folyamatokat, így a mellékletkezelés zökkenőmentes minden osztályban.

## Teljesítmény szempontok
A GroupDocs.Viewer használatakor a teljesítmény optimalizálása érdekében:

- **Optimize File Handling** – Nagy fájlok esetén használjon pufferelt streamet, és zárja le a forrásokat időben.  
- **Memory Management** – Zárja le a `Viewer` példányokat gyorsan (try‑with‑resources), hogy elkerülje a memória‑szivárgásokat.  
- **Quantified Benefit** – A GroupDocs.Viewer akár 500 MB‑os dokumentumokat is képes feldolgozni, és fájlonként akár 200 mellékletet kezelni, miközben a memóriahasználat 150 MB alatt marad egy standard 8 GB JVM‑en.

A Java legjobb gyakorlatait követve jelentősen növelheti a melléklet‑feldolgozó csővezeték hatékonyságát.

## Összegzés
Most már megismerte, hogyan lehet lekérni és menteni a dokumentum mellékleteket **java file output stream** használatával a GroupDocs.Viewer for Java segítségével. Ez a hatékony API leegyszerűsíti a dokumentumadatok kezelését, és elengedhetetlen eszköz a digitális dokumentumokkal dolgozó fejlesztők számára. A GroupDocs.Viewer további funkcióinak felfedezéséhez kísérletezzen más lehetőségekkel – például oldalak renderelésével, formátumok konvertálásával vagy szöveg kinyerésével. Ha kérdése van vagy támogatásra van szüksége, forduljon a hivatalos forrásokhoz.

## Gyakran Ismételt Kérdések

**Q: How do I install GroupDocs.Viewer in my Java project?**  
A: Add the Maven dependency shown earlier; the repository URL and version are all you need for a quick start.

**Q: Can GroupDocs.Viewer handle all document types?**  
A: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG, and many image types—so most common business files are covered.

**Q: What if I encounter errors while saving attachments?**  
A: Verify that the output path is correct, the directory exists, and your process has write permissions. Also ensure you’re using `FileOutputStream` correctly as shown.

**Q: Is a license required for production use?**  
A: Yes, a valid GroupDocs.Viewer license is required for production deployments. A free trial is available for evaluation.

**Q: Does this approach work with large attachment files?**  
A: Using `java file output stream` with buffered I/O efficiently handles large binaries; monitor memory usage and consider streaming in chunks for files larger than 200 MB.

---

**Last Updated:** 2026-06-30  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs  

---

## Kapcsolódó oktatóanyagok

- [How to Retrieve Attachments and Print Document Attachments with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Render Document Attachments into HTML Using GroupDocs.Viewer Java: A Step‑By‑Step Guide](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [Custom Rendering Handler Java – GroupDocs Viewer Tutorial](/viewer/java/custom-rendering/)