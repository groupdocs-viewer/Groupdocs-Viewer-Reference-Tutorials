---
date: '2026-09-15'
description: Ismerje meg, hogyan alakíthatja át az e‑mailt HTML-re, és nevezheti át
  az e‑mail mezőket a GroupDocs Viewer for Java segítségével. Ez az útmutató bemutatja
  az e‑mail HTML-re történő renderelését egyedi fejlécekkel.
keywords:
- convert email to html
- rename email fields java
- render emails html groupdocs viewer
- customize email headers
- customize email metadata
lastmod: '2026-09-15'
og_description: Alakítsa át az e‑mailt HTML-re és nevezze át az e‑mail mezőket Java-ban
  a GroupDocs Viewer-rel. Ismerje meg a lépésről‑lépésre beállítást, a mezőleképezést
  és a tiszta HTML kimenet legjobb gyakorlatait.
og_image_alt: Guide showing how to convert email to HTML and rename fields using GroupDocs
  Viewer for Java
og_title: E‑mail átalakítása HTML-re egyedi fejlécekkel a GroupDocs Viewer for Java
  használatával
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  headline: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  type: TechArticle
- description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  name: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  steps:
  - name: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
    text: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
  - name: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
    text: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
  - name: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
    text: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
  type: HowTo
- questions:
  - answer: Yes, GroupDocs.Viewer supports both MSG and EML files; the same field‑mapping
      logic applies.
    question: Does this approach work with other email formats like EML?
  - answer: You can use `HtmlViewOptions.forExternalResources(...)` if you prefer
      separate CSS/JS files.
    question: Can I output the HTML without embedded resources?
  - answer: The code was tested with GroupDocs.Viewer **25.2**.
    question: What version of GroupDocs.Viewer was tested?
  - answer: Styling can be applied via CSS after rendering, or you can inject custom
      CSS using `HtmlViewOptions.getResourcesPath()`.
    question: Is it possible to change the font or style of the custom headers?
  - answer: The file path follows the pattern defined in `pageFilePathFormat`; you
      can construct it using `String.format` with the page number.
    question: How do I programmatically retrieve the generated HTML file path?
  type: FAQPage
tags:
- convert email to html
- groupdocs viewer java
- email rendering
- html conversion
- java email processing
title: E‑mail átalakítása HTML-re és mezők átnevezése – GroupDocs Viewer Java
type: docs
url: /hu/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# E‑mail konvertálása HTML‑re és mezők átnevezése – GroupDocs Viewer Java

Ha **e‑mailt HTML‑re kell konvertálni**, miközben az e‑mail fejléceket egyedi megjelenést adsz, jó helyen vagy. Ebben az útmutatóban lépésről‑lépésre bemutatjuk, hogyan lehet átnevezni az e‑mail mezőket, **e‑mailt HTML‑re konvertálni**, és testreszabni az e‑mail fejléceket a GroupDocs.Viewer for Java használatával. A végére egy tiszta HTML‑reprezentációt kapsz a kívánt fejlécnevekkel, ami megkönnyíti a kimenet olvasását és az alkalmazásokba való integrálását.

![E‑mail mezők átnevezése e‑mail HTML‑re konvertálásakor a GroupDocs.Viewer for Java használatával](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Amit megtanul

- **Hogyan használjuk a GroupDocs.Viewer for Java‑t **e‑mail HTML‑re konvertálásához**.  
- **Technikák a **e‑mail mezők átnevezésére**, például a „From”, „To”, „Sent” és „Subject”.  
- **Legjobb gyakorlatok a Maven és a licenc beállításához**.  
- **Valós példák, ahol a **e‑mail fejlécek testreszabása** értéket teremt**.

## Gyors válaszok

- **Mi jelent a „convert email to HTML”?** Ez azt jelenti, hogy egy e‑mail fájlt (MSG/EML) web‑kész HTML dokumentummá rendereljük.  
- **Melyik könyvtár kezeli a konvertálást?** GroupDocs.Viewer for Java (v25.2+).  
- **Szükségem van licencre?** A próbaverzió értékelésre használható; a teljes licenc a termeléshez kötelező.  
- **Át tudok-e nevezni bármelyik fejlécet?** Igen, bármelyik szabványos e‑mail fejléc átállítható a `fieldTextMap` segítségével.  
- **A kimenet HTML vagy beágyazott erőforrások?** Választható beágyazott erőforrások egy önálló fájlhoz.

## Mi a „convert email to HTML” a GroupDocs.Viewer kontextusában?

**Convert email to HTML** a folyamat, amely során egy nyers e‑mail fájlt (MSG vagy EML) HTML oldalra alakítunk, amely megjeleníti az üzenet törzsét és a metaadatait. Amikor **e‑mail mezőket is átnevezünk**, az alapértelmezett címkék (pl. „From”) egyedi szövegre (pl. „Sender”) cserélődnek, ami segít a vállalati terminológia egyeztetésében vagy a felhasználói felület konzisztenciájának javításában.

## Miért konvertáljuk e‑mailt HTML‑re és nevezünk át e‑mail mezőket?

Az e‑mail HTML‑re konvertálása és mezőinek átnevezése teljes kontrollt biztosít a felhasználók felé történő megjelenítés felett. Az egyedi fejlécek a kimenetet a vállalati terminológiához igazítják, javítják a keresőindexelést, és lehetővé teszik a zökkenőmentes integrációt webportálokba vagy támogatási műszerfalakba, míg a HTML formátum széles kompatibilitást biztosít a böngészők és eszközök között.

- **Következetes márkázás:** A kimenet igazítása a szervezet nyelvéhez.  
- **Javított kereshetőség:** Az egyedi fejlécek hatékonyabban indexelhetők archiváló rendszerekben.  
- **Jobb UI integráció:** Az HTML részletet úgy alakíthatod, hogy zökkenőmentesen illeszkedjen webportálokba vagy támogatási műszerfalakba.  
- **Teljesítményelőny:** A GroupDocs.Viewer 500 oldalas e‑mailt kevesebb, mint 2 másodperc alatt dolgoz fel egy standard szerveren, és **50+** bemeneti és kimeneti formátumot támogat, többek között MSG, EML, PDF és HTML.

## Előfeltételek

- **GroupDocs.Viewer for Java** – 25.2 vagy újabb verzió.  
- **Java Development Kit (JDK)** – 8+ verzió.  
- **Maven** a függőségkezeléshez.  
- Egy IDE, például IntelliJ IDEA, Eclipse vagy VS Code.  
- Az alapvető Java és Maven ismeretek felgyorsítják a beállítást.

## A GroupDocs.Viewer for Java beállítása

### Maven konfiguráció
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

### Licenc beszerzési lépések
- **Ingyenes próba:** Tölts le egy ingyenes próbaverziót a [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) oldalról.  
- **Ideiglenes licenc:** Szerezz ideiglenes licencet a teljes funkciók korlátok nélküli kipróbálásához a [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) oldalon.  
- **Vásárlás:** A folyamatos használathoz fontold meg a licenc megvásárlását a [GroupDocs Purchase](https://purchase.groupdocs.com/buy) oldalon.

### Alapvető inicializálás és beállítás
A `Viewer` osztály a belépési pont minden renderelési művelethez a GroupDocs.Viewer for Java-ban. Automatikusan kezeli a fájl betöltését, a formátum felismerését és az erőforrások tisztítását.  
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Állítsd be a fájl útvonalát, hogy a saját `.msg` fájlodra mutasson.

## Hogyan konvertáljunk e‑mailt HTML‑re és nevezünk át mezőket – lépésről‑lépésre

Töltsd be az e‑mailt, definiálj egy mező‑leképező szótárat, konfiguráld a HTML nézet beállításait, és hívd meg a renderelési metódust. Az egész munkafolyamat hat tömör lépésben fejezhető ki.

### 1. Állítsd be a kimeneti könyvtár útvonalát
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Cseréld le a `"YOUR_OUTPUT_DIRECTORY"`-t arra a mappára, ahová az HTML fájlokat menteni szeretnéd.*

### 2. Definiáld az oldal fájl útvonal formátumát
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` a renderelés során az oldalszámmal lesz helyettesítve.*

### 3. Hozz létre egy leképezést az e‑mail mezőkről az új nevekhez
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Itt cseréljük le az alapértelmezett címkéket egyedi szövegekre.*

### 4. Állítsd be a HTML nézet opciókat
A `HtmlViewOptions` osztály szabályozza, hogyan jön létre a végső HTML. A `forEmbeddedResources` beállítása CSS/JS-t ágyaz be a HTML-be, míg a `setFieldTextMap` alkalmazza a definiált egyedi fejlécneveket.  
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```

### 5. Rendereld az e‑mailt HTML‑re
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Cseréld le a `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"`-t a MSG fájlod tényleges útvonalára.*

#### Hibaelhárítási tippek
- Ellenőrizd, hogy a kimeneti könyvtár írható-e.  
- Győződj meg róla, hogy a bemeneti MSG fájl létezik és az útvonal helyes.  
- Használd ugyanazt a GroupDocs.Viewer verziót (25.2), amelyet a Mavenben deklaráltál.

## Gyakorlati alkalmazások

1. **Egyedi e‑mail jelentések:** Az e‑mail fejlécek igazítása a vállalati terminológiához a tisztább jelentésekért.  
2. **E‑mail archiváló rendszerek:** A kereshetőség javítása szabványosított fejlécnevek használatával.  
3. **Ügyfélszolgálati platformok:** Jegyek megjelenítése személyre szabott fejléccímkékkel a jobb ügynöki élményért.

## Teljesítményfontosságú szempontok

- A `Viewer` objektumokat try‑with‑resources használatával szabadítsd fel a memóriát gyorsan.  
- Nagy kötegeket profilozz, és szükség esetén fontold meg az e‑mail-ek párhuzamos stream‑ekben történő feldolgozását.  
- A GroupDocs.Viewer **akár 200 MB** méretű e‑mail fájlokat is renderelhet anélkül, hogy a teljes dokumentumot memóriába töltené, köszönhetően a streaming architektúrának.

## Következtetés

Most már tudod, **hogyan konvertálj e‑mailt HTML‑re**, miközben **átnevezed az e‑mail mezőket** és **testreszabod az e‑mail fejléceket** a GroupDocs.Viewer for Java segítségével. Ez a technika teljes kontrollt ad az e‑mail metaadatok HTML kimenetben való megjelenítése felett.

### Következő lépések
- Kísérletezz további mezőleképezésekkel (pl. CC, BCC).  
- Fedezd fel a többi renderelési formátumot, például PDF vagy PNG.  
- Látogasd meg a [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) oldalt a mélyebb API ismeretekért.

## Gyakran ismételt kérdések

**Q: Működik ez a megközelítés más e‑mail formátumokkal, például EML‑lel?**  
A: Igen, a GroupDocs.Viewer támogatja az MSG és EML fájlokat is; ugyanaz a mezőleképezési logika érvényes.

**Q: Készíthetek HTML‑t beágyazott erőforrások nélkül?**  
A: Használhatod a `HtmlViewOptions.forExternalResources(...)`‑t, ha külön CSS/JS fájlokat szeretnél.

**Q: Melyik GroupDocs.Viewer verziót tesztelték?**  
A: A kód a GroupDocs.Viewer **25.2** verzióval lett tesztelve.

**Q: Lehet-e megváltoztatni a betűtípust vagy a stílust az egyedi fejlécekhez?**  
A: A stílus CSS‑sel alkalmazható a renderelés után, vagy egyedi CSS‑t injektálhatsz a `HtmlViewOptions.getResourcesPath()` használatával.

**Q: Hogyan tudom programozottan lekérni a generált HTML fájl útvonalát?**  
A: A fájl útvonal a `pageFilePathFormat`‑ben definiált mintát követi; a `String.format`‑et használva az oldalszámmal építheted fel.

## Erőforrások

- **Dokumentáció:** Átfogó útmutatók érhetők el a [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) oldalon.  
- **API referencia:** Részletes API információk a [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/) oldalon.  
- **GroupDocs.Viewer letöltése:** A legújabb verzió a [Downloads Page](https://releases.groupdocs.com/viewer/java/) oldalon érhető el.

---

**Legutóbb frissítve:** 2026-09-15  
**Tesztelve a:** GroupDocs.Viewer 25.2  
**Szerző:** GroupDocs

## Kapcsolódó oktatóanyagok

- [EML konvertálása HTML‑re egyedi dátummal Java-ban a GroupDocs.Viewer használatával](/viewer/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/)
- [java convert msg to pdf – Email‑to‑PDF renderelés optimalizálása a GroupDocs.Viewer‑rel](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Dokumentum mellékletek HTML‑re renderelése GroupDocs.Viewer Java‑val – Lépésről‑lépésre útmutató](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
