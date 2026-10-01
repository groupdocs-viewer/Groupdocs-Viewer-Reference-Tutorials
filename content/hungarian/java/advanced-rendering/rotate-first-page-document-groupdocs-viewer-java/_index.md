---
date: '2026-09-30'
description: Ismerje meg, hogyan lehet 90 fokkal elforgatni egy oldalt Java-ban a
  GroupDocs Viewer segítségével, beleértve a beállítást, a kódot és a teljesítmény
  tippeket.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Oldal 90 fokos elforgatása Java-ban a GroupDocs Viewer használatával.
  Lépésről‑lépésre útmutató, teljesítmény tippek és valós példák fejlesztőknek.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Oldal 90 fokos elforgatása a GroupDocs Viewer for Java-val
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Oldal 90 fokos elforgatása a GroupDocs Viewer for Java-val
type: docs
url: /hu/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# Oldal 90 fokos elforgatása a GroupDocs Viewer for Java segítségével

Ha egy dokumentumban **oldal 90 fokos elforgatására** van szükség — legyen az PDF, Word fájl vagy táblázat — a Java programozott megoldás időt takarít meg, kiküszöböli a kézi hibákat, és lehetővé teszi a művelet beágyazását automatizált folyamatokba. Ebben a haladó útmutatóban megtanulja, hogyan kell elforgatni egy támogatott dokumentum első oldalát a **GroupDocs Viewer for Java** használatával, miért fontos ez a képesség a valós projektekben, és hogyan tartsa a folyamatot könnyűsúlyú és memóriahatékony.

![Az első oldal elforgatása egy dokumentumban a GroupDocs.Viewer for Java segítségével](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Gyors válaszok
- **Mi jelent a “rotate page 90 degrees”?** Az kiválasztott oldalt egy negyed fordulatot forgatja az óramutató járásával megegyező irányba.  
- **Melyik könyvtár kezeli az elforgatást?** A GroupDocs Viewer for Java biztosítja a `rotatePage` metódust.  
- **Forgathatok PDF oldalakat Java-val?** Igen — használja ugyanazt a `rotatePage` hívást; PDF, DOCX, XLSX és további formátumok esetén is működik.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez használható; a termeléshez fizetett licenc szükséges.  
- **Memóriaigényes a művelet?** Nem, ha a `Viewer` példányt gyorsan bezárja; lásd az alábbi teljesítmény tippeket.

## Mi az a “rotate page 90 degrees”?
Az oldal 90 fokos elforgatása újraorientálja az oldalt álló formátumból fekvő formátumba (vagy fordítva) anélkül, hogy a mögöttes tartalmat megváltoztatná. Ez hasznos prezentációkhoz, csak fekvő tájolású grafikák nyomtatásához, vagy a féloldalas beolvasott dokumentumok korrigálásához, amelyek oldalra lettek rögzítve. Az elforgatás a renderelés során kerül alkalmazásra, az eredeti fájlt változatlanul hagyva.

## Miért érdemes programozottan elforgatni oldalakat a GroupDocs Viewer for Java használatával?
A GroupDocs Viewer **50+ bemeneti és kimeneti formátumot** támogat — beleértve a PDF, DOCX, PPTX, XLSX és számos képformátumot — így bármilyen dokumentumot megjeleníthet külső konvertáló nélkül. Az API folyékony, szálbiztos, és bármely Java 8+ környezetben fut, ami megbízható választássá teszi vállalati szintű automatizáláshoz, amelynek konzisztensen kell kezelnie tucatnyi fájltípust.

## Előfeltételek

- GroupDocs Viewer for Java (legújabb verzió)
- JDK 8 vagy újabb
- Maven (vagy Gradle) a függőségkezeléshez
- IDE, például IntelliJ IDEA vagy Eclipse
- Alapvető ismeretek a Java I/O-val kapcsolatban

## A GroupDocs.Viewer for Java beállítása

Adja hozzá a GroupDocs tárolót és függőséget a `pom.xml` fájlhoz. Ez a kódrészlet változatlan az eredeti útmutatóból:

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

### Licenc beszerzése
- **Free trial** – letöltés a GroupDocs weboldaláról.  
- **Temporary license** – kérje, ha hosszabb értékelési időszakra van szüksége.  
- **Full license** – vásárlás termelési környezethez.

### Alapvető Viewer inicializálás
A `Viewer` osztály a belépési pont, amely betölti a dokumentumot, és elérhetővé teszi a renderelési és transzformációs metódusokat. Tartsa a kódot pontosan úgy, ahogy látható:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Hogyan forgassuk el a PDF oldalt Java-val a GroupDocs Viewer segítségével
Töltse be a célfájlt a `Viewer` segítségével, adja meg az oldalszámot, és hívja meg a `rotatePage` metódust. A metódus PDF, DOCX, PPTX, XLSX és a könyvtár által támogatott bármely más formátum esetén működik. Az elforgatás után a dokumentumot új PDF-be renderelheti vagy közvetlenül a kliensnek streamelheti, biztosítva, hogy az eredeti fájl érintetlen marad.

## Lépésről‑lépésre megvalósítás: az első oldal 90 fokos elforgatása

### 1. A szükséges csomagok importálása
`PdfViewOptions` azt mondja a Viewernek, hogy PDF fájlt generáljon, míg a `Rotation` enum határozza meg a szöget. Mindkét osztály a `com.groupdocs.viewer.options` csomagban található.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Kimeneti helyek definiálása és a Viewer létrehozása
Cserélje le a helyőrző útvonalakat a saját könyvtáraira. A `Viewer` konstruktor egy `File` objektumot fogad, amely a forrásdokumentumra mutat.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. PDF nézet opciók konfigurálása és az elforgatás alkalmazása
A `rotatePage(int, Rotation)` metódus **1‑alapú** oldalkezelést és egy `Rotation` enum értéket vár. Ebben a példában a `Rotation.ON_90_DEGREE` értéket használjuk az első oldal óramutató járásával megegyező irányú elforgatásához.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Dokumentum renderelése
A `view` hívása a konfigurált opciókkal a forgatott PDF-et a kimeneti mappába írja.

```java
viewer.view(viewOptions);
```

#### Hogyan működik
- **PdfViewOptions** a Viewernek PDF kimeneti fájlt generál.  
- **rotatePage(int, Rotation)** csak a megadott oldalt forgatja el, a többi oldal változatlan marad.  
- A metódus három forgatási konstansot támogat: `ON_90_DEGREE`, `ON_180_DEGREE` és `ON_270_DEGREE`.

## Gyakori problémák és megoldások

| Tünet | Valószínű ok | Megoldás |
|---------|--------------|-----|
| **FileNotFoundException** | Helytelen útvonal vagy hiányzó mappa | Ellenőrizze, hogy a `YOUR_OUTPUT_DIRECTORY` és a `YOUR_DOCUMENT_DIRECTORY` létezik és olvasható. |
| **Unsupported file format** | Olyan formátum elforgatásának kísérlete, amelyet a Viewer nem támogat | Ellenőrizze a [GroupDocs Viewer supported formats] oldalt. |
| **No rotation visible** | A hibás oldalszám használata (0‑alapú) | Ne feledje, hogy a `rotatePage` **1‑alapú** indexelést használ. |
| **Out‑of‑memory errors on large docs** | Sok nagy fájl renderelése egyetlen szálban | Feldolgozza a dokumentumokat sorban, vagy használjon korlátozott párhuzamosságú szálkészletet. |

## Gyakorlati alkalmazások

- **Presentation adjustments** – Átalakítja a portré diát helyben fekvő formátumba a jobb vizuális hatás érdekében.  
- **Bulk document correction** – Automatizálja a féloldalas beolvasott PDF-ek javítását, amelyek oldalra lettek rögzítve, órákat takarítva meg a kézi munkában.  
- **Print‑ready output** – Biztosítja, hogy a fekvő grafikák helyesen nyomtatódjanak portré tájolású papírra a nyomtató driverben történő kézi elforgatás nélkül.

## Teljesítmény tippek

- **Close resources promptly** – A `try‑with‑resources` blokk automatikusan felszabadítja a `Viewer` példányt, így memória felszabadul.  
- **Batch processing** – Használjon egyetlen `Viewer` példányt szálanként a kezdeti költségek csökkentéséhez.  
- **Monitor memory** – 100 MB-nál nagyobb dokumentumok esetén streamelje a kimenetet lemezre ahelyett, hogy a teljes fájlt memóriában tartaná; a GroupDocs Viewer 200 MB-os fájlokat képes feldolgozni 250 MB alatti RAM használattal.

## Gyakran ismételt kérdések

**Q: Forgathatok több oldalt egyszerre?**  
A: Igen — hívja meg a `rotatePage()` metódust minden elforgatni kívánt oldalszámra, akár ciklusban, akár láncolt hívásokkal.

**Q: Van mód az elforgatás visszavonására a renderelés után?**  
A: Nem közvetlenül. Újra kell renderelni a dokumentumot a forgatási opciók nélkül.

**Q: Mely fájlformátumok támogatják az oldal elforgatását a GroupDocs Viewerben?**  
A: DOCX, PDF, PPTX, XLSX és számos egyéb formátum, amely a hivatalos dokumentációban szerepel.

**Q: Hogyan forgathatok oldalakat automatikusan egy dokumentumcsoportban?**  
A: Tegye a forgatási logikát egy ciklusba, amely egy fájlútvonalak gyűjteményén iterál, és minden fájlra ugyanazt a `rotatePage` konfigurációt alkalmazza.

**Q: Mi a legjobb gyakorlat a hibakezelésre az elforgatás során?**  
A: A Viewer használatát `try‑catch` blokkba kell helyezni, naplózni a kivétel részleteit, és opcionálisan folytatni a következő fájl feldolgozását, hogy egyetlen hiba ne állítsa le az egész köteg feldolgozását.

## Források

- **Dokumentáció**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API referencia**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Letöltés**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Licenc vásárlása**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Ingyenes próba**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Ideiglenes licenc kérése**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Támogatás**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Legutóbb frissítve:** 2026-09-30  
**Tesztelve a következővel:** GroupDocs Viewer 25.2 for Java  
**Szerző:** GroupDocs

## Kapcsolódó oktatóanyagok

- [Hogyan forgassuk el a konkrét PDF oldalakat a GroupDocs.Viewer for Java segítségével](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Dokumentum betöltése URL-ről Java-ban – GroupDocs.Viewer oktatóanyag](/viewer/java/document-loading/)
- [Groupdocs Viewer Java dokumentum nézetek](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)