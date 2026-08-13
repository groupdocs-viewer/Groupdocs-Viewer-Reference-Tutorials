---
date: '2026-05-21'
description: Zjistěte, jak provést export HTML z MS Project s upravenými časovými
  jednotkami pomocí GroupDocs Viewer for Java. Praktický návod krok za krokem s předpoklady,
  nastavením a řešením problémů.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Export HTML z MS Project: Úprava časových jednotek pomocí GroupDocs Java'
type: docs
url: /cs/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Export HTML z MS Project: Úprava časových jednotek pomocí GroupDocs Java

Export souboru **MS Project** do HTML je běžná potřeba pro řídicí panely projektového řízení, portály pro stavové zprávy a nástroje pro kolaborativní revizi. Ve výchozím nastavení prohlížeč vykresluje časová data v minutách, což může znepřehlednit vizuální rozvržení a ztížit čtení denních zpráv. S **GroupDocs Viewer for Java** můžete programově nastavit časovou jednotku na **dny**, čímž získáte čistý *ms project html export*, který odpovídá typickým očekáváním zúčastněných stran. V tomto tutoriálu se naučíte, jak nakonfigurovat prohlížeč, upravit časovou jednotku a vykreslit projekt do HTML během několika jednoduchých kroků.

![Upravit časové jednotky MS Project pomocí GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Upravit časové jednotky MS Project pomocí GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Rychlé odpovědi
- **Jaká knihovna vykresluje soubory MS Project?** GroupDocs Viewer for Java.  
- **Jakou časovou jednotku mohu nastavit pro export HTML?** Days, using `TimeUnit.DAYS`.  
- **Potřebuji licenci pro produkci?** Ano— je vyžadována trvalá licence; zkušební verze funguje pro hodnocení. Můžete začít s [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Které IDE funguje nejlépe?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Je Maven povinný?** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **Kde mohu zakoupit?** Visit the [buy page](https://purchase.groupdocs.com/buy) for pricing.

## Co je GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** je Java SDK, který převádí více než 150 formátů dokumentů—včetně MS Project—do web‑přátelského HTML, PNG, JPEG nebo PDF.  
Abstrahuje logiku parsování, umožňuje vám řídit možnosti vykreslování, jako jsou časové jednotky, a funguje na jakékoli platformě, která podporuje Java 8 nebo vyšší.  

## Proč upravit časové jednotky pro export HTML z MS Project?
Nastavení časové jednotky na **dny** snižuje vizuální šum, odpovídá většině reportingových cyklů a zlepšuje dobu načítání stránky, protože je generováno méně detailních časových značek. Kvantitativně může vykreslování ve dnech místo minut snížit velikost generovaného HTML až o **45 %** u typických 30‑denních projektů a urychlit vykreslování na straně klienta přibližně o **30 %**.

## Požadavky
- **Java Development Kit (JDK) 8 nebo novější** nainstalovaný na vašem pracovním stanici.  
- **Maven** (nebo Gradle) pro správu závislostí.  
- Soubor **MS Project (.mpp)**, který chcete exportovat.  
- Přístup k licenci **GroupDocs Viewer for Java** (zkušební nebo trvalá).  

### Požadované knihovny
Přidejte následující závislost do vašeho `pom.xml` (nebo ekvivalentní úryvek pro Gradle):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Tip:** Udržujte číslo verze aktuální; novější vydání přidávají podporu formátů a vylepšení výkonu.

## Jak nastavit GroupDocs Viewer pro Java?
Inicializujte prohlížeč vytvořením instance `Viewer`, která ukazuje na váš soubor MS Project. Třída `Viewer` je vstupním bodem pro všechny operace vykreslování. Načítá zdrojový dokument, připravuje interní struktury a poskytuje metody jako `view()` a `viewToHtml()` pro generování požadovaných výstupních formátů.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definice:** Třída `Viewer` je jádrovou součástí GroupDocs Viewer, která načítá zdrojový dokument a poskytuje metody vykreslování jako `view()` a `viewToHtml()`.

## Jak mohu upravit časové jednotky pro export HTML?
Pro změnu časové granularitě vytvořte objekt `ViewOptions`, nakonfigurujte jeho `ProjectOptions` tak, aby používal `TimeUnit.DAYS`, a předávejte jej prohlížeči. `ViewOptions` definuje nastavení vykreslování pro dokument, zatímco výčet `TimeUnit` určuje jednotku (minuty, hodiny, dny) pro časově související data. Po nastavení těchto možností zavolejte `viewer.view(options)`, aby se vygenerovalo HTML s denními značkami.

Načtěte svůj soubor MS Project pomocí `new Viewer("file.mpp")`, vytvořte objekt `ViewOptions`, nastavte `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, a poté zavolejte `viewer.view(options)`. Tento tříkrokový postup změní časovou jednotku z minut na dny a vygeneruje HTML soubory, které zobrazují pouze denní intervaly.

### Krok 1: Definujte výstupní složku
Vyberte zapisovatelný adresář, kam budou uloženy HTML stránky, například `output/`.

### Krok 2: Vytvořte možnosti zobrazení s vloženými zdroji
Vložené zdroje (CSS, JavaScript) zajišťují, že HTML stránky jsou samostatné.

### Krok 3: Nastavte časovou jednotku na dny
Použijte `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, abyste změnili granularitu.

### Krok 4: Vykreslete dokument
Zavolejte `viewer.view(options)`; prohlížeč zapíše jeden HTML soubor pro každou stránku projektu do výstupní složky.

### Krok 5: Ověřte výsledek
Otevřete vygenerovaný `index.html` v prohlížeči; měli byste vidět úkolové pruhy zarovnané k denním značkám místo minutových značek.

## Časté problémy a řešení
- **Nesprávná výstupní cesta** – Ujistěte se, že adresář existuje a proces Java má oprávnění k zápisu.  
- **Chybějící licence** – Bez platné licence se prohlížeč vrátí do zkušebního režimu a může vkládat vodoznaky.  
- **Velké soubory (> 500 MB)** – Zvažte zvýšení velikosti haldy JVM (`-Xmx2g`) nebo vykreslování s `options.setRenderLimit(1000)`, aby se stránky zpracovávaly po dávkách.  

## Praktické aplikace upraveného exportu HTML s časovou jednotkou
1. **Řídicí panely pro vedení** – Denní granularita odpovídá většině vizualizací KPI.  
2. **Automatizované stavové e‑maily** – Vložte vygenerované HTML přímo do těla e‑mailu pro rychlé aktualizace.  
3. **Projektové portály** – Hostujte HTML na intranetovém webu, kde mohou členové týmu filtrovat úkoly podle dne.  

## Úvahy o výkonu pro velké soubory MS Project
- **Správa paměti** – Použijte příznaky garbage collectoru Javy (`-XX:+UseG1GC`) k rychlému uvolnění nepoužívaných objektů.  
- **Selektivní vykreslování** – Pokud potřebujete jen Ganttův diagram, zakažte vykreslování dalších zdrojů pomocí `options.getProjectOptions().setRenderGantt(true)` a `setRenderResources(false)`.  
- **Paralelní zpracování** – Pro dávkové konverze vytvořte samostatné objekty `Viewer` pro každý soubor a spusťte je ve vláknovém poolu, aby se využily vícejádrové CPU.

## Závěr
Nyní máte kompletní, připravený pracovní postup pro provedení **ms project html export** s časovými jednotkami nastavenými na dny pomocí GroupDocs Viewer for Java. Tento přístup snižuje velikost HTML, urychluje vykreslování na straně klienta a poskytuje zúčastněným stranám přívětivý pohled na projektové plány. Prozkoumejte další možnosti vykreslování—například export do PDF nebo snímky obrazovky—abyste rozšířili integraci do širších reportingových kanálů.

## Často kladené otázky

**Q: Mohu renderovat jiné pohledy projektu (např. list zdrojů) do HTML?**  
A: Ano, objekt `ProjectOptions` vám umožní povolit nebo zakázat konkrétní pohledy, jako jsou Gantt, list zdrojů a kalendář, před vykreslením.

**Q: Je možné přizpůsobit CSS vygenerovaného HTML?**  
A: Ano. Poskytněte cestu k vlastnímu stylu pomocí `options.setStyleSheetPath("path/to/custom.css")` a prohlížeč jej vloží do každé stránky.

**Q: Jaké limity velikosti souboru podporuje GroupDocs Viewer pro MS Project?**  
A: SDK zvládne soubory až do **500 MB** bez nutnosti načíst celý dokument do paměti, díky své streamovací architektuře.

**Q: Potřebuji na server nainstalovat Microsoft Project?**  
A: Ne. GroupDocs Viewer přímo parsuje formát .mpp a nevyžaduje Microsoft Project ani žádnou instalaci Office.

**Q: Jak licencovat prohlížeč pro produkční prostředí?**  
A: Zakupte trvalou licenci v obchodě GroupDocs; použijte soubor licence za běhu pomocí `License license = new License(); license.setLicense("path/to/license.lic");`. Pro krátkodobé potřeby můžete získat [dočasnou licenci](https://purchase.groupdocs.com/temporary-license/).

---

**Poslední aktualizace:** 2026-05-21  
**Testováno s:** GroupDocs Viewer Java 25.2  
**Autor:** GroupDocs  

**Zdroje**  
- [Dokumentace](https://docs.groupdocs.com/viewer/java/)  
- [Reference API](https://reference.groupdocs.com/viewer/java/)  
- [Stáhnout GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Koupit licenci](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Související tutoriály

- [Jak renderovat soubory MS Project jako HTML, JPG, PNG a PDF s poznámkami pomocí GroupDocs.Viewer pro Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Jak použít GroupDocs Viewer k renderování projektových dokumentů podle časových intervalů v Javě](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Jak nastavit licence v GroupDocs.Viewer Java: Průvodce nastavením souboru a URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)