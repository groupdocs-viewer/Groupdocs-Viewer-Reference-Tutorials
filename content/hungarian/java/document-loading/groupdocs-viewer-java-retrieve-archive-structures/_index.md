---
date: '2026-02-05'
description: Tanulja meg, hogyan lehet lekérni a viewinfo-t és visszanyerni a Java
  archívum fájltípusú struktúrákat a GroupDocs.Viewer használatával. Ez az útmutató
  lefedi a beállítást, a kódrészleteket és a valós felhasználási eseteket.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Hogyan kapjunk ViewInfo-t és nyerjünk ki archív struktúrákat Java-ban
type: docs
url: /hu/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Hogyan szerezhetünk ViewInfo-t és nyerhetünk ki archívum struktúrákat Java-ban

Az archívumfájlok hatékony kezelése megköveteli azok struktúrájának alapos megértését. Ebben az oktatóanyagról megtanulja, **hogyan szerezhet meg viewinfo-t** bármely archívumhoz, és hogy ez hogyan segíti a **java archive file type** kezelését. Végigvezetjük a GroupDocs.Viewer beállításán, a nézetinformációk kinyerésén, és a mappahierarchiák rekurzív olvasásán, hogy a megoldást valós projektekbe integrálhassa.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Mit fog megtanulni**
- A GroupDocs.Viewer beállítása és konfigurálása Java-hoz.  
- Módszerek a **viewinfo megszerzésére** archívumokból.  
- Technikák egy archívumfájl mappaszerkezetének olvasására és megjelenítésére.  
- Gyakorlati alkalmazások és teljesítménybeli szempontok a GroupDocs.Viewer Java projektekben való használatakor.

## Quick Answers
- **Mi ad vissza a “viewinfo”?** Visszaadja a fájltípust, az oldalszámot és az archívum mappalistákat.  
- **Mely archívumok támogatottak?** ZIP, RAR, TAR és más gyakori formátumok.  
- **Szükségem van licencre?** Egy ingyenes próba a kiértékeléshez elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Feldolgozhatok nagy archívumokat?** Igen – használjon streaminget és megfelelő memória kezelést, ahogy később bemutatjuk.  
- **Szükséges a Maven?** A Maven a javasolt mód a GroupDocs.Viewer függőség kezelésére.

## Mi az a “how to get viewinfo”?
`getViewInfo` egy metódus a GroupDocs.Viewer API-ban, amely metaadatokat nyer ki egy dokumentumról vagy archívumról anélkül, hogy a teljes tartalmat renderelné. Archívumok esetén felfedi a belső mappafát, lehetővé téve, hogy eldöntse, mely részeket kell renderelni vagy tovább feldolgozni.

## Miért kell lekérdezni a Java archívum fájltípus struktúrákat?
A **java archive file type** (pl. ZIP, RAR) belső felépítésének megértése lehetővé teszi, hogy:
- Gyorsan megtalálja a szükséges fájlokat anélkül, hogy mindent kicsomagolna.  
- Automatizált folyamatokat épít, amelyek csak a releváns alkönyvtárakat dolgozzák fel.  
- Az archívumnavigációt integrálja tartalomkezelő vagy adatbeviteli rendszerekbe.

## Prerequisites

- **Java Development Kit (JDK):** 8-as vagy újabb verzió.  
- **Maven:** A függőségkezeléshez és a buildeléshez.  
- **Alap Java ismeretek:** Az OOP koncepciók ismerete segít, de nem kötelező.

Emellett hozzá kell férnie a GroupDocs.Viewer könyvtárhoz, amelyet a Maven projektjéhez az alábbiak szerint adhat hozzá.

## Setting Up GroupDocs.Viewer for Java

### Maven Configuration

Add the repository and dependency to your `pom.xml`.

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

### License Acquisition

- **Ingyenes próba:** Töltse le a próba verziót a GroupDocs weboldaláról.  
- **Ideiglenes licenc:** Kérjen ideiglenes kulcsot rövid távú kiértékeléshez.  
- **Teljes licenc:** Vásároljon kereskedelmi licencet korlátlan termelési használathoz.

Miután a könyvtár a classpath-on van, elkezdhet kódolni.

## Implementation Guide

### How to Get ViewInfo for Archive Files

Ez a szakasz bemutatja a pontos lépéseket a `getViewInfo` meghívásához és a mappahierarchia olvasásához.

#### Initialize the Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Retrieve View Information

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Display Folder Structure

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Recursive Folder Reading

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

### Feature 2: Retrieve Archive Folder Structure

Ez a funkció az archívumfájl mappaszerkezetének kiíratására fókuszál. Hasonló az első funkcióhoz, de a rekurzív feltárásra helyezi a hangsúlyt.

#### Setup View Info Options

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Recursive Exploration

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Practical Applications

- **Adatkezelés:** Nagy adathalmazok gyors szervezése az archívum struktúrák megértésével.  
- **Automatizált fájlfeldolgozás:** Archívált fájlok kötegelt feldolgozása teljes kicsomagolás nélkül.  
- **CMS integráció:** Tartalomkezelő rendszerek fejlesztése valós idejű archívumnavigációval.

## Performance Considerations

- **Memóriahasználat optimalizálása:** Mappákat egy szinten egyszer feldolgozni, és a `Viewer` példányt gyorsan lezárni.  
- **Legyen naprakész:** Használja a legújabb GroupDocs.Viewer verziót és JDK kiadásokat a teljesítményjavulásért.

## Common Issues and Solutions

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| `NullPointerException` mappák olvasásakor | `viewInfo.getFolders()` null értéket ad üres könyvtárak esetén | Ellenőrizze a null vagy üres listát a bejárás előtt. |
| Lassú feldolgozás hatalmas ZIP fájlok esetén | Az egész archívum memóriába töltődik | Használja a streaming opciókat, amelyek az újabb GroupDocs verziókban elérhetők. |
| Licenc nem található | A licencfájl útvonala helytelen | Helyezze a licencfájlt az alkalmazás gyökerébe, vagy állítsa be a `License.setLicense("path/to/license.json")`-t. |

## Frequently Asked Questions

**K: Mi a GroupDocs.Viewer?**  
A GroupDocs.Viewer egy erőteljes Java könyvtár dokumentumok, köztük archívumok, HTML, kép és PDF formátumokba történő renderelésére.

**K: Használhatom a GroupDocs.Viewer-t más programozási nyelvekkel?**  
Igen, a GroupDocs több platformra kínál SDK-kat, de ez az oktatóanyag a Java megvalósításra koncentrál.

**K: Hogyan kezeljem a nagy archívum fájlokat?**  
Használjon hatékony memória kezelési gyakorlatokat, és szükség esetén bontsa fel az archívumokat.

**K: Milyen típusú archívumokat támogat a GroupDocs.Viewer?**  
Számos formátumot támogat, többek között ZIP, RAR, TAR és egyebek.

**K: Van korlátja az archívumok méretének, amelyeket feldolgozhatok?**  
A korlátok a rendszer erőforrásaitól függenek. Tesztelje a célkörnyezetben a gyakorlati határokat.

**K: A “how to get viewinfo” működik jelszóval védett archívumokkal?**  
Igen, a jelszót a `ArchiveOptions.setPassword("yourPassword")` hívással adhatja meg a `getViewInfo` meghívása előtt.

## Conclusion

Az útmutató követésével most már tudja, **hogyan szerezhet meg viewinfo-t** bármely támogatott archívumhoz, és hogyan járhatja be a mappahierarchiáját a GroupDocs.Viewer for Java segítségével. Ezek a technikák lehetővé teszik intelligensebb adatfeldolgozó csővezetékek építését, a CMS integrációk fejlesztését, valamint a nagy méretű archívumgyűjtemények magabiztos kezelését. Következő lépésként fedezze fel az egyes fájlok renderelését az archívumból, vagy azok PDF/HTML konvertálását a Viewer további funkcióival.

---

**Last Updated:** 2026-02-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**
- **Dokumentáció:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Referencia:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs.Viewer letöltése:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Licenc vásárlása:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Ingyenes próba és ideiglenes licenc:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)