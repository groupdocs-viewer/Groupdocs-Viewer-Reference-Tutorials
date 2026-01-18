---
date: '2026-01-18'
description: Ismerje meg, hogyan lehet 90 fokkal elforgatni az oldalt Java-ban a GroupDocs
  Viewer használatával, beleértve a beállítást, a kódot és a teljesítmény tippeket.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Oldal 90 fokos elforgatása a GroupDocs Viewer for Java-val
type: docs
url: /hu/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Oldal 90 fokos forgatása a GroupDocs Viewer for Java segítségével

Amikor egy dokumentumban **oldal 90 fokos forgatása** szükséges — legyen az PDF, Word fájl vagy táblázat — a programozott megoldás időt takarít meg és kiküszöböli a kézi hibákat. Ebben a haladó útmutatóban lépésről lépésre bemutatjuk, hogyan forgathatja el egy támogatott dokumentum első oldalát a **GroupDocs Viewer for Java** használatával. A végére egy újrahasználható kódrészletet kap, amelyet beilleszthet saját projektjeibe.

![Az első oldal forgatása egy dokumentumban a GroupDocs.Viewer for Java segítségével](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Gyors válaszok
- **Mi jelent a „rotate page 90 degrees”?** A kiválasztott oldalt az óramutató járásával megegyező irányban egy negyed fordulattal forgatja.  
- **Melyik könyvtár kezeli a forgatást?** A GroupDocs Viewer for Java biztosítja a `rotatePage` metódust.  
- **Forgathatok PDF oldalakat Java-val?** Igen — használja ugyanazt a `rotatePage` hívást; működik PDF, DOCX, XLSX és más formátumok esetén is.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez megfelelő; a termeléshez fizetett licenc szükséges.  
- **Az operáció memóriaigényes?** Nem, ha a `Viewer` példányt gyorsan bezárja; lásd az alábbi teljesítmény tippeket.

## Mi az a „rotate page 90 degrees”?
Az oldal 90 fokos forgatása a lapot álló helyzetből fekvőbe (vagy fordítva) állítja át anélkül, hogy a benne lévő tartalmat módosítaná. Különösen hasznos prezentációkhoz, csak fekvő tájolású grafikák nyomtatásához, vagy a féloldalra rögzített beolvasott dokumentumok javításához.

## Miért forgassuk az oldalakat a GroupDocs Viewer for Java-val?
A GroupDocs Viewer elrejti a több tucat fájlformátum kezelésének összetettségét. Lehetővé teszi az oldal‑szintű átalakítások — például a forgatás — alkalmazását, miközben az eredeti fájl érintetlen marad. Az API folyékony, szál‑biztos, és bármely Java 8+ környezetben működik.

## Előkövetelmények

- **GroupDocs.Viewer for Java** (legújabb verzió)
- **JDK 8** vagy újabb
- **Maven** (vagy Gradle) a függőségek kezeléséhez
- IntelliJ IDEA vagy Eclipse típusú IDE
- Alapvető ismeretek a Java I/O-val kapcsolatban

## A GroupDocs.Viewer for Java beállítása

Adja hozzá a GroupDocs tárolót és függőséget a `pom.xml` fájlhoz. Ez a kódrészlet változatlan az eredeti útmutatóból:

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
- **Ingyenes próba** – letöltés a GroupDocs weboldaláról.  
- **Ideiglenes licenc** – kérje, ha hosszabb értékelési időszakra van szüksége.  
- **Teljes licenc** – vásárlás termelési környezethez.

### Alapvető Viewer inicializálás
Az alábbi kód mutatja a minimális módot egy `Viewer` példány létrehozására. Tartsa pontosan úgy, ahogy látható:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Lépésről‑lépésre megvalósítás: Az első oldal 90 fokos forgatása

### 1. A szükséges csomagok importálása
Az alábbi importok hozzáférést biztosítanak a PDF renderelési beállításokhoz és a forgatás enum-hoz.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Kimeneti helyek meghatározása és a Viewer létrehozása
Az helyőrző útvonalakat cserélje le a saját könyvtáraira.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. PDF nézet beállítások konfigurálása és a forgatás alkalmazása
Az `rotatePage` metódus a lap számát (1‑alapú) és egy `Rotation` enum értéket vár.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Dokumentum renderelése
Végül hívja meg a `view` metódust a forgatott PDF előállításához.

```java
viewer.view(viewOptions);
```

#### Hogyan működik
- **PdfViewOptions** azt mondja a Viewernek, hogy PDF fájlt állítson elő.  
- **rotatePage(int, Rotation)** csak a megadott oldalt forgatja, a többit érintetlenül hagyja.  
- A metódus támogatja az `ON_90_DEGREE`, `ON_180_DEGREE` és `ON_270_DEGREE` értékeket.

## Gyakori problémák és megoldások

| Tünet | Valószínű ok | Javítás |
|---------|--------------|-----|
| **FileNotFoundException** | Helytelen útvonal vagy hiányzó mappa | Ellenőrizze, hogy a `YOUR_OUTPUT_DIRECTORY` és a `YOUR_DOCUMENT_DIRECTORY` létezik és olvasható. |
| **Unsupported file format** | Olyan formátum forgatása, amelyet a Viewer nem támogat | Ellenőrizze a [GroupDocs Viewer supported formats] oldalt. |
| **No rotation visible** | Hibás oldal szám használata (0‑alapú) | Ne feledje, hogy a `rotatePage` **1‑alapú** indexelést használ. |
| **Out‑of‑memory errors on large docs** | Sok nagy fájl renderelése egyetlen szálban | A dokumentumokat sorban dolgozza fel, vagy használjon korlátozott párhuzamosságú szálkészletet. |

## Gyakorlati alkalmazások

1. **Prezentációs beállítások** – Átalakítja a portré diát valós időben fekvő formátumba.  
2. **Tömeges dokumentumjavítás** – Automatizálja a féloldalra rögzített beolvasott PDF-ek javítását.  
3. **Nyomtatásra kész kimenet** – Biztosítja, hogy a fekvő grafikák helyesen nyomtatódjanak portré tájolású papírra.

## Teljesítmény tippek

- **Erőforrások gyors lezárása** – A `try‑with‑resources` blokk automatikusan felszabadítja a `Viewer`-t.  
- **Kötegelt feldolgozás** – Sok fájl kezelésekor használjon egyetlen `Viewer` példányt szálanként a terhelés csökkentése érdekében.  
- **Memória figyelése** – 100 MB-nál nagyobb dokumentumok esetén fontolja meg a kimenet lemezre streamelését a memóriában tartás helyett.

## Gyakran feltett kérdések

**K: Forgathatok több oldalt egyszerre?**  
V: Igen — hívja meg a `rotatePage()`-t minden forgatni kívánt oldal számához.

**K: Van mód a forgatás visszavonására a renderelés után?**  
V: Nem közvetlenül. Újra kell renderelni a dokumentumot a forgatási beállítások nélkül.

**K: Mely fájlformátumok támogatják az oldal forgatását a GroupDocs Viewer-ben?**  
V: DOCX, PDF, PPTX, XLSX és számos más formátum, amely a hivatalos dokumentációban szerepel.

**K: Hogyan forgathatok oldalakat automatikusan egy dokumentumcsoportban?**  
V: Tegye a kódot egy ciklusba, amely egy fájlútvonalak gyűjteményén iterál, és minden egyes fájlra alkalmazza a `rotatePage` logikát.

**K: Mi a legjobb gyakorlat a forgatás közbeni hibakezeléshez?**  
V: Zárja a Viewer használatát egy `try‑catch` blokkba, naplózza a kivételt, és opcionálisan folytassa a következő fájl feldolgozását.

## Erőforrások

- **Dokumentáció**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API referencia**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Letöltés**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Vásárlás**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Ingyenes próba**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Ideiglenes licenc**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Támogatás**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Utoljára frissítve:** 2026-01-18  
**Tesztelve a következővel:** GroupDocs Viewer 25.2 for Java  
**Szerző:** GroupDocs  

---