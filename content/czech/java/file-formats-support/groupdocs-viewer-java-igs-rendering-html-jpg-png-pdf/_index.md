---
date: '2026-08-08'
description: Zjistěte, jak převést IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer
  pro Java. Praktický návod krok za krokem, požadavky a řešení problémů pro vývojáře
  Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Převod IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer pro Java.
  Podrobná konfigurace, ukázky kódu a řešení problémů pro vývojáře Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Převod IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Převod IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer Java
type: docs
url: /cs/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Převod IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer Java

Pokud potřebujete **převést IGS na PDF** (nebo na HTML, JPG, PNG) přímo z Java aplikace, jste na správném místě. V tomto tutoriálu projdeme vše, co potřebujete – od instalace knihovny po vykreslení 3‑D modelu ve formátu, který vyhovuje vašemu projektu. Pochopíte, proč je GroupDocs.Viewer solidní volbou pro rychlé a spolehlivé konverze, a získáte připravené úryvky kódu, které můžete vložit do svého řešení.

![Převod souborů IGS na HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer pro Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Rychlé odpovědi
- **Mohu převést IGS na PDF pomocí Javy?** Ano, použijte `PdfViewOptions` spolu s API `Viewer`.  
- **Jaké výstupní formáty jsou podporovány?** HTML, JPG, PNG a PDF jsou všechny nativně podporovány.  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; bezplatná zkušební verze vám umožní otestovat základní funkce.  
- **Jaká verze Javy je vyžadována?** JDK 8 nebo vyšší; knihovna také běží na Java 11, 17 a novějších.  
- **Je Maven jediný způsob, jak přidat knihovnu?** Ne, můžete také použít Gradle nebo ručně přidat JAR soubory do classpath.

## Co je převod IGS na PDF?
Převod IGS na PDF znamená převést neutrální 3‑D CAD soubor na statický, univerzálně zobrazitelný dokument. To vám umožní sdílet vizuály návrhů se zainteresovanými stranami, které nemají CAD nástroje, vložit vykreslení do zpráv nebo archivovat model pro účely shody.

## Proč použít GroupDocs.Viewer pro konverze IGS?
GroupDocs.Viewer zpracovává soubory IGS bez potřeby externího CAD softwaru. Podporuje **více než 50 vstupních a výstupních formátů**, dokáže vykreslit sestavy obsahující **stovky součástí**, přičemž spotřeba paměti zůstává pod **200 MB**, a poskytuje výsledky za méně než **2 sekundy** pro typické modely na standardním serveru. Tyto kvantifikované výhody z něj činí vysoce výkonnou a nákladově efektivní volbu pro podnikové pipeline.

## Předpoklady
- **GroupDocs.Viewer pro Java** ≥ 25.2 (nejnovější stabilní verze).  
- **JDK 8+** nainstalováno a nakonfigurováno ve vašem IDE (IntelliJ IDEA, Eclipse, NetBeans atd.).  
- Základní znalost Maven (volitelné, ale doporučené pro správu závislostí).  

## Nastavení GroupDocs.Viewer pro Java

### Maven závislost
Přidejte repozitář GroupDocs a závislost Viewer do vašeho `pom.xml`:

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
GroupDocs.Viewer nabízí tři licenční možnosti:
- **Free trial** – omezené použití, ideální pro rychlé testy proof‑of‑concept.  
- **Temporary license** – plná sada funkcí na krátkou evaluační dobu, ideální pro pilotní projekty.  
- **Commercial license** – neomezené použití v produkci, zahrnuje prioritní podporu a aktualizace.

### Základní inicializace vieweru
Třída `Viewer` je vstupním bodem pro všechny operace vykreslování. Načte zdrojový soubor, parsuje formát a poskytuje metody pro vytvoření požadovaného výstupu.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Vykreslení IGS do HTML

### Jak převést IGS na HTML?
Načtěte soubor IGS pomocí instance `Viewer` a předávejte objekt `HtmlViewOptions`, který vkládá všechny potřebné zdroje. Volání vrátí jeden HTML soubor, který obsahuje kompletní 3‑D pohled, což usnadňuje vložení do webových stránek. Můžete také přizpůsobit vykreslení nastavením možností, jako je velikost stránky, barva pozadí a zda zahrnout interaktivní ovládací prvky.  
`HtmlViewOptions` konfiguruje, jak je generován HTML výstup, včetně vkládání zdrojů a rozvržení stránky.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Vykreslení IGS do JPG

### Jak převést IGS na JPG?
Vytvořte objekt `JpgViewOptions`, nastavte požadované rozlišení a kvalitu komprese a nechte `Viewer` generovat rastrové obrázky pro každou stránku modelu. Vygenerované JPG soubory lze uložit do určeného adresáře a můžete upravit parametr kvality, aby byl vyvážený poměr velikosti souboru a vizuální věrnosti, což je užitečné pro náhledy nebo vysoce rozlišené tisky.  
`JpgViewOptions` určuje nastavení pro generování JPG obrázků, jako je rozlišení, kvalita a výstupní adresář.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Vykreslení IGS do PNG

### Jak převést IGS na PNG?
Třída `PngViewOptions` vám umožňuje vytvářet bezztrátové obrázky s volitelnou průhledností. Tento formát je ideální pro překrytí modelu na barevných pozadích v marketingových materiálech. Můžete také definovat rozlišení a barvu pozadí tak, aby odpovídaly vašim brandovým směrnicím, což zajišťuje konzistentní vzhled napříč všemi generovanými aktivy.  
`PngViewOptions` definuje parametry pro PNG vykreslování, včetně rozlišení, průhlednosti a barvy pozadí.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Vykreslení IGS do PDF

### Jak převést IGS na PDF?
Použijte `PdfViewOptions` k vytvoření stránkovaného PDF, které zachovává vizuální rozvržení 3‑D modelu. Můžete také vložit písma a řídit velikost stránky tak, aby vyhovovala firemním brandovým směrnicím. Další nastavení umožňuje specifikovat kvalitu obrázku, úroveň komprese a zda zahrnout obsah pro vícestránkové sestavy.  
`PdfViewOptions` řídí tvorbu PDF, umožňuje nastavení velikosti stránky, kvality obrázku a vložení písem.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Praktické aplikace
- **Webové portály** – vložte modely vykreslené do HTML přímo do konfigurátorů produktů, což zákazníkům umožní otáčet a přibližovat bez instalace pluginů.  
- **Marketingové materiály** – generujte vysoce rozlišené JPG/PNG obrázky pro brožury, prezentace a příspěvky na sociálních sítích.  
- **Technická dokumentace** – zahrňte PDF vykreslení CAD modelů do uživatelských příruček, aby inženýři mohli prohlížet návrhy offline.  
- **Zajištění kvality** – automatizujte tvorbu náhledů pro tisíce IGS souborů, čímž urychlíte workflow vizuální inspekce.

## Časté problémy a řešení

| Issue | Solution |
|-------|----------|
| **Výstupní složka nebyla nalezena** | Ověřte cestu předanou do `Path outputDirectory` a zajistěte, aby Java proces měl práva zápisu do cílového adresáře. |
| **Prázdné stránky v PDF** | Potvrďte, že zdrojový IGS soubor není poškozený; nejprve jej otevřete v nativním CAD prohlížeči. |
| **Pomalé vykreslování velkých sestav** | Zvyšte velikost haldy JVM (`-Xmx2g` nebo více) a zvažte vykreslování stránku po stránce pomocí `viewer.getPageCount()`, abyste zpracovávali části. |
| **Chybějící písma v PDF** | Použijte `PdfViewOptions` k vložení požadovaných písem nebo nainstalujte chybějící písma na server, který hostuje konverzní službu. |

## Často kladené otázky

**Q: Mohu převést více IGS souborů v jednom běhu?**  
A: Ano. Procházejte kolekci cest k souborům a zavolejte odpovídající metodu `view` pro každý soubor ve stejné instanci `Viewer`.

**Q: Je možné přizpůsobit velikost stránky PDF?**  
A: Rozhodně. `PdfViewOptions` nabízí `setPageSize(PageSize.A4)`, `PageSize.Letter` a vlastní rozměry pomocí `setCustomSize(width, height)`.

**Q: Potřebuji samostatnou licenci pro každý výstupní formát?**  
A: Ne. Jedna licence GroupDocs.Viewer pokrývá všechny podporované formáty, včetně HTML, JPG, PNG a PDF.

**Q: Jak velký může být IGS soubor, než se výkon zhorší?**  
A: Knihovna spolehlivě zpracovává soubory až do **500 MB**; pro modely větší než 200 MB přidělte další paměť JVM a zvažte vykreslování po dávkách.

**Q: Mohu vykreslit pouze konkrétní pohled nebo orientaci?**  
A: GroupDocs.Viewer vykresluje výchozí orientaci definovanou v IGS souboru. Pro vlastní pohledy předzpracujte soubor CAD nástrojem nebo upravte model před konverzí.

---

**Poslední aktualizace:** 2026-08-08  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Související tutoriály

- [převod cdr na html, jpg, png, pdf pomocí GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Jak převést pdf na html a optimalizovat kvalitu obrázku v Javě s GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)