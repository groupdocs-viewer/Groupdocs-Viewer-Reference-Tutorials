---
date: '2026-08-30'
description: Naučte se, jak převést DWG na PNG, nastavit barvu pozadí v Javě a přizpůsobit
  velikost obrázku pomocí GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Převod DWG na PNG pomocí GroupDocs.Viewer for Java při nastavení vlastní
  šířky obrázku a barvy pozadí. Tento průvodce poskytuje krok za krokem nastavení,
  ukázky kódu a tipy na řešení problémů.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Převod DWG na PNG s vlastní velikostí a barvou pozadí v Javě
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Jak převést DWG na PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer
  for Java
type: docs
url: /cs/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Jak převést DWG na PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer pro Java

V tomto tutoriálu se naučíte **jak převést DWG na PNG** při řízení rozměrů výstupu a barvy pozadí pomocí GroupDocs.Viewer pro Java. Ať už potřebujete vložit CAD výkresy do zprávy, generovat náhledy pro webový portál nebo automatizovat dávkové renderování, níže uvedené kroky vám poskytnou plnou kontrolu nad vizuálním vzhledem každého souboru PNG.

## Rychlé odpovědi
- **Co znamená „převod DWG na PNG“?** Jedná se o proces převodu souboru DWG CAD na obrázek PNG pomocí kódu, přičemž se zachovává vektorová detailnost jako rastrové pixely.  
- **Mohu nastavit vlastní šířku?** Ano – zavolejte `CadOptions.forRenderingByWidth(int width)`, abyste definovali přesnou šířku v pixelech, kterou potřebujete.  
- **Jak změním barvu pozadí?** Použijte `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` před renderováním.  
- **Která knihovna je vyžadována?** GroupDocs.Viewer pro Java (verze 25.2 nebo novější).  
- **Potřebuji licenci?** Dočasná nebo plná licence odstraňuje omezení hodnocení a umožňuje neomezené renderování.

![Vykreslit CAD výkresy jako PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Co je GroupDocs.Viewer pro Java?
GroupDocs.Viewer pro Java je server‑side API, které vykresluje více než 150 formátů souborů – včetně CAD souborů – do obrázků, PDF nebo HTML. Funguje bez nutnosti jakéhokoli softwaru třetí strany, jako je AutoCAD, což jej činí ideálním pro automatizované pipeline.

## Jak převést DWG na PNG s vlastní velikostí a barvou pozadí?
Načtěte soubor DWG pomocí instance `Viewer`, nakonfigurujte `CadOptions` pro požadovanou šířku a pozadí a nakonec zavolejte `viewer.view` s `PngViewOptions`. Tento tříkrokový tok zpracovává souborové I/O, renderování a pojmenování výstupu v jediné, paměťově úsporné operaci.

Viewer je hlavní třída, která načítá dokument a provádí renderování.  
CadOptions konfiguruje CAD‑specifické nastavení, jako je šířka obrázku a barva pozadí.  
PngViewOptions definuje výstupní formát PNG a vzor pojmenování pro vykreslené stránky.

Nyní můžete vykreslit libovolný DWG výkres do PNG s přesně šířkou, kterou zadáte, a můžete zvolit libovolnou plnou barvu (nebo průhledné) pozadí, aby odpovídalo vaší značce nebo UI tématu.

## Proč nastavit vlastní barvu pozadí?
Nastavení barvy pozadí zajišťuje, že vykreslené PNG se hladce integruje s okolními UI prvky, vyhýbá se nechtěným bílým okrajům a může zvýraznit detaily výkresu, které by jinak byly ztraceny na výchozím bílém plátně. GroupDocs.Viewer podporuje jakýkoli `java.awt.Color`, včetně vlastních RGB hodnot, což vám poskytuje pixel‑dokonalou kontrolu.

java.awt.Color představuje hodnotu barvy používanou pro vykreslování pozadí.

## Předpoklady
- **Java Development Kit (JDK) 8+** – API cílí na Java 8 a novější.  
- **Maven** – pro správu závislostí.  
- **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli editor, který preferujete.  
- **Základní znalost manipulace se soubory v Javě** – pro čtení zdrojových DWG souborů a zápis PNG výstupů.

## Nastavení GroupDocs.Viewer pro Java
Přidejte repozitář GroupDocs a závislost Viewer do vašeho Maven `pom.xml`:

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
Získejte dočasný nebo plný licenční klíč z portálu GroupDocs a umístěte soubor `license.lic` do složky resources vašeho projektu. Tím se odstraní omezení 20‑stránkového hodnocení a odemkne renderování v plném rozlišení.

### Základní inicializace a nastavení
Vytvořte instanci `Viewer`, která ukazuje na složku obsahující vaše DWG soubory:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Funkce 1: renderování CAD výkresů s vlastní velikostí obrázku a barvou pozadí
### Jak změnit barvu pozadí CAD
Pro změnu barvy pozadí CAD nakonfigurujte objekt CadOptions před renderováním. Nastavte požadovanou šířku pomocí `forRenderingByWidth` a aplikujte nové pozadí pomocí `setBackgroundColor`. Viewer pak generuje PNG obrázky, které odrážejí zadanou barvu, což zajišťuje konzistentní vizuální styl napříč všemi výstupními soubory.

#### Implementace krok za krokem
##### Import požadovaných balíčků
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Nastavte výstupní adresář a formát cesty k souboru
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inicializujte viewer s vlastními renderovacími možnostmi
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Vysvětlení parametrů**  
- `PngViewOptions` – definuje výstupní formát PNG a vzor pojmenování.  
- `forRenderingByWidth(int width)` – nutí renderér vytvořit obrázek, jehož šířka odpovídá zadané hodnotě v pixelech; výška je škálována proporčně.  
- `setBackgroundColor(Color color)` – přepíše výchozí bílé plátno barvou, kterou zvolíte, a zlepšuje vizuální konzistenci napříč generovanými prostředky.

#### Tipy pro řešení problémů
- Ujistěte se, že výstupní složka existuje; pokud ne, použijte `Files.createDirectories(outputDir)`.  
- Ověřte, že cesta vstupního souboru je správná a že aplikace má oprávnění ke čtení.

## Funkce 2: nastavení barvy pozadí v renderovacích možnostech
### Jak nastavit barvu pozadí PNG
Nastavení barvy pozadí PNG zahrnuje vytvoření instance Color a přiřazení k CadOptions před renderováním. To zajišťuje, že každý vygenerovaný PNG používá zadané pozadí, které odpovídá vašim značkovým směrnicím nebo UI tématu. Můžete použít předdefinované konstanty nebo definovat vlastní RGB hodnoty pro přesnou kontrolu.

java.awt.Color představuje hodnotu barvy používanou pro vykreslování pozadí.

#### Implementace krok za krokem
##### Import požadovaných balíčků
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Nakonfigurujte renderovací možnosti s barvou pozadí
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Klíčové konfigurační možnosti**  
- Upravit `forRenderingByWidth(int width)` pro různé rozměry, například 800 px pro webové náhledy nebo 1920 px pro vysoce rozlišené tisky.  
- Použijte libovolnou předdefinovanou konstantu `Color` (např. `Color.LIGHT_GRAY`) nebo vytvořte vlastní instanci pomocí `new Color(r, g, b)` pro přesné brandování.

## Praktické aplikace
### 1. Technická dokumentace
Vlastní renderování zajišťuje, že každý výkres odpovídá firemnímu stylovému průvodci, čímž se eliminuje ruční úprava obrázku po exportu.

### 2. Architektonická vizualizace
Prezentujte plány s pozadím, které odpovídá prezentacím nebo klientským portálům, čímž se zlepšuje vizuální soudržnost.

### 3. Výroba prototypů
Generujte PNG pro workflow rychlých prototypů, kde následné nástroje očekávají konkrétní velikost obrázku a pozadí.

### Možnosti integrace
Propojte tento renderovací pipeline s dokumentovým systémem (např. SharePoint) a automaticky generujte náhledové obrázky při nahrání souboru DWG.

## Úvahy o výkonu
### Optimalizace výkonu
- **Dávkové zpracování:** Procházejte adresář DWG souborů a renderujte je jeden po druhém, aby se amortizovaly náklady na zahřátí JVM.  
- **Správa zdrojů:** Pro velké výkresy (500+ stránek) zvyšte haldu JVM (`-Xmx2g`) nebo zpracovávejte soubory v menších dávkách, aby nedocházelo k chybám nedostatku paměti.

### Pokyny pro využití zdrojů
Sledujte využití CPU a paměti pomocí nástrojů jako VisualVM; uvolňujte instance `Viewer` okamžitě pomocí try‑with‑resources.

### Nejlepší praktiky pro správu paměti v Javě
- Používejte try‑with‑resources (jak je ukázáno) k automatickému uzavření `Viewer`.  
- Vyhněte se uchovávání velkých objektů `Path` po dobu delší, než je jejich okamžité použití.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| Výstupní složka nenalezena | Vytvořte složku předem nebo přidejte `Files.createDirectories(outputDirectory);` |
| Prázdný obrázek | Ujistěte se, že `cadOptions.setBackgroundColor` je voláno po `forRenderingByWidth`. |
| Chyby nedostatku paměti | Zvyšte volbu JVM `-Xmx` nebo zpracovávejte soubory v menších dávkách. |

## Často kladené otázky
**Q: Mohu renderovat jiné CAD formáty kromě DWG?**  
A: Ano, GroupDocs.Viewer podporuje DXF, DWF a několik dalších CAD formátů.

**Q: Jak použít vlastní RGB barvu místo předdefinované konstanty?**  
A: Vytvořte novou `Color` pomocí `new Color(123, 45, 67)` a předávejte ji do `setBackgroundColor`.

**Q: Je možné renderovat pouze konkrétní rozvržení nebo vrstvu?**  
A: Můžete specifikovat možnosti rozvržení nebo vrstvy pomocí `CadOptions` před voláním `viewer.view`.

**Q: Podporuje knihovna průhledná pozadí?**  
A: Nastavte barvu pozadí na `new Color(0,0,0,0)` pro plnou průhlednost, pokud výstupní formát podporuje průhlednost.

**Q: Jaká verze GroupDocs.Viewer je požadována?**  
A: Tutoriál používá verzi 25.2, ale novější vydání zachovávají stejné API.

---

**Poslední aktualizace:** 2026-08-30  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs

## Související tutoriály
- [groupdocs viewer dwg – Jak renderovat konkrétní CAD výkresy v Javě pomocí GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render CAD Layers Java s GroupDocs.Viewer – Kompletní průvodce](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Jak převést pdf na html a optimalizovat kvalitu obrázku v Javě s GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)