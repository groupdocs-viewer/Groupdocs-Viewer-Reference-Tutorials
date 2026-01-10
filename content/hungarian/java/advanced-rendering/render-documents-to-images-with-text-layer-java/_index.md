---
date: '2026-01-10'
description: Tanulja meg, hogyan konvertáljon Word dokumentumot képpé szövegréteggel
  Java-ban a GroupDocs.Viewer használatával, szövegréteg kinyerésével kereshető, nagy
  felbontású dokumentumképekhez.
keywords:
- convert word to image
- extract text overlay
- render pdf with text
- improve document image clarity
- configure view options
- generate searchable images
title: Word konvertálása képpé szövegréteggel Java‑ban
type: docs
url: /hu/java/advanced-rendering/render-documents-to-images-with-text-layer-java/
weight: 1
---

# Convert Word to Image with Text Layer in Java Using GroupDocs.Viewer

Szüksége van **Word konvertálására képpé**, miközben a szöveg kiválasztható és kereshető marad? A DOCX képpé renderelése gyakran elveszíti a rejtett szöveget, így a keresés és a másolás‑beillesztés lehetetlen. Ebben az útmutatóban megmutatjuk, hogyan rendereljünk egy Word dokumentumot PNG képekké **egy átfedő szövegréteggel** a GroupDocs.Viewer for Java használatával. Ez a megközelítés nem csak **javítja a dokumentum képélességét**, hanem **kereshető képeket is generál**, amelyek tökéletesen működnek webportálokban és CMS megoldásokban.

![Dokumentumok renderelése képekké szövegréteggel a GroupDocs.Viewer for Java segítségével](/viewer/advanced-rendering/render-documents-as-images-with-text-layer-java.png)

## Gyors válaszok
- **Mit jelent a “Word konvertálása képpé”?** Minden oldalhoz raszteres képet (PNG) hoz létre, miközben az eredeti szöveget egy rejtett rétegben megőrzi.  
- **Miért adunk hozzá szövegréteget?** Az átfedés kereshetővé és kiválaszthatóvá teszi a képet, javítva a hozzáférhetőséget és az SEO-t.  
- **Melyik könyvtár kezeli ezt?** A GroupDocs.Viewer for Java beépített támogatást nyújt a szövegkinyeréshez és a képrendereléshez.  
- **Szükségem van licencre?** A fejlesztéshez egy ingyenes próba működik; a termeléshez fizetett licenc szükséges.  
- **Használhatom ugyanazt a kódot PDF-ekhez?** Igen – ugyanazok a megjelenítési beállítások alkalmazhatók PDF, DOCX és számos más formátumra.

## Mi az a “Word konvertálása képpé” szövegréteggel?
A Word fájl képpé konvertálása általában egy bitmapet eredményez, amely csak pixeleket tartalmaz. A **szövegkinyerés átfedés** engedélyezésével a GroupDocs.Viewer egy láthatatlan szövegréteget ad minden kép tetejére, lehetővé téve a böngészők és keresőmotorok számára a tartalom olvasását.

## Miért használjuk a GroupDocs.Viewer-t ehhez a feladathoz?
- **Magas minőségű PNG kimenet**, amely megőrzi az eredeti elrendezést.  
- **Szövegkinyerés átfedés** automatikusan, így extra feldolgozás nélkül kap kereshető képeket.  
- **Egyszerű API** – néhány Java sor kezeli az egész folyamatot.  
- **Széles körű formátumtámogatás** – ugyanaz a megközelítés működik PDF-ekkel, PPTX-szel és másokkal is.

## Előkövetelmények
- Java Development Kit (JDK) telepítve és konfigurálva.  
- Maven a függőségkezeléshez.  
- Alapvető ismeretek a Java fájlkezelésről és Maven projektekről.

## A GroupDocs.Viewer beállítása Java-hoz
### Telepítési információk
Adja hozzá a GroupDocs.Viewer-t Maven projektjéhez a repository és a függőség beillesztésével a `pom.xml` fájlba:

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
Kezdje egy ingyenes próba verzióval a GroupDocs.Viewer letöltésével a [letöltési oldalról](https://releases.groupdocs.com/viewer/java/). Termelési használathoz vásároljon licencet vagy szerezzen ideiglenes kulcsot a [ideiglenes licenc oldalról](https://purchase.groupdocs.com/temporary-license/).

### Alapvető inicializálás és beállítás
A Maven szinkronizálás után létrehozhat egy `Viewer` példányt – ez az objektum fogja irányítani a renderelési folyamatot.

## Lépésről‑lépésre útmutató a Word képpé konvertálásához

### 1. lépés: A kimeneti könyvtár meghatározása
Először adja meg a viewernek, hogy hová tárolja a generált PNG fájlokat. Az alábbi kód létrehozza (vagy újra felhasználja) a `YOUR_OUTPUT_DIRECTORY` nevű mappát.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
```

> **Pro tipp:** Használja a `Files.createDirectories(outputDirectory);` kódot, ha szeretné, hogy a mappa automatikusan létrejöjjön.

### 2. lépés: Nézetbeállítások konfigurálása
Ezután állítsa be a renderelési opciókat. A `PngViewOptions` használatával és a `setExtractText(true)` engedélyezésével azt mondja a GroupDocs.Viewer-nek, hogy **kivonja a szöveg átfedést** és beágyazza minden képbe.

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
viewOptions.setExtractText(true);  // Enable extracting text over the image
```

### 3. lépés: Dokumentum renderelése (Word képpé konvertálás)
Végül nyissa meg a forrás DOCX-et, és hívja a `viewer.view(viewOptions)` metódust. A `try‑with‑resources` blokk garantálja, hogy a `Viewer` példány megfelelően le legyen zárva.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);  // Perform rendering operation
}
```

Amikor a kód befejeződik, a Word dokumentum minden oldala magas felbontású PNG-ként jelenik meg egy láthatatlan szövegréteggel, készen állva az indexelésre és a keresésre.

## Hibaelhárítási tippek
- **Fájl nem található:** Ellenőrizze a `SAMPLE_DOCX` elérési útját. Használjon abszolút útvonalakat a biztosításhoz.  
- **Jogosultsági problémák:** Győződjön meg róla, hogy a Java folyamat írni tud a `YOUR_OUTPUT_DIRECTORY` könyvtárba.  
- **Verzióeltérés:** Ellenőrizze, hogy a `pom.xml`-ben szereplő verzió megegyezik a letöltött könyvtárral.

## Gyakorlati alkalmazások
1. **Web Portálok:** Mutasson dokumentum előnézeteket, amelyeket a felhasználók kereshetnek anélkül, hogy letöltenék az eredeti fájlt.  
2. **Tartalomkezelő rendszerek:** Tároljon kereshető képképmásokat archiválási célokra.  
3. **Dokumentum archiválás:** Tartson egy könnyű súlyú képverziót, miközben továbbra is lehetővé teszi a teljes szöveges keresést.

## Teljesítmény szempontok
- A `Viewer` objektumokat gyorsan szabadítsa fel (ahogy a `try‑with‑resources` példában látható).  
- Válassza a PNG-t a minőségért; ha a sávszélesség aggály, válthat JPEG-re.  
- Cache-elje a renderelt oldalakat, ha ugyanazt a dokumentumot többször kérik.

## Gyakran ismételt kérdések

**Q: Hogyan kezeljem a nagy dokumentumokat?**  
A: Renderelje az oldalakat fokozatosan, és minden `Viewer` példányt szabadítson fel egy köteg feldolgozása után, hogy alacsony maradjon a memóriahasználat.

**Q: Renderelhetek PDF-eket ugyanazzal a megközelítéssel?**  
A: Igen, a GroupDocs.Viewer támogatja a PDF-et, és ugyanaz a `setExtractText(true)` jelző kereshető PDF képeket generál.

**Q: Mi van, ha a szövegréteg nem látható a kimenetben?**  
A: Ellenőrizze, hogy a `viewOptions.setExtractText(true)` be van állítva, és hogy a kimeneti mappának írási jogosultsága van.

**Q: Támogatottak más képformátumok is?**  
A: A PNG mellett használhatja a `JpgViewOptions` vagy `BmpViewOptions` osztályt a nézet opció cseréjével.

**Q: Hol találok részletesebb API dokumentációt?**  
A: A hivatalos dokumentáció kimerítő példákat és konfigurációs részleteket nyújt.

## Erőforrások
- **Dokumentáció:** [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API referencia:** [API Reference Guide](https://reference.groupdocs.com/viewer/java/)  
- **Letöltés:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Vásárlás:** [Buy License](https://purchase.groupdocs.com/buy)  
- **Ingyenes próba:** [Download Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Ideiglenes licenc:** [Acquire Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Támogatás:** [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Utoljára frissítve:** 2026-01-10  
**Tesztelve ezzel:** GroupDocs.Viewer 25.2 for Java  
**Szerző:** GroupDocs