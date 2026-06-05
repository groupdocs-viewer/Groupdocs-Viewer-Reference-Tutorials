---
date: '2026-06-05'
description: Ismerje meg, hogyan konvertálhatja az Excelt HTML-re, JPG-re, PNG-re
  és PDF-re a GroupDocs.Viewer Java használatával. Ez a lépésről-lépésre útmutató
  bemutatja a beállítást, a renderelési lehetőségeket és a gyakorlati példákat.
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: Hogyan konvertáljunk Excel-t HTML-re, JPG-re, PNG-re és PDF-re a GroupDocs.Viewer
  Java segítségével
type: docs
url: /hu/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# Hogyan konvertáljuk az Excelt HTML-re, JPG-re, PNG-re és PDF-re a GroupDocs.Viewer Java segítségével

Az Excel HTML-re konvertálása gyakori igény, amikor a táblázat adatokat szeretnénk a weben megjeleníteni, miközben megőrzik a sor- és oszlopfejléceket. Ebben az oktatóanyagban megtanulja, hogyan egyszerűsíti a GroupDocs.Viewer for Java a **convert excel to html** folyamatot, valamint hogyan jeleníthető meg ugyanaz a munkafüzet JPG, PNG és PDF formátumokban. Áttekintjük az előfeltételeket, a könyvtár beállítását, és minden megjelenítési forgatókönyvet világos, termelésre kész kódrészletekkel.

## Gyors válaszok
- **Képes a GroupDocs.Viewer Excel-t több formátumba renderelni?** Igen – a HTML, JPG, PNG és PDF alapértelmezés szerint támogatott.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba a teszteléshez működik; a termeléshez állandó licenc szükséges.  
- **Megmaradnak a sor- és oszlopfejlécek?** Állítsa be a `setRenderHeadings(true)` opciót a nézetbeállításokon a megjelenítéshez.  
- **Melyik Java verzió szükséges?** Java 8 vagy újabb; a könyvtár kompatibilis a Java 11, 17 és későbbi verziókkal.  
- **Gyors a konverzió nagy munkafüzetek esetén?** A GroupDocs.Viewer 200 oldalas táblázatot egy másodpercnél gyorsabban képes feldolgozni tipikus szerverhardveren.

## Mi az a “convert excel to html”?
**Convert excel to html** azt jelenti, hogy egy Excel munkafüzetet web‑kész HTML dokumentummá alakítunk, miközben megőrzik az eredeti elrendezést, képleteket és fejléceket. Ez lehetővé teszi a táblázatok zökkenőmentes beágyazását weboldalakba vagy portálokba anélkül, hogy a végfelhasználónak Excelnek kellene lennie.

## Miért használja a GroupDocs.Viewer Java-t Excel megjelenítéshez?
A GroupDocs.Viewer Java támogatja a **50+ bemeneti és kimeneti formátumot**, beleértve a DOCX, XLSX, PPTX, HTML, JPG, PNG és PDF formátumokat. Több száz oldalas munkafüzeteket dolgoz fel anélkül, hogy a teljes fájlt a memóriába töltené, és a konverziós sebesség akár **10 × gyorsabb** is lehet sok nyílt forráskódú alternatívánál. A könyvtár finomhangolt vezérlést is biztosít a megjelenítési beállításokhoz, például a fejlécek láthatósága, az oldalméret és a képminőség.

## Előfeltételek

- **Java Development Kit (JDK) 8+** telepítve és konfigurálva az IDE-jében (IntelliJ IDEA, Eclipse stb.).
- **Maven** a függőségkezeléshez.
- Alapvető ismeretek a Java szintaxisról és a Maven `pom.xml`-ről.
- Aktív **GroupDocs.Viewer Java** licenc (próba vagy állandó).

### Szükséges könyvtárak és függőségek
Add the GroupDocs.Viewer Java dependency to your `pom.xml`:

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

### Környezet beállítása
- Ellenőrizze, hogy a `java -version` 1.8 vagy újabb verziót ad vissza.
- Nyissa meg a kedvenc IDE-jét, és hozzon létre egy Maven projektet.

Kezdjük az implementációba merülés előtt szükséges előfeltételekkel.

![convert Excel files into HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## A GroupDocs.Viewer Java beállítása

### Telepítési információk
Tegye bele a fent bemutatott Maven függőséget a projekt `pom.xml`-jébe. A `mvn clean install` futtatása után a könyvtár elérhető lesz az osztályútvonalon.

### Licenc beszerzési lépések
1. **Free Trial:** Töltse le a próbaverziót a [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) oldalról.  
2. **Temporary License:** Szerezzen ideiglenes licencet a kiterjesztett teszteléshez a [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) oldalról.  
3. **Purchase:** Szerezzen teljes licencet a termeléshez a [GroupDocs Purchase](https://purchase.groupdocs.com/buy) oldalon.

### Alap inicializálás
A `Viewer` osztály minden megjelenítési művelet belépési pontja. Az inicializálása egyszerű:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

Ez létrehozza a `Viewer` példányt, amely egy helyi licencfájlhoz van kötve, és készen áll az Excel fájlok feldolgozására.

## Implementációs útmutató

Az alábbiakban minden megjelenítési célt bemutatunk. Minden formátumnál először **importáljuk a szükséges osztályokat**, majd **beállítjuk a kimeneti könyvtárat**, végül **konfiguráljuk a nézetbeállításokat** a `setRenderHeadings(true)` használatával a sor- és oszlopfejlécek megtartásához.

### Táblázat renderelése HTML-re
**Hogyan konvertálhatok egy Excel munkafüzetet HTML-re a GroupDocs.Viewer Java használatával?**  
Az Excel munkafüzet HTML-re konvertálásához töltse be a fájlt a Viewer-rel, hozzon létre egy HtmlViewOptions példányt, engedélyezze a fejlécek megjelenítését, és hívja meg a view metódust. A folyamat minden munkalapot külön HTML fájlba ír, megőrizve a cellaformázást, képleteket és az eredeti elrendezést a pontos webes megjelenítéshez.

#### Lépésről‑lépésre megvalósítás
**1. Szükséges könyvtárak importálása**  
A HtmlViewOptions beállítja, hogyan renderelődik a munkafüzet HTML-re, lehetővé téve a fejlécek, stílusok és az oldalelrendezés testreszabását.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. Kimeneti könyvtár beállítása**  
Adjon meg egy mappát, ahová a generált HTML oldalak íródnak.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. Viewer inicializálása és beállítások konfigurálása**  
Hozzon létre egy `Viewer` példányt, állítsa be a `setRenderHeadings(true)` opciót, és hívja meg a `view` metódust.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Magyarázat:** A `HtmlViewOptions` szabályozza a HTML kimenetet. A `setRenderHeadings(true)` engedélyezése biztosítja, hogy az első sor és oszlop (általában a fejlécek) megjelenjenek a létrehozott HTML-ben, így az adatok azonnal érthetőek.

### Táblázat renderelése JPG-re
**Hogyan renderelhetek egy Excel munkalapot JPG képként a fejlécekkel együtt?**  
Az Excel munkalap JPG-képpé renderelése magában foglalja a Viewer inicializálását a munkafüzettel, egy JpgViewOptions objektum létrehozását, a renderHeadings true-ra állítását, és a view hívását. A könyvtár rasterizálja az egyes oldalakat a megadott DPI-n, magas felbontású JPG fájlokat hozva létre, amelyek megtartják a táblázat vizuális struktúráját és fejléceit.

#### Lépésről‑lépésre megvalósítás
**1. Szükséges könyvtárak importálása**  
A JpgViewOptions beállítja a munkalapok JPG képekké renderelésének paramétereit, beleértve a DPI-t, a minőséget és a fejlécek láthatóságát.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. Kimeneti könyvtár beállítása**  
Határozza meg, hol tárolódjanak a JPG fájlok.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. Viewer inicializálása és beállítások konfigurálása**  
Hozza létre a viewer-t, állítsa be a fejlécek renderelését, és hajtsa végre a konverziót.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Magyarázat:** A `JpgViewOptions` lehetővé teszi a DPI és a minőség szabályozását. A `setRenderHeadings(true)` használatával a kapott képek megtartják a táblázat fejlécsorait és -oszlopait, ami elengedhetetlen a jelentésekhez és prezentációkhoz.

### Táblázat renderelése PNG-re
**Mi a folyamat az Excel PNG-re konvertálásához, miközben megmaradnak az oszlopfejlécek?**  
PNG képek előállításához egy Excel fájlból használja a Viewer-t a munkafüzet megnyitásához, hozzon létre egy PngViewOptions példányt, engedélyezze a fejlécek renderelését, és hajtsa végre a view-t. A PNG kimenet veszteségmentes minőséget biztosít, megtartva minden cellastílust és fejlécsort, így ideális archiváláshoz vagy további képfeldolgozáshoz.

#### Lépésről‑lépésre megvalósítás
**1. Szükséges könyvtárak importálása**  
A PngViewOptions szabályozza a munkalapok PNG képekké renderelését, veszteségmentes tömörítést és fejlécek beállításait biztosítva.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. Kimeneti könyvtár beállítása**  
Válasszon egy mappát a PNG kimenetnek.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. Viewer inicializálása és beállítások konfigurálása**  
Hozza létre a viewer-t, engedélyezze a fejlécek renderelését, és hívja meg a `view` metódust.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Magyarázat:** A `setRenderHeadings(true)` hívásával a PNG fájlok tartalmazzák az eredeti táblázat fejlécsorait és -oszlopait, megőrizve a kontextust a további felhasználók számára.

### Táblázat renderelése PDF-re
**Hogyan konvertálhatok egy Excel fájlt PDF-re, miközben a sor- és oszlopfejlécek láthatóak?**  
Az Excel PDF-re konvertálása egyszerű: hozza létre a Viewer példányt a forrásfájllal, konfiguráljon egy PdfViewOptions objektumot a fejlécek rendereléséhez, és hívja meg a view-t. A kapott PDF tükrözi a munkafüzet elrendezését, beleértve a sor- és oszlopfejléceket, és vektoros grafikát támogat a tiszta nyomtatáshoz és terjesztéshez.

#### Lépésről‑lépésre megvalósítás
**1. Szükséges könyvtárak importálása**  
A PdfViewOptions meghatározza a PDF generálás paramétereit, például az oldalméretet, margókat és a fejlécek renderelését.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. Kimeneti könyvtár beállítása**  
Adja meg a célmappát a PDF dokumentum számára.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. Viewer inicializálása és beállítások konfigurálása**  
Hozzon létre egy `Viewer` példányt, engedélyezze a fejlécek renderelését, és hajtsa végre a konverziót.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Magyarázat:** A `setRenderHeadings(true)` beállítása a `PdfViewOptions`-on garantálja, hogy az első sor/oszlop megjelenjen a végső PDF-ben, így a dokumentum nyomtatásra vagy archiválásra kész.

## Gyakorlati alkalmazások

Valós életbeli esetek, ahol a **convert excel to html**, **excel to pdf java**, vagy a **convert spreadsheet to image** felbecsülhetetlen értékű:

1. **Üzleti jelentés:** HTML műszerfalak vagy PDF jelentések generálása pénzügyi modellekből manuális másolás‑beillesztés nélkül.  
2. **Adatvizualizáció:** JPG/PNG pillanatképek beágyazása a táblázatokból prezentációkba, biztosítva, hogy a fejlécek azonnali kontextust adjanak a nézőknek.  
3. **Dokumentum archiválás:** Excel munkafüzetek tárolása PDF-ként a megfelelőség érdekében, miközben megmarad az eredeti elrendezés és fejlécek.  
4. **Web portálok:** Táblázatok HTML verzióinak közvetlen kiszolgálása böngészőkben, lehetővé téve az interaktív szűrést JavaScript‑tel.

## Gyakran Ismételt Kérdések

**Q: Konvertálhatok jelszóval védett Excel fájlokat?**  
A: Igen. Adja át a jelszót a `Viewer` konstruktorának, és a könyvtár a megjelenítés előtt feloldja a munkafüzetet.

**Q: Támogatja a GroupDocs.Viewer a makrókkal ellátott munkafüzeteket (.xlsm)?**  
A: Teljes mértékben. A viewer a makrókat adatként kezeli; a megjelenítés során figyelmen kívül hagyja őket, biztosítva a biztonságos konverziót.

**Q: Mi a maximálisan támogatott fájlméret?**  
A: A könyvtár akár **2 GB** méretű fájlokat is képes feldolgozni anélkül, hogy a teljes dokumentumot a memóriába töltené, köszönhetően a streaming architektúrának.

**Q: Lehetséges csak egy adott munkalapot renderelni?**  
A: Igen. Használja a `ViewOptions.setPageNumber(pageIndex)` metódust egyetlen lap célzásához HTML, JPG, PNG vagy PDF generálásakor.

**Q: Hogyan szabályozhatom a JPG kimenet képminőségét?**  
A: Állítsa be a `JpgViewOptions.setQuality(90)` (0‑100 érték) értéket a fájlméret és a vizuális hűség egyensúlyozásához.

## Következtetés

Most már rendelkezik egy teljes, termelésre kész útmutatóval a **convert excel to html**, **excel to pdf java**, és a **convert spreadsheet to image** használatához a GroupDocs.Viewer Java segítségével. A fenti lépések követésével beépítheti a táblázat megjelenítést bármely Java backendbe, HTML jelentéseket, nagy felbontású képeket vagy archiválási PDF-eket szolgáltatva, a fejlécek automatikus megőrzésével.

---

**Utoljára frissítve:** 2026-06-05  
**Tesztelve:** GroupDocs.Viewer Java 23.12  
**Szerző:** GroupDocs

## Kapcsolódó oktatóanyagok

- [Hogyan konvertáljunk DOCX-et HTML-re a GroupDocs.Viewer for Java használatával: Lépésről‑lépésre útmutató](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Reszponzív HTML renderelés a GroupDocs.Viewer for Java-val: Átfogó útmutató](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – ODF konvertálása HTML-re, JPG-re, PNG-re, PDF-re a GroupDocs.Viewer for Java használatával](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)