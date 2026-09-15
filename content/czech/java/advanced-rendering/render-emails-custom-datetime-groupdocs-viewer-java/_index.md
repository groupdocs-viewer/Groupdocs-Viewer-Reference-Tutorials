---
date: '2026-09-15'
description: Zjistěte, jak převést eml na html s vlastním formátem data a času a posunem
  časového pásma pomocí GroupDocs.Viewer pro Java — ideální pro archivaci e‑mailů
  a podpůrné portály.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Převod eml na html s vlastním formátem data a času a posunem časového
  pásma pomocí GroupDocs.Viewer pro Java. Postupujte podle tohoto krok‑za‑krokem průvodce
  pro přesné vykreslení e‑mailů.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: Převod eml na html s vlastním formátem data a času v jazyce java pomocí
  GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: Převod eml na html s vlastním formátem data a času v jazyce java pomocí GroupDocs.Viewer
type: docs
url: /cs/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Převod eml na html s vlastním formátem data a času v jave pomocí GroupDocs.Viewer

V moderních systémech podpory a archivace je **convert eml to html** rychle a při zachování přesných časových razítek nezbytnou schopností. Tento tutoriál vám ukáže, jak vykreslit e‑mail EML do HTML, použít **vlastní formát data a času** a nastavit **posun časového pásma** pomocí GroupDocs.Viewer pro Java. Na konci budete mít znovupoužitelný úryvek kódu, který vytváří přesné, web‑připravené zobrazení e‑mailů pro jakýkoli **email to html conversion** workflow.

![Vykreslení e‑mailů s vlastním datem a časem pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Rychlé odpovědi
- **Může GroupDocs.Viewer převést EML na HTML?** Ano – API vykresluje soubory EML přímo do HTML bez externích e‑mailových klientů.  
- **Potřebuji licenci pro produkci?** Bezplatná zkušební verze stačí pro testování; placená licence je vyžadována pro nasazení do produkce.  
- **Která verze Javy je podporována?** Java 8 nebo novější je plně podporována.  
- **Jak změním zobrazený formát data?** Zavolejte `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **Mohu upravit časové pásmo?** Ano, použijte `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## Co je „převod eml na html“?
`Convert eml to html` je proces transformace souboru e‑mailu EML do HTML dokumentu pro vykreslení v prohlížeči. Převod souboru EML na HTML změní surový e‑mail (včetně hlaviček, těla a příloh) na web‑přátelský formát, který prohlížeče zobrazí bez dalších pluginů. To usnadňuje vkládání e‑mailů do webových aplikací, archivů nebo panelů podpory.

## Proč použít GroupDocs.Viewer pro tento úkol?
GroupDocs.Viewer podporuje **50+ vstupních a výstupních formátů**, včetně EML, MSG, PST a PDF, a může vykreslovat e‑maily o stovkách stránek bez načítání celého souboru do paměti. Jeho engine bez závislostí eliminuje potřebu Outlooku nebo třetích stran parserů, což vám dává plnou kontrolu nad **vlastním formátem data a času** a **posunem časového pásma** při nízké spotřebě zdrojů.

## Požadavky
- GroupDocs.Viewer pro Java ≥ 25.2  
- JDK 8+ a Java IDE (IntelliJ IDEA, Eclipse, VS Code)  
- Maven pro správu závislostí  

## Nastavení GroupDocs.Viewer pro Java

### Konfigurace Maven
Přidejte repozitář GroupDocs a závislost Viewer do souboru `pom.xml`.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
Začněte s bezplatnou zkušební verzí nebo požádejte o dočasnou licenci pro rozšířené testování. Pro produkční použití zakupte plnou licenci.

### Základní inicializace
Vytvořte instanci `Viewer`, která ukazuje na soubor EML, který chcete převést.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Převod eml na html s vlastním formátem data a času v jave

Následující kroky vás provedou vykreslením souboru EML do HTML při aplikaci vlastního formátu data a času a posunu časového pásma.

### Krok 1: nastavení výstupního adresáře a cesty k souboru
Definujte, kam bude vygenerované HTML uloženo.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Vysvětlení:* `Path.of()` vytváří odkaz na složku, kde bude HTML uloženo. `resolve()` přidá název souboru.

### Krok 2: inicializace vieweru s e‑mailovým souborem
Instancujte třídu `Viewer` pro cílový soubor EML.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Vysvětlení:* Instance `Viewer` ukazuje na soubor EML, který chcete převést.

### Krok 3: konfigurace HtmlViewOptions
Vytvořte objekt `HtmlViewOptions`, který vloží obrázky a další zdroje přímo do výstupního HTML.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Vysvětlení:* `forEmbeddedResources()` vkládá obrázky a další zdroje přímo do HTML výstupu.

### Krok 4: nastavení vlastního formátu data a času *(custom datetime java)*
`setDateTimeFormat` určuje vzor data‑času používaný při vykreslování časových razítek e‑mailu.  
Definujte vzor, který bude použit pro všechna časová razítka ve vykresleném HTML.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Vysvětlení:* Tento vzor zobrazuje měsíc, den, rok, hodinu, minutu, označení AM/PM a posun časového pásma (`zzz`).

### Krok 5: nastavení posunu časového pásma *(timezone offset java)*
`setTimeZoneOffset` určuje časové pásmo, které bude aplikováno na všechna časová razítka e‑mailu.  
Upravte časová razítka na požadované časové pásmo.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Vysvětlení:* Upravená časová razítka budou zobrazena v požadovaném časovém pásmu. Nahraďte `"GMT+1"` libovolným platným identifikátorem pásma.

### Jak upravit časové pásmo e‑mailu v Javě
Pokud potřebujete **upravit časové pásmo e‑mailu** nad rámec jednoduchých posunů – například při změnách letního času – můžete získat odpovídající objekt `TimeZone` z API `java.util.TimeZone` pomocí regionálních ID jako `"Europe/Paris"` nebo `"America/New_York"` a předat jej metodě `setTimeZoneOffset`. Tím zajistíte, že časová razítka e‑mailu vždy odrážejí správný místní čas.

### Krok 6: vykreslení dokumentu
Proveďte převod a vytvořte finální HTML soubor.

```java
viewer.view(options);
```
*Vysvětlení:* Spustí převod a vytvoří HTML soubor s vašimi nastaveními data‑času.

## Jaký vliv má vlastní formát data a času na vykreslené HTML?
Vlastní formát data a času určuje, jak se každé časové razítko e‑mailu zobrazí v generovaném HTML, což ovlivňuje čitelnost a soulad s lokálními standardy. Zadáním vzoru jako `"MMM dd, yyyy hh:mm a zzz"` zajistíte konzistentní zobrazení data, včetně zkráceného názvu měsíce, dne, roku, hodiny, minuty, AM/PM a explicitního posunu časového pásma – což je klíčové pro globální týmy podpory.

## Jaké souborové formáty GroupDocs.Viewer podporuje pro vykreslování e‑mailů?
GroupDocs.Viewer může vykreslovat **EML, MSG, PST, MBOX a EMLX** soubory do HTML, PDF, PNG a JPEG. Podporuje více než 50 celkových formátů dokumentů a obrázků, což vám umožní převádět e‑maily do jakéhokoli běžného web‑přátelského výstupu bez dalších konvertorů.

## Jak mohu hromadně převést více souborů eml?
Umístěte všechny soubory EML do jednoho adresáře, projděte je pomocí smyčky `for` nebo `foreach`, znovu použijte stejnou instanci `HtmlViewOptions` a zavolejte `viewer.view` pro každý soubor. Tento přístup minimalizuje vytváření objektů a urychluje hromadné převody.

## Tipy pro řešení problémů
- **FileNotFoundException:** Ověřte cesty použité v `Viewer` a `Path.of()`.  
- **Incorrect timestamps:** Ujistěte se, že ID `TimeZone` odpovídá vaší cílové oblasti.  
- **Missing images:** Zkontrolujte, že jste použili `HtmlViewOptions.forEmbeddedResources()`; jinak mohou být externí zdroje vynechány.  

## Praktické aplikace
1. **Archivace e‑mailů:** Ukládejte prohledávatelné HTML snímky e‑mailů pro audity shody.  
2. **Portály zákaznické podpory:** Zobrazujte příchozí tikety s přesnými lokálními časy pro agenty po celém světě.  
3. **Právní dokumentace:** Vytvářejte soudně použitelné záznamy e‑mailů se standardizovanými časovými razítky.  

## Úvahy o výkonu
- Nasazujte na dedikovaném serveru pro hromadné převody.  
- Sledujte využití haldy Javy; zvýšte `-Xmx`, pokud narazíte na `OutOfMemoryError`.  
- Kešujte vykreslené HTML, když je stejný e‑mail požadován opakovaně, čímž snížíte zátěž CPU.  

## Závěr
Nyní máte kompletní, připravenou pro produkci metodu pro **convert eml to html** s vlastním formátem data a času a posunem časového pásma pomocí GroupDocs.Viewer pro Java. Toto řešení zlepšuje čitelnost, zajišťuje přesnost časových razítek a hladce zapadá do archivních, podpůrných nebo právních pracovních toků.

**Další kroky:** Prozkoumejte další možnosti Vieweru, jako je injekce vlastního CSS, stránkování nebo převod do PDF, abyste výstup ještě lépe přizpůsobili potřebám vaší aplikace.

## Často kladené otázky

**Q: Jak zacházet se soubory eml s přílohami?**  
A: Přílohy jsou automaticky vloženy, když použijete `HtmlViewOptions.forEmbeddedResources()`. Pokud potřebujete samostatné soubory, můžete je extrahovat pomocí Viewer API.

**Q: Mohu změnit HTML šablonu nebo přidat vlastní CSS?**  
A: Ano, po vykreslení můžete upravit vygenerovaný HTML soubor nebo programově vložit CSS před uložením.

**Q: Je možné hromadně vykreslit více souborů eml?**  
A: Zabalte logiku vykreslování do smyčky a pro každý soubor znovu použijte stejnou instanci `HtmlViewOptions`.

**Q: Co když potřebuji podporovat jiné formáty e‑mailů, jako je msg?**  
A: GroupDocs.Viewer také podporuje MSG, PST a další e‑mailové kontejnery – stačí změnit příponu souboru v konstruktoru `Viewer`.

**Q: Potřebuji samostatnou licenci pro každý server?**  
A: Licence je vázána na nasazení; konzultujte průvodce licencováním GroupDocs pro scénáře s více servery.

## Zdroje

- [Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [Reference API](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout](https://releases.groupdocs.com/viewer/java/)
- [Koupit](https://purchase.groupdocs.com/buy)
- [Bezplatná zkuška](https://releases.groupdocs.com/viewer/java/)
- [Dočasná licence](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-09-15  
**Testováno s:** GroupDocs.Viewer 25.2 (Java)  
**Autor:** GroupDocs

## Související tutoriály

- [Převod e‑mailu na HTML a přejmenování polí – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java převod msg na pdf – Optimalizace vykreslování e‑mailu do PDF pomocí GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [GroupDocs Viewer Java Responzivní vykreslování HTML](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
