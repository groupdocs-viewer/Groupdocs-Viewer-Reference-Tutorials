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

## Quick Answers
- **Co dělá „zakázat seskupování“?** Vynutí, aby vykreslovací engine zacházel s každým znakem jako s nezávislým prvkem, čímž zachová přesné rozvržení.  
- **Která možnost API to řídí?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Potřebuji licenci?** Zkušební verze funguje pro testování, ale pro produkci je vyžadována plná licence.  
- **Mohu současně generovat Java HTML z PDF?** Ano – použijte `HtmlViewOptions` k vytvoření HTML výstupu při zakázání seskupování.  
- **Je tato funkce omezena na PDF?** Primárně se týká PDF, ale prohlížeč podporuje mnoho dalších formátů.

## Introduction

Při práci s PDF dokumenty je přesnost vykreslování zásadní – zejména při zpracování složitých textových struktur, jako jsou hieroglyfy nebo jazyky, které vyžadují přesnou reprezentaci znaků. Funkce „Character Grouping“ často způsobuje problémy tím, že nesprávně seskupuje znaky, což vede k nesprávnému výkladu obsahu dokumentu. To může být zvláště problematické pro uživatele, kteří potřebují přesnou replikaci rozvržení textu svých dokumentů.

### Prerequisites

Před tím, než se pustíte do implementace kódu, ujistěte se, že splňujete následující požadavky:
- **Knihovny a závislosti**: Budete potřebovat GroupDocs.Viewer pro Java verze 25.2 nebo novější.
- **Nastavení prostředí**: Ujistěte se, že máte nainstalovaný Java Development Kit (JDK) a vaše IDE je nastavené pro práci s Maven projekty.
- **Předpoklady znalostí**: Základní pochopení programování v Javě, zejména práce s cestami k souborům a používání externích knihoven.

## How to Disable Grouping in PDF Rendering

### Setting Up GroupDocs.Viewer for Java

#### Installation via Maven

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

#### License Acquisition

Pro plné využití GroupDocs.Viewer zvažte získání licence:
- **Bezplatná zkušební verze**: Začněte s bezplatnou zkušební verzí pro vyzkoušení funkcí.  
- **Dočasná licence**: Požádejte o dočasnou licenci, pokud potřebujete více času.  
- **Nákup**: Pro dlouhodobé projekty se doporučuje zakoupit licenci.

#### Basic Initialization and Setup

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

### Implementation Guide

#### Feature: Disable Characters Grouping

##### Step 1: Define Output Directory

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Proč?** Zajišťuje, že je výstup organizovaný a snadno přístupný.

##### Step 2: Configure File Path Format

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Proč?** Pomáhá systematicky organizovat stránky PDF dokumentu.

##### Step 3: Initialize HTML View Options

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Proč?** Vložené zdroje zajišťují, že všechny potřebné soubory jsou zahrnuty v HTML souboru každé stránky.

##### Step 4: Disable Character Grouping

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Proč?** Zajišťuje, že jsou znaky vykresleny jednotlivě, zachovávají své zamýšlené rozvržení a význam.

##### Step 5: Render the Document

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Proč?** Zajišťuje, že jsou všechny zdroje řádně uzavřeny, čímž se předchází únikům paměti.

### Generating Java HTML from PDF without Grouping

Třída `HtmlViewOptions` vám umožní vytvořit **java html from pdf** a zároveň ponechat každý znak oddělený. To je zvláště užitečné, když potřebujete vložit vykreslené stránky do webového portálu nebo e‑learningové platformy, kde je důležité přesné umístění glyfů.

### Troubleshooting Tips

- Ujistěte se, že cesta k dokumentu je správná, aby nedošlo k `FileNotFoundException`.  
- Ověřte, že výstupní adresář má oprávnění k zápisu.  
- Dvakrát zkontrolujte, že používáte kompatibilní verzi GroupDocs.Viewer pro Java.

## Practical Applications

1. **Zachování jazyků**: Ideální pro vykreslování dokumentů v jazycích jako čínština, japonština nebo starověké písmo, kde je přesnost znaků důležitá.  
2. **Právní a finanční dokumenty**: Zaručuje přesnost v dokumentech vyžadujících přesné zobrazení textu pro soulad s předpisy.  
3. **Vzdělávací materiály**: Perfektní pro učebnice a akademické práce, které obsahují složité diagramy nebo anotace.

## Performance Considerations

- **Optimalizace využití zdrojů**: Zajistěte, aby váš server měl dostatečné zdroje pro zpracování velkých PDF souborů.  
- **Správa paměti v Javě**: Používejte efektivní datové struktury a postupy garbage collection pro efektivní správu paměti.  
- **Dávkové zpracování**: Při vykreslování více dokumentů je zpracovávejte po dávkách pro zvýšení propustnosti.

## Conclusion

Nyní jste zvládli **jak zakázat seskupování** během vykreslování PDF pomocí GroupDocs.Viewer pro Java. Tato schopnost je klíčová pro aplikace, které vyžadují přesnou reprezentaci textu. Pro další zkoumání zkuste integrovat tuto funkci s jinými systémy správy dokumentů nebo experimentovat s dalšími možnostmi vykreslování.

Další kroky zahrnují prozkoumání pokročilejších funkcí GroupDocs.Viewer a doladění výkonu pro nasazení ve velkém měřítku.

## FAQ Section

1. **Co dosahuje zakázání seskupování znaků?**  
   - Zajišťuje, že jsou znaky vykresleny jednotlivě, zachovávají jejich původní rozvržení.  
2. **Mohu tuto funkci použít s jinými typy dokumentů?**  
   - Ano, i když se zde zaměřujeme na PDF, GroupDocs.Viewer podporuje mnoho formátů.  
3. **Jak efektivně zpracovat velké dokumenty?**  
   - Použijte dávkové zpracování a optimalizujte zdroje serveru.  
4. **Co dělat, pokud není výstupní adresář zapisovatelný?**  
   - Zkontrolujte oprávnění nebo vyberte jiný adresář s odpovídajícími přístupovými právy.  
5. **Existují licenční omezení pro GroupDocs.Viewer?**  
   - K dispozici je bezplatná zkušební verze, ale dlouhodobé používání vyžaduje zakoupenou licenci.

## Frequently Asked Questions

**Q:** *Proč bych vůbec potřeboval zakázat seskupování znaků?*  
**A:** Zakázání seskupování zabraňuje vykreslovacímu enginu sloučit znaky, které patří k odlišným glyfům, což je nezbytné pro písma, kde mezery a pořadí nesou význam.

**Q:** *Je nastavení `setDisableCharsGrouping` použitelné jen pro HTML výstup?*  
**A:** Ne, ovlivňuje podkladový engine pro vykreslování PDF, takže jakýkoli výstupní formát (HTML, PNG atd.) bude změnu reflektovat.

**Q:** *Mohu toto nastavení kombinovat s vlastními fonty?*  
**A:** Ano – stačí načíst vlastní fonty před inicializací `Viewer` a pravidlo seskupování bude i nadále platit.

**Q:** *Ovlivňuje zakázání seskupování výkon?*  
**A:** Mírně, protože engine zpracovává každý znak zvlášť, ale dopad je u většiny dokumentů minimální.

**Q:** *Existuje způsob, jak přepínat seskupování na úrovni jednotlivých stránek?*  
**A:** V současnosti je volba globální pro každou instanci `PdfOptions`; pro různé stránky byste museli vytvořit samostatné instance `Viewer`.

## Resources

- [GroupDocs Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [Reference API](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Zakoupit licenci](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/java/)
- [Žádost o dočasnou licenci](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs