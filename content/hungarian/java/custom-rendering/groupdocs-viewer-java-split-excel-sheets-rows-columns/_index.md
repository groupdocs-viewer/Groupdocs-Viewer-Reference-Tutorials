---
date: '2026-01-31'
description: Ismerje meg, hogyan lehet Java-ban a GroupDocs Viewer segítségével Excel-munkalapokat
  sorok és oszlopok szerint felosztani. Ez a lépésről‑lépésre útmutató bemutatja a
  beállítást, a kódot és a legjobb gyakorlatokat.
keywords:
- split Excel sheets Java
- GroupDocs Viewer Java tutorial
- manageable data segments
title: Hogyan osztható fel az Excel munkalap sorok és oszlopok szerint (Java)
type: docs
url: /hu/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

apokat sorok és oszlopok szerint (Java)

A nagy Excel munkafüzetek gyakran több adatot tartalmaznak, mint ami kényelmesen megjeleníthető egyetlen kéott oldalon. Az **Excel felosztönnyíti a megosztást, beágyazást vagy csak a szükséges részek nyomtat és oszlopok szerint a **GroupDocs Viewer** Java verziójával, valamint érintjük aző megjelenítését.

![Excel munkalapok felosztása sorok és oszlopok szerint a GroupDocs.Viewer for Java segítségével](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Gyors válaszok
- **Melyik könyvtárat használják?** GroupDocs Viewer for Java.  
- **Lehet-e sorok és oszlopok szerint is felosztani?** Igen – meghatározhatja a sorok‑oldalanként és oszlopok‑oldalanként értékeket együtt.  
- **Szükség van licencre?** A próbaverzió vagy ideiglenes licenc fejlesztéshez elegendő; a teljes licenc a termeléshez kötelező.  
- **Milyen kimeneti formátumok támogatottak?** A példában HTML (beágyazott erőforrások) látható; PDF is előállítható ugyanazzal a beállítással.  
- **Kell-e Maven? felosztása”?
Az Excel munkalap felosztása azt jelenti, hogy egyetlen munkalapot több oldalra vagy fájlra osztunk fel egy előre meghatározott sor-, oszlop- vagy mindkettő szám alapján. Ez a technika hasznos, ha oldalas jelentéseket kell készíteni, adatokat weboldalakba ágyazni, vagy nyomtatható szakaszokat generálni szeretnénk anélkül, hogy egyszerre betöltenénk az egész munkafüzetet.

## Miért használjuk a GroupDocs Viewer for Java‑t?
- **Gyors renderelés** – natív támogatás XLSX, XLS, CSV és egyebek számára.  
- **Beépített oldalszámozás** – nincs szükség kézi számításokra.  
- **HTML vagy PDF kimenet** – tökéletes webalkalmazásokhoz vagy offline jelentésekhez.  
- **Keresztplatformos** – minden JVM‑kompatibilis környezetben működik.

## Előkövetelmények
- Java 17 vagy újabb telepítve.  
- IDE, például IntelliJ IDEA vagy Eclipse.  
- Maven a függőségkezeléshez.  
- Alapvető Java ismeretek és tapasztalat az Excel fájlok kezelésében.

### Szükséges könyvtárak, verziók és függőségek
Adja hozzá a GroupDocs tárolót és a viewer függőséget a `pom.xml`‑hez:

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

## Hogyan bontsuk szét az Excel munkalapokat sorok szerint

### Áttekintés
A sorok szerinti felosztás lehetővé teszi, hogy HTML oldalak sorozatát hozzuk létre, ahol minden oldal egy előre meghatározott sor számot tartalmaz (pl. 15). Ez ideális irányítópultok számára, amelyek korlátozott számú rekordot jelenítenek meg nézetenkéntlépésre megvalósítás

#### 1. lépés: Útvonalak beállítása és a Viewer inicializálása
Először határozza meg, hogy hová legyenek mentve a felosztott oldalak, és hozza létre a `Viewer` példányt a forrás munkafüzethez.

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
Végül renderelje a munkafüzetet a megadott beállításokkal.

```java
viewer.view(viewOptions);
```

## Hogyan bontsuk szét az Excel munkalapokat sorok és oszlopok szerint

### Áttekintés
Néha egyetlen oldalnak mátrixként kell megjelenítenie sorokat **és** oszlopokat (pl. 15 sor × 7 oszlop). Ez teljes kontrollt ad az egyes HTML oldalak elrendezése felett.

### Lépésről‑lépésre megvalak beállítása és a Viewer inicializálása
A beállítás megegyezik a csak soros példával, csak a fájlnév változik.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### 2. lépés: Sorok ésanként beállítása
Adja meg mindkét dimenziót a rács‑stílusú felosztáshoz.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### 3. lépés: Dokumentum renderelése
Renderelje ugyanazzal a `view` hívással.

```java
viewer.view(options);
```

## Gyakorlati alkalmazások
- **Excel jelentés generálása Java‑ban**: Nagy pénzügyi modelleket alakítson át oldalas HTML jelentések sorozatává.  
- **GroupDocs Viewer Excel**: A felosztott oldalakat közvetlenül egy webportálba ágyazza be az interaktív adatfeltárás érdekében.**: Szolgáltassa a generált HTML oldalensoldali rendereléshez.

## Teljesítménybeli megfontolások
- **Memóriahasználat** – A nagy munkafüzetek jelentős heap memóriát fogyaszthatnak; fontolja meg a JVM `-Xmx` beállításának növelését.  
- **Darabméret** – Válasszon sor-/oszlopszámot, amely egyenselési sebességet.  
- **Verziófrissítések** – Tartsa naprakészen a GroupDocs Viewer‑t a teljesítményjavulások érdekében.

##ibaelhárítás

| Tünet | Valószínű ok | Megoldás |
|-------|--------------|----------|
| `OutOfMemoryError` | Nagyon nagy munkalap renderelése túl sok sorral oldalank` értéket vagy növelje a JVM heap‑et |
| Üres kimeneti fájlok | Helytelen fájlútvonal erőforrások nem töltődnek be | `forEmbeddedResources` használata, de a fájlok más alap‑URL‑ről szolgáltatva | Szolgáltassa az egész kimeneti mappát, vagy váltson `forExternalResources`‑ra |

## Gyakran feltett kérdések

**K: Generálhatok PDF‑et HTML helyett?**  
V: Igen. Cserélje le a `HtmlViewOptions`‑t `PdfViewOptions`‑ra, és tartsa meg ugyanazt a `SpreadsheetOptions` konfigurációt.

**K: Lehetséges‑e a felosztás cellatartalom alapján, nem fix sorok/oszlopok szerint?**  
V: A közvetlen tartalom‑alapú felosztás nincs beépítve a GroupDocs Viewer‑be, de előfeldolgozhatja a munkafüzetet Apache POI‑val, hogy külön munkalapokat hozzon létre a renderelés előtt.

**K: Támogatja‑e a GroupDocs Viewer a régebbi Excel formátumokat (XLS)?**  
V: Teljesen. A viewer kezeli az XLS, XLSX, CSV és egyéb táblázatformátumokat.

**K: Hogyan ágyazhatom be a generált HTML‑t egy Spring MVC nézetbe?**  
 mappát statikus erőforrásként, és hivatkozzon a generált `page_0.html`, `page_1.html` stb. fájlokra a Thymeleaf vagy JSP sablonjaiban.

**K: Milyen licencre van szükség a kereskedelmi üéges a GroupDocs‑t szolgálnak.

## Források
- **Dokumentáció**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API referencia**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Letöltés**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Vásárlás**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Ingyenes próba**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Ideiglenes licenc**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Támogatás**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

**Utoljára frissítve:** 2026-01-31  
**Tesztelve a következővel:** GroupDocs Viewer 25.2 for Java  
**Szerző:** GroupDocs