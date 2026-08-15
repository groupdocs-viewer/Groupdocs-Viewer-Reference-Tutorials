---
date: '2026-07-19'
description: Zjistěte, jak převést PST na HTML a další formáty, jako jsou JPG, PNG
  a PDF pomocí GroupDocs.Viewer for Java. Tento průvodce pokrývá všechny potřebné
  kroky a konfigurace.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Rychle převádějte PST na HTML pomocí GroupDocs.Viewer for Java. Naučte
  se krok za krokem, jak také exportovat do JPG, PNG a PDF v průvodci připraveném
  pro produkční nasazení.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Převod PST na HTML s GroupDocs.Viewer for Java – Rychlý export e‑mailů
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
title: Převod PST na HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer for Java
type: docs
url: /cs/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Převod PST do HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer pro Java

Hledáte **convert pst to html** nebo jiné formáty jako JPG, PNG nebo PDF? S výkonnou knihovnou GroupDocs.Viewer pro Java je tento úkol jednoduchý a efektivní. V tomto tutoriálu se naučíte, jak vykreslit soubory Outlook PST/OST do webově přátelského HTML, obrazových souborů nebo jediného PDF, což usnadní sdílení a archivaci vašich e‑mailových archivů.

![Převod PST/OST do HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer pro Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Co se naučíte**
- Jak nastavit GroupDocs.Viewer pro Java v Maven projektu.  
- Krok‑za‑krokem instrukce k **java convert pst** souborům do HTML, JPG, PNG a PDF.  
- Tipy na konfiguraci pro optimální výkon a běžné úskalí.

## Rychlé odpovědi
- **Jaká knihovna zpracovává převod PST?** GroupDocs.Viewer for Java.  
- **Mohu převést PST přímo do PDF?** Ano, pomocí `PdfViewOptions`.  
- **Je licence vyžadována pro produkci?** Je potřeba platná licence GroupDocs.  
- **Která verze Javy je podporována?** JDK 8 nebo vyšší.  
- **Musím ručně extrahovat přílohy?** Ne, prohlížeč je vykreslí automaticky.

## Co je GroupDocs.Viewer pro Java?
GroupDocs.Viewer pro Java je server‑side API, které načítá více než 100 formátů dokumentů a e‑mailů a vykresluje je do výstupu HTML, obrázku nebo PDF bez externího softwaru. Zpracovává soubory PST až do 2 GB při zachování využití paměti pod 200 MB.

## Jak převést pst do html pomocí GroupDocs.Viewer pro Java?
Načtěte soubor PST pomocí `new Viewer("source.pst")`, nakonfigurujte `HtmlViewOptions`, aby ukazovaly na výstupní složku, a zavolejte `viewer.view(htmlOptions)`. API extrahuje každý e‑mail, zachovává formátování, přílohy a metadata a zapíše samostatnou HTML stránku pro každou zprávu – vše v jediném volání metody.

### Proč zvolit GroupDocs.Viewer?
- **Vysoká věrnost vykreslování** – 99,9 % obsahu e‑mailu (včetně bohatých textových těles, tabulek a vložených obrázků) je reprodukováno přesně.  
- **Více výstupních formátů** – Jedno volání API může vygenerovat HTML, JPG, PNG nebo PDF, pokrývající více než 50 exportních možností.  
- **Žádné externí závislosti** – Není potřeba Outlook, Exchange Server ani třetí strany konvertory; vše běží uvnitř vašeho Java runtime.

## Požadavky

- **GroupDocs.Viewer pro Java** – verze 25.2 nebo novější.  
- **Java Development Kit (JDK)** – 8 nebo novější.  
- Maven pro správu závislostí.  
- Základní znalost Javy a obeznámení s Mavenem.

## Nastavení GroupDocs.Viewer pro Java

`Viewer` je hlavní třída v GroupDocs.Viewer pro Java, která načítá dokument a vykresluje jej do zvoleného formátu. Přidejte repozitář GroupDocs a závislost do vašeho `pom.xml`:

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

### Získání licence
- **Bezplatná zkušební verze** – prozkoumejte všechny funkce bez poplatku.  
- **Dočasná licence** – prodlužte dobu hodnocení podle potřeby.  
- **Plná licence** – vyžadována pro nasazení do produkce.

### Základní inicializace
`Viewer` instance jsou lehké; můžete znovu použít jedinou instanci pro mnoho souborů, abyste minimalizovali režii vytváření objektů.

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

## Průvodce implementací

Následující sekce vás provedou vykreslováním souborů PST/OST do každého podporovaného formátu.

### Vykreslování dokumentů PST/OST do HTML

#### Krok 1: Nastavte výstupní adresář
Definujte složku, kam budou zapisovány HTML stránky. GroupDocs vytvoří podadresář pro každý e‑mail, aby udržel prostředky uspořádané.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Krok 2: Nakonfigurujte Load Options
`LoadOptions` vám umožňuje nastavit zpracování hesla, časové limity načítání zdrojů a selektivní vykreslování stránek. Nastavení časového limitu na 30 sekund funguje dobře pro většinu serverových prostředí.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Krok 3: Definujte HTML View Options
`HtmlViewOptions` určuje výstupní složku, zpracování zdrojů a volitelné nastavení CSS pro konverzi do HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Krok 4: Inicializujte Viewer a vykreslete HTML
Vytvořte objekt `Viewer`, předáte cestu k souboru PST a zavoláte `view` s `HtmlViewOptions`. API automaticky prochází všechny zprávy v PST a generuje přehlednou HTML hierarchii.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Vykreslování dokumentů PST/OST do JPG

#### Krok 1: Nastavte výstupní adresář
Vytvořte vyhrazenou složku pro JPG snímky; každý e‑mail se stane jedním nebo více obrazovými soubory v závislosti na jeho délce.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Krok 2: Nakonfigurujte Load Options
Stejné `LoadOptions`, které byly použity pro HTML, lze zde znovu použít, což zajišťuje konzistentní zpracování hesla napříč formáty.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Krok 3: Definujte JPG View Options
`JpgViewOptions` řídí rozlišení obrazu, kvalitu a výstupní složku pro konverzi JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Krok 4: Inicializujte Viewer a vykreslete JPG
Použijte `viewer.view(jpgOptions)` k vygenerování vysoce kvalitních JPEG souborů připravených pro webový náhled.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Vykreslování dokumentů PST/OST do PNG

#### Krok 1: Nastavte výstupní adresář
Výstup PNG je užitečný, když potřebujete bezztrátovou kvalitu pro archivaci nebo OCR zpracování.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Krok 2: Nakonfigurujte Load Options
Nejsou vyžadována žádná další nastavení kromě konfigurace hesla a časového limitu.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Krok 3: Definujte PNG View Options
`PngViewOptions` vám umožňuje nastavit průhledné pozadí a výstupní složku pro bezztrátové PNG obrázky.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Krok 4: Inicializujte Viewer a vykreslete PNG
Instanci `viewer.view(pngOptions)` použijte k vytvoření PNG snímků každého e‑mailu.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Vykreslování dokumentů PST/OST do PDF

#### Krok 1: Nastavte výstupní adresář
Jeden PDF soubor na PST zjednodušuje workflow právního přezkoumání a snižuje úložnou zátěž.

CODE_BLOCK_PLACEHOLDER_14_END

#### Krok 2: Nakonfigurujte Load Options
Při konverzi do PDF můžete chtít povolit `setEmbedFonts(true)`, aby byla zajištěna vizuální věrnost na jakémkoli zařízení.

CODE_BLOCK_PLACEHOLDER_15_END

#### Krok 3: Definujte PDF View Options
`PdfViewOptions` vám umožňuje zvolit úroveň komprese, vložit fonty a nastavit název výstupního souboru pro konverzi do PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Krok 4: Inicializujte Viewer a vykreslete PDF
Vytvořte `PdfViewOptions`, volitelně zvolte úroveň komprese a zavolejte `viewer.view(pdfOptions)`. API sloučí všechny e‑maily do jednoho prohledávatelného PDF dokumentu.

CODE_BLOCK_PLACEHOLDER_17_END

## Praktické aplikace
- **Archivace e‑mailů:** Převést velké PST archivy na prohledávatelné HTML nebo PDF pro soulad s předpisy.  
- **Systémy správy dokumentů:** Ukládat konvertované soubory v systémech, které přijímají jen PDF, PNG nebo JPG.  
- **Platformy pro spolupráci:** Sdílet konvertované e‑maily jako obrázky ve Slacku nebo Teams.  
- **Právní přezkum:** Poskytnout soudům PDF verze e‑mailových důkazů.  
- **Zálohovací strategie:** Uchovávat lehké PNG nebo JPG snímky kritických zpráv.

## Úvahy o výkonu
- **Správa zdrojů:** Znovu použijte instance `Viewer` při zpracování více souborů, aby se snížil režijní náklad.  
- **Ladění paměti:** Upravit `loadOptions.setResourceLoadingTimeout` podle kapacity serveru.  
- **Asynchronní zpracování:** Přesunout konverzi do background vláken pro responzivní UI.

## Často kladené otázky

**Q: Jak mohu **convert pst to pdf** pomocí stejné základny kódu?**  
A: Použijte `PdfViewOptions` jak je ukázáno v sekci renderování PDF; zbytek kódu zůstane stejný.

**Q: Dokáže GroupDocs.Viewer zpracovat šifrované PST soubory?**  
A: Ano, před vykreslením poskytněte heslo pomocí `LoadOptions.setPassword("yourPassword")`.

**Q: Jaký je rozdíl mezi **java convert pst** na PNG a JPG?**  
A: PNG zachovává bezztrátovou kvalitu, ideální pro snímky obrazovky, zatímco JPG nabízí menší velikosti souborů pro náhledy e‑mailů.

**Q: Existuje způsob, jak **how to convert pst** soubory hromadně?**  
A: Zabalte logiku renderování do smyčky, která prochází adresář PST souborů; pro každý soubor znovu použijte stejnou konfiguraci `Viewer`.

**Q: Podporuje API konverzi PST souborů větších než 1 GB?**  
A: Ano, GroupDocs.Viewer streamuje data a může zpracovat soubory až do 2 GB bez načítání celého archivu do paměti.

## Závěr

Nyní máte kompletní, připravený průvodce pro **convert pst to html**, JPG, PNG a PDF pomocí GroupDocs.Viewer pro Java. Dodržením výše uvedených kroků můžete integrovat konverzi e‑mailů do jakéhokoli Java‑založeného workflow, zlepšit přístupnost a splnit požadavky na soulad.

---

**Poslední aktualizace:** 2026-07-19  
**Testováno s:** GroupDocs.Viewer for Java 25.2  
**Autor:** GroupDocs

## Související tutoriály

- [Převod NSF do PDF, HTML, JPG, PNG pomocí GroupDocs.Viewer pro Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Převod ODF do HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer pro Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Jak převést DOCX do HTML pomocí GroupDocs.Viewer pro Java: Průvodce krok za krokem](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)