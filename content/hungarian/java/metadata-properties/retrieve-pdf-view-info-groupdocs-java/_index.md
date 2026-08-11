---
date: '2026-04-13'
description: Tudja meg, hogyan lehet kinyerni a PDF oldalszámát és egyéb PDF metaadatokat,
  például a dokumentumtípust és a jogosultságokat a GroupDocs.Viewer for Java használatával.
  Kövesse ezt a lépésről‑lépésre útmutatót, hogy fejlessze alkalmazása dokumentumfeldolgozási
  képességeit.
keywords:
- extract pdf page count
- read pdf document type
- retrieve pdf metadata java
title: PDF oldalszám és metaadatok kinyerése a GroupDocs.Viewer Java segítségével
type: docs
url: /hu/java/metadata-properties/retrieve-pdf-view-info-groupdocs-java/
weight: 1
---

# PDF oldal számának és metaadatainak kinyerése a GroupDocs.Viewer Java segítségével

Üdvözöljük ebben az átfogó útmutatóban, amely a **extract pdf page count** és egyéb megjelenítési információk kinyeréséről szól egy PDF dokumentumból a GroupDocs.Viewer könyvtár Java-ban történő használatával. Ha programozott módon szeretné beolvasni egy PDF dokumentumtípusát, lekérni a jogosultságait, vagy egyszerűen megszámolni az oldalakat, jó helyen jár.

![PDF metaadatok és tulajdonságok lekérése a GroupDocs.Viewer for Java segítségével](/viewer/metadata-properties/retrievepdf-metadata-and-properties-java.png)

## Gyors válaszok
- **Mit tudok lekérni?** PDF page count, document type, and printing permissions.  
- **Melyik könyvtár?** GroupDocs.Viewer for Java (version 25.2).  
- **Szükségem van licencre?** A free trial works for testing; a commercial license is required for production.  
- **Támogatott Java verzió?** Java 8 or higher.  
- **Hány sor kódra van szükség?** Less than 20 lines to get full view info.

## Amit megtanul
- Értse meg, hogyan teszi lehetővé a GroupDocs.Viewer for Java a dokumentumok megjelenítését.  
- Állítsa be a környezetet a GroupDocs.Viewer Java-val való használathoz.  
- Kérje le és nyomtassa ki a megjelenítési információkat egy PDF fájlból, beleértve a **extract pdf page count**.  
- Fedezze fel a gyakorlati alkalmazásokat és a teljesítménybeli szempontokat.

## Miért kell kinyerni a pdf oldal számát és egyéb metaadatokat?
Az oldalak száma, a dokumentumtípus és a jogosultságok ismerete segít Önnek:
1. **Rövid összefoglalók megjelenítése** tartalomkezelő rendszerekben.  
2. **Biztonság érvényesítése** azzal, hogy ellenőrzi, engedélyezett-e a nyomtatás a megjelenítés előtt.  
3. **Erőforrás-használat optimalizálása** csak a szükséges oldalak betöltésével.  

## Előfeltételek
- **Könyvtárak és függőségek**: GroupDocs.Viewer for Java (added via Maven).  
- **Környezet**: Java 8 or newer installed on your development machine.  
- **Tudásbázis**: Basic Java programming and Maven familiarity.

## A GroupDocs.Viewer for Java beállítása

### Maven konfiguráció
Adja hozzá a tárolót és a függőséget a `pom.xml` fájlhoz:

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
Kezdhet ingyenes próbaverzióval, vagy szerezhet ideiglenes licencet a GroupDocs.Viewer teljes funkcióinak felfedezéséhez. Hosszú távú használathoz a licenc megvásárlása ajánlott.

## Hogyan nyerjük ki a pdf oldal számát a GroupDocs.Viewer Java-ban

### 1. lépés: `ViewInfoOptions` konfigurálása
```java
// Create ViewInfoOptions for HTML view, which is necessary for retrieving view info
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
```
*Miért*: `ViewInfoOptions` megmondja a Viewernek, milyen ábrázolásra van szüksége. A `forHtmlView()` használata előkészíti a motorot, hogy HTML rendereléshez hasznos metaadatokat adjon vissza, beleértve az oldal számát.

### 2. lépés: `Viewer` inicializálása
```java
try (Viewer viewer = new Viewer(pdfFilePath)) {
    // Retrieval and processing steps will be done here
}
```
*Miért*: `Viewer` objektum a PDF fájl elérési útjához van kötve. Try‑with‑resources blokkba ágyazva garantálja, hogy a natív erőforrások automatikusan felszabadulnak.

### 3. lépés: Megjelenítési információk (metaadatok) lekérése
```java
// Retrieve view information from the document using the specified options
PdfViewInfo viewInfo = (PdfViewInfo) viewer.getViewInfo(viewInfoOptions);

// Output the retrieved view information
System.out.println("Document type is: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
System.out.println("Printing allowed: " + viewInfo.isPrintingAllowed());
```
*Miért*: Ez a kódrészlet egyetlen hívásban kinyeri a **read pdf document type**, **extract pdf page count**, és **get pdf permissions java** értékeket. A `PdfViewInfo` objektum tartalmazza az összes szükséges adatot a további feldolgozáshoz.

### Gyakori hibák és tippek
- **Incorrect file path** → `FileNotFoundException`-t dob. Ellenőrizze a teljes vagy relatív útvonalat.  
- **Version mismatch** → győződjön meg róla, hogy a Maven verzió (`25.2`) egyezik a futási könyvtárral.  
- **Large PDFs** → fontolja meg a streaminget vagy az oldalak kötegelt feldolgozását a memóriahasználat alacsonyan tartása érdekében.

## Gyakorlati alkalmazások
1. **Content Management Systems** – automatikusan kinyeri a metaadatokat a feltöltött PDF-ekből az indexeléshez.  
2. **Document Management Workflows** – eldönti, engedélyezett-e a nyomtatás a `isPrintingAllowed` jelző alapján.  
3. **Web Dashboards** – élő előnézetet mutat az oldal számáról és a dokumentumtípusról a teljes fájl betöltése nélkül.

## Teljesítménybeli szempontok
- Használja a `ViewInfoOptions`-t csak akkor, ha metaadatokra van szüksége; kerülje a `getViewInfo` minden kérésnél történő hívását, ha már rendelkezik a gyorsítótárazott információval.  
- Figyelje a memóriahasználatot, különösen nagy PDF-ek esetén, és zárja le a `Viewer`-t időben (a try‑with‑resources blokk ezt kezeli).

## Következtetés
Most már tudja, hogyan **extract pdf page count**, olvassa a dokumentumtípust, és szerezze be a jogosultságokat a GroupDocs.Viewer for Java használatával. Nyugodtan kísérletezzen más `ViewInfoOptions`-okkal (pl. `forImageView`), hogy különböző megjelenítési forgatókönyvekhez illeszkedjen.

### Következő lépések
- Fedezze fel az oldalak képekké vagy HTML-é történő renderelését a `viewer.view` segítségével.  
- Kombinálja a metaadat-kinyerést egy adatbázissal, hogy kereshető dokumentumkatalógusokat építsen.

## Gyakran Ismételt Kérdések
**Q: Hogyan kezdhetek ingyenes próbaverzióval?**  
A: Látogassa meg a [GroupDocs' Free Trial page](https://releases.groupdocs.com/viewer/java/) oldalt a licenc megszerzésének útmutatásáért.

**Q: Használható a GroupDocs.Viewer felhőalkalmazásokban?**  
A: Igen, a könyvtár különböző környezeteket támogat, és integrálható felhőalapú megoldásokba.

**Q: Mi a teendő, ha PDF renderelési hibát kapok?**  
A: Ellenőrizze a dokumentum kompatibilitását, vagy frissítsen a GroupDocs.Viewer legújabb verziójára a jobb támogatás érdekében.

## Források
- **Documentation**: [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs Viewer API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Viewer Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-04-13  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs