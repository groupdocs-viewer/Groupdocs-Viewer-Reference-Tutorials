---
date: '2026-04-01'
description: Ismerje meg, hogyan lehet a CAD rajzokat csempékre bontani a GroupDocs
  Viewer for Java használatával, ezáltal növelve a renderelési teljesítményt és egyszerűsítve
  a nagy fájlok kezelését.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Hogyan oszthatjuk fel a CAD rajzokat csempékre a GroupDocs Viewerrel
type: docs
url: /hu/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Hogyan oszthatók fel a CAD rajzok csempékre a GroupDocs Viewer segítségével

Ha kíváncsi vagy **hogyan lehet felosztani a CAD** fájlokat kisebb, könnyebben kezelhető darabokra, jó helyen jársz. Ebben az útmutatóban lépésről‑lépésre bemutatjuk, hogyan lehet nagy CAD rajzokat csempékre bontani a **GroupDocs Viewer for Java** segítségével. A végére egy kész megoldásod lesz, amely javítja a renderelés sebességét, csökkenti a memóriahasználatot, és egyszerűbbé teszi a rajzok megjelenítését web‑ vagy mobilalkalmazásokban.

![CAD rajzok felosztása a GroupDocs.Viewer for Java-val](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Gyors válaszok
- **Miért hasznos a „CAD felosztása”?** Egy hatalmas rajzot kisebb képekre (csempékre) bont, amelyek gyorsabban töltődnek be és kevesebb memóriát fogyasztanak.  
- **Milyen formátumot használnak a csempékhez?** Alapértelmezés szerint PNG fájlok jönnek létre, de más formátumok is támogatottak a Viewer beállításain keresztül.  
- **Szükségem van licencre?** A fejlesztéshez egy ingyenes próba verzió működik; a termeléshez fizetett licenc szükséges.  
- **Módosíthatom a csempe méretét?** Igen – állítsa be a `tileWidth` és `tileHeight` számításokat igényei szerint.  
- **Ez a megközelítés szálbiztos?** Minden csempe renderelése saját `Viewer` példányban a try‑with‑resources használatával biztonságos a párhuzamos végrehajtás során.

## Mi a „CAD felosztása”?
A CAD felosztása egyetlen, gyakran hatalmas CAD rajz több téglalap alakú részre (csempére) bontását jelenti. Minden csempe önállóan kerül renderelésre, lehetővé téve, hogy csak a felhasználó által ténylegesen szükséges részeket töltse be – tökéletes webes térképekhez, dokumentumportálokhoz és mobil nézőkhöz.

## Miért használjuk a GroupDocs Viewer for Java-t?
A GroupDocs Viewer készre kész támogatást nyújt több mint 100 fájlformátumhoz, többek között a DWG, DXF és DWF formátumokhoz. A csempe API lehetővé teszi a pontos koordináták megadását, így a teljes fájl előfeldolgozása nélkül renderelheti a kívánt területet. Ez CPU‑ciklusokat takarít meg, csökkenti a sávszélesség használatát, és simább felhasználói élményt biztosít.

## Előfeltételek
- **Könyvtárak**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Bármely friss Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse vagy más Java‑kompatibilis IDE.  
- **Build eszköz**: Maven (más build eszközök is működnek, amíg a függőség hozzá van adva).  

## A GroupDocs.Viewer for Java beállítása
Adja hozzá a GroupDocs tárolót és függőséget a `pom.xml` fájlhoz:

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
A GroupDocs.Viewer ingyenes próba licencet kínál értékeléshez:

- **Ingyenes próba**: Látogassa meg a [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) oldalt a könyvtár letöltéséhez.  
- **Ideiglenes licenc**: Jelentkezzen a [Temporary License Page](https://purchase.groupdocs.com/temporary-license/) oldalon.  
- **Teljes licenc**: Vásároljon termelési licencet a [Purchase Page](https://purchase.groupdocs.com/buy) oldalon.  

### Alap inicializálás
Hozzon létre egy egyszerű `Viewer` példányt, hogy ellenőrizze, a könyvtár helyesen betöltődik‑e:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Lépésről‑lépésre útmutató a CAD rajzok csempékre bontásához

### 1. lépés: A kimeneti könyvtár meghatározása
Minden csempét külön PNG fájlként tárolunk. Egy segédmetódus használata tisztán és újrahasználhatóan tartja az útvonal logikát.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### 2. lépés: Nézet beállítások konfigurálása
Állítsa be a renderelési formátumot PNG‑re, és mondja meg a viewernek, hogy ne töltse be előre az összes oldalt (ez memóriát takarít meg).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### 3. lépés: Csempe méretek kiszámítása
Először megkapjuk a rajz eredeti szélességét és magasságát, majd négy egyenlő kvadrántra osztjuk.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### 4. lépés: A csempék renderelése és mentése
Adja hozzá a kiszámított csempéket a renderelési beállításokhoz, és hagyja, hogy a `Viewer` generálja a PNG fájlokat.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Hibaelhárítási tippek
- **Build útvonal** – Győződjön meg róla, hogy a GroupDocs JAR fájlok a classpath‑on vannak.  
- **Jogosultságok** – A kimeneti mappának írhatóvá kell tennie a Java folyamat számára.  
- **Kivételek** – Ha `ViewerException`‑t lát, ellenőrizze, hogy a DWG fájl nem sérült, és a megfelelő licenc van alkalmazva.

## Gyakori felhasználási esetek a CAD csempék felosztásához
1. **Webes térképezés** – Töltse be csak a látható részt egy alaprajzból, ahogy a felhasználó pásztáz vagy nagyít.  
2. **Dokumentumkezelés** – Tárolja a csempéket külön‑külön a gyorsabb előnézet generálás érdekében.  
3. **Mobil megtekintés** – Csökkentse a sávszélességet, ha csak a jelenlegi képernyőhöz szükséges csempéket tölti le.

## Teljesítmény szempontok
- **Csempe méret** – A nagyobb csempék kevesebb fájlt jelentenek, de lassabb renderelést; találjon egy egyensúlyt a felhasználói felület igényei alapján.  
- **Memória figyelés** – Használja a Java profilozó eszközeit (pl. VisualVM) a heap használat megfigyelésére nagyon nagy rajzok feldolgozásakor.  
- **Erőforrás tisztítás** – A fent bemutatott try‑with‑resources minta automatikusan felszabadítja a natív erőforrásokat.

## Gyakran ismételt kérdések

**Q: Más fájltípusokat (PDF, képek) is fel lehet osztani csempékre ugyanazzal a megközelítéssel?**  
A: Igen. A GroupDocs Viewer sok formátumot támogat; csak a megfelelő opciós osztályt kell használni (pl. `PdfViewOptions`).

**Q: Hogyan változtathatom meg a kimeneti kép minőségét?**  
A: Állítsa be a `viewOptions.setResolution(int dpi)` értéket, vagy állítson be tömörítési beállításokat a `PngOptions` objektumon.

**Q: Az alkalmazásom memóriakimerülést okoz nagyon nagy DWG fájlok esetén – mit tehetek?**  
A: Csökkentse a csempe méreteket, növelje a JVM heap méretét (`-Xmx`), vagy renderelje a csempéket sorban külön `Viewer` példányokban.

**Q: Lehet aszinkron módon renderelni a csempéket?**  
A: Természetesen. Csomagolja minden csempe renderelési hívást egy `CompletableFuture`‑be, vagy használjon executor szolgáltatást a feladat párhuzamosításához.

**Q: Szükségem van külön licencre minden egyes csempéhez?**  
A: Nem. Egyetlen érvényes GroupDocs Viewer licenc lefedi az összes renderelési műveletet az alkalmazásban.

## Források
- [Dokumentáció](https://docs.groupdocs.com/viewer/java/)
- [API referencia](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer letöltése](https://releases.groupdocs.com/viewer/java/)
- [Licenc vásárlása](https://purchase.groupdocs.com/buy)
- [Ingyenes próba](https://releases.groupdocs.com/viewer/java/)
- [Ideiglenes licenc](https://purchase.groupdocs.com/temporary-license/)
- [Támogatási fórum](https://forum.groupdocs.com/c/viewer/9)

---

**Legutóbb frissítve:** 2026-04-01  
**Tesztelve ezzel:** GroupDocs.Viewer 25.2 for Java  
**Szerző:** GroupDocs