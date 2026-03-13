---
date: '2026-01-28'
description: Naučte se, jak upravit časové jednotky v MS Project pomocí GroupDocs
  Viewer Java. Zefektivněte proces vykreslování dokumentů projektu efektivně a přesně.
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
title: 'Jak upravit časové jednotky v MS Project pomocí GroupDocs Viewer Java - krok
  za krokem průvodce'
type: docs
url: /cs/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Jak upravit časové jednotky v MS Project pomocí groupdocs viewer java: Průvodce krok za krokem

## Úvod
Už vás nebaví ručně upravovat časové jednotky ve vašich dokumentech MS Project před jejich převodem do formátu HTML? Tento proces může být zdlouhavý a náchylný k chybám, zejména při práci s velkými projekty. S **groupdocs viewer java** můžete snadno programově upravit nastavení časových jednotek, což zajišťuje přesnost a efektivitu.

![Upravit časové jednotky v MS Project pomocí GroupDocs.Viewer pro Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

V tomto průvodci ukážeme, jak změnit časové jednotky dokumentů MS Project na dny pomocí groupdocs viewer java. Na konci tohoto tutoriálu budete schopni:
- Nastavit své prostředí pro převod souborů MS Project pomocí GroupDocs.Viewer.
- Upravit časové jednotky projektového řízení přímo ve vašem kódu.
- Bezproblémově integrovat tato nastavení do vaší aplikace.

Než se pustíme dál, ujistěte se, že máte vše připravené k zahájení!

## Rychlé odpovědi
- **Jaká knihovna zajišťuje převod MS Project?** groupdocs viewer java
- **Která časová jednotka může být nastavena?** Dny (pomocí `TimeUnit.DAYS`)
- **Potřebuji licenci?** K dispozici je zkušební nebo dočasná licence; pro produkci je vyžadována trvalá licence.
- **Jaké IDE je nejlepší?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse), které podporuje Maven.
- **Je Maven vyžadován?** Ano, Maven zjednodušuje správu závislostí pro groupdocs viewer java.

## Co je groupdocs viewer java?
groupdocs viewer java je Java SDK, který umožňuje vývojářům převádět širokou škálu formátů dokumentů — včetně souborů MS Project — do webových formátů, jako je HTML nebo obrázky. Abstrahuje složitost parsování souborů, což vám umožní soustředit se na obchodní logiku.

## Proč upravovat časové jednotky pomocí groupdocs viewer java?
Změna časové jednotky z výchozí (často minut) na dny činí výstup čitelnějším pro zainteresované strany, ladí s typickým cyklem reportování a snižuje vizuální nepořádek v HTML zprávách. To je zvláště užitečné při vkládání časových os projektů do dashboardů nebo při generování denních souhrnů stavu.

## Předpoklady

### Požadované knihovny a závislosti
Pro sledování tohoto tutoriálu budete potřebovat následující:
- **groupdocs viewer java** knihovna (verze 25.2 nebo novější).
- Maven nainstalovaný na vašem počítači pro správu závislostí.
- Základní znalost programování v Javě.

### Požadavky na nastavení prostředí
Ujistěte se, že vaše vývojové prostředí je nastaveno s JDK (Java Development Kit) a IDE jako IntelliJ IDEA nebo Eclipse, které podporují Maven projekty.

### Předpoklady znalostí
Základní znalost syntaxe Javy, práce se soubory v Javě a práce se závislostmi Maven bude užitečná. Tento průvodce však usiluje o to, aby byl proces srozumitelný pro všechny úrovně dovedností.

## Nastavení groupdocs viewer java
Pro zahájení používání groupdocs viewer java přidejte tuto knihovnu jako závislost do souboru `pom.xml` vašeho projektu:

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

### Krok získání licence
groupdocs nabízí bezplatnou zkušební verzi svých knihoven, která vám umožní vyzkoušet funkce před zakoupením nebo žádostí o dočasnou licenci:
- **Free Trial**: Navštivte [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) pro stažení a zahájení používání knihovny.
- **Temporary License**: Pro rozšířené testování požádejte o [temporary license](https://purchase.groupdocs.com/temporary-license/).
- **Purchase**: Pokud se rozhodnete, že groupdocs.viewer java je pro váš projekt vhodný, zakupte jej přímo na jejich [buy page](https://purchase.groupdocs.com/buy).

### Základní inicializace a nastavení
Jakmile je závislost nastavena ve vašem Maven `pom.xml`, můžete začít kódovat. Inicializujte instanci Viewer s cestou k vašemu souboru MS Project a připravte se na převod.

## Průvodce implementací
Ponořme se do toho, jak můžete pomocí groupdocs viewer java upravit časové jednotky v dokumentech MS Project. Rozložíme to krok po kroku.

### Přehled funkce: Úprava časových jednotek v dokumentech MS Project
Tato funkce vám umožní změnit nastavení časové jednotky projektového řízení z výchozí (obvykle minut) na dny, čímž se vaše vygenerované HTML stane uživatelsky přívětivějším a sladěným s typickými standardy reportování.

#### Krok 1: Definujte výstupní adresář a formát cesty souboru stránky
Nejprve určete, kde budou uloženy vygenerované HTML soubory:

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

Použijte tento adresář k dynamickému řešení cest souborů pro každou stránku vašeho dokumentu MS Project:

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

#### Krok 2: Inicializujte View Options
Vytvořte view options s vloženými zdroji, které vám umožní určit, jak má být projekt zobrazen a převeden:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### Krok 3: Nastavte časovou jednotku
Určete, že časová jednotka pro projektové řízení je nastavena na dny, což je často vhodnější pro prezentace a zprávy:

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

#### Krok 4: Převod dokumentu MS Project
Nakonec použijte třídu Viewer k převodu vašeho dokumentu s určenými view options:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

### Tipy pro řešení problémů
- Ujistěte se, že cesta k výstupnímu adresáři je správně zadána a je zapisovatelná.
- Ověřte, že cesta k souboru MS Project je správná a přístupná.
- Pokud nastanou problémy s převodem, zkontrolujte případné výjimky vyhozené třídou Viewer.

## Praktické aplikace
Zde jsou některé reálné případy použití, kde úprava časových jednotek v dokumentech MS Project může být zvláště užitečná:
1. **Project Reporting** – Zainteresované strany často upřednostňují denní souhrny před podrobnými minutovými údaji.
2. **Integration with Dashboards** – Vkládání časových os do obchodních dashboardů, které vyžadují denní granularitu.
3. **Automated Updates** – Systémy, které potřebují automaticky aktualizovat stav projektů denně.

## Úvahy o výkonu
Při práci s velkými soubory MS Project zvažte následující pro optimální výkon:
- Používejte vložené zdroje střídmě, pokud jsou často potřeba jen určité části dokumentu.
- Sledujte využití paměti při práci s více nebo velmi velkými projekty současně.
- Efektivně využívejte garbage collection v Javě k řízení alokace a uvolňování zdrojů.

## Závěr
Nyní jste se naučili, jak upravit časové jednotky v MS Project pomocí groupdocs viewer java. Tato funkce zjednodušuje proces převodu projektových dokumentů, činí je přístupnějšími a snáze integrovatelnými do širších systémů.

Zvažte prozkoumání dalších možností groupdocs viewer java pro další vylepšení vašich řešení správy dokumentů. Připraveni posunout to dál? Vyzkoušejte implementaci tohoto řešení ve vašem dalším projektu!

## Často kladené otázky
**1. K čemu slouží GroupDocs.Viewer pro Java?**  
GroupDocs.Viewer pro Java umožňuje vývojářům převádět dokumenty v různých formátech, včetně souborů MS Project, do HTML nebo obrazových formátů pro prohlížení.

**2. Mohu použít GroupDocs.Viewer i pro jiné typy dokumentů?**  
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů mimo MS Project, jako jsou PDF, Word dokumenty a tabulky.

**3. Jak řešit licencování pro GroupDocs.Viewer?**  
GroupDocs nabízí různé licenční možnosti, včetně bezplatných zkušebních verzí, dočasných licencí pro rozšířené testování a trvalých licencí po zakoupení.

**4. Co když narazím na chyby při převodu mých projektových souborů?**  
Zkontrolujte cesty k souborům, ujistěte se, že máte právo zápisu do výstupního adresáře, a prohlédněte si případné výjimky vyhozené GroupDocs.Viewer pro nápovědu k řešení problémů.

**5. Mohu přizpůsobit způsob, jakým jsou dokumenty převáděny pomocí GroupDocs.Viewer?**  
Určitě! GroupDocs.Viewer poskytuje řadu možností pro přizpůsobení převodu, včetně nastavení časových jednotek pro projekty, výběru, které zdroje vložit, a dalších.

## Zdroje
- [Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Zakoupit licenci](https://purchase.groupdocs.com/buy)

---

**Poslední aktualizace:** 2026-01-28  
**Testováno s:** groupdocs viewer java 25.2  
**Autor:** GroupDocs