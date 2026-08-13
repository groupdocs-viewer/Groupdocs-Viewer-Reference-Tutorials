---
date: '2026-05-21'
description: Ismerje meg, hogyan végezhet MS Project HTML exportálást módosított időegységekkel
  a GroupDocs Viewer for Java használatával. Lépésről‑lépésre útmutató előfeltételekkel,
  telepítéssel és hibaelhárítással.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML Export: Időegységek módosítása a GroupDocs Java segítségével'
type: docs
url: /hu/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML Export: Időegységek módosítása a GroupDocs Java segítségével

Az **MS Project** fájl HTML‑re exportálása gyakori igény a projektmenedzsment műszerfalak, állapotjelentés portálok és együttműködő felülvizsgálati eszközök számára. Alapértelmezés szerint a néző percben jeleníti meg az időhöz kapcsolódó adatokat, ami elzsúfolhatja a vizuális elrendezést és nehezebbé teheti a napi jelentések olvasását. A **GroupDocs Viewer for Java** segítségével programozottan beállíthatja az időegységet **napokra**, így tiszta *ms project html export* jön létre, amely megfelel a tipikus érintettek elvárásainak. Ebben az útmutatóban megtanulja, hogyan konfigurálja a nézőt, módosítsa az időegységet, és néhány egyszerű lépésben renderelje a projektet HTML‑be.

![MS Project időegységek módosítása a GroupDocs.Viewer for Java segítségével](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[MS Project időegységek módosítása a GroupDocs.Viewer for Java segítségével](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Gyors válaszok
- **Melyik könyvtár rendereli az MS Project fájlokat?** GroupDocs Viewer for Java.  
- **Melyik időegységet állíthatom be a HTML exporthoz?** Napok, a `TimeUnit.DAYS` használatával.  
- **Szükségem van licencre a termeléshez?** Igen— állandó licenc szükséges; a próbaverzió értékelésre használható. Kezdhet egy [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)-val.  
- **Melyik IDE a legjobb?** Bármely Java IDE (IntelliJ IDEA, Eclipse, NetBeans), amely támogatja a Maven‑t.  
- **Kötelező a Maven?** A Maven egyszerűsíti a függőségkezelést, de használhat Gradle‑t vagy manuális JAR‑beillesztést is.  
- **Hol vásárolhatok?** Látogassa meg a [vásárlási oldalt](https://purchase.groupdocs.com/buy) az árakért.

## Mi a GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** egy Java SDK, amely több mint 150 dokumentumformátumot—köztük az MS Project‑et—web‑barát HTML‑re, PNG‑re, JPEG‑re vagy PDF‑re konvertál.  
Absztrahálja a feldolgozási logikát, lehetővé teszi a renderelési beállítások, például az időegységek vezérlését, és bármely, Java 8‑at vagy újabbat támogató platformon működik.

## Miért módosítsuk az időegységeket az MS Project HTML exportnál?
Az időegység **napokra** állítása csökkenti a vizuális zajt, megfelel a legtöbb jelentési ciklusnak, és javítja az oldalbetöltési időket, mivel kevesebb részletes időjelző kerül előállításra. Kvantitatív szempontból a napokkal történő renderelés a percek helyett akár **45 %**‑kal is csökkentheti a generált HTML méretét tipikus 30‑napos projektek esetén, és körülbelül **30 %**‑kal gyorsítja a kliensoldali renderelést.

## Előfeltételek
- **Java Development Kit (JDK) 8 vagy újabb** telepítve a munkaállomáson.  
- **Maven** (vagy Gradle) a függőségkezeléshez.  
- Egy **MS Project (.mpp)** fájl, amelyet exportálni szeretne.  
- Hozzáférés egy **GroupDocs Viewer for Java** licenchez (próba vagy állandó).  

### Szükséges könyvtárak
Adja hozzá a következő függőséget a `pom.xml` fájlhoz (vagy a megfelelő Gradle részlethez):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tipp:** Tartsa naprakészen a verziószámot; az újabb kiadások további formátumtámogatást és teljesítményjavulást hoznak.

## Hogyan állítsuk be a GroupDocs Viewer for Java‑t?
Inicializálja a nézőt egy `Viewer` példány létrehozásával, amely az MS Project fájlra mutat. A `Viewer` osztály a belépési pont minden renderelési művelethez. Betölti a forrásdokumentumot, előkészíti a belső struktúrákat, és elérhetővé teszi a `view()` és `viewToHtml()` metódusokat a kívánt kimeneti formátumok generálásához.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definíció horgony:** A `Viewer` osztály a GroupDocs Viewer központi komponense, amely betölti a forrásdokumentumot és renderelési metódusokat biztosít, mint a `view()` és a `viewToHtml()`.

## Hogyan módosíthatom az időegységeket a HTML exportnál?
Az időgranularitás módosításához hozzon létre egy `ViewOptions` objektumot, állítsa be a `ProjectOptions`‑ban a `TimeUnit.DAYS` értéket, majd adja át a nézőnek. A `ViewOptions` a dokumentum renderelési beállításait határozza meg, míg a `TimeUnit` enum az időhöz kapcsolódó adatok egységét (perc, óra, nap) adja meg. Ezek beállítása után hívja meg a `viewer.view(options)` metódust a napi jelölőkkel ellátott HTML előállításához.

Töltse be az MS Project fájlt a `new Viewer("file.mpp")` segítségével, hozza létre a `ViewOptions` objektumot, állítsa be a `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` értéket, majd hívja meg a `viewer.view(options)` metódust. Ez a háromlépéses folyamat a időegységet percről napra változtatja, és olyan HTML fájlokat generál, amelyek csak napi intervallumokat jelenítenek meg.

### 1. lépés: A kimeneti mappa meghatározása
Válasszon egy írható könyvtárat, ahová a HTML oldalak mentésre kerülnek, például `output/`.

### 2. lépés: Nézetbeállítások létrehozása beágyazott erőforrásokkal
A beágyazott erőforrások (CSS, JavaScript) biztosítják, hogy a HTML oldalak önállóak legyenek.

### 3. lépés: Az időegység napokra állítása
Használja a `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` kifejezést a granularitás átváltásához.

### 4. lépés: A dokumentum renderelése
Hívja meg a `viewer.view(options)` metódust; a néző egy HTML fájlt ír minden projektoldalra a kimeneti mappába.

### 5. lépés: Az eredmény ellenőrzése
Nyissa meg a generált `index.html` fájlt egy böngészőben; a feladat sávoknak napjelölőkhöz kell igazodniuk, nem percjelölőkhöz.

## Gyakori buktatók és hibaelhárítás
- **Helytelen kimeneti útvonal** – Győződjön meg róla, hogy a könyvtár létezik, és a Java folyamatnak írási jogosultsága van.  
- **Hiányzó licenc** – Érvényes licenc nélkül a néző visszatér a próbaverzió módba, és vízjeleket ágyazhat be.  
- **Nagy fájlok (> 500 MB)** – Fontolja meg a JVM heap méretének növelését (`-Xmx2g`), vagy rendereljen `options.setRenderLimit(1000)` használatával, hogy a lapokat kötegekben dolgozza fel.  

## A módosított időegységű HTML export gyakorlati alkalmazásai
1. **Vezetői műszerfalak** – A napi granularitás megfelel a legtöbb KPI vizualizációnak.  
2. **Automatizált állapot e‑mailek** – Ágyazza be a generált HTML‑t közvetlenül az e‑mail szövegébe a gyors frissítésekhez.  
3. **Projekt portálok** – Helyezze el a HTML‑t egy intranet oldalon, ahol a csapattagok nap szerint szűrhetik a feladatokat.  

## Teljesítményfontosságú szempontok nagy MS Project fájlok esetén
- **Memória kezelése** – Használja a Java szemétgyűjtő zászlókat (`-XX:+UseG1GC`) a nem használt objektumok gyors felszabadításához.  
- **Szelektív renderelés** – Ha csak a Gantt-diagramra van szükség, tiltsa le a többi erőforrás renderelését a `options.getProjectOptions().setRenderGantt(true)` és `setRenderResources(false)` segítségével.  
- **Párhuzamos feldolgozás** – Kötetes konverziókhoz hozzon létre külön `Viewer` objektumokat fájlonként, és futtassa őket szálkezelőben a többmagos CPU-k kihasználásához.  

## Következtetés
Most már rendelkezik egy teljes, termelésre kész munkafolyamattal az **ms project html export** végrehajtásához, ahol az időegység napokra van állítva a GroupDocs Viewer for Java használatával. Ez a megközelítés csökkenti a HTML méretét, felgyorsítja a kliensoldali renderelést, és érintettek számára barátságos projektmenetrendet biztosít. Fedezzen fel további renderelési lehetőségeket—például PDF export vagy képképek—hogy a integrációt szélesebb jelentési csővezetékekbe bővítse.

## Gyakran Ismételt Kérdések

**Q: Renderelhetek más Project nézeteket (pl. Erőforráslap) HTML‑re?**  
A: Igen, a `ProjectOptions` objektum lehetővé teszi, hogy a renderelés előtt engedélyezze vagy letiltsa a konkrét nézeteket, mint a Gantt, Erőforráslap és Naptár.

**Q: Lehet testreszabni a generált HTML CSS‑ét?**  
A: Teljesen. Adjon meg egy egyedi stíluslap útvonalát a `options.setStyleSheetPath("path/to/custom.css")` segítségével, és a néző minden oldalba beágyazza azt.

**Q: Milyen fájlméret korlátokat támogat a GroupDocs Viewer az MS Project esetén?**  
A: Az SDK képes akár **500 MB**‑ig terjedő fájlok kezelésére anélkül, hogy a teljes dokumentumot memóriába kellene tölteni, köszönhetően a streaming architektúrának.

**Q: Szükséges a Microsoft Project telepítése a szerveren?**  
A: Nem. A GroupDocs Viewer közvetlenül a .mpp formátumot dolgozza fel, és nem igényel Microsoft Project‑et vagy bármilyen Office telepítést.

**Q: Hogyan licenceljem a nézőt egy termelési környezetben?**  
A: Vásároljon állandó licencet a GroupDocs áruházból; a licencfájlt futásidőben alkalmazza a `License license = new License(); license.setLicense("path/to/license.lic");` kóddal. Rövid távú igényekhez szerezhet [ideiglenes licencet](https://purchase.groupdocs.com/temporary-license/).

---

**Last Updated:** 2026-05-21  
**Tested With:** GroupDocs Viewer Java 25.2  
**Author:** GroupDocs  

## Erőforrások
- [Dokumentáció](https://docs.groupdocs.com/viewer/java/)  
- [API Referencia](https://reference.groupdocs.com/viewer/java/)  
- [GroupDocs.Viewer letöltése](https://releases.groupdocs.com/viewer/java/)  
- [Licenc vásárlása](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Kapcsolódó oktatóanyagok

- [Hogyan rendereljük az MS Project fájlokat HTML‑ként, JPG‑ként, PNG‑ként és PDF‑ként megjegyzésekkel a GroupDocs.Viewer for Java használatával](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Hogyan használjuk a GroupDocs Viewer‑t projekt dokumentumok időintervallumok szerinti renderelésére Java‑ban](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Hogyan állítsunk be licenceket a GroupDocs.Viewer Java‑ban: Fájl és URL beállítási útmutató](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)