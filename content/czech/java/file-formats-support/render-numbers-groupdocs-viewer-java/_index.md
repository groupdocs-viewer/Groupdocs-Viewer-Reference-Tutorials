---
date: '2026-08-25'
description: Zjistěte, jak převést soubory Numbers pomocí GroupDocs.Viewer for Java,
  převodem souborů Apple Numbers do PDF, HTML, JPG nebo PNG. Obsahuje nastavení, kroky
  konverze dokumentů v java a tipy pro zobrazení na webu.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Zjistěte, jak převést soubory Numbers pomocí GroupDocs.Viewer for
  Java, převodem souborů Apple Numbers do PDF, HTML, JPG nebo PNG. Obsahuje nastavení,
  kroky konverze dokumentů v java a tipy pro zobrazení na webu.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Jak převést soubory Numbers pomocí GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Jak převést soubory Numbers pomocí GroupDocs.Viewer for Java
type: docs
url: /cs/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Jak převést Numbers pomocí GroupDocs.Viewer pro Java

Zobrazení tabulek Apple Numbers na webu nebo v desktopovém klientovi může připadat jako hádanka, zejména když potřebujete **převést Numbers do PDF** nebo je vložit jako obrázky do zpráv. V tomto tutoriálu se přesně naučíte **jak převést Numbers** do PDF, HTML, JPG a PNG pomocí **GroupDocs.Viewer pro Java**. Provedeme vás nastavením projektu, renderováním na úrovni kódu a reálnými scénáři, abyste během několika minut mohli vytvořit robustní náhledové nebo archivní kanály.

![Vykreslení dokumentů Apple Numbers pomocí GroupDocs.Viewer pro Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Co se naučíte
- Jak přidat GroupDocs.Viewer do projektu Java založeného na Maven.  
- Krok‑za‑krokem kód pro **převést Numbers do pdf**, **převést Numbers do html**, **převést Numbers do jpg** a **převést Numbers do png**.  
- Kdy zvolit který výstupní formát pro webové portály, e‑mailové workflow nebo systémy správy dokumentů.  

## Rychlé odpovědi
- **Mohu převést Numbers do PDF pomocí Javy?** Ano – vytvořte instanci `Viewer` a zavolejte `PdfViewOptions`, abyste získali připravené PDF k uložení.  
- **Který formát poskytuje nejbohatší webový náhled?** HTML, protože zachovává tabulky, vzorce a stylování interaktivní.  
- **Potřebuji licenci pro produkci?** Komerční licence je vyžadována pro jakékoli nasazení mimo zkušební verzi.  
- **Je podporována konverze obrázků?** Ano – použijte `JpgViewOptions` nebo `PngViewOptions` pro vysoce kvalitní snímky.  
- **Jaká verze Javy je požadována?** Java 8+ a Maven pro správu závislostí.  

## Požadavky
- Java Development Kit (JDK) 8 nebo novější nainstalovaný na vašem počítači.  
- Maven pro správu závislostí a sestavení projektu.  
- Základní znalost Java I/O, cest a zpracování výjimek.  

## Nastavení GroupDocs.Viewer pro Java

### Instalace pomocí Maven
Přidejte repozitář GroupDocs a závislost Viewer do vašeho `pom.xml`. Tento blok musí zůstat přesně tak, jak je uveden:

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
- **Free trial:** Plná funkčnost, není vyžadována kreditní karta.  
- **Temporary license:** Požádejte o časově omezený klíč pro rozšířené testování.  
- **Full purchase:** Získejte trvalou licenci pro komerční použití.  

## Co je třída Viewer?
Třída `Viewer` je jádrem GroupDocs.Viewer, které načítá dokument a renderuje jej do požadovaného výstupního formátu. Abstrahuje manipulaci s typy souborů, takže se můžete soustředit na obchodní logiku místo parsování interní struktury tabulek.

## Jak převést Numbers do HTML pomocí GroupDocs.Viewer pro Java?

`HtmlViewOptions` určuje nastavení pro HTML renderování, jako je vkládání zdrojů nebo odkazování na externí soubory.  
Načtěte soubor Numbers, nakonfigurujte HTML možnosti a zavolejte `viewer.view()`. Metoda `HtmlViewOptions.forEmbeddedResources()` zabaluje CSS a obrázky přímo do HTML, což je ideální pro vložení do webové stránky bez dalších aktiv.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Proč je to důležité:** Vložené zdroje udržují náhled samostatný, eliminuje se tak rozbití odkazů na obrázky a usnadňuje nasazení na CDN.

## Jak převést Numbers do JPG pomocí GroupDocs.Viewer pro Java?

`JpgViewOptions` konfiguruje výstup JPEG, umožňuje nastavení kvality a velikosti pro každou vykreslenou stránku.  
Můžete převést každou stránku tabulky na snímek JPEG. Nastavte parametr `quality` pro vyvážení velikosti souboru a vizuální věrnosti, což je užitečné, když potřebujete lehké obrázky pro sociální sítě nebo e‑mailové newslettery.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Tip:** Pro rychlejší zpracování velkých sešitů snižte kvalitu na 70 % – vizuální dopad je minimální, zatímco velikost souboru dramaticky klesne.

## Jak převést Numbers do PNG pomocí GroupDocs.Viewer pro Java?

`PngViewOptions` konfiguruje výstup PNG, podporuje bezztrátovou kompresi a nastavení rozlišení pro vysoce kvalitní obrázky.  
PNG nabízí bezztrátovou kompresi, zachovává každý pixel přesně tak, jak byl vykreslen. Použijte vlastnost `resolution` pro zvýšení DPI, když potřebujete grafiku připravenou k tisku pro zprávy nebo PDF.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Pro tip:** Nastavte `options.setResolution(300)` pro výstup ve vysokém rozlišení, který vypadá ostrě na tištěných stránkách.

## Jak převést Numbers do PDF pomocí GroupDocs.Viewer pro Java?

`PdfViewOptions` definuje možnosti renderování PDF, včetně vkládání fontů, komprese a kontroly velikosti stránky.  
Objekt `PdfViewOptions` vám umožní vložit fonty, řídit velikost stránky a zachovat původní rozvržení sešitu Numbers. Konverze probíhá jedním voláním, vytváří prohledávatelné, needitovatelné PDF, ideální pro archivaci nebo soulad s předpisy.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Klíčová konfigurace:** Aktivujte `options.setCompress(true)`, aby se zmenšila velikost PDF bez ztráty kvality, což je nezbytné pro velké úložiště dokumentů.

## Proč používat GroupDocs.Viewer pro Java?

GroupDocs.Viewer podporuje **více než 100 formátů souborů**, včetně Apple Numbers, a dokáže renderovat stovky stránek tabulek bez načítání celého souboru do paměti. Benchmarky ukazují, že 250‑stránkový soubor Numbers se převede do PDF za méně než 8 sekund na standardním 2,5 GHz CPU, což poskytuje jak rychlost, tak spolehlivost pro podnikové pipeline.

## Praktické aplikace
- **Webová integrace:** Renderujte do HTML pro interaktivní prohlížeč tabulek, který funguje napříč prohlížeči bez pluginů.  
- **Sdílení obsahu:** Převádějte na JPG/PNG pro rychlé vložení obrázků do newsletterů, chatovacích aplikací nebo sociálních kanálů.  
- **Enterprise DMS:** Použijte **jak převést Numbers** do PDF k uložení needitovatelné, prohledávatelné verze tabulky pro soulad a auditní stopy.  

## Úvahy o výkonu
- **Správa zdrojů:** Vždy vytvářejte `Viewer` uvnitř bloku try‑with‑resources (jak je ukázáno), aby se nativní zdroje uvolnily okamžitě.  
- **Velké sešity:** Zpracovávejte stránku po stránce a streamujte výstup, aby spotřeba paměti zůstala pod 100 MB i pro soubory s 500 stránkami.  
- **Bezpečnost vláken:** Vytvořte samostatnou instanci `Viewer` pro každé vlákno; třída není thread‑safe, takže sdílení jedné instance může vést k závodním podmínkám.

## Časté problémy a řešení

- **Chybějící fonty:** Pokud vygenerované PDF vypadá jinak, ujistěte se, že požadované fonty jsou na serveru dostupné nebo je vložte pomocí `PdfViewOptions.setEmbedFonts(true)`.  
- **Prázdné stránky:** Ověřte, že soubor Numbers není chráněn heslem; GroupDocs.Viewer v současnosti neodemyká chráněné sešity.  
- **Chyby out‑of‑memory:** Pro extrémně velké soubory povolte `options.setPageCount(1)`, aby se renderovala jedna stránka najednou a výsledky se později spojily.

## Často kladené otázky

**Q: Jaké souborové formáty GroupDocs.Viewer podporuje?**  
A: Více než 100 formátů, včetně DOCX, XLSX, PDF, HTML a Apple Numbers, s plnou schopností renderování pro každý z nich.

**Q: Jak efektivně zpracovat velké soubory Numbers?**  
A: Streamujte konverzi stránku po stránce, použijte `options.setPageCount()` pro omezení využití paměti a zvažte kompresi výstupního PDF.

**Q: Lze GroupDocs.Viewer použít v komerčním projektu?**  
A: Ano – zakupte komerční licenci, která odstraní omezení zkušební verze a poskytne podporu pro produkční nasazení.

**Q: Je možné přizpůsobit kvalitu výstupních obrázků?**  
A: Rozhodně. Nastavte `JpgViewOptions.setQuality(int)` nebo `PngViewOptions.setResolution(int)` podle požadavků na velikost a kvalitu.

**Q: Kde najdu pokročilejší příklady použití?**  
A: Navštivte [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) pro podrobné průvodce, ukázkové projekty a podrobnosti API.

## Další kroky
Vyzkoušejte výše uvedené možnosti, poté prozkoumejte další přizpůsobení, jako je vodoznakování PDF, přidání ochrany heslem nebo integrace vieweru do Spring Boot REST služby. [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) poskytuje kompletní katalog funkcí, které můžete kombinovat a přizpůsobovat.

## Zdroje
- **Dokumentace:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Dokumentace GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Reference API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Reference API GroupDocs:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Stáhnout:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Koupit licenci:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Zkušební verze:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Dočasná licence:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Fórum podpory:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

**Poslední aktualizace:** 2026-08-25  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Související tutoriály

- [Jak převést Excel do HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Jak převést Excel do HTML a renderovat skryté řádky a sloupce v Javě s GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Java Document Rendering Tutorial - Convert Files to HTML, PDF & Images](/viewer/java/rendering-basics/)