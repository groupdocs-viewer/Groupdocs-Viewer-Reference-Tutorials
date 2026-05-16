---
date: '2026-02-18'
description: Naučte se, jak převádět soubory WMZ a WMF do formátů PDF, HTML, JPG a
  PNG pomocí GroupDocs Viewer pro Javu. Tento průvodce pokrývá GroupDocs Viewer Java
  a konverzi vektorové grafiky v Javě.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Jak převést WMZ na PDF a další formáty pomocí GroupDocs Viewer pro Javu
type: docs
url: /cs/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 2026-02-18  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

Make sure formatting.

Now produce final content with all translations, preserving placeholders and code blocks.

Let's assemble.# Jak převést WMZ na PDF a další formáty pomocí GroupDocs Viewer pro Java

Převod souborů WMZ (Web Metafile) a WMF (Windows Metafile) do přístupnějších formátů—zejména **convert WMZ to PDF**—může být obtížný, protože tyto vektorové grafické formáty ukládají instrukce pro kreslení místo pixelových dat. S **GroupDocs Viewer for Java** můžete renderovat dokumenty WMZ/WMF do HTML, JPG, PNG, **PDF** a dalších populárních formátů během několika řádků kódu.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

V tomto tutoriálu se naučíte, jak nastavit knihovnu, renderovat soubory WMZ/WMF do požadovaného výstupu a řešit běžné úskalí. Na konci budete schopni integrovat **groupdocs viewer java** do svých Java aplikací a **java convert vector graphics** rychle a spolehlivě.

## Rychlé odpovědi
- **Do jakých formátů lze WMZ/WMF převést?** HTML, JPG, PNG a PDF jsou plně podporovány.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; komerční licence odstraňuje omezení hodnocení.  
- **Jaká verze Javy je vyžadována?** Doporučuje se Java 8 nebo novější.  
- **Mohu renderovat jen konkrétní stránky?** Ano, můžete specifikovat rozsahy stránek ve view options.  
- **Je spotřeba paměti problémem u velkých souborů?** Používejte try‑with‑resources a renderujte jen potřebné stránky, aby byla paměť nízká.

## Co je “convert WMZ to PDF”?
Převod WMZ na PDF znamená převzít vektorový soubor WMZ a rasterizovat jej (nebo zachovat jeho vektorová data) uvnitř PDF kontejneru. PDF je univerzálně zobrazitelné, prohledávatelné a tisknutelné, což ho činí ideálním pro archivaci a sdílení WMZ grafiky.

## Proč použít GroupDocs Viewer pro Java k převodu vektorové grafiky?
- **Vysoká věrnost**: Knihovna zachovává původní kvalitu kresby, ať už výstupem je PDF nebo PNG.  
- **Žádné externí závislosti**: Není potřeba nativních Windows knihoven; vše běží na jakékoli platformě s JDK.  
- **Jednoduché API**: Jedna instance `Viewer` a jediný volání `view` zvládne celý převod.  
- **Škálovatelné**: Funguje stejně dobře pro jednostránkové ikony i vícestránkové technické výkresy.

## Prerequisites

### Požadované knihovny
- **GroupDocs.Viewer for Java** – jádro renderovacího enginu.  
- Java Development Kit (JDK) 8+.

### Nastavení prostředí
- IDE jako IntelliJ IDEA nebo Eclipse.  
- Maven pro správu závislostí (nebo Gradle, pokud dáváte přednost).

### Předpoklady znalostí
- Znalost Java file I/O (`java.nio.file.Path`).  
- Základní pochopení, jak dokumentové prohlížeče renderují obsah.

## Nastavení GroupDocs.Viewer pro Java

Přidejte repozitář a závislost do svého `pom.xml`:

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

> **Tip k licenci:** Použijte bezplatnou zkušební verzi pro hodnocení, poté aplikujte dočasnou nebo zakoupenou licenci pro odemknutí plné funkčnosti.

Jakmile je závislost vyřešena, můžete vytvořit instanci `Viewer`, která bude znovu použita pro každý krok převodu.

## Průvodce implementací

Provedeme čtyři scénáře převodu: HTML, JPG, PNG a PDF. Každý příklad následuje stejný vzor—definujte výstupní cestu, vytvořte `Viewer` se zdrojovým WMZ souborem, nakonfigurujte příslušné view options a zavolejte `view`.

### Renderování WMZ/WMF do HTML

#### Přehled
HTML výstup vám umožní vložit grafiku přímo do webových stránek, přičemž všechny zdroje (obrázky, CSS) jsou obsaženy v jediném souboru.

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
PDF poskytuje platformově nezávislý, prohledávatelný dokument, který zachovává původní rozvržení.

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

| Problém | Příčina | Řešení |
|-------|-------|----------|
| **OutOfMemoryError** při velkých WMZ souborech | Viewer načítá celý dokument do paměti | Renderujte jednu stránku najednou pomocí `PageStreamViewOptions` nebo zvětšete heap JVM (`-Xmx`). |
| **Chybějící fonty** v PDF | Font není vložen ve zdrojovém WMZ | Nainstalujte požadované fonty na hostitelském stroji nebo použijte `FontSettings` k poskytnutí vlastních fontů. |
| **Prázdný PNG výstup** | Nesprávná výstupní cesta nebo nedostatečná oprávnění k zápisu | Ověřte, že `outputDirectory` existuje a aplikace má právo zápisu. |
| **HTML zdroje se nenačítají** | Použití `forExternalResources` bez kopírování souborů | Použijte `forEmbeddedResources` pro samostatný HTML soubor. |

## Často kladené otázky

**Q: Mohu převést WMF na PNG pomocí stejného kódu?**  
A: Ano. PNG příklad funguje pro soubory WMZ i WMF; stačí nahradit `TestFiles.SAMPLE_WMZ` vaším WMF zdrojem.

**Q: Je možné převést jen podmnožinu stránek?**  
A: Rozhodně. Použijte `PdfViewOptions` (nebo odpovídající možnosti pro jiné formáty) a před renderováním zavolejte `setPageNumbers(List<Integer>)`.

**Q: Potřebuji samostatnou licenci pro každý výstupní formát?**  
A: Ne. Jedna licence GroupDocs Viewer pokrývá všechny podporované formáty, včetně HTML, JPG, PNG a PDF.

**Q: Jak „java convert vector graphics“ ovlivňuje výkon?**  
A: Převod vektor‑na‑raster je náročný na CPU. Pro velké dávky zvažte vícevláknové zpracování a opětovné použití jedné instance `Viewer` napříč soubory.

**Q: Zachová PDF vektorovou kvalitu, nebo je rasterizováno?**  
A: Při převodu WMZ/WMF na PDF GroupDocs Viewer zachovává vektorové instrukce, kde je to možné, což vede ke škálovatelnému PDF.

## Závěr

Nyní máte kompletní, připravený průvodce pro **convert WMZ to PDF** a další běžné formáty pomocí **GroupDocs Viewer for Java**. Ať už vytváříte webovou službu, která poskytuje grafiku za běhu, nebo archivní nástroj, který ukládá dokumenty jako PDF, výše uvedené kroky vám pomohou dosáhnout cíle rychle.

---

**Poslední aktualizace:** 2026-02-18  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs