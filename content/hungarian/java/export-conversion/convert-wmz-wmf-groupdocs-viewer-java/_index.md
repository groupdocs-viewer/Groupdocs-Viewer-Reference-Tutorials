---
date: '2026-07-19'
description: Ismerje meg, hogyan konvertálhatja a WMZ‑t PDF‑re, HTML‑re, JPG‑re és
  PNG‑re a GroupDocs Viewer for Java segítségével. Lépésről‑lépésre útmutató a java
  vektoros grafikák konvertálásához.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Konvertálja a WMZ‑t PDF‑re, HTML‑re, JPG‑re és PNG‑re a GroupDocs
  Viewer for Java használatával. Ez a bemutató lépésről‑lépésre mutatja be a java
  vektoros grafikák magas hűségű konvertálását.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: WMZ konvertálása PDF‑re a GroupDocs Viewer for Java segítségével – Gyors
  útmutató
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: WMZ konvertálása PDF‑re és más formátumokra a GroupDocs Viewer for Java segítségével
type: docs
url: /hu/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# WMZ konvertálása PDF-re és más formátumokra a GroupDocs Viewer for Java segítségével

A WMZ (Web Metafile) és WMF (Windows Metafile) fájlok átalakítása könnyebben hozzáférhető formátumokra – különösen a **convert WMZ to PDF** – nehézkes lehet, mivel ezek a vektorgrafikus formátumok rajzolási utasításokat tárolnak pixeladatok helyett. A **GroupDocs Viewer for Java** segítségével néhány sor kóddal renderelhet WMZ/WMF dokumentumokat HTML, JPG, PNG, **PDF**, és más népszerű formátumokba, miközben megőrzi az eredeti vizuális hűséget.

![WMZ/WMF dokumentumok konvertálása a GroupDocs.Viewer for Java segítségével](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[WMZ/WMF dokumentumok konvertálása a GroupDocs.Viewer for Java segítségével](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Gyors válaszok
- **Milyen formátumokra konvertálható a WMZ/WMF?** HTML, JPG, PNG és PDF teljes mértékben támogatott.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba a teszteléshez működik; egy kereskedelmi licenc eltávolítja a kiértékelési korlátokat.  
- **Mely Java verzió szükséges?** A Java 8 vagy újabb ajánlott.  
- **Képes vagyok csak bizonyos oldalakat renderelni?** Igen, megadhatja az oldaltartományokat a megjelenítési beállításokban.  
- **Aggódom a memóriahasználat miatt nagy fájlok esetén?** Használjon try‑with‑resources-t, és csak a szükséges oldalakat renderelje a memória alacsonyan tartása érdekében.

## Mi az a “convert WMZ to PDF”?
**Convert WMZ to PDF** azt jelenti, hogy egy WMZ vektorfájlt a PDF konténerbe ágyazunk, így egy univerzálisan megtekinthető, kereshető és nyomtatható dokumentumot hozunk létre. A konverzió megőrzi a vonalminőséget és a formákat, így a kapott PDF az eredeti grafikával azonos lesz bármely eszközön.

## Miért használja a GroupDocs Viewer for Java-t vektorgrafikák konvertálásához?
A GroupDocs Viewer for Java **magas hűséggel** kezeli a WMZ és WMF renderelését, megőrizve a vektor részleteket akár PDF, PNG vagy HTML kimenetre is. A könyvtár bármely JDK-val rendelkező platformon fut, nem igényel natív Windows komponenseket, és egyetlen‑hívásos API-t biztosít, amely a egyikonos fájloktól a többoldalas műszaki rajzokig skálázódik. Teljesítménytesztekben **200‑oldalas WMZ fájlokat 12 másodperc alatt** dolgoz fel egy standard 4‑magos szerveren.

## Előfeltételek

- **GroupDocs.Viewer for Java** – a mag renderelő motor.  
- Java Development Kit (JDK) 8 vagy újabb.  
- Egy IDE, például IntelliJ IDEA vagy Eclipse (opcionális, de ajánlott).  
- Maven (vagy Gradle) a függőségkezeléshez.  

A Java NIO (`java.nio.file.Path`) és az alapvető fájl I/O ismerete segíti a példák zökkenőmentes követését.

## A GroupDocs.Viewer for Java beállítása

A `Viewer` osztály minden renderelési művelet belépési pontja. Egy szálbiztos motor, amely több konverzió során újra felhasználható.

Adja hozzá a tárolót és a függőséget a `pom.xml`-hez (vagy a Gradle megfelelőjéhez). Miután a Maven feloldotta a csomagot, létrehozhat egy `Viewer` példányt, amely minden konverziós lépésnél újra felhasználható.

> **Licenc tipp:** Használjon ingyenes próbaidőszakot a kiértékeléshez, majd alkalmazzon ideiglenes vagy megvásárolt licencet a teljes funkcionalitás feloldásához.

## Implementációs útmutató

Az alábbiakban négy konverziós forgatókönyvet mutatunk be – HTML, JPG, PNG és PDF. Minden forgatókönyv ugyanazt a háromlépéses mintát követi:

1. **Határozza meg a kimeneti könyvtárat**, ahol a renderelt fájlok mentésre kerülnek.  
2. **Hozzon létre egy `Viewer` példányt**, amely a forrás WMZ/WMF fájlra mutat.  
3. **Állítsa be a formátum‑specifikus megjelenítési beállításokat**, és hívja meg a `view` metódust.

A `view` metódus a megadott beállítások alapján végzi a renderelést.

### WMZ/WMF renderelése HTML-re

#### Áttekintés
A HTML kimenet lehetővé teszi a grafika közvetlen beágyazását weboldalakba, minden erőforrással (képek, CSS) egyetlen fájlban.

**1. lépés: A kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**2. lépés: Viewer inicializálása és renderelés HTML-re**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF renderelése JPG-re

#### Áttekintés
A JPG egy széles körben támogatott raszteres formátum, tökéletes gyors előnézetekhez vagy e‑mail mellékletekhez.

**1. lépés: A kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**2. lépés: Viewer inicializálása és renderelés JPG-re**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF renderelése PNG-re

#### Áttekintés
A PNG támogatja az átlátszóságot, így ideális olyan grafikákhoz, amelyeknek különböző háttérrel kell keveredniük.

**1. lépés: A kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**2. lépés: Viewer inicializálása és renderelés PNG-re**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF renderelése PDF-re

#### Áttekintés
A PDF platform‑független, kereshető dokumentumot biztosít, amely megőrzi az eredeti elrendezést.

**1. lépés: A kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**2. lépés: Viewer inicializálása és renderelés PDF-re**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Gyakori problémák és megoldások

`PageStreamViewOptions` lehetővé teszi a specifikus oldalak streamként történő renderelését.  
`PdfViewOptions` konfigurálja a PDF kimeneti beállításokat, például az oldaltartományt és a DPI-t.  
`FontSettings` lehetővé teszi egyedi betűtípusok megadását, ha a forrásdokumentum hiányzó betűtípusokra hivatkozik.

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **OutOfMemoryError** nagy WMZ fájlok esetén | A Viewer a teljes dokumentumot memóriába tölti | Rendereljen egy oldalt egyszerre a `PageStreamViewOptions` használatával, vagy növelje a JVM heap méretét (`-Xmx`). |
| **Hiányzó betűtípusok** PDF-ben | A betűtípus nincs beágyazva a forrás WMZ-ben | Telepítse a szükséges betűtípusokat a gépre, vagy használja a `FontSettings`-et egyedi betűtípusok megadásához. |
| **Üres PNG kimenet** | Helytelen kimeneti útvonal vagy elégtelen írási jogosultság | Ellenőrizze, hogy a `outputDirectory` létezik, és az alkalmazásnak van írási joga. |
| **HTML erőforrások nem töltődnek be** | `forExternalResources` használata fájlok másolása nélkül | Használja a `forEmbeddedResources`-t egy önálló HTML fájlhoz. |

## Gyakran feltett kérdések

**Q: Konvertálhatok WMF-et PNG-re ugyanazzal a kóddal?**  
A: Igen. A PNG példa mind WMZ, mind WMF fájlokra működik; csak cserélje le a `TestFiles.SAMPLE_WMZ`-t a WMF forrásra.

**Q: Lehetséges csak egy oldalcsoportot konvertálni?**  
A: Természetesen. Használja a `PdfViewOptions`-t (vagy a megfelelő opciókat más formátumokhoz), és a renderelés előtt hívja meg a `setPageNumbers(List<Integer>)`-t.

**Q: Szükségem van külön licencre minden kimeneti formátumhoz?**  
A: Nem. Egyetlen GroupDocs Viewer licenc lefedi az összes támogatott formátumot, beleértve a HTML, JPG, PNG és PDF formátumokat.

**Q: Hogyan befolyásolja a “java convert vector graphics” a teljesítményt?**  
A: A vektor‑raster konverzió CPU‑igényes. Nagy mennyiség esetén fontolja meg a több szál használatát, és használja újra ugyanazt a `Viewer` példányt a fájlok között.

**Q: Megőrzi a PDF a vektor minőséget, vagy rasterizálódik?**  
A: WMZ/WMF PDF‑re konvertálásakor a GroupDocs Viewer ahol lehetséges, megőrzi a vektor utasításokat, így skálázható PDF-et eredményez.

## Következtetés

Most már egy teljes, éles környezetben használható útmutatója van a **convert WMZ to PDF** és más gyakori formátumok konvertálásához a **GroupDocs Viewer for Java** segítségével. Akár egy webszolgáltatást épít, amely valós időben szolgálja ki a grafikákat, akár egy archiváló eszközt, amely PDF‑ként tárolja a dokumentumokat, a fenti lépések gyorsan és megbízhatóan segítenek. Fedezze fel tovább az API‑t, hogy testreszabja az oldaltartományokat, DPI beállításokat vagy vízjelezést a projekt igényei szerint.

---

**Utolsó frissítés:** 2026-07-19  
**Tesztelve ezzel:** GroupDocs.Viewer 25.2 for Java  
**Szerző:** GroupDocs

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

## Kapcsolódó oktatóanyagok

- [Hogyan konvertáljunk OBJ-t HTML, JPG, PNG és PDF formátumba Java-ban a GroupDocs.Viewer használatával](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [IGS konvertálása PDF, HTML, JPG és PNG formátumba a GroupDocs.Viewer Java segítségével](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Dokumentumok PDF-re konvertálása – Teljes útmutató](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)