---
date: '2026-02-23'
description: Tanulja meg, hogyan állíthatja be az egy oldalra jutó elemek számát,
  hogyan ágyazhat be HTML‑erőforrásokat, és hogyan konvertálhat kötegelt módon archívumokat
  egyoldalas vagy többoldalas HTML‑re a GroupDocs.Viewer Java használatával.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Állítsa be az oldalankénti elemek számát: Archivumok konvertálása HTML-be
  a GroupDocs.Viewer Java-val'
type: docs
url: /hu/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Elemek száma oldalanként beállítása: Archívumok konvertálása HTML-re a GroupDocs.Viewer Java-val

Az olyan archívumfájlok, mint a ZIP vagy RAR, web‑barát HTML-re való konvertálása gyakori igény, ha közvetlenül a böngészőben szeretnénk megosztani vagy áttekinteni a dokumentumokat. Ebben az útmutatóban megtanulja, **hogyan állítsa be az oldalankénti elemek számát** az archívumok renderelésekor, hogyan ágyazza be a forrásokat HTML-be egy önálló kimenethez, és hogyan konvertáljon archívumokat kötegelt módon hatékonyan a GroupDocs.Viewer Java segítségével.

![Archívumok konvertálása HTML-re a GroupDocs.Viewer for Java használatával](/viewer/export-conversion/convert-archives-to-html-java.png)

## Gyors válaszok
- **Mit szabályoz a „set items per page” beállítás?** Meghatározza, hogy egy archívumból hány fájl vagy mappa jelenjen meg az egyes generált HTML‑oldalakon.  
- **Be tudom-e ágyazni a képeket és a CSS‑t közvetlenül a HTML‑be?** Igen – használja a `forEmbeddedResources` opciót a források HTML‑be ágyazásához.  
- **Lehetséges a kötegelt konvertálás?** Természetesen; egy archívumgyűjteményen iterálva ugyanazokkal a beállításokkal renderelheti őket.  
- **Szükségem van Maven‑re a GroupDocs.Viewer használatához?** Igen, adja hozzá a `maven groupdocs viewer` függőséget az alább látható módon.  
- **Mely kimeneti formátumok támogatottak?** Az egyoldalas HTML Java és a többoldalas HTML Java egyaránt elérhető.

## Mi az a „set items per page” a GroupDocs.Viewer‑ben?
A **set items per page** beállítás az archívum‑renderelési opciók része. Megmondja a megjelenítőnek, hány archívumbejegyzés (fájl vagy mappa) jelenjen meg minden HTML‑oldalon, amikor többoldalas HTML‑dokumentumot generál. Ennek az értéknek a módosítása segít egyensúlyt teremteni az oldalméret és a navigációs sebesség között, különösen nagy archívumok esetén.

## Miért ágyazzuk be a források HTML‑jét?
A források (képek, CSS, betűkészletek) közvetlen beágyazása a HTML‑fájlba egyetlen, hordozható dokumentumot hoz létre, amely külső fájlok nélkül is megnyitható. Ez ideális e‑mail mellékletekhez, offline megtekintéshez vagy a kimenet más weboldalakba történő beágyazásához.

## Előfeltételek

- **Szükséges könyvtárak:** GroupDocs.Viewer 25.2 vagy újabb verzió.  
- **Környezet:** Telepített és konfigurált Java Development Kit (JDK).  
- **Ismeretek:** Alapvető Java és Maven függőségkezelés.

## Maven GroupDocs Viewer beállítása

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
A GroupDocs.Viewer **ingyenes próba linket**, ideiglenes licencet vagy teljes vásárlási lehetőséget kínál. Válassza ki a projekt idővonalához leginkább illőt.

### Alapvető inicializálás
A Maven beállítás után hozza be a viewert a kódjába:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Hogyan rendereljük az archívumokat egyoldalas HTML‑re

### 1. lépés: Kimeneti könyvtár meghatározása
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 2. lépés: Fájlnév beállítása egyoldalas kimenethez
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 3. lépés: A Viewer inicializálása
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 4. lépés: Renderelési opciók konfigurálása (források HTML‑be ágyazása)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 5. lépés: Renderelés egy oldalként
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Hogyan rendereljük az archívumokat többoldalas HTML‑re és állítsuk be az oldalankénti elemek számát

### 1. lépés: A kimeneti könyvtár újrahasználata
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 2. lépés: Fájlnév formátum meghatározása több oldalhoz
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 3. lépés: A Viewer újra inicializálása
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 4. lépés: Többoldalas opciók konfigurálása (források HTML‑be ágyazása)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 5. lépés: Elem számának beállítása oldalanként (fő kulcsszó a műveletben)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Gyakorlati alkalmazások

- **Dokumentumkezelő rendszerek:** Archívum‑előnézet funkció hozzáadása extra nézőprogramok telepítése nélkül.  
- **Webportálok:** Felhasználók számára gyors, letöltés nélküli mód biztosítása a csomagolt dokumentumok felfedezésére.  
- **Együttműködési eszközök:** Csapatok közvetlenül a böngészőben ellenőrizhetik a megosztott archívumokat.

## Teljesítménybeli megfontolások

- **Erőforrás‑kezelés:** Figyelje a memóriahasználatot; nagy kötegek esetén érdemes a JVM szemétgyűjtőjét finomhangolni.  
- **Kötegelt archívumkonvertálás:** Iteráljon egy archívumfájl‑listán, és hívja meg ugyanazt a renderelési logikát a maximális áteresztőképesség érdekében.  
- **Gyorsítótárazási stratégia:** Tárolja a renderelt HTML‑t gyorsítótárban, ha ugyanazt az archívumot gyakran kérik le.

## Gyakran Ismételt Kérdések

**Q: Mi a GroupDocs.Viewer Java?**  
A: Egy sokoldalú könyvtár dokumentumok – köztük archívumok – HTML‑re, PDF‑re és képekre történő rendereléséhez.

**Q: Hogyan szerezhetek ingyenes próbaverziót a GroupDocs.Viewer‑hez?**  
A: Látogassa meg a [free trial link](https://releases.groupdocs.com/viewer/java/) oldalt a letöltéshez és teszteléshez.

**Q: Konvertálhatok más dokumentumtípusokat is az archívumok mellett?**  
A: Igen, a viewer támogatja a PDF‑eket, Word‑et, Excelt és még sok más formátumot.

**Q: Mit tegyek, ha a renderelés lassú?**  
A: Csökkentse az oldalankénti elemek számát, engedélyezze a streaminget, vagy dolgozzon kisebb kötegekkel.

**Q: Hol kaphatok segítséget vagy támogatást?**  
A: Lépjen kapcsolatba a [support forum](https://forum.groupdocs.com/c/viewer/9) segítségével.

**Q: Lehetséges a CSS és a képek közvetlen beágyazása a HTML‑be?**  
A: Teljesen – használja a `HtmlViewOptions.forEmbeddedResources`‑t a példákban látható módon.

**Q: Hogyan konvertálok kötegelt módon egy mappában lévő archívumokat?**  
A: Iteráljon minden fájlon egy `for` ciklussal, és alkalmazza ugyanazt a `Viewer` és `HtmlViewOptions` konfigurációt minden iterációra.

## Források

- **Dokumentáció:** Mélyedjen el a funkcionalitásban a [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) segítségével.  
- **API referencia:** Tekintse meg a teljes API‑t a [GroupDocs API](https://reference.groupdocs.com/viewer/java/) oldalon.  
- **Letöltés:** Szerezze be a legújabb binárisokat a [download page](https://releases.groupdocs.com/viewer/java/) oldalról.  
- **Vásárlás és licenc:** Tekintse át a lehetőségeket a [purchase page](https://purchase.groupdocs.com/buy) oldalon.  
- **Támogatás és közösség:** Csatlakozzon a beszélgetésekhez a [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) oldalon.

---

**Utoljára frissítve:** 2026-02-23  
**Tesztelve a következővel:** GroupDocs.Viewer 25.2  
**Szerző:** GroupDocs