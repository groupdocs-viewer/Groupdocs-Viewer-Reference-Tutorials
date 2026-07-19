---
date: '2026-07-19'
description: Ismerje meg, hogyan konvertálhatja a PST‑t HTML‑re és más formátumokra,
  például JPG‑re, PNG‑re, PDF‑re a GroupDocs.Viewer for Java segítségével. Ez az útmutató
  lefedi a szükséges összes lépést és beállítást.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Konvertálja gyorsan a PST‑t HTML‑re a GroupDocs.Viewer for Java segítségével.
  Ismerje meg lépésről lépésre, hogyan exportálhat JPG‑re, PNG‑re és PDF‑re egy termelésre
  kész útmutatóban.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: PST konvertálása HTML‑re a GroupDocs.Viewer for Java‑val – Gyors e‑mail
  export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: PST konvertálása HTML‑re, JPG‑re, PNG‑re, PDF‑re a GroupDocs.Viewer for Java
  használatával
type: docs
url: /hu/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# PST konvertálása HTML-re, JPG-re, PNG-re, PDF-re a GroupDocs.Viewer for Java használatával

Szeretne **convert pst to html** vagy más formátumokra, például JPG, PNG vagy PDF konvertálni? A hatékony GroupDocs.Viewer for Java könyvtárral ez a feladat egyszerű és hatékony. Ebben az útmutatóban megtanulja, hogyan jelenítheti meg az Outlook PST/OST fájlokat web‑barát HTML‑ben, képfájlokban vagy egyetlen PDF‑ben, így az e‑mail archívumok könnyen megoszthatók és archiválhatók.

![PST/OST konvertálása HTML-re, JPG-re, PNG-re, PDF-re a GroupDocs.Viewer for Java segítségével](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Mit fog megtanulni**
- Hogyan állítsa be a GroupDocs.Viewer for Java-t egy Maven projektben.  
- Lépésről‑lépésre útmutató a **java convert pst** fájlok HTML, JPG, PNG és PDF formátumba konvertálásához.  
- Konfigurációs tippek az optimális teljesítményhez és a gyakori hibák elkerüléséhez.

## Gyors válaszok
- **Melyik könyvtár kezeli a PST konvertálást?** GroupDocs.Viewer for Java.  
- **Konvertálhatok PST‑t közvetlenül PDF‑re?** Igen, a `PdfViewOptions` használatával.  
- **Szükséges licenc a termeléshez?** Érvényes GroupDocs licenc szükséges.  
- **Melyik Java verzió támogatott?** JDK 8 vagy újabb.  
- **Kézzel kell kicsomagolni a mellékleteket?** Nem, a megjelenítő automatikusan rendereli őket.

## Mi a GroupDocs.Viewer for Java?
A GroupDocs.Viewer for Java egy szerver‑oldali API, amely több mint 100 dokumentum- és e‑mail formátumot tölt be, és HTML, kép vagy PDF kimenetként jeleníti meg külső szoftver nélkül. PST fájlokat 2 GB-ig dolgoz fel, miközben a memóriahasználat 200 MB alatt marad.

## Hogyan konvertáljunk pst-t html-re a GroupDocs.Viewer for Java használatával?
Töltse be a PST fájlt a `new Viewer("source.pst")` segítségével, állítsa be a `HtmlViewOptions`-t egy kimeneti mappára, és hívja meg a `viewer.view(htmlOptions)` metódust. Az API automatikusan kinyeri minden e‑mailt, megőrzi a formázást, a mellékleteket és a metaadatokat, és minden üzenethez külön HTML oldalt ír – mindezt egyetlen metódushívásban.

### Miért válassza a GroupDocs.Viewer‑t?
- **Magas‑hűségű renderelés** – Az e‑mail tartalom 99,9 %-a (beleértve a gazdag szöveges testeket, táblázatokat és beágyazott képeket) pontosan reprodukálódik.  
- **Több kimeneti formátum** – Egy API hívás generálhat HTML‑t, JPG‑t, PNG‑t vagy PDF‑t, több mint 50 exportálási lehetőséggel.  
- **Nulla külső függőség** – Nem szükséges Outlook, Exchange Server vagy harmadik fél konverter; minden a Java futtatókörnyezetén belül fut.

## Előfeltételek
- **GroupDocs.Viewer for Java** – 25.2 vagy újabb verzió.  
- **Java Development Kit (JDK)** – 8 vagy újabb.  
- Maven a függőségkezeléshez.  
- Alap Java ismeretek és Maven ismerete.

## A GroupDocs.Viewer for Java beállítása
`Viewer` a GroupDocs.Viewer for Java központi osztálya, amely betölti a dokumentumot és a választott formátumba rendereli. Adja hozzá a GroupDocs tárolót és a függőséget a `pom.xml`-hez:

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
- **Free trial** – minden funkció kipróbálása költség nélkül.  
- **Temporary license** – a kiértékelési idő meghosszabbítása szükség esetén.  
- **Full license** – szükséges a termelési környezetben való telepítéshez.

### Alap inicializálás
`Viewer` példányok könnyűek; egyetlen példányt újra felhasználhat sok fájlhoz, hogy minimalizálja az objektum‑létrehozási terhelést.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Megvalósítási útmutató
A következő szakaszok végigvezetik a PST/OST fájlok minden támogatott formátumba történő renderelésén.

### PST/OST dokumentumok renderelése HTML-be

#### 1. lépés: Kimeneti könyvtár beállítása
Határozzon meg egy mappát, ahová a HTML oldalak íródnak. A GroupDocs minden e‑mailhez egy alkönyvtárat hoz létre az eszközök rendezett tárolásához.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### 2. lépés: Load Options konfigurálása
A `LoadOptions` lehetővé teszi a jelszókezelés, az erőforrás‑betöltési időkorlátok és a szelektív oldalrenderelés megadását. 30 másodperces időkorlát beállítása a legtöbb szerverkörnyezetben jól működik.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 3. lépés: HTML View Options meghatározása
A `HtmlViewOptions` megadja a kimeneti mappát, az erőforráskezelést és opcionális CSS beállításokat a HTML konvertáláshoz.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### 4. lépés: Viewer inicializálása és HTML renderelése
Hozzon létre egy `Viewer` objektumot, adja meg a PST fájl útvonalát, és hívja meg a `view` metódust a `HtmlViewOptions`‑szal. Az API automatikusan végigiterál a PST‑ben lévő összes üzeneten, és rendezett HTML hierarchiát generál.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### PST/OST dokumentumok renderelése JPG-be

#### 1. lépés: Kimeneti könyvtár beállítása
Hozzon létre egy dedikált mappát a JPG pillanatképeknek; minden e‑mail a hosszától függően egy vagy több képfájlt eredményez.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 2. lépés: Load Options konfigurálása
Az HTML‑hez használt `LoadOptions` ugyanúgy felhasználható itt is, biztosítva a jelszókezelés konzisztenciáját a formátumok között.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 3. lépés: JPG View Options meghatározása
A `JpgViewOptions` szabályozza a kép felbontását, minőségét és a JPEG konvertálás kimeneti mappáját.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### 4. lépés: Viewer inicializálása és JPG renderelése
Használja a `viewer.view(jpgOptions)` metódust, hogy magas minőségű JPEG fájlokat generáljon, amelyek készen állnak a webes előnézetre.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### PST/OST dokumentumok renderelése PNG-be

#### 1. lépés: Kimeneti könyvtár beállítása
A PNG kimenet hasznos, ha veszteségmentes minőségre van szükség archiváláshoz vagy OCR feldolgozáshoz.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 2. lépés: Load Options konfigurálása
A jelszó és időkorlát beállításon kívül nincs szükség további beállításokra.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### 3. lépés: PNG View Options meghatározása
A `PngViewOptions` lehetővé teszi átlátszó háttér és kimeneti mappa beállítását a veszteségmentes PNG képekhez.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 4. lépés: Viewer inicializálása és PNG renderelése
Hozzon létre egy `viewer.view(pngOptions)` hívást, hogy PNG pillanatképeket készítsen minden e‑mailről.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST dokumentumok renderelése PDF-be

#### 1. lépés: Kimeneti könyvtár beállítása
Egyetlen PDF fájl PST‑nként egyszerűsíti a jogi felülvizsgálati munkafolyamatokat és csökkenti a tárolási terhelést.

CODE_BLOCK_PLACEHOLDER_14_END

#### 2. lépés: Load Options konfigurálása
PDF‑re konvertáláskor érdemes engedélyezni a `setEmbedFonts(true)` beállítást, hogy bármely gépen garantálja a vizuális hűséget.

CODE_BLOCK_PLACEHOLDER_15_END

#### 3. lépés: PDF View Options meghatározása
A `PdfViewOptions` lehetővé teszi a tömörítési szint, a betűk beágyazása és a PDF konvertálás kimeneti fájlnevének beállítását.

CODE_BLOCK_PLACEHOLDER_16_END

#### 4. lépés: Viewer inicializálása és PDF renderelése
Hozzon létre `PdfViewOptions`‑t, opcionálisan válasszon tömörítési szintet, és hívja meg a `viewer.view(pdfOptions)` metódust. Az API az összes e‑mailt egy kereshető PDF dokumentummá egyesíti.

CODE_BLOCK_PLACEHOLDER_17_END

## Gyakorlati alkalmazások
- **Email Archiving:** Nagy PST archívumok kereshető HTML‑re vagy PDF‑re alakítása a megfelelőség érdekében.  
- **Document Management Systems:** A konvertált fájlok tárolása olyan rendszerekben, amelyek csak PDF‑et, PNG‑t vagy JPG‑t fogadnak el.  
- **Collaboration Platforms:** A konvertált e‑mailek megosztása képként a Slack‑en vagy a Teams‑en.  
- **Legal Review:** A bíróságok számára PDF verziók biztosítása az e‑mail bizonyítékokról.  
- **Backup Strategies:** Könnyű PNG vagy JPG pillanatképek megtartása a kritikus üzenetekről.

## Teljesítmény szempontok
- **Resource Management:** Több fájl feldolgozásakor használja újra a `Viewer` példányokat a terhelés csökkentése érdekében.  
- **Memory Tuning:** Állítsa be a `loadOptions.setResourceLoadingTimeout` értékét a szerver kapacitása alapján.  
- **Asynchronous Processing:** A konvertálást háttérszálakra helyezze át a válaszkész UI‑k érdekében.

## Gyakran Ismételt Kérdések

**Q: Hogyan **convert pst to pdf** ugyanazzal a kódbázissal?**  
A: Használja a `PdfViewOptions`‑t, ahogy a PDF renderelési szakaszban látható; a kód többi része változatlan marad.

**Q: Képes a GroupDocs.Viewer titkosított PST fájlok kezelésére?**  
A: Igen, adja meg a jelszót a `LoadOptions.setPassword("yourPassword")` segítségével a renderelés előtt.

**Q: Mi a különbség a **java convert pst** PNG és JPG közti konvertálás között?**  
A: A PNG megőrzi a veszteségmentes minőséget, ideális képernyőképekhez, míg a JPG kisebb fájlméreteket kínál az e‑mail előnézetekhez.

**Q: Van mód **how to convert pst** fájlok tömeges konvertálására?**  
A: A renderelési logikát egy ciklusba ágyazza, amely egy PST fájlok könyvtárán iterál; használja ugyanazt a `Viewer` konfigurációt minden fájlhoz.

**Q: Támogatja az API a 1 GB-nál nagyobb PST fájlok konvertálását?**  
A: Igen, a GroupDocs.Viewer adatfolyamként dolgozza fel a fájlokat, és akár 2 GB-ig képes feldolgozni a teljes archívum memóriába töltése nélkül.

## Összegzés
Most már rendelkezik egy teljes, termelés‑kész útmutatóval a **convert pst to html**, JPG, PNG és PDF konvertálásához a GroupDocs.Viewer for Java használatával. A fenti lépések követésével bármely Java‑alapú munkafolyamatba integrálhatja az e‑mail konvertálást, javíthatja az elérhetőséget és megfelelhet a megfelelőségi követelményeknek.

---

**Utoljára frissítve:** 2026-07-19  
**Tesztelve ezzel:** GroupDocs.Viewer for Java 25.2  
**Szerző:** GroupDocs

## Kapcsolódó oktatóanyagok

- [NSF konvertálása PDF-re, HTML-re, JPG-re, PNG-re a GroupDocs.Viewer for Java használatával](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – ODF konvertálása HTML-re, JPG-re, PNG-re, PDF-re a GroupDocs.Viewer for Java használatával](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Hogyan konvertáljunk DOCX-et HTML-re a GroupDocs.Viewer for Java használatával: Lépésről‑lépésre útmutató](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)