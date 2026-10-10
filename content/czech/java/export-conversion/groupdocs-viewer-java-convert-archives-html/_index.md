---
date: '2026-10-10'
description: Zjistěte, jak převést zip na html pomocí GroupDocs.Viewer Java, nastavit
  položky na stránku, vložit zdroje html a efektivně hromadně převádět archivy.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: Zjistěte, jak převést zip na html pomocí GroupDocs.Viewer Java, vložit
  zdroje, nastavit položky na stránku a hromadně zpracovat archivy pro rychlé, přenosné
  webové náhledy.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: Převod zipu na HTML s stránkováním pomocí GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
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
title: Převod zipu na html a nastavení položek na stránku pomocí GroupDocs.Viewer
  Java
type: docs
url: /cs/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod zip na html a nastavení položek na stránku pomocí GroupDocs.Viewer Java

V mnoha webových aplikacích potřebujete zobrazit obsah ZIP nebo RAR archivu přímo v prohlížeči. **Jak převést zip** soubory do HTML pomocí GroupDocs.Viewer pro Java je běžná potřeba a knihovna vám umožní vložit obrázky, CSS a fonty, takže výsledek je jediná, přenosná stránka. Tento tutoriál vás provede vším – od nastavení Maven až po vícestránkové vykreslování – a zároveň vysvětlí, proč každá volba ovlivňuje výkon a použitelnost.

![Převod archivů do HTML pomocí GroupDocs.Viewer pro Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Rychlé odpovědi
- **Co řídí nastavení „set items per page“?** Určuje, kolik souborů nebo složek z archivu se zobrazí na každé vygenerované HTML stránce.  
- **Mohu vložit obrázky a CSS přímo do HTML?** Ano – použijte volbu `forEmbeddedResources` pro vložení zdrojů do HTML.  
- **Je hromadná konverze možná?** Rozhodně; můžete projít kolekci archivů a vykreslit každý se stejným nastavením.  
- **Potřebuji Maven k použití GroupDocs.Viewer?** Ano, přidejte Maven závislost `groupdocs-viewer` podle níže uvedeného příkladu.  
- **Jaké výstupní formáty jsou podporovány?** Jednostránkové HTML i vícestránkové HTML jsou k dispozici a knihovna podporuje více než 50 typů vstupních archivů.

## Co je „set items per page“ v GroupDocs.Viewer?
Říká prohlížeči, kolik položek archivu (souborů nebo složek) se má zobrazit na každé HTML stránce při generování více‑stránkového dokumentu. Úprava této hodnoty vám pomůže vyvážit velikost stránky a rychlost navigace, zejména u velkých archivů, tím, že omezí množství načítaných dat na stránku a sníží dobu vykreslování pro koncové uživatele.

## Proč vkládat zdroje do HTML?
Vkládání zdrojů (obrázky, CSS, fonty) přímo do HTML souboru vytvoří jediný, přenosný dokument, který lze otevřít bez externích souborů. To je ideální pro e‑mailové přílohy, offline prohlížení nebo vložení výstupu do jiných webových stránek. Navíc odstraňuje potřebu spravovat externí cesty k assetům.

## Požadavky

- **Požadované knihovny:** Zahrňte GroupDocs.Viewer verze 25.2 nebo novější.  
- **Prostředí:** Nainstalovaný a nakonfigurovaný Java Development Kit (JDK).  
- **Znalosti:** Základy Javy a správy Maven závislostí.  

## Nastavení Maven pro GroupDocs Viewer

Přidejte repozitář GroupDocs a závislost vieweru do svého `pom.xml`:

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
GroupDocs.Viewer nabízí **odkaz na bezplatnou zkušební verzi**, dočasnou licenci nebo plnou koupi. Vyberte možnost, která nejlépe vyhovuje časovému plánu vašeho projektu.

## Základní inicializace
Třída `Viewer` je vstupním bodem pro vykreslování dokumentů a archivů. Po nastavení Maven přidejte viewer do svého kódu:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Jak vykreslit archivy do jednostránkového HTML
Třída `HtmlViewOptions` definuje nastavení pro HTML výstup, například vkládání zdrojů. Načtěte archiv, nakonfigurujte HTML možnosti pro vložení zdrojů a vykreslete vše do jedné samostatné stránky. Výsledkem je jediný HTML soubor, který obsahuje všechny soubory, obrázky, CSS a fonty, připravený pro offline použití nebo e‑mailovou přílohu.

**Přímá odpověď:** Vytvořte instanci `Viewer` pro ZIP soubor, zavolejte `HtmlViewOptions.forEmbeddedResources()` a spusťte `viewer.view(documentPath, options)`. Tím získáte jediný HTML soubor, který obsahuje všechny soubory, obrázky, CSS a fonty, připravený pro offline použití nebo e‑mailovou přílohu.

### Krok 1: Definujte výstupní adresář
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Nastavte název souboru pro jednostránkový výstup
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Krok 3: Inicializujte prohlížeč
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Krok 4: Nastavte možnosti vykreslování (vkládání zdrojů do HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Vykreslete jako jednostránkový výstup
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Jak vykreslit archivy do více‑stránkového HTML a nastavit položky na stránku
Třída `HtmlViewOptions` také podporuje stránkování. Voláním `options.setItemsPerPage(N)` řeknete vieweru, aby archiv rozdělil do několika HTML souborů, přičemž každý zobrazí až **N** položek. Tento přístup zvyšuje rychlost navigace u velkých archivů a zároveň udržuje každou stránku lehkou.

**Přímá odpověď:** Použijte `HtmlViewOptions.forEmbeddedResources()`, zavolejte `options.setItemsPerPage(N)` a vykreslete archiv. Viewer vygeneruje samostatné HTML soubory – jeden na stránku – každý obsahující až **N** položek, což urychluje navigaci u velkých archivů.

### Krok 1: Znovu použijte výstupní adresář
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Definujte formát názvu souboru pro více stránek
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Krok 3: Znovu inicializujte prohlížeč
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Krok 4: Nastavte možnosti více stránek (vkládání zdrojů do HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Nastavte položky na stránku (hlavní klíčové slovo v akci)
`options.setItemsPerPage(20); // how to convert zip archives with 20 entries per page`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktické aplikace

- **Systémy pro správu dokumentů:** Přidejte funkci náhledu archivů bez nutnosti instalovat další prohlížeče.  
- **Webové portály:** Nabídněte uživatelům rychlý způsob prozkoumání zabalených dokumentů bez stahování.  
- **Nástroje pro spolupráci:** Umožněte týmům prohlížet sdílené archivy přímo v prohlížeči.

## Úvahy o výkonu

- **Správa zdrojů:** Udržujte nízkou spotřebu paměti zpracováním archivů ve streamu; prohlížeč zvládne archivy až do 500 MB bez načítání celého souboru do paměti.  
- **Hromadná konverze archivů:** Procházejte seznam souborů archivů a volajte stejnou logiku vykreslování pro maximalizaci propustnosti.  
- **Strategie cachování:** Ukládejte vykreslené HTML do cache, pokud je stejný archiv často přistupován, čímž snížíte opakovaný čas zpracování až o 70 %.

## Často kladené otázky

**Q: What is GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java je server‑side knihovna, která převádí více než 50 formátů dokumentů a archivů – včetně ZIP a RAR – do HTML, PDF nebo obrázkových souborů bez nutnosti externích aplikací.

**Q: How can I obtain a free trial of GroupDocs.Viewer?**  
A: Navštivte [free trial link](https://releases.groupdocs.com/viewer/java/) a stáhněte si zkušební verzi.

**Q: Can I convert other document types besides archives?**  
A: Ano, viewer podporuje PDF, Word, Excel, PowerPoint a dalších 35+ formátů.

**Q: What should I do if rendering is slow?**  
A: Snižte počet položek na stránku, povolte streamování nebo zpracovávejte archivy v menších dávkách pro zrychlení.

**Q: Where can I get help or support?**  
A: Obrátit se můžete prostřednictvím [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Is it possible to embed CSS and images directly in the HTML?**  
A: Rozhodně – použijte `HtmlViewOptions.forEmbeddedResources` podle ukázek.

**Q: How do I batch convert a folder of archives?**  
A: Projděte každý soubor ve smyčce `for` a použijte stejnou konfiguraci `Viewer` a `HtmlViewOptions` pro každou iteraci.

**Q: Where can I discuss issues with other users?**  
A: Navštivte [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) pro komunitní diskuze.

## Zdroje

- **Dokumentace:** Prozkoumejte podrobně funkce v [GroupDocs dokumentaci](https://docs.groupdocs.com/viewer/java/).  
- **API reference:** Prohlédněte si kompletní API na [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Získejte nejnovější binárky na [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and licensing:** Prohlédněte možnosti na [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and community:** Připojte se k diskusím na [support forum](https://forum.groupdocs.com/c/viewer/9).  
- **GroupDocs forum:** Získejte komunitní pomoc na [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

**Poslední aktualizace:** 2026-10-10  
**Testováno s:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs

## Související tutoriály

- [How to convert zip to HTML and render zip folders in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [convert zip to pdf with GroupDocs.Viewer Java - Custom Filenames](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [How to Convert DOCX to HTML Using GroupDocs.Viewer for Java: A Step‑By‑Step Guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}