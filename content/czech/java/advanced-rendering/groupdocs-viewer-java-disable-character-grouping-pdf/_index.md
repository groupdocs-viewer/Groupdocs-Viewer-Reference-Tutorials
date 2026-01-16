---
date: '2025-12-21'
description: Naučte se, jak zakázat seskupování v PDF pomocí GroupDocs.Viewer pro
  Java, využitím java html z možností vykreslování PDF, aby byla zajištěna přesná
  reprezentace textu.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Jak zakázat seskupování v PDF pomocí GroupDocs.Viewer pro Javu
type: docs
url: /cs/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Jak zakázat seskupování v PDF pomocí GroupDocs.Viewer pro Java

Když potřebujete **jak zakázat seskupování** při vykreslování PDF, zejména pro složité skripty nebo starověké jazyky, je nezbytné přesné umístění znaků. Výchozí funkce *Character Grouping* může nesprávně sloučit znaky, což vede k nesprávnému výkladu obsahu. V tomto průvodci vám krok za krokem ukážeme, jak zakázat seskupování pomocí GroupDocs.Viewer pro Java, aby každý glyf zůstal přesně tam, kde má být.

![Techniky přesného vykreslování s GroupDocs.Viewer pro Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Rychlé odpovědi
- **Co „zakázat seskupování“?** Vynutí, aby vykreslovací motor zacházel s každým znakem jako s nezávislým prvkem, čímž zachová přesně rozvržení.
- **Která možnost API to řídí?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.
- **Potřebuji licenci?** Zkušební verze pro testování, ale pro produkci je vyžadována plná licence.
- **Mohu současně generovat Java HTML z PDF?** Ano – použijte `HtmlViewOptions` k vytvoření HTML výstupu při zakázání seskupování.
- **Je tato funkce omezena na PDF?** Primárně se týká PDF, ale prohlížeč podporuje mnoho dalších formátů.

## Úvod

Při s PDF dokumenty je přesnost vykreslování zásadní – zejména při zpracování složitých textových struktur, jako jsou hieroglyfy nebo jazyky, které vyžadují přesné reprezentaci znaků. Funkce „Chracter Grouping“ často problémy tím, že nesprávně seskupuje znaky, což vede k nesprávnému výkladu obsahu dokumentu. To může být zvláště problematické pro uživatele, kteří potřebují přesnou replikaci rozvržení textu svých dokumentů.

### Předpoklady

Před tím, než se pustíte do implementace kódu, získáte následující, že splníte požadavky:
- **Knihovny a závislosti**: Budete potřebovat GroupDocs.Viewer pro Java verze 25.2 nebo novější.
- **Nastavení prostředí**: stačí se, že máte nainstalovaný Java Development Kit (JDK) a vaše IDE je použito pro práci s Maven projekty.
- **Předpoklady znalostí**: Základní pochopení programování v Javě, zejména práce s cestami k souborům a používání externích knihoven.

## Jak zakázat seskupování při vykreslování PDF

### Nastavení GroupDocs.Viewer pro Java

#### Instalace přes Maven

Nejprve integrujte potřebnou knihovnu do svého projektu. Přidejte následující konfiguraci do souboru `pom.xml`:

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

#### Získání licence

Pro plné GroupDocs.Viewer získané využití licence:
- **Bezplatná zkušební verze**: Začněte s bezplatnou zkušební verzí pro testování funkcí.
- **Dočasná licence**: Požádejte o dočasnou licenci, pokud potřebujete více času.
- **Nákup**: Pro projekty dlouhodobé se doporučuje zakoupit licenci.

#### Základní inicializace a nastavení

Začněte nastavením prostředí vašeho projektu:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Průvodce implementací

#### Funkce: Zakázat seskupování znaků

##### Krok 1: Definování výstupního adresáře

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Proč?** Zajišťuje, že je výstup organizovaný a snadno přístupný.

##### Krok 2: Nakonfigurujte formát cesty k souboru

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Proč?** Pomáhá systematicky organizovat stránky PDF dokumentu.

##### Krok 3: Inicializujte možnosti zobrazení HTML

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Proč?** Vložené zdroje zajišťují, že všechny potřebné soubory jsou zahrnuty v HTML souboru každé stránky.

##### Krok 4: Zakažte seskupování znaků

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Proč?** Zajišťuje, že jsou znaky vykresleny jednotlivě, zachovávají své zamýšlené rozvržení a význam.

##### Krok 5: Vykreslení dokumentu

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Proč?** Zajišťuje, že jsou všechny zdroje řádně uzavřeny, čímž se předchází únikům paměti.

### Generování Java HTML z PDF bez seskupování

Třída `HtmlViewOptions` vám umožní vytvořit **java html z pdf** a zároveň ponechat každý znak oddělený. To je zvláště užitečné, když potřebujete vložit vykreslené stránky do webového portálu nebo e‑learningové platformy, kde je důležité přesné umístění glyfů.

### Tipy pro odstraňování problémů

- zvlášť se, že cesta k dokumentu je správná, aby nedošlo k `FileNotFoundException`.
- Ověřte, že adresář má oprávnění k zápisu.
- Dvakrát nejlepší, že používáte kompatibilní verzi GroupDocs.Viewer pro Java.

## Praktické aplikace

1. **Zachování jazyků**: Ideální pro vykreslování dokumentů v jazycích jako čínština, japonština nebo starověké písmo, kde je přesnost znaků důležitá.
2. **Právní a finanční dokumenty**: Zaručuje přesnost v dokumentech požadovaných přesných zobrazení textu pro soulad s předpisy.
3. **Vzdělávací materiály**: Perfektní pro učebnice a akademické práce, které obsahují složité diagramy nebo anotace.

## Úvahy o výkonu

- **Optimalizace využití zdrojů**: Zajistěte, aby váš server měl dostatečné zdroje pro zpracování velkých souborů PDF.
- **Správa paměti v Javě**: Používejte efektivní datové struktury a postupy odvozu odpadu pro efektivní správu paměti.
- **Dávkové zpracování**: Při vykreslování více dokumentů je zpracovávejte po dávkách pro zvýšení propustnosti.

## Závěr

Nyní jste zvládli **jak zakázat seskupování** během vykreslování PDF pomocí GroupDocs.Viewer pro Java. Tato schopnost je klíčová pro aplikaci, které vyžadují přesnou reprezentaci textu. Pro další zkoumání zkuste integrovat tuto funkci s jinými systémy správy dokumentů nebo experimentovat s dalšími možnostmi vykreslování.

Další kroky zahrnují prozkoumání pokročilejších funkcí GroupDocs.Viewer a doladění výkonu pro nasazení ve velkém měřítku.

## Často kladené otázky

**O:** *Proč bych vůbec potřeboval zakázat seskupování znaků?*
**A: Zakázání seskupování** znovu vykreslovacímu enginu sloučit znaky, které patří k odlišnému glyfům, což je nezbytné pro písmo, kde mezery a pořadí nesouvisí s významem.

**O:** *Je nastavení `setDisableCharsGrouping` použitelný jen pro HTML výstup?*
**A:** Ne, reflektovaný podkladový engine pro vykreslování PDF, takže jakýkoli výstupní formát (HTML, PNG atd.) bude změna ovat.

**Q:** *Mohu toto nastavení kombinovat s vlastními fonty?*
**A:** Ano – stačí načíst vlastní fonty před inicializací `Viewer` a pravidlo seskupování bude i nadále platit.

**Q:** *Ovlivňuje zakázání seskupování výkonu?*
**A:** Mírně, protože engine zpracovává každý znak zvlášť, ale je dopad u většiny minimálních dokumentů.

**Q:** *Existuje způsob, jak přepínat seskupování na úrovni jednotlivých stránek?*
**A:** V současnosti je volba globální pro každou instanci `PdfOptions`; pro různé stránky byste museli vytvořit samostatnou instanci `Viewer`.

## Zdroje

- [GroupDocs Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [Reference API](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Zakoupit licenci](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/java/)
- [Žádost o dočasnou licenci](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 21.12.2025
**Testováno s:** GroupDocs.Viewer 25.2 pro Java
**Autor:** GroupDocs