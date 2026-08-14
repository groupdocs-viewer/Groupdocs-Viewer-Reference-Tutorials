---
date: '2026-06-15'
description: Ismerje meg, hogyan konvertálhatja az Excelt PDF-re Java-val, és hogyan
  oszthatja fel az Excel munkalapokat sorok és oszlopok szerint a GroupDocs Viewer
  segítségével. Tartalmaz beállítást, kódot és legjobb gyakorlatokat.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Excel konvertálása PDF-re Java-val és munkalapok felosztása sorok és oszlopok
  szerint
type: docs
url: /hu/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel konvertálása PDF-re Java-val és munkalapok felosztása sorok és oszlopok szerint (Java)

A nagy Excel munkafüzetek gyakran több adatot tartalmaznak, mint ami kényelmesen megjeleníthető egyetlen képernyőn vagy nyomtatott oldalon. **convert excel to pdf java** egy gyakori követelmény, amikor statikus, megosztható formátumra van szükség, míg **splitting Excel sheets by rows and columns** megkönnyíti az adatok felhasználását webes vagy nyomtatási elrendezésekben. Ebben az útmutatóban lépésről lépésre bemutatjuk mindkét feladatot a **GroupDocs Viewer for Java** használatával, megmutatjuk, hogyan konfigurálható a lapozás, és elmagyarázzuk a teljesítményre és a hibaelhárításra vonatkozó legjobb gyakorlatokat.

![Excel munkalapok felosztása sorok és oszlopok szerint a GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Excel munkalapok felosztása sorok és oszlopok szerint a GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Gyors válaszok
- **Melyik könyvtárat használják?** GroupDocs Viewer for Java.  
- **Feloszthatok sorok és oszlopok szerint is?** Igen – meghatározhatja a sorok‑oldalanként és oszlopok‑oldalanként értékeket együtt.  
- **Szükségem van licencre?** Egy próbaverzió vagy ideiglenes licenc fejlesztéshez működik; a teljes licenc szükséges a termeléshez.  
- **Milyen kimeneti formátumok támogatottak?** HTML (beágyazott erőforrások) látható; PDF is előállítható ugyanazzal a beállítással.  
- **Szükséges a Maven?** A Maven a javasolt módja a függőségek kezelésének.  
- **Konvertálhatom is az Excelt PDF-re?** Természetesen – csak cserélje a `HtmlViewOptions`-t `PdfViewOptions`-ra, és használja újra ugyanazokat a lapozási beállításokat.

## Mi az a „How to Split Excel”?
Az Excel munkalap felosztása azt jelenti, hogy egyetlen munkalapot több oldalra vagy fájlra osztunk fel egy rögzített sor-, oszlop- vagy mindkettő szám alapján. Ez a technika hasznos, ha oldalas jelentéseket kell készíteni, adatokat be kell ágyazni weboldalakba, vagy nyomtatható szakaszokat kell generálni anélkül, hogy egyszerre betöltené a teljes munkafüzetet.

## Miért használja a GroupDocs Viewer for Java?
A GroupDocs Viewer egyetlen átfutásban dolgozza fel a táblázatokat, és automatikusan lapozza őket, kiküszöbölve a manuális számításokat. **A gyors renderelés egy 250 oldalas XLSX munkafüzetet kevesebb mint 2 másodperc alatt dolgoz fel egy tipikus 2‑magos szerveren**, és **a könyvtár több mint 50 bemeneti és kimeneti formátumot támogat**, beleértve az XLS, XLSX, CSV, PDF és HTML formátumokat. Bármely JVM‑kompatibilis platformon fut—Windows, Linux, macOS, Docker konténerek vagy felhőalapú serverless környezet—így bárhol integrálható, ahol a Java alkalmazása fut.

## Előkövetelmények
- Java 17 vagy újabb telepítve.  
- Egy IDE, például IntelliJ IDEA vagy Eclipse.  
- Maven a függőségkezeléshez.  
- Alapvető Java ismeretek és tapasztalat az Excel fájlkezelésben.

### Szükséges könyvtárak, verziók és függőségek
Adja hozzá a GroupDocs tárolót és a viewer függőséget a `pom.xml`-hez:

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
Szerezzen be egy ingyenes próbaverziót, ideiglenes licencet, vagy vásároljon teljes licencet a [GroupDocs](https://purchase.groupdocs.com/buy) oldalról.

## Hogyan konvertáljuk az Excelt PDF-re Java?
`Viewer` osztály a GroupDocs Viewer központi komponense, amely betölti a dokumentumot, és különböző kimeneti formátumokhoz nyújt renderelési metódusokat. A `SpreadsheetOptions` lehetővé teszi a lapozási beállítások, például a sorok‑oldalanként és oszlopok‑oldalanként értékek szabályozását a táblázat rendereléséhez. Töltse be az Excel fájlt a `new Viewer("source.xlsx")` segítségével, konfigurálja a `SpreadsheetOptions`-t a lapozáshoz, és hívja meg a `viewer.view(pdfOptions, stream)` metódust – ez az egyetlen hívás konvertálja a munkafüzetet PDF-re, miközben betartja a beállított sor/oszlop korlátokat. A konverzió megőrzi a képleteket, képeket és cellastílusokat, egy hiteles PDF másolatot biztosítva a terjesztéshez.

## Hogyan oszthatók fel az Excel munkalapok sorok szerint
A sorok szerinti felosztás egy sor HTML oldalt hoz létre, mindegyik egy rögzített számú sort tartalmaz (pl. 15). Ez a megközelítés ideális irányítópultokhoz, amelyek korlátozott számú rekordot jelenítenek meg nézetenként. A viewer különálló HTML fájlokat generál, például `page_0.html`, `page_1.html` stb., mindegyik a megadott sorok számát tartalmazza. Ez egyszerűvé teszi, hogy csak a szükséges részt töltsük be egy webes felületen, csökkentve a sávszélességet és a renderelési időt.

### Definíció horgony
`Viewer` a GroupDocs Viewer központi osztálya, amely betölti a dokumentumot és irányítja a renderelést a kiválasztott kimeneti formátumba.

### Lépésről‑lépésre megvalósítás

#### 1. lépés: Útvonalak beállítása és a Viewer inicializálása
Először határozza meg, hogy hol legyenek mentve a felosztott oldalak, és hozza létre a `Viewer` példányt a forrás munkafüzethez.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### 2. lépés: Sorok oldalanként beállítása
Adja meg a viewernek, hogy hány sort tartalmazzon egy oldal.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### 3. lépés: Dokumentum renderelése
Végül renderelje a munkafüzetet a meghatározott beállításokkal.

```java
viewer.view(viewOptions);
```

## Hogyan oszthatók fel az Excel munkalapok sorok és oszlopok szerint
Néha egyetlen oldalnak egy sor‑ és oszlopmátrixot kell megjelenítenie (pl. 15 sor × 7 oszlop). Ez teljes irányítást ad az egyes HTML oldalak elrendezése felett. A kapott oldalak egy téglalap alakú cellablokkot mutatnak, például az első oldalon az 1‑15 sorok és A‑G oszlopok, a következő oldalon a 16‑30 sorok és H‑N oszlopok. Ez a rács‑stílusú lapozás hasznos nyomtatható jelentések létrehozásához, amelyek szabványos papírméretekhez illeszkednek.

### Definíció horgony
`SpreadsheetOptions` beállítja, hogy hány sor és oszlop jelenjen meg minden generált oldalon.

### Lépésről‑lépésre megvalósítás

#### 1. lépés: Útvonalak beállítása és a Viewer inicializálása
A beállítás tükrözi a csak soros példát, csak a fájlnév változik.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### 2. lépés: Sorok és oszlopok oldalanként beállítása
Adja meg mindkét dimenziót a rács‑stílusú felosztáshoz.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### 3. lépés: Dokumentum renderelése
Renderelje a ugyanazzal a `view` hívással.

```java
viewer.view(options);
```

## Gyakorlati alkalmazások
- **Generate Excel report Java**: Nagy pénzügyi modelleket alakítson sorozatos, lapozott HTML jelentésekké.  
- **GroupDocs Viewer Excel**: A felosztott oldalakat közvetlenül egy webportálba ágyazza be az interaktív adatfeltárás érdekében.  
- **Render Excel HTML Java**: Szolgáltassa a generált HTML oldalakat servlet vagy Spring kontroller segítségével a gyors kliensoldali rendereléshez.  

## Teljesítmény szempontok
- **Memory usage** – A nagy munkafüzetek jelentős heap memóriát fogyaszthatnak; fontolja meg a JVM `-Xmx` beállítás növelését.  
- **Chunk size** – Válasszon sor/oszlop számokat, amelyek egyensúlyban tartják az oldal méretét és a renderelési sebességet.  
- **Version updates** – Tartsa naprakészen a GroupDocs Viewer‑t a teljesítményjavulások érdekében; a legújabb 25.2 kiadás akár 30 %-kal is növeli a renderelési sebességet a 24.x-hez képest.  

## Gyakori problémák és hibaelhárítás
| Tünet | Valószínű ok | Megoldás |
|---------|--------------|-----|
| `OutOfMemoryError` | Nagyon nagy munkalap renderelése túl sok sor/oldal beállítással | Csökkentse a `countRowsPerPage` értéket vagy növelje a JVM heap-et |
| Blank output files | Helytelen fájlútvonal vagy hiányzó írási jogosultság | Ellenőrizze, hogy az `outputDirectory` létezik és írható |
| HTML resources not loading | `forEmbeddedResources` használata, de a fájlok más alap‑URL‑ről szolgáltatva | Szolgáltassa az egész kimeneti mappát, vagy váltson `forExternalResources`‑ra |

## Gyakran feltett kérdések

**Q: Generálhatok PDF-et HTML helyett?**  
A: Igen. Cserélje a `HtmlViewOptions`-t `PdfViewOptions`-ra, és tartsa meg ugyanazt a `SpreadsheetOptions` konfigurációt.

**Q: Lehetséges a felosztás cellatartalom alapján, nem rögzített sorok/oszlopok szerint?**  
A: A közvetlen tartalom‑alapú felosztás nincs beépítve a GroupDocs Viewer‑be, de előfeldolgozhatja a munkafüzetet Apache POI‑val, hogy a renderelés előtt külön munkalapokat hozzon létre.

**Q: Támogatja a GroupDocs Viewer a régebbi Excel formátumokat (XLS)?**  
A: Természetesen. A viewer kezeli az XLS, XLSX, CSV és egyéb táblázatformátumokat.

**Q: Hogyan ágyazhatom be a generált HTML-t egy Spring MVC nézetbe?**  
A: Szolgáltassa a kimeneti mappát statikus erőforrásként, és hivatkozzon a generált `page_0.html`, `page_1.html` stb. fájlokra a Thymeleaf vagy JSP sablonjaiban.

**Q: Milyen licencre van szükség a kereskedelmi üzembe helyezéshez?**  
A: Teljes termelési licenc szükséges a GroupDocs‑tól; a próbaverziók csak értékelésre szolgálnak.

## Források
- **Dokumentáció**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API referencia**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Letöltés**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Vásárlás**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Ingyenes próba**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Ideiglenes licenc**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Támogatás**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Legutóbb frissítve:** 2026-06-15  
**Tesztelve ezzel:** GroupDocs Viewer 25.2 for Java  
**Szerző:** GroupDocs  

## Kapcsolódó oktatóanyagok

- [Rejtett sorok és oszlopok renderelése Java táblázatokban a GroupDocs.Viewer segítségével](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Üres sorok renderelésének kihagyása Java-ban a GroupDocs.Viewer-rel: Teljesítmény útmutató](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Átfogó útmutató: Excel 2003 XML konvertálása HTML/JPG/PNG/PDF formátumba a GroupDocs.Viewer Java segítségével](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)