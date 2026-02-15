---
date: '2026-02-15'
description: Ismerje meg, hogyan konvertálhatja a PST fájlokat HTML-re és más formátumokra,
  például JPG, PNG, PDF, a GroupDocs.Viewer for Java használatával. Ez az útmutató
  lefedi a szükséges összes lépést és beállítást.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: PST átalakítása HTML, JPG, PNG, PDF formátumokra a GroupDocs.Viewer for Java
  segítségével
type: docs
url: /hu/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# PST konvertálása HTML-re, JPG-re, PNG-re, PDF-re a GroupDocs.Viewer for Java segítségével

Szeretne **convert pst to html** vagy más formátumokra, például JPG, PNG vagy PDF konvertálni? A hatékony GroupDocs.Viewer for Java könyvtárral ez a feladat egyszerű és hatékony. Ebben az útmutatóban megtanulja, hogyan jelenítheti meg az Outlook PST/OST fájlokat web‑barát HTML‑ben, képfájlokban vagy egyetlen PDF‑ben, így az e‑mail archívumok könnyen megoszthatók és archiválhatók.

![PST/OST konvertálása HTML-re, JPG-re, PNG-re, PDF-re a GroupDocs.Viewer for Java segítségével](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Mit fog megtanulni**
- Hogyan állítsa be a GroupDocs.Viewer for Java-t egy Maven projektben.  
- Lépésről‑lépésre útmutató a **java convert pst** fájlok HTML, JPG, PNG és PDF formátumba konvertálásához.  
- Konfigurációs tippek az optimális teljesítményhez és a gyakori hibák elkerüléséhez.

## Gyors válaszok
- **Melyik könyvtár kezeli a PST konverziót?** GroupDocs.Viewer for Java.  
- **Konvertálhatom a PST‑t közvetlenül PDF‑re?** Igen, a `PdfViewOptions` használatával.  
- **Szükséges licenc a termeléshez?** Érvényes GroupDocs licenc szükséges.  
- **Melyik Java verzió támogatott?** JDK 8 vagy újabb.  
- **Kézzel kell kicsomagolni a mellékleteket?** Nem, a viewer automatikusan megjeleníti őket.

## Hogyan konvertáljon pst-t html-re a GroupDocs.Viewer for Java segítségével
Az alábbiakban egy tömör áttekintést talál a konverziós folyamatról, mielőtt a részletes kódrészletekbe merülne.

### Miért válassza a GroupDocs.Viewer‑t?
- **High fidelity** megjelenítés az e‑mail tartalmak, mellékletek és formázás esetén.  
- **Multiple output formats** (HTML, JPG, PNG, PDF) egyetlen API‑ból.  
- **No external dependencies** – minden a Java alkalmazásán belül fut.

## Előfeltételek
- **GroupDocs.Viewer for Java** – 25.2 vagy újabb verzió.  
- **Java Development Kit (JDK)** – 8 vagy újabb.  
- Maven a függőségek kezeléséhez.  
- Alap Java ismeretek és Maven ismerete.

## A GroupDocs.Viewer for Java beállítása

Adja hozzá a GroupDocs tárolót és a függőséget a `pom.xml` fájlhoz:

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
- **Full license** – szükséges a termelési környezethez.

### Alap inicializálás

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

## Implementációs útmutató

Az alábbi szakaszok végigvezetik a PST/OST fájlok minden támogatott formátumba történő renderelésén.

### PST/OST dokumentumok renderelése HTML-re

#### 1. lépés: Kimeneti könyvtár beállítása

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### 2. lépés: Betöltési beállítások konfigurálása

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 3. lépés: Viewer inicializálása és HTML renderelése

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST dokumentumok renderelése JPG-re

#### 1. lépés: Kimeneti könyvtár beállítása

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### 2. lépés: Betöltési beállítások konfigurálása

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 3. lépés: Viewer inicializálása és JPG renderelése

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST dokumentumok renderelése PNG-re

#### 1. lépés: Kimeneti könyvtár beállítása

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### 2. lépés: Betöltési beállítások konfigurálása

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 3. lépés: Viewer inicializálása és PNG renderelése

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST dokumentumok renderelése PDF-re

#### 1. lépés: Kimeneti könyvtár beállítása

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### 2. lépés: Betöltési beállítások konfigurálása

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 3. lépés: Viewer inicializálása és PDF renderelése

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Gyakorlati alkalmazások
- **Email Archiving:** Nagy PST archívumok átalakítása kereshető HTML‑re vagy PDF‑re a megfelelőség érdekében.  
- **Document Management Systems:** A konvertált fájlok tárolása olyan rendszerekben, amelyek csak PDF, PNG vagy JPG formátumot fogadnak.  
- **Collaboration Platforms:** A konvertált e‑mailek megosztása képként a Slack‑ben vagy Teams‑ben.  
- **Legal Review:** A bíróságok számára PDF verziók biztosítása e‑mail bizonyítékokról.  
- **Backup Strategies:** Könnyű PNG vagy JPG pillanatképek tárolása kritikus üzenetekről.

## Teljesítményfontosságú szempontok
- **Resource Management:** Több fájl feldolgozásakor újrahasználja a `Viewer` példányokat a terhelés csökkentése érdekében.  
- **Memory Tuning:** Állítsa be a `loadOptions.setResourceLoadingTimeout` értékét a szerver kapacitása alapján.  
- **Asynchronous Processing:** A konverzió áthelyezése háttérszálakra a válaszkész UI‑k érdekében.  

## Gyakran ismételt kérdések

**Q: Hogyan **convert pst to pdf** ugyanazzal a kódbázissal?**  
A: Használja a `PdfViewOptions`-t, ahogy a PDF renderelési szakaszban látható; a kód többi része változatlan marad.

**Q: Kezelni tudja a GroupDocs.Viewer a titkosított PST fájlokat?**  
A: Igen, adja meg a jelszót a `LoadOptions.setPassword("yourPassword")` segítségével a renderelés előtt.

**Q: Mi a különbség a **java convert pst** PNG és JPG közti konvertálásban?**  
A: A PNG veszteségmentes minőséget biztosít, ideális képernyőképekhez, míg a JPG kisebb fájlméretet kínál az e‑mail előnézetekhez.

**Q: Van mód **how to convert pst** fájlok tömeges konvertálására?**  
A: A renderelési logikát egy ciklusba ágyazza, amely egy PST fájlok könyvtárán iterál; minden fájlhoz használja ugyanazt a `Viewer` konfigurációt.

## Következtetés

Most már rendelkezik egy teljes, termelésre kész útmutatóval a **convert pst to html**, JPG, PNG és PDF konvertálásához a GroupDocs.Viewer for Java segítségével. A fenti lépések követésével bármely Java‑alapú munkafolyamatba beépítheti az e‑mail konverziót, javíthatja a hozzáférhetőséget, és megfelelhet a megfelelőségi követelményeknek.

---

**Utolsó frissítés:** 2026-02-15  
**Tesztelve ezzel:** GroupDocs.Viewer for Java 25.2  
**Szerző:** GroupDocs