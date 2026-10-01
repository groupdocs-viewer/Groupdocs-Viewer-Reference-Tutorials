---
date: '2026-09-30'
description: Zjistěte, jak v Javě otočit stránku o 90 stupňů pomocí GroupDocs Viewer,
  včetně nastavení, kódu a tipů na výkon.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Otočte stránku o 90 stupňů v Javě pomocí GroupDocs Viewer. Průvodce
  krok za krokem, tipy na výkon a reálné příklady použití pro vývojáře.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Otočte stránku o 90 stupňů pomocí GroupDocs Viewer pro Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Otočte stránku o 90 stupňů pomocí GroupDocs Viewer pro Java
type: docs
url: /cs/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# Otočit stránku o 90 stupňů pomocí GroupDocs Viewer for Java

Pokud potřebujete **otočit stránku o 90 stupňů** v dokumentu — ať už jde o PDF, Word nebo tabulku — provedení toho programově v Javě šetří čas, eliminuje ruční chyby a umožňuje začlenit operaci do automatizovaných pipeline. V tomto pokročilém průvodci se naučíte, jak otočit první stránku libovolného podporovaného dokumentu pomocí **GroupDocs Viewer for Java**, proč je tato schopnost důležitá v reálných projektech a jak udržet proces lehký a paměťově úsporný.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Rychlé odpovědi
- **Co znamená „otočit stránku o 90 stupňů“?** Otočí vybranou stránku po směru hodinových ručiček o čtvrt otáčky.  
- **Která knihovna provádí rotaci?** GroupDocs Viewer for Java poskytuje metodu `rotatePage`.  
- **Mohu otočit PDF stránky pomocí Javy?** Ano — použijte stejnou volání `rotatePage`; funguje pro PDF, DOCX, XLSX a další.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována placená licence.  
- **Je operace náročná na paměť?** Ne, pokud `Viewer` instanci rychle uzavřete; viz tipy pro výkon níže.

## Co je „otočit stránku o 90 stupňů“?
Otočení stránky o 90 stupňů přenastaví orientaci stránky z portrétu na krajinu (nebo naopak) bez změny podkladového obsahu. To je užitečné pro prezentace, tisk grafiky jen v krajině nebo opravu naskenovaných dokumentů pořízených šikmo. Rotace se aplikuje při renderování, původní soubor zůstává nezměněn.

## Proč otáčet stránky programově pomocí GroupDocs Viewer for Java?
GroupDocs Viewer podporuje **více než 50 vstupních a výstupních formátů** — včetně PDF, DOCX, PPTX, XLSX a mnoha typů obrázků — takže můžete renderovat jakýkoli dokument bez externích konvertorů. API je plynulé, thread‑safe a běží na libovolném Java 8+ runtime, což z něj činí spolehlivou volbu pro podnikovou automatizaci, která musí konzistentně zvládat desítky typů souborů.

## Požadavky

- GroupDocs Viewer for Java (nejnovější verze)
- JDK 8 nebo novější
- Maven (nebo Gradle) pro správu závislostí
- IDE jako IntelliJ IDEA nebo Eclipse
- Základní znalost Java I/O

## Nastavení GroupDocs.Viewer pro Java

Přidejte repozitář GroupDocs a závislost do svého `pom.xml`. Tento úryvek zůstává beze změny oproti originálnímu tutoriálu:

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
- **Bezplatná zkušební verze** – stáhněte z webu GroupDocs.  
- **Dočasná licence** – požádejte, pokud potřebujete prodloužené zkušební období.  
- **Plná licence** – zakupte pro produkční nasazení.

### Základní inicializace Vieweru
Třída `Viewer` je vstupní bod, který načte dokument a poskytuje metody pro renderování a transformaci. Uchovejte kód přesně tak, jak je uveden:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Jak otočit PDF stránku v Javě pomocí GroupDocs Viewer
Načtěte cílový soubor pomocí `Viewer`, zadejte číslo stránky a zavolejte `rotatePage`. Metoda funguje pro PDF, DOCX, PPTX, XLSX i jakýkoli jiný formát podporovaný knihovnou. Po otočení můžete dokument renderovat do nového PDF nebo jej streamovat přímo klientovi, přičemž původní soubor zůstane nedotčen.

## Postupná implementace: otočit první stránku o 90 stupňů

### 1. Importujte požadované balíčky
`PdfViewOptions` říká Vieweru, aby výstupem byl PDF soubor, zatímco výčtový typ `Rotation` definuje úhel. Obě třídy patří do balíčku `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definujte výstupní umístění a vytvořte Viewer
Nahraďte zástupné cesty svými skutečnými adresáři. Konstruktor `Viewer` přijímá objekt `File`, který ukazuje na zdrojový dokument.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Nastavte možnosti PDF zobrazení a aplikujte rotaci
Metoda `rotatePage(int, Rotation)` přijímá **1‑based** index stránky a hodnotu výčtu `Rotation`. V tomto příkladu použijeme `Rotation.ON_90_DEGREE` k otočení první stránky po směru hodinových ručiček.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Vykreslete dokument
Volání `view` s nakonfigurovanými možnostmi zapíše otočené PDF do výstupní složky.

```java
viewer.view(viewOptions);
```

#### Jak to funguje
- **PdfViewOptions** nasměruje Viewer k vytvoření PDF výstupního souboru.  
- **rotatePage(int, Rotation)** otáčí pouze zadanou stránku, ostatní stránky zůstávají beze změny.  
- Metoda podporuje tři konstanty rotace: `ON_90_DEGREE`, `ON_180_DEGREE` a `ON_270_DEGREE`.

## Časté problémy a řešení
| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| **FileNotFoundException** | Nesprávná cesta nebo chybějící složka | Ověřte, že `YOUR_OUTPUT_DIRECTORY` a `YOUR_DOCUMENT_DIRECTORY` existují a jsou čitelné. |
| **Unsupported file format** | Pokus o otočení formátu, který Viewer nepodporuje | Zkontrolujte stránku [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Použití špatného čísla stránky (základ 0) | Pamatujte, že `rotatePage` používá **1‑based** indexování. |
| **Out‑of‑memory errors on large docs** | Vykreslování mnoha velkých souborů v jednom vlákně | Zpracovávejte dokumenty sekvenčně nebo použijte pool vláken s omezenou souběžností. |

## Praktické aplikace

1. **Úpravy prezentací** – Převod portrétové snímky na krajinu za běhu pro lepší vizuální dopad.  
2. **Hromadná oprava dokumentů** – Automatizujte opravu naskenovaných PDF, které byly pořízeny šikmo, a ušetřete hodiny ruční práce.  
3. **Výstup připravený k tisku** – Zajistěte, aby se krajinová grafika tiskla správně na papír orientovaný na portrét, bez ruční rotace v ovladači tiskárny.

## Tipy pro výkon

- **Uzavírejte zdroje okamžitě** – Blok `try‑with‑resources` automaticky uvolní `Viewer`, čímž šetří paměť.  
- **Dávkové zpracování** – Znovu použijte jedinou instanci `Viewer` na vlákno, abyste snížili režii inicializace.  
- **Sledujte paměť** – U dokumentů větších než 100 MB streamujte výstup na disk místo udržování celého souboru v paměti; GroupDocs Viewer dokáže zpracovat soubory 200 MB s využitím méně než 250 MB RAM.

## Často kladené otázky

**Q: Mohu otočit více stránek najednou?**  
A: Ano — volání `rotatePage()` opakujte pro každé číslo stránky, které potřebujete otočit, buď ve smyčce, nebo řetězením volání.

**Q: Existuje způsob, jak po renderování rotaci vrátit zpět?**  
A: Ne přímo. Museli byste dokument znovu renderovat bez nastavení rotace.

**Q: Které formáty souborů podporují rotaci stránek v GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX a mnoho dalších formátů uvedených v oficiální dokumentaci.

**Q: Jak mohu automaticky otáčet stránky ve skupině dokumentů?**  
A: Zabalte logiku rotace do smyčky, která iteruje přes kolekci cest k souborům a aplikuje stejnou konfiguraci `rotatePage` na každý soubor.

**Q: Jaká je nejlepší praxe pro zpracování chyb během rotace?**  
A: Obalte používání Vieweru do bloku `try‑catch`, logujte podrobnosti výjimky a volitelně pokračujte dalším souborem, aby jedna chyba nezastavila celý batch.

## Zdroje

- **Dokumentace**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Stáhnout**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Koupit licenci**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Bezplatná zkušební verze**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Dočasná licence**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Podpora**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-09-30  
**Testováno s:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs

## Související tutoriály

- [How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Load Document from URL in Java – GroupDocs.Viewer Tutorial](/viewer/java/document-loading/)
- [Groupdocs Viewer Java Document Views](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)