---
date: '2026-06-15'
description: Naučte se, jak převést Excel na PDF v Javě a rozdělit listy Excelu podle
  řádků a sloupců pomocí GroupDocs Viewer. Obsahuje nastavení, kód a osvědčené postupy.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Převod Excelu na PDF v Javě a rozdělení listů podle řádků a sloupců
type: docs
url: /cs/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Převod Excelu na PDF v Javě a rozdělení listů podle řádků a sloupců (Java)

Velké sešity Excelu často obsahují více dat, než lze pohodlně zobrazit na jedné obrazovce nebo vytisknout na jedné stránce. **convert excel to pdf java** je běžný požadavek, když potřebujete statický, sdílitelný formát, zatímco **rozdělení listů Excel podle řádků a sloupců** usnadňuje konzumaci dat ve webových nebo tištěných rozvrženích. V tomto průvodci projdeme oba úkoly pomocí **GroupDocs Viewer for Java**, ukážeme vám, jak nastavit stránkování, a vysvětlíme tipy pro nejlepší praxi ohledně výkonu a řešení problémů.

![Rozdělení listů Excel podle řádků a sloupců pomocí GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Rozdělení listů Excel podle řádků a sloupců pomocí GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Rychlé odpovědi
- **Jaká knihovna se používá?** GroupDocs Viewer for Java.  
- **Mohu rozdělit jak podle řádků, tak podle sloupců?** Ano – můžete definovat rows‑per‑page a columns‑per‑page společně.  
- **Potřebuji licenci?** Zkušební nebo dočasná licence funguje pro vývoj; plná licence je vyžadována pro produkci.  
- **Jaké výstupní formáty jsou podporovány?** HTML (vložené zdroje) je zobrazeno; PDF lze vygenerovat se stejnými možnostmi.  
- **Je Maven vyžadován?** Maven je doporučený způsob správy závislostí.  
- **Mohu také převést Excel na PDF?** Ano – stačí přepnout `HtmlViewOptions` na `PdfViewOptions` a znovu použít stejná nastavení stránkování.

## Co je „Jak rozdělit Excel“?
Rozdělení listu Excel znamená rozdělení jednoho listu do více stránek nebo souborů na základě pevného počtu řádků, sloupců nebo obojího. Tato technika je užitečná, když potřebujete vytvořit stránkované zprávy, vložit data do webových stránek nebo generovat tisknutelné sekce bez načítání celého sešitu najednou.

## Proč použít GroupDocs Viewer pro Java?
GroupDocs Viewer zpracovává tabulky v jediném průchodu a automaticky je stránkuje, čímž eliminuje ruční výpočty. **Fast rendering processes a 250‑page XLSX workbook in under 2 seconds on a typical 2‑core server**, and **the library supports 50+ input and output formats**, including XLS, XLSX, CSV, PDF, and HTML. Běží na libovolné platformě kompatibilní s JVM – Windows, Linux, macOS, Docker kontejnerech nebo cloudových serverless runtime – takže jej můžete integrovat kdekoliv běží vaše Java aplikace.

## Předpoklady
- Java 17 nebo novější nainstalována.  
- IDE, jako je IntelliJ IDEA nebo Eclipse.  
- Maven pro správu závislostí.  
- Základní znalost Javy a povědomí o práci se soubory Excel.

### Požadované knihovny, verze a závislosti
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
Získejte bezplatnou zkušební verzi, dočasnou licenci nebo zakupte plnou licenci na [GroupDocs](https://purchase.groupdocs.com/buy).

## Jak převést Excel na PDF v Javě?

Třída `Viewer` je jádrovou součástí GroupDocs Viewer, která načítá dokument a poskytuje metody renderování pro různé výstupní formáty. `SpreadsheetOptions` vám umožňuje řídit nastavení stránkování, jako jsou rows‑per‑page a columns‑per‑page pro renderování tabulek.

Načtěte svůj Excel soubor pomocí `new Viewer("source.xlsx")`, nakonfigurujte `SpreadsheetOptions` pro stránkování a zavolejte `viewer.view(pdfOptions, stream)` – toto jediné volání převede sešit na PDF při zachování nastavených limitů řádků/sloupců. Konverze zachovává vzorce, obrázky a styly buněk, poskytuje věrnou PDF repliku připravenou k distribuci.

## Jak rozdělit listy Excel podle řádků

Rozdělení podle řádků vytvoří sérii HTML stránek, z nichž každá obsahuje pevný počet řádků (např. 15). Tento přístup je ideální pro dashboardy, které zobrazují omezený počet záznamů na pohled. Viewer vygeneruje samostatné HTML soubory jako `page_0.html`, `page_1.html` atd., z nichž každý obsahuje určený počet řádků. To usnadňuje načtení jen potřebné části ve webovém rozhraní, snižuje šířku pásma a dobu renderování.

### Definiční kotva
`Viewer` je jádrová třída GroupDocs Viewer, která načítá dokument a orchestruje renderování do zvoleného výstupního formátu.

### Implementace krok za krokem

#### Krok 1: Nastavte cesty a inicializujte Viewer
Nejprve definujte, kam budou rozdělené stránky uloženy, a vytvořte instanci `Viewer` pro zdrojový sešit.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Krok 2: Nastavte řádky na stránku
Řekněte vieweru, kolik řádků má každá stránka obsahovat.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Krok 3: Vykreslete dokument
Nakonec vykreslete sešit pomocí definovaných možností.

```java
viewer.view(viewOptions);
```

## Jak rozdělit listy Excel podle řádků a sloupců

Někdy jedna stránka potřebuje zobrazit mřížku řádků **a** sloupců (např. 15 řádků × 7 sloupců). To vám dává plnou kontrolu nad rozvržením každé HTML stránky. Výsledné stránky zobrazují obdélníkový blok buněk, například řádky 1‑15 a sloupce A‑G na první stránce, řádky 16‑30 a sloupce H‑N na další. Toto stránkování ve stylu mřížky je užitečné pro tvorbu tisknutelných zpráv, které odpovídají standardním formátům papíru.

### Definiční kotva
`SpreadsheetOptions` konfiguruje, kolik řádků a sloupců se zobrazí na každé vygenerované stránce.

### Implementace krok za krokem

#### Krok 1: Nastavte cesty a inicializujte Viewer
Nastavení je podobné příkladu pouze s řádky, mění se jen název souboru.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Krok 2: Nastavte řádky a sloupce na stránku
Zadejte obě dimenze pro vytvoření rozdělení ve stylu mřížky.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Krok 3: Vykreslete dokument
Renderujte pomocí stejného volání `view`.

```java
viewer.view(options);
```

## Praktické aplikace
- **Generate Excel report Java**: Převést velké finanční modely na sérii stránkovaných HTML zpráv.  
- **GroupDocs Viewer Excel**: Vložit rozdělené stránky přímo do webového portálu pro interaktivní průzkum dat.  
- **Render Excel HTML Java**: Poskytnout vygenerované HTML stránky přes servlet nebo Spring controller pro rychlé renderování na straně klienta.  

## Úvahy o výkonu
- **Memory usage** – Velké sešity mohou spotřebovat značnou část haldy; zvažte zvýšení nastavení JVM `-Xmx`.  
- **Chunk size** – Vyberte počty řádků/sloupců, které vyvažují velikost stránky a rychlost renderování.  
- **Version updates** – Udržujte GroupDocs Viewer aktuální, abyste těžili z vylepšení výkonu; poslední verze 25.2 zvyšuje rychlost renderování až o 30 % ve srovnání s 24.x.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| `OutOfMemoryError` | Renderování velmi velkého listu s příliš mnoha řádky na stránku | Snižte `countRowsPerPage` nebo zvyšte JVM haldu |
| Prázdné výstupní soubory | Nesprávná cesta k souboru nebo chybějící oprávnění k zápisu | Ověřte, že `outputDirectory` existuje a je zapisovatelný |
| HTML zdroje se nenačítají | Používáte `forEmbeddedResources`, ale soubory jsou servírovány z jiné základní URL | Servírujte celý výstupní adresář nebo přepněte na `forExternalResources` |

## Často kladené otázky

**Q: Mohu generovat PDF místo HTML?**  
A: Ano. Nahraďte `HtmlViewOptions` za `PdfViewOptions` a zachovejte stejnou konfiguraci `SpreadsheetOptions`.

**Q: Je možné rozdělit na základě obsahu buňky místo pevných řádků/sloupců?**  
A: Přímé rozdělení na základě obsahu není v GroupDocs Viewer implementováno, ale můžete předzpracovat sešit pomocí Apache POI a vytvořit samostatné listy před renderováním.

**Q: Podporuje GroupDocs Viewer starší formáty Excelu (XLS)?**  
A: Ano. Viewer pracuje s XLS, XLSX, CSV a dalšími formáty tabulek.

**Q: Jak vložit vygenerované HTML do Spring MVC view?**  
A: Servírujte výstupní složku jako statický zdroj a odkazujte na vygenerované `page_0.html`, `page_1.html` atd. ve vašich šablonách Thymeleaf nebo JSP.

**Q: Jakou licenci potřebuji pro komerční nasazení?**  
A: Pro komerční nasazení je vyžadována plná produkční licence od GroupDocs; zkušební licence jsou pouze pro hodnocení.

## Zdroje
- **Dokumentace**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Reference API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Stáhnout**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Nákup**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Bezplatná zkušební verze**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Dočasná licence**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Podpora**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-06-15  
**Testováno s:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs  

## Související tutoriály

- [Vykreslení skrytých řádků a sloupců v Java tabulkách pomocí GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Přeskočit vykreslování prázdných řádků v Javě pomocí GroupDocs.Viewer: Průvodce výkonem](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Komplexní průvodce: Převod Excel 2003 XML na HTML/JPG/PNG/PDF pomocí GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)