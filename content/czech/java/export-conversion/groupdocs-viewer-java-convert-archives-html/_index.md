---
date: '2026-08-03'
description: Zjistěte, jak převést zip na html pomocí GroupDocs.Viewer Java, nastavit
  položky na stránku, vložit html zdroje a efektivně hromadně převádět archivy.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Zjistěte, jak převést zip na html pomocí GroupDocs.Viewer Java, nastavit
  položky na stránku, vložit html zdroje a efektivně hromadně převádět archivy. Postupujte
  podle step‑by‑step kódu a performance tips.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Převod zip na html a nastavení položek na stránku pomocí GroupDocs.Viewer
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Převod zip na html a nastavení položek na stránku pomocí GroupDocs.Viewer Java
type: docs
url: /cs/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Převod zip na html a nastavení položek na stránku pomocí GroupDocs.Viewer Java

V mnoha webových aplikacích potřebujete zobrazit obsah ZIP nebo RAR archivu přímo v prohlížeči. S GroupDocs.Viewer pro Java můžete **convert zip to html** v jediném kroku, řídit, kolik položek archivu se zobrazí na každé stránce, vložit všechny související obrázky a CSS a dokonce hromadně zpracovat desítky archivů. Tento tutoriál vás provede kompletním pracovním postupem, od nastavení Maven až po vícestránkové vykreslování, a vysvětlí, proč je každé nastavení důležité pro výkon a použitelnost.

![Převod archivů do HTML pomocí GroupDocs.Viewer pro Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Rychlé odpovědi
- **Co řídí “set items per page”?** Určuje, kolik souborů nebo složek z archivu se objeví na každé vygenerované HTML stránce.  
- **Mohu vložit obrázky a CSS přímo do HTML?** Ano – použijte možnost `forEmbeddedResources` k vložení zdrojů do HTML.  
- **Je hromadná konverze možná?** Rozhodně; můžete projít kolekci archivů a vykreslit každý s těmi samými nastaveními.  
- **Potřebuji Maven pro použití GroupDocs.Viewer?** Ano, přidejte Maven závislost `groupdocs-viewer` jak je uvedeno níže.  
- **Jaké výstupní formáty jsou podporovány?** Single‑page HTML a multi‑page HTML jsou oba k dispozici a knihovna podporuje více než 50 vstupních typů archivů.

## Co je “set items per page” v GroupDocs.Viewer?
Nastavení **set items per page** patří k možnostem vykreslování archivů. Říká prohlížeči, kolik položek archivu (souborů nebo složek) má být zobrazeno na každé HTML stránce při generování vícestránkového HTML dokumentu. Úprava této hodnoty vám pomůže vyvážit velikost stránky a rychlost navigace, zejména u velkých archivů.

## Proč vložit resources html?
Vkládání zdrojů (obrázků, CSS, fontů) přímo do HTML souboru vytvoří jeden přenosný dokument, který lze otevřít bez externích souborů. To je ideální pro e‑mailové přílohy, offline prohlížení nebo vložení výstupu do jiných webových stránek. Tento přístup také zjednodušuje nasazení, protože není nutné spravovat cesty k externím assetům.

## Požadavky

- **Požadované knihovny:** Zahrňte GroupDocs.Viewer verze 25.2 nebo novější.  
- **Prostředí:** Nainstalovaný a nakonfigurovaný Java Development Kit (JDK).  
- **Znalosti:** Základní Java a správa Maven závislostí.  

## Nastavení Maven GroupDocs Viewer

Přidejte repozitář GroupDocs a závislost viewer do vašeho `pom.xml`:

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

### Získání licence
GroupDocs.Viewer nabízí **free trial link**, dočasnou licenci nebo plnou možnost zakoupení. Vyberte tu, která vyhovuje časovému plánu vašeho projektu.

### Základní inicializace
Po nastavení Maven přidejte viewer do svého kódu:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Jak vykreslit archivy do jedné stránky html
Viewer je hlavní třída, která načítá dokument nebo archiv pro vykreslení.

Pro vygenerování jediného HTML souboru, který obsahuje celý archiv, vytvořte instanci `Viewer` pro ZIP soubor a použijte `HtmlViewOptions.forEmbeddedResources()` k vložení všech obrázků, CSS a fontů. Vykreslení archivu s těmito možnostmi vytvoří jednu samostatnou stránku vhodnou pro e‑mail nebo offline použití.

### Krok 1: Definujte výstupní adresář
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Nastavte název souboru pro jednostránkový výstup
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Krok 3: Inicializujte viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Krok 4: Nakonfigurujte možnosti vykreslování (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Vykreslete jako jedinou stránku
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Jak vykreslit archivy do vícestránkového html a nastavit položky na stránku
`HtmlViewOptions` konfiguruje, jak viewer vykresluje HTML výstup, včetně stránkování a vkládání zdrojů.

Pro rozdělení archivu na více stránek vytvořte `HtmlViewOptions.forEmbeddedResources()` a nastavte požadovanou velikost stránky pomocí `options.setItemsPerPage(20)`. Viewer vygeneruje samostatné HTML soubory, z nichž každý zobrazí až zadaný počet položek, což zlepšuje navigaci u velkých archivů a zajišťuje rychlejší načítání.

### Krok 1: Znovu použijte výstupní adresář
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Definujte formát názvu souboru pro více stránek
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Krok 3: Znovu inicializujte viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Krok 4: Nakonfigurujte možnosti vícestránkového výstupu (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Nastavte položky na stránku (hlavní klíčové slovo v akci)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktické aplikace

- **Document management systems:** Přidejte funkci náhledu archivu bez instalace dalších prohlížečů.  
- **Web portals:** Nabídněte uživatelům rychlý způsob, jak prozkoumat zabalené dokumenty bez stahování.  
- **Collaboration tools:** Umožněte týmům prohlížet sdílené archivy přímo v prohlížeči.

## Úvahy o výkonu

- **Resource management:** Udržujte nízkou spotřebu paměti zpracováním archivů ve streamu; viewer dokáže zpracovat archivy až do 500 MB bez načtení celého souboru do paměti.  
- **Batch convert archives:** Procházejte seznam archivních souborů a volajte stejnou logiku vykreslování pro maximalizaci propustnosti.  
- **Caching strategy:** Uložte vygenerované HTML do cache, pokud je stejný archiv často přistupován, čímž snížíte opakovaný čas zpracování až o 70 %.

## Často kladené otázky

**Q: Co je GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java je server‑side knihovna, která převádí více než 50 formátů dokumentů a archivů — včetně ZIP a RAR — do HTML, PDF nebo obrazových souborů bez potřeby externích aplikací.

**Q: Jak mohu získat free trial link GroupDocs.Viewer?**  
A: Navštivte [free trial link](https://releases.groupdocs.com/viewer/java/) pro stažení a testování.

**Q: Mohu převádět i jiné typy dokumentů kromě archivů?**  
A: Ano, viewer podporuje PDF, Word, Excel, PowerPoint a více než 35 dalších formátů.

**Q: Co mám dělat, pokud je vykreslování pomalé?**  
A: Snižte počet položek na stránku, povolte streamování nebo zpracovávejte archivy v menších dávkách pro zrychlení.

**Q: Kde mohu získat pomoc nebo podporu?**  
A: Kontaktujte nás prostřednictvím [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Je možné vložit CSS a obrázky přímo do HTML?**  
A: Rozhodně — použijte `HtmlViewOptions.forEmbeddedResources` jak je ukázáno v příkladech.

**Q: Jak mohu hromadně převést složku archivů?**  
A: Procházejte každý soubor pomocí `for` smyčky a aplikujte stejnou konfiguraci `Viewer` a `HtmlViewOptions` pro každou iteraci.

## Zdroje

- **Documentation:** Prozkoumejte podrobněji funkčnost v [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API reference:** Prozkoumejte kompletní API na [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Získejte nejnovější binární soubory ze [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and licensing:** Prohlédněte si možnosti na [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and community:** Připojte se k diskuzím na [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Poslední aktualizace:** 2026-08-03  
**Testováno s:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs

## Související tutoriály

- [Jak převést zip na HTML a vykreslit složky zip v Java s GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [převést zip na pdf s GroupDocs.Viewer Java - Vlastní názvy souborů](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Jak převést DOCX na HTML pomocí GroupDocs.Viewer pro Java: Průvodce krok za krokem](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)