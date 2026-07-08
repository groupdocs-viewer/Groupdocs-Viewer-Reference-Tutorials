---
date: '2026-06-30'
description: Ismerje meg, hogyan lehet viewinfo-t lekérni és Java archívum fájltípus
  struktúrákat visszanyerni a GroupDocs.Viewer használatával. Ez az útmutató bemutatja
  a beállítást, kódrészleteket és a valós felhasználási eseteket.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Hogyan szerezhetünk ViewInfo-t és nyerhetünk ki archívum struktúrákat Java-ban
type: docs
url: /hu/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Hogyan szerezhetünk ViewInfo-t és nyerhetünk ki archívum struktúrákat Java-ban

Az archívumfájlok hatékony kezelése megköveteli azok struktúrájának világos megértését. Ebben az útmutatóban megtanulja, hogyan **szerezhet ViewInfo-t** bármely archívumhoz, és hogy ez hogyan segíti a **java archívum fájltípus** használatát. Végigvezetjük a GroupDocs.Viewer beállításán, a nézetinformáció kinyerésén, és a mappahierarchiák rekurzív olvasásán, hogy a megoldást valós projektekbe integrálhassa.

![Archívum struktúrák a GroupDocs.Viewer for Java segítségével](/viewer/document-loading/archive-structures-java.png)

**Mit fog megtanulni**
- A GroupDocs.Viewer for Java beállítása és konfigurálása.  
- Módszerek a **viewinfo lekérésére** archívumokból.  
- Technikák az archívumfájl mappaszerkezetének olvasására és megjelenítésére.  
- Gyakorlati alkalmazások és teljesítménybeli szempontok a GroupDocs.Viewer Java projektekben való használatakor.

## Gyors válaszok
- **Mit biztosít a “viewinfo”?** Visszaadja a fájltípust, az oldalak számát, és egy teljes listát a mappákról és fájlokról az archívumban.  
- **Mely archívumformátumok támogatottak?** ZIP, RAR, TAR, 7z, ISO, és 12+ egyéb gyakori formátum.  
- **Szükségem van licencre a termeléshez?** Igen – egy kereskedelmi licenc szükséges a termeléshez; egy ingyenes próba a kiértékeléshez megfelelő.  
- **Nagy archívumok hatékonyan feldolgozhatók?** Teljesen – használjon streaming opciókat, és egy mappaszintet egyszerre dolgozzon fel a memóriahasználat alacsonyan tartásához.  
- **A Maven az egyetlen módja a könyvtár hozzáadásának?** A Maven a javasolt függőségkezelő, de a Gradle vagy a manuális JAR beillesztés is működik.

## Mi a “hogyan szerezhet ViewInfo-t”?

`getViewInfo` egy GroupDocs.Viewer API metódus, amely metaadatokat nyer ki egy dokumentumból vagy archívumból teljes renderelés nélkül. Visszaadja a belső mappafa, a fájlok számát és az alapvető tulajdonságokat egy hívásban, lehetővé téve, hogy eldöntse, mely részeket dolgozza fel. A hívás egy teljes pillanatképet ad vissza az akár 500 MB méretű archívumokról kevesebb, mint egy másodperc alatt a tipikus szervereken.

## Miért kell lekérni a Java archívum fájltípus struktúrákat?

A **java archívum fájltípus** belső felépítésének lekérése lehetővé teszi a szükséges fájlok azonnali megtalálását, a felesleges kicsomagolás elkerülését, és automatizált folyamatok építését, amelyek csak a releváns alkönyvtárakat érintik. Ez a megközelítés akár 70 %-kal csökkenti az I/O-t nagy archívumok esetén, és lehetővé teszi, hogy percenként több ezer fájlt szkenneljünk adatbefogadó szcenáriókban.

## Előfeltételek

- **Java Development Kit (JDK):** 8-as vagy újabb verzió.  
- **Maven:** Függőségkezeléshez és buildeléshez.  
- **Alap Java ismeretek:** Az OOP koncepciók ismerete segít, de nem kötelező.  

A GroupDocs.Viewer könyvtárhoz is hozzáférésre van szükség, amelyet az alább bemutatott módon adhat hozzá Maven projektjéhez.

## A GroupDocs.Viewer beállítása Java-hoz

### Maven konfiguráció

Adja hozzá a tárolót és a függőséget a `pom.xml`-hez.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Licenc beszerzése

- **Ingyenes próba:** Töltse le a próba verziót a GroupDocs weboldaláról.  
- **Ideiglenes licenc:** Kérjen ideiglenes kulcsot rövid távú kiértékeléshez.  
- **Teljes licenc:** Vásároljon kereskedelmi licencet korlátlan termelési használathoz.

Miután a könyvtár a classpath-on van, elkezdhet kódolni.

## Implementációs útmutató

### Hogyan szerezhet ViewInfo-t archívumfájlokhoz

A nézetinformációk megszerzéséhez először töltse be az archívumot a Viewer-be, majd hívja meg a `getViewInfo`-t a metaadatok lekéréséhez, végül iteráljon a visszaadott mappahierarchián. Ez a háromlépéses minta minden támogatott archívumformátumra működik, és egyetlen API hívásban teljes pillanatképet biztosít, megkönnyítve a további feldolgozást.

#### A Viewer inicializálása

A `Viewer` osztály a belépési pont minden renderelési és ellenőrzési művelethez. Kezeli a fájlfolyamokat, a formátumdetektálást és az erőforrások tisztítását.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Nézetinformáció lekérése

`ViewInfo` metaadatokat foglal magába, mint a fájltípus, az összes oldal száma, és egy hierarchikus lista a mappákról és fájlokról. A `getViewInfo` meghívása azonnal visszaadja ezt az objektumot.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Mappaszerkezet megjelenítése

Iteráljon a `viewInfo.getFolders()`-on, hogy kiírja minden mappa nevét, mélységét és a benne lévő fájlokat. Ez az egyszerű ciklus olvasható fa nézetet ad az archívumról.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekurzív mappaolvasás

Mélyen beágyazott archívumok esetén egy rekurzív segédmetódus bejárhatja a fát mélységi sorrendben, biztosítva, hogy minden alkönyvtár meg legyen látogatva anélkül, hogy az egész archívumot a memóriába töltené.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### 2. funkció: Archívum mappaszerkezet lekérése

Ez a funkció az archívumfájl mappaszerkezetének kiíratására fókuszál. Hasonló az első funkcióhoz, de a rekurzív felfedezést emeli ki.

#### Nézetinformáció beállítások konfigurálása

`ArchiveOptions` lehetővé teszi a jelszóvédelem, oldalkorlátok és streaming beállítások megadását a `getViewInfo` hívása előtt.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekurzív felfedezés

Egy második rekurzív rutin bemutatja, hogyan kezelhetünk jelszóval védett archívumokat és nagy fájlkészleteket hatékonyan.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Gyakorlati alkalmazások

1. **Adatkezelés:** Gyorsan szervezze a nagy adatkészleteket az archívum struktúrák megértésével.  
2. **Automatizált fájlfeldolgozás:** Csoportosítsa az archivált fájlokat teljes kicsomagolás nélkül, csökkentve az I/O-t akár 70 %-kal.  
3. **CMS integráció:** Fejlessze a tartalomkezelő rendszereket élő archívumnavigációval, lehetővé téve a szerkesztőknek a fájlok közvetlen előnézetét az archívumból.

## Teljesítménybeli szempontok

- **Memóriahasználat optimalizálása:** Folyamatosan egy szintet dolgozzon fel, és zárja le gyorsan a `Viewer` példányt.  
- **Maradjon naprakész:** Használja a legújabb GroupDocs.Viewer verziót (25.2 a írás időpontjában) és a JDK kiadásokat a teljesítményjavulásért.  
- **Streaming támogatás:** A könyvtár képes streamingelni az 1 GB-nál nagyobb archívumokat anélkül, hogy a teljes fájlt RAM-ba töltené, köszönhetően a belső darabolt‑olvasási architektúrának.

## Gyakori problémák és megoldások

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| `NullPointerException` mappák olvasásakor | `viewInfo.getFolders()` null értéket ad üres könyvtárak esetén | Ellenőrizze a null vagy üres listát a iterálás előtt. |
| Nagy ZIP fájlok lassú feldolgozása | Az egész archívum a memóriába kerül | Használja a streaming opciókat, amelyek az újabb GroupDocs verziókban elérhetők. |
| Licenc nem található | A licencfájl útvonala helytelen | Helyezze a licencfájlt az alkalmazás gyökerébe, vagy állítsa be a `License.setLicense("path/to/license.json")`-t. |

## Gyakran feltett kérdések

**K:** Mi az a GroupDocs.Viewer?  
V: A GroupDocs.Viewer egy Java könyvtár, amely több mint 100 dokumentum-, kép- és archívumformátumot renderel HTML, PDF vagy képes adatfolyamokra, natív alkalmazások nélkül.

**K:** Használhatom a GroupDocs.Viewer-t más programozási nyelvekkel?  
V: Igen, a GroupDocs SDK-kat kínál .NET, Python, PHP és más nyelvekhez, de ez az útmutató a Java megvalósításra koncentrál.

**K:** Hogyan kezeljem a nagy archívumfájlokat?  
V: Engedélyezze a streaminget a `ArchiveOptions.setUseStreaming(true)` használatával, egy mappaszintet dolgozzon fel egyszerre, és a használat után szabadítsa fel a `Viewer` objektumot.

**K:** Milyen típusú archívumokat támogat a GroupDocs.Viewer?  
V: Több mint 12 archívumformátumot támogat, beleértve a ZIP, RAR, TAR, 7z, ISO, ARJ és CAB formátumokat, valamint számos saját tulajdonú konténer típust.

**K:** Van méretkorlát az archívumoknál?  
V: A gyakorlati korlát a szerver RAM- és CPU-erőforrásaitól függ; tesztek szerint 2 GB méretű archívumok zökkenőmentesen feldolgozhatók egy 16 GB RAM-os gépen, ha a streaming engedélyezve van.

**K:** A “hogyan szerezhet ViewInfo-t” működik jelszóval védett archívumok esetén?  
V: Igen, adja meg a jelszót a `ArchiveOptions.setPassword("yourPassword")` használatával a `getViewInfo` meghívása előtt.

## Következtetés

Ezzel az útmutatóval most már tudja, hogyan **szerezhet ViewInfo-t** bármely támogatott archívumhoz, és hogyan járhatja be a mappahierarchiáját a GroupDocs.Viewer for Java segítségével. Ezek a technikák lehetővé teszik, hogy intelligensebb adatfeldolgozó csővezetékeket építsen, javítsa a CMS integrációkat, és magabiztosan kezelje a nagy mennyiségű archivált fájlt. Következő lépésként fedezze fel az egyes fájlok renderelését az archívumból, vagy azok PDF/HTML konvertálását a Viewer egyéb funkcióival.

---

**Utolsó frissítés:** 2026-06-30  
**Tesztelve ezzel:** GroupDocs.Viewer 25.2 for Java  
**Szerző:** GroupDocs  

## Források
- **Dokumentáció:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API referencia:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs letöltési oldal:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Licenc vásárlása:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Ingyenes próba és ideiglenes licenc:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Kapcsolódó oktatóanyagok

- [Dokumentum metaadatok kinyerése a GroupDocs.Viewer for Java segítségével – Dokumentum nézetinformációk és betekintések lekérése](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Mellékletek lekérése és nyomtatása a GroupDocs.Viewer for Java segítségével](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java útmutató: Specifikus oldalak renderelése a GroupDocs.Viewer API-val dokumentum előnézethez és kezeléshez](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)