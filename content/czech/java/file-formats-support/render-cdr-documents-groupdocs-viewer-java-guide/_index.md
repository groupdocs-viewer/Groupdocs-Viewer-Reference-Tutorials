---
date: '2026-08-19'
description: Zjistěte, jak převést cdr na html, stejně jako jpg, png a pdf pomocí
  GroupDocs.Viewer for Java. Obsahuje nastavení, ukázky kódu a tipy na výkon.
keywords:
- convert cdr to html
- convert cdr to pdf
- convert cdr to jpg
- convert cdr to png
- java convert coreldraw
lastmod: '2026-08-19'
og_description: Zjistěte, jak převést cdr na html, jpg, png a pdf pomocí GroupDocs.Viewer
  for Java. Průvodce krok za krokem s nastavením, úryvky kódu a osvědčenými postupy
  pro výkon.
og_image_alt: Guide showing conversion of CorelDRAW CDR files to HTML, JPG, PNG, and
  PDF using GroupDocs.Viewer for Java
og_title: Převést cdr na html, jpg, png, pdf pomocí GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  headline: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  type: TechArticle
- description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  name: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  steps:
  - name: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
    text: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Basic Java knowledge** – to understand the code snippets.'
    text: '**Basic Java knowledge** – to understand the code snippets.'
  type: HowTo
- questions:
  - answer: Yes. Load the file with a `Viewer` instance that accepts a password parameter
      (see the API docs).
    question: Can I convert password‑protected CDR files?
  - answer: No hard limit, but very large files may require more memory; consider
      processing page‑by‑page.
    question: Is there a limit on the number of pages that can be converted at once?
  - answer: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded
      as Base64, ensuring consistent rendering across browsers.
    question: Does the HTML output include embedded fonts?
  - answer: '`JpgViewOptions` provides a `setQuality(int)` method where you can specify
      a value from 1‑100.'
    question: How do I control JPEG quality?
  - answer: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is
      installed.
    question: Can I convert CDR files on a Linux server?
  type: FAQPage
tags:
- convert cdr
- groupdocs.viewer
- java file conversion
- coreldraw cdr
- document rendering
title: Převést cdr na html, jpg, png, pdf pomocí GroupDocs.Viewer Java
type: docs
url: /cs/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# Převod cdr na html, jpg, png, pdf pomocí GroupDocs.Viewer Java

Pokud potřebujete **převést cdr na html** (nebo na JPG, PNG a PDF) rychle a spolehlivě, jste na správném tutoriálu. V tomto průvodci projdeme vše, co potřebujete – od instalace GroupDocs.Viewer pro Java až po vykreslení souborů CorelDRAW (CDR) do webových HTML stránek, vysoce kvalitních obrázků a univerzálně čitelných PDF. Na konci budete schopni integrovat tyto převody do jakékoli Java aplikace pomocí několika řádků kódu.

![Vykreslení souborů CDR pomocí GroupDocs.Viewer pro Java](/viewer/file-formats-support/render-cdr-files.png)

[Vykreslení souborů CDR pomocí GroupDocs.Viewer pro Java](/viewer/file-formats-support/render-cdr-files.png)

## Rychlé odpovědi
- **Jaká knihovna převádí CDR na HTML?** GroupDocs.Viewer pro Java.  
- **Mohu také převádět CDR na JPG, PNG a PDF?** Ano – použijte stejnou Viewer API s různými možnostmi zobrazení.  
- **Potřebuji licenci?** Bezplatná zkušební verze nebo dočasná licence funguje pro testování; pro produkci je vyžadována plná licence.  
- **Jaká verze Javy je vyžadována?** JDK 8 nebo novější.  
- **Je podporována hromadná konverze?** Rozhodně – stačí iterovat soubory se stejnou instancí Viewer.

## Co je “convert cdr to html”?
Konverze cdr na html znamená převod vektorového souboru CorelDRAW do standardního HTML markupu, případně vložení obrázků a stylů, aby bylo možné návrh zobrazit přímo ve webovém prohlížeči bez nutnosti původního designového softwaru. Proces zachovává původní rozvržení, barvy a vektorové tvary tím, že je převádí na škálovatelné SVG elementy nebo rastrové obrázky vložené do HTML, což umožňuje přesné vizuální zobrazení napříč prohlížeči při zachování malé velikosti souboru.

## Proč převádět cdr na html, jpg, png nebo pdf?
Můžete vykreslit jeden zdroj CDR do čtyř široce podporovaných formátů, z nichž každý slouží jinému účelu: HTML pro okamžitý webový náhled, JPG/PNG pro rastrové obrázky a PDF pro tisknutelné, archivovatelné dokumenty. Tato flexibilita vám umožní poskytovat optimální typ souboru každému klientovi, snížit duplicitní úložiště a zajistit budoucí použitelnost vašich aktiv.

## Předpoklady

Před začátkem se ujistěte, že máte:

1. **Knihovny a závislosti** – GroupDocs.Viewer přidán do vašeho Maven projektu.  
2. **Java Development Kit (JDK)** – nainstalována verze 8 nebo novější.  
3. **Základní znalost Javy** – pro pochopení ukázek kódu.

### Požadované knihovny, verze a závislosti

Přidejte následující Maven konfiguraci do vašeho `pom.xml` (beze změny oproti originálnímu tutoriálu):

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

### Kroky získání licence

GroupDocs.Viewer nabízí bezplatnou zkušební verzi, dočasné licence pro testování nebo možnosti plného zakoupení:

- **Bezplatná zkušební verze** – Stáhněte z [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/).  
- **Dočasná licence** – Požádejte o ni na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Zakoupení** – Získejte trvalou licenci prostřednictvím [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Nastavení GroupDocs.Viewer pro Java

Viewer je hlavní třída, která načítá dokument a poskytuje metody vykreslování pro všechny podporované výstupní formáty.

### Instalace pomocí Maven
Výše uvedený Maven úryvek automaticky stáhne všechny potřebné JAR soubory. Po uložení souboru stačí spustit `mvn clean install`.

### Inicializace licence
`Viewer` je hlavní třída, která načítá dokument a poskytuje metody vykreslování pro všechny podporované výstupní formáty. Inicializujte svou licenci před vykreslením jakýchkoli dokumentů:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Průvodce implementací

Níže najdete krok za krokem příklady pro každý výstupní formát. Kódové bloky jsou identické s originálním tutoriálem; pouze jsme přidali vysvětlující text kolem nich.

### Jak převést cdr na html pomocí GroupDocs.Viewer

Načtěte soubor CDR a zavolejte HTML rendering API – to je vše, co potřebujete k vygenerování web‑připraveného markupu. Proces vyžaduje nastavení cest k souborům, vytvoření instance `HtmlViewOptions` a volání `viewer.view()`. Tento dvoustupňový vzor funguje pro jakoukoli velikost dokumentu a zachovává vektorovou věrnost.

#### Vykreslení dokumentu cdr do HTML
**Přehled:** Převést vaše CDR soubory do web‑přátelského HTML pro snadné sdílení.

**Krok 1 – nastavení cest k souborům**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Krok 2 – inicializace viewer a vykreslení**

HtmlViewOptions konfiguruje HTML vykreslování, umožňuje vkládat zdroje nebo je ukládat odděleně. Následující kód vykreslí každou stránku do samostatného HTML souboru a vloží obrázky jako Base64 řetězce.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### Jak převést cdr na jpg pomocí GroupDocs.Viewer

Můžete vytvořit vysoce kvalitní JPEG obrázky ze zdroje CDR pouhými dvěma řádky kódu. Nejprve nakonfigurujte `JpgViewOptions` s požadovanou kvalitou, poté zavolejte `viewer.view()`. Tento přístup je ideální pro náhledy, e‑mailové přílohy nebo jakýkoli scénář, kde je potřeba kompaktní rastrový obrázek.

#### Vykreslení dokumentu cdr do JPG
**Přehled:** Vytvořit vysoce kvalitní JPEG obrázky z vašeho CDR zdroje.

**Krok 1 – nastavení cest k souborům**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Krok 2 – inicializace viewer a vykreslení**

JpgViewOptions definuje nastavení JPEG vykreslování, jako je kvalita komprese a pojmenování výstupu. Níže uvedený příklad ukládá každou stránku jako samostatný JPEG soubor.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### Jak převést cdr na png pomocí GroupDocs.Viewer

Výstup PNG vám poskytuje bezztrátové rastrové obrázky, ideální pro archivaci nebo další grafické zpracování. Použijte `PngViewOptions` k zachování každého pixelu, poté vykreslete dokument stránku po stránce.

#### Vykreslení dokumentu cdr do PNG
**Přehled:** Vytvořit bezztrátové PNG obrázky pro archivaci nebo designové účely.

**Krok 1 – nastavení cest k souborům**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Krok 2 – inicializace viewer a vykreslení**

PngViewOptions specifikuje parametry PNG vykreslování, včetně podpory transparentních pozadí. Kód automaticky vytvoří PNG pro každou stránku.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### Jak převést cdr na pdf pomocí GroupDocs.Viewer

Převod souboru CDR na PDF vám poskytne univerzálně čitelný, připravený k tisku dokument. `PdfViewOptions` interně provádí konverzi vektorů na raster, zachovává rozvržení a písma bez nutnosti Adobe Illustratoru.

#### Vykreslení dokumentu cdr do PDF
**Přehled:** Převést vaše CDR soubory na univerzálně čitelné PDF.

**Krok 1 – nastavení cest k souborům**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Krok 2 – inicializace viewer a vykreslení**

PdfViewOptions řídí generování PDF, umožňuje vkládání písem a přizpůsobení rozvržení stránky. Úryvek vytvoří jedno PDF obsahující všechny stránky.

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Praktické aplikace

- **Webové portály:** Použijte HTML konverzi k vložení CDR návrhů přímo na vaše stránky.  
- **Obrázkové galerie:** Nasazujte výstupy JPG/PNG pro rychle načítané galerie nebo produktové katalogy.  
- **Sdílení dokumentů:** Poskytněte PDF klientům, kteří potřebují tisknutelnou, pouze ke čtení verzi.  
- **Archivace:** Ukládejte více formátů, aby byla zajištěna budoucí přístupnost nezávisle na změnách softwaru.  
- **Cross‑platform integrace:** Přenášejte vygenerované soubory do následných služeb, jako je OCR, analytika nebo systémy pro správu digitálních aktiv.

## Úvahy o výkonu

- **Uvolnění instancí Viewer** okamžitě (jak je ukázáno pomocí try‑with‑resources) pro uvolnění paměti.  
- **Hromadné zpracování:** Procházejte kolekci souborů CDR pomocí stejné konfigurace Viewer pro snížení režie.  
- **Alokace zdrojů:** GroupDocs.Viewer může vykreslovat dokumenty až do 500 stránek bez načítání celého souboru do paměti, ale velmi složité výkresy mohou těžit ze zvýšení velikosti haldy. Sledujte využití CPU a RAM během rozsáhlých konverzí.

## Časté problémy a tipy na odstraňování potíží

- **Chybějící písma:** Pokud výstup vypadá odlišně, ujistěte se, že požadovaná písma jsou na serveru dostupná nebo je vložte pomocí `PdfViewOptions`.  
- **Velké soubory:** Pro soubory CDR přesahující 200 MB zvažte zpracování stránka po stránce, aby se předešlo `OutOfMemoryError`.  
- **Nesprávná kvalita obrázku:** Upravte hodnotu `setQuality` v `JpgViewOptions`, pokud jsou JPEGy příliš komprimované.  
- **Chyby licence:** Ověřte, že cesta k souboru licence je správná a že verze licence odpovídá verzi vaší knihovny Viewer.

## Závěr

Ukázali jsme vám, jak **převést cdr na html**, stejně jako na JPG, PNG a PDF, pomocí GroupDocs.Viewer pro Java. Dodržením stručných úryvků kódu a tipů na osvědčené postupy můžete tyto konverze začlenit do jakéhokoli Java‑založeného pracovního postupu a poskytovat uživatelům flexibilní, vysoce kvalitní výstupy.

### Další kroky
- Experimentujte s pokročilými možnostmi vykreslování, jako jsou vlastní velikosti stránek nebo vodoznaky.  
- Kombinujte konverzní pipeline s REST API pro nabídku transformace souborů na požádání.  
- Připojte se ke komunitě a ptejte se na otázky ve [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## Často kladené otázky

**Q: Můžu převádět CDR soubory chráněné heslem?**  
A: Ano. Načtěte soubor pomocí instance `Viewer`, která přijímá parametr hesla (viz dokumentace API).

**Q: Existuje limit na počet stránek, které lze převést najednou?**  
A: Žádný pevný limit, ale velmi velké soubory mohou vyžadovat více paměti; zvažte zpracování stránka po stránce.

**Q: Obsahuje HTML výstup vložená písma?**  
A: Při použití `HtmlViewOptions.forEmbeddedResources` jsou písma vložena jako Base64, což zajišťuje konzistentní vykreslování napříč prohlížeči.

**Q: Jak mohu řídit kvalitu JPEG?**  
A: `JpgViewOptions` poskytuje metodu `setQuality(int)`, kde můžete zadat hodnotu od 1‑100.

**Q: Můžu převádět CDR soubory na Linux serveru?**  
A: Rozhodně – GroupDocs.Viewer je platformově nezávislý, pokud je nainstalována JDK.

---

**Poslední aktualizace:** 2026-08-19  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Související tutoriály

- [Jak převést Excel na HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [Jak převést CF2 na PDF, HTML, JPG, PNG pomocí GroupDocs.Viewer pro Java](/viewer/java/rendering-basics/render-cf2-files-groupdocs-java/)
- [Jak převést pdf na html a optimalizovat kvalitu obrázku v Javě s GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)