---
date: '2026-02-18'
description: Ismerje meg, hogyan konvertálhat WMZ és WMF fájlokat PDF, HTML, JPG és
  PNG formátumba a GroupDocs Viewer for Java segítségével. Ez az útmutató a GroupDocs
  Viewer Java és a Java vektorgrafika konvertálás témakörét fedi le.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Hogyan konvertáljunk WMZ-t PDF-re és más formátumokra a GroupDocs Viewer for
  Java segítségével
type: docs
url: /hu/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

er 25.2 for Java"

"**Author:** GroupDocs" => "**Szerző:** GroupDocs"

Now ensure we keep all markdown formatting.

Also note "###" headings etc.

Check for any other shortcodes: none.

Now produce final content.# Hogyan konvertáljunk WMZ-et PDF-be és más formátumokra a GroupDocs Viewer for Java segítségével

Converting WMZ (Web Metafile) and WMF (Windows Metafile) files to more accessible formats—especially **convert WMZ to PDF**—can be tricky because these vector graphic formats store drawing instructions rather than pixel data. With **GroupDocs Viewer for Java**, you can render WMZ/WMF documents to HTML, JPG, PNG, **PDF**, and other popular formats in just a few lines of code.

![WMZ/WMF dokumentumok konvertálása a GroupDocs.Viewer for Java segítségével](/viewer/export-conversion/convert-wmz-wmf-documents.png)

In this tutorial you’ll learn how to set up the library, render WMZ/WMF files to the desired output, and handle common pitfalls. By the end, you’ll be able to integrate **groupdocs viewer java** into your Java applications to **java convert vector graphics** quickly and reliably.

## Gyors válaszok
- **Milyen formátumokra konvertálható a WMZ/WMF?** HTML, JPG, PNG és PDF teljes körűen támogatott.  
- **Szükségem van licencre a fejlesztéshez?** Az ingyenes próba a teszteléshez megfelelő; egy kereskedelmi licenc eltávolítja a kiértékelési korlátokat.  
- **Melyik Java verzió szükséges?** A Java 8 vagy újabb ajánlott.  
- **Renderelhetek csak meghatározott oldalakat?** Igen, a nézetbeállításokban megadhatja az oldaltartományokat.  
- **Nagy fájlok esetén aggály a memóriahasználat?** Használjon try‑with‑resources-t, és rendereljen csak a szükséges oldalakat a memória alacsonyan tartása érdekében.

## Mi az a „WMZ PDF-be konvertálása”?
A WMZ PDF-be konvertálása azt jelenti, hogy a vektoralapú WMZ fájlt rasterizáljuk (vagy megőrizzük vektoradatait) egy PDF konténerben. A PDF univerzálisan megtekinthető, kereshető és nyomtatható, így ideális a WMZ grafikák archiválásához és megosztásához.

## Miért használjuk a GroupDocs Viewer for Java-t vektorgrafikák konvertálásához?
- **Magas hűség**: A könyvtár megőrzi az eredeti rajzminőséget, akár PDF-be, akár PNG-be exportál.  
- **Nulla külső függőség**: Nem szükséges natív Windows könyvtár; minden JDK-val rendelkező platformon fut.  
- **Egyszerű API**: Egy `Viewer` példány és egyetlen `view` hívás kezeli a teljes konverziót.  
- **Skálázható**: Egyoldalas ikonok és többoldalas műszaki rajzok esetén egyaránt jól működik.

## Előkövetelmények

### Szükséges könyvtárak
- **GroupDocs.Viewer for Java** – a magrenderelő motor.  
- Java Development Kit (JDK) 8+.

### Környezet beállítása
- IDE, például IntelliJ IDEA vagy Eclipse.  
- Maven a függőségkezeléshez (vagy Gradle, ha azt részesíti előnyben).

### Tudás előkövetelmények
- Ismeret a Java fájl I/O-val (`java.nio.file.Path`).  
- Alapvető megértés arról, hogyan renderelnek a dokumentumnézők tartalmat.

## A GroupDocs.Viewer for Java beállítása

Add the repository and dependency to your `pom.xml`:

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

> **Licenc tipp:** Használjon ingyenes próbaverziót a kiértékeléshez, majd alkalmazzon ideiglenes vagy megvásárolt licencet a teljes funkcionalitás feloldásához.

Once the dependency is resolved, you can create a `Viewer` instance that will be reused for each conversion step.

## Implementációs útmutató

We'll walk through four conversion scenarios: HTML, JPG, PNG, and PDF. Each example follows the same pattern—define an output path, instantiate `Viewer` with the source WMZ file, configure the appropriate view options, and call `view`.

### WMZ/WMF renderelése HTML-be

#### Áttekintés
A HTML kimenet lehetővé teszi a grafika közvetlen beágyazását weboldalakba, minden erőforrás (képek, CSS) egyetlen fájlban tárolva.

**1. lépés: Kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**2. lépés: Viewer inicializálása és renderelés HTML-be**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF renderelése JPG-be

#### Áttekintés
A JPG egy széles körben támogatott raszter formátum, tökéletes gyors előnézetekhez vagy e‑mail mellékletekhez.

**1. lépés: Kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**2. lépés: Viewer inicializálása és renderelés JPG-be**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF renderelése PNG-be

#### Áttekintés
A PNG támogatja az átlátszóságot, így ideális olyan grafikákhoz, amelyeknek különböző háttérrel kell keveredniük.

**1. lépés: Kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**2. lépés: Viewer inicializálása és renderelés PNG-be**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF renderelése PDF-be

#### Áttekintés
A PDF platformfüggetlen, kereshető dokumentumot biztosít, amely megőrzi az eredeti elrendezést.

**1. lépés: Kimeneti könyvtár útvonalának meghatározása**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**2. lépés: Viewer inicializálása és renderelés PDF-be**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **OutOfMemoryError** nagy WMZ fájlok esetén | A Viewer betölti a teljes dokumentumot a memóriába | Rendereljen egy oldalt egyszerre a `PageStreamViewOptions` használatával, vagy növelje a JVM heap méretét (`-Xmx`). |
| **Hiányzó betűkészletek** a PDF-ben | A betűkészlet nincs beágyazva a forrás WMZ-ben | Telepítse a szükséges betűkészleteket a gépre, vagy használja a `FontSettings`-et egyedi betűkészletek megadásához. |
| **Üres PNG kimenet** | Helytelen kimeneti útvonal vagy elégtelen írási jogosultság | Ellenőrizze, hogy az `outputDirectory` létezik, és az alkalmazásnak van írási joga. |
| **HTML erőforrások nem töltődnek** | `forExternalResources` használata fájlok másolása nélkül | Maradjon a `forEmbeddedResources` mellett egy önálló HTML fájlhoz. |

## Gyakran ismételt kérdések

**K: Konvertálhatom a WMF-et PNG-be ugyanazzal a kóddal?**  
V: Igen. A PNG példa mind WMZ, mind WMF fájlokra működik; csak cserélje le a `TestFiles.SAMPLE_WMZ`-t a WMF forrásra.

**K: Lehetséges csak egy oldalcsoportot konvertálni?**  
V: Természetesen. Használja a `PdfViewOptions`-t (vagy a megfelelő opciókat más formátumokhoz), és a renderelés előtt hívja meg a `setPageNumbers(List<Integer>)`-t.

**K: Szükségem van külön licencre minden kimeneti formátumhoz?**  
V: Nem. Egyetlen GroupDocs Viewer licenc lefedi az összes támogatott formátumot, beleértve a HTML, JPG, PNG és PDF formátumokat.

**K: Hogyan befolyásolja a „java konvertálja a vektorgrafikákat” a teljesítményt?**  
V: A vektor‑raszter konverzió CPU‑igényes. Nagy mennyiség esetén fontolja meg a több szálas feldolgozást és egyetlen `Viewer` példány újrahasználatát a fájlok között.

**K: A PDF megőrzi a vektor minőséget, vagy rasterizálódik?**  
V: WMZ/WMF PDF-be konvertálásakor a GroupDocs Viewer ahol lehetséges, megőrzi a vektor utasításokat, így skálázható PDF-et eredményez.

## Következtetés

Most már rendelkezik egy teljes, termelésre kész útmutatóval a **WMZ PDF-be konvertálásához** és más gyakori formátumokhoz a **GroupDocs Viewer for Java** segítségével. Akár egy olyan webszolgáltatást épít, amely valós időben szolgálja ki a grafikákat, akár egy archiváló eszközt, amely PDF‑ként tárolja a dokumentumokat, a fenti lépések gyorsan segítenek elérni a célt.

---

**Utolsó frissítés:** 2026-02-18  
**Tesztelve a következővel:** GroupDocs.Viewer 25.2 for Java  
**Szerző:** GroupDocs