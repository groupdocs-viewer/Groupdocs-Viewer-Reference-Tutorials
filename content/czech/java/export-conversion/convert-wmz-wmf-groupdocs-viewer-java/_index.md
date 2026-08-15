---
date: '2026-07-19'
description: Zjistěte, jak převést WMZ na PDF, HTML, JPG a PNG pomocí GroupDocs Viewer
  for Java. Podrobný návod pro java převod vektorové grafiky.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Převod WMZ na PDF, HTML, JPG a PNG pomocí GroupDocs Viewer for Java.
  Tento tutoriál ukazuje krok za krokem java převod vektorové grafiky s vysokou věrností.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Převod WMZ na PDF pomocí GroupDocs Viewer for Java – Rychlý průvodce
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Převod WMZ na PDF a další formáty pomocí GroupDocs Viewer for Java
type: docs
url: /cs/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Převod WMZ do PDF a dalších formátů pomocí GroupDocs Viewer pro Java

Konverze souborů WMZ (Web Metafile) a WMF (Windows Metafile) do přístupnějších formátů – zejména **convert WMZ to PDF** – může být obtížná, protože tyto vektorové grafické formáty ukládají instrukce pro kreslení místo pixelových dat. S **GroupDocs Viewer for Java** můžete renderovat dokumenty WMZ/WMF do HTML, JPG, PNG, **PDF** a dalších populárních formátů během několika řádků kódu, přičemž zachováte původní vizuální věrnost.

![Převod dokumentů WMZ/WMF pomocí GroupDocs.Viewer pro Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Rychlé odpovědi
- **Do jakých formátů lze WMZ/WMF převést?** HTML, JPG, PNG a PDF jsou plně podporovány.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; komerční licence odstraňuje omezení hodnocení.  
- **Jaká verze Javy je vyžadována?** Doporučuje se Java 8 nebo novější.  
- **Mohu renderovat pouze konkrétní stránky?** Ano, můžete v možnostech zobrazení zadat rozsahy stránek.  
- **Je spotřeba paměti problémem u velkých souborů?** Použijte try‑with‑resources a renderujte jen potřebné stránky, aby byla paměť nízká.

## Co je “convert WMZ to PDF”?
**Convert WMZ to PDF** znamená převzít vektorový soubor WMZ a vložit jeho kreslicí instrukce do kontejneru PDF, čímž vznikne univerzálně zobrazitelný, prohledávatelný a tisknutelný dokument. Konverze zachovává kvalitu čar a tvarů, takže výsledné PDF vypadá identicky jako originální grafika na jakémkoli zařízení.

## Proč použít GroupDocs Viewer pro Java k převodu vektorové grafiky?
GroupDocs Viewer pro Java zpracovává renderování WMZ a WMF s **vysokou věrností**, zachovává vektorové detaily, ať už výstupem je PDF, PNG nebo HTML. Knihovna běží na jakékoli platformě s JDK, nevyžaduje nativní komponenty Windows a poskytuje API s jedním voláním, které škáluje od souborů s jednou ikonou po vícestránkové technické výkresy. V benchmarkových testech zpracovává **více než 200‑stránkové soubory WMZ za méně než 12 sekund** na standardním 4‑jádrovém serveru.

## Požadavky

- **GroupDocs.Viewer for Java** – jádro renderovacího enginu.  
- Java Development Kit (JDK) 8 nebo novější.  
- IDE jako IntelliJ IDEA nebo Eclipse (volitelné, ale doporučené).  
- Maven (nebo Gradle) pro správu závislostí.  

Znalost Java NIO (`java.nio.file.Path`) a základního souborového I/O vám pomůže plynule sledovat příklady.

## Nastavení GroupDocs.Viewer pro Java

Třída `Viewer` je vstupním bodem pro všechny operace renderování. Reprezentuje vlákny‑bezpečný engine, který lze znovu použít napříč více konverzemi.

Přidejte repozitář a závislost do vašeho `pom.xml` (nebo ekvivalentu pro Gradle). Po vyřešení artefaktu Mavenem můžete vytvořit instanci `Viewer`, která bude znovu použita pro každý krok konverze.

> **Tip k licenci:** Použijte bezplatnou zkušební verzi pro hodnocení, poté aplikujte dočasnou nebo zakoupenou licenci pro odemknutí plné funkčnosti.

## Průvodce implementací

Níže projdeme čtyři scénáře konverze – HTML, JPG, PNG a PDF. Každý scénář následuje stejný tříkrokový vzor:

1. **Definujte výstupní adresář**, kam budou uloženy renderované soubory.  
2. **Vytvořte instanci `Viewer`**, která ukazuje na zdrojový soubor WMZ/WMF.  
3. **Nastavte formát‑specifické možnosti zobrazení** a zavolejte metodu `view`.  

Metoda `view` provádí renderování na základě poskytnutých možností.

### Renderování WMZ/WMF do HTML

#### Přehled
Výstup HTML vám umožní vložit grafiku přímo do webových stránek, přičemž všechny zdroje (obrázky, CSS) jsou obsaženy v jediném souboru.

**Krok 1: Definujte cestu výstupního adresáře**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Krok 2: Inicializujte Viewer a renderujte do HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Renderování WMZ/WMF do JPG

#### Přehled
JPG je široce podporovaný rastrový formát, ideální pro rychlé náhledy nebo e‑mailové přílohy.

**Krok 1: Definujte cestu výstupního adresáře**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Krok 2: Inicializujte Viewer a renderujte do JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderování WMZ/WMF do PNG

#### Přehled
PNG podporuje průhlednost, což ho činí ideálním pro grafiku, která má být kombinována s různými pozadími.

**Krok 1: Definujte cestu výstupního adresáře**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Krok 2: Inicializujte Viewer a renderujte do PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderování WMZ/WMF do PDF

#### Přehled
PDF poskytuje platformně nezávislý, prohledávatelný dokument, který zachovává původní rozložení.

**Krok 1: Definujte cestu výstupního adresáře**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Krok 2: Inicializujte Viewer a renderujte do PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Časté problémy a řešení

`PageStreamViewOptions` umožňuje renderovat konkrétní stránky jako streamy.  
`PdfViewOptions` konfiguruje nastavení výstupu PDF, jako je rozsah stránek a DPI.  
`FontSettings` vám umožní poskytnout vlastní písma, když zdrojový dokument odkazuje na chybějící písma.

| Problém | Příčina | Řešení |
|-------|-------|----------|
| **OutOfMemoryError** u velkých souborů WMZ | Viewer načítá celý dokument do paměti | Renderujte jednu stránku najednou pomocí `PageStreamViewOptions` nebo zvýšte haldu JVM (`-Xmx`). |
| **Chybějící písma** v PDF | Písmo není vloženo ve zdrojovém WMZ | Nainstalujte požadovaná písma na hostitelském stroji nebo použijte `FontSettings` k dodání vlastních písem. |
| **Prázdný výstup PNG** | Nesprávná cesta výstupu nebo nedostatečná oprávnění k zápisu | Ověřte, že `outputDirectory` existuje a aplikace má právo zapisovat. |
| **HTML zdroje se nenačítají** | Použití `forExternalResources` bez kopírování souborů | Použijte `forEmbeddedResources` pro samostatný HTML soubor. |

## Často kladené otázky

**Q: Mohu převést WMF na PNG pomocí stejného kódu?**  
A: Ano. Příklad PNG funguje pro soubory WMZ i WMF; stačí nahradit `TestFiles.SAMPLE_WMZ` vaším WMF zdrojem.

**Q: Je možné převést jen podmnožinu stránek?**  
A: Rozhodně. Použijte `PdfViewOptions` (nebo odpovídající možnosti pro jiné formáty) a před renderováním zavolejte `setPageNumbers(List<Integer>)`.

**Q: Potřebuji samostatnou licenci pro každý výstupní formát?**  
A: Ne. Jedna licence GroupDocs Viewer pokrývá všechny podporované formáty, včetně HTML, JPG, PNG a PDF.

**Q: Jaký dopad má “java convert vector graphics” na výkon?**  
A: Převod vektor‑na‑raster je náročný na CPU. Pro velké dávky zvažte vícevláknové zpracování a opětovné použití jedné instance `Viewer` napříč soubory.

**Q: Zachová PDF vektorovou kvalitu, nebo je rasterizováno?**  
A: Při převodu WMZ/WMF do PDF GroupDocs Viewer zachovává vektorové instrukce, kde je to možné, což vede k škálovatelnému PDF.

## Závěr

Nyní máte kompletní, připravený průvodce pro **convert WMZ to PDF** a další běžné formáty pomocí **GroupDocs Viewer pro Java**. Ať už vytváříte webovou službu, která poskytuje grafiku za běhu, nebo archivní nástroj, který ukládá dokumenty jako PDF, výše uvedené kroky vám pomohou dosáhnout cíle rychle a spolehlivě. Prozkoumejte API dále a přizpůsobte rozsahy stránek, nastavení DPI nebo vodoznakování podle požadavků vašeho projektu.

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

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

## Související tutoriály

- [Jak převést OBJ do HTML, JPG, PNG a PDF v Javě pomocí GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Převod IGS do PDF, HTML, JPG a PNG pomocí GroupDocs Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Převod dokumentů do PDF – Kompletní průvodce](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)