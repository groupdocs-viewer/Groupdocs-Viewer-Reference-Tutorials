---
date: '2026-01-08'
description: Naučte se, jak renderovat CAD výkresy do vysoce kvalitních PNG obrázků
  s vlastními rozměry a barvami pozadí pomocí GroupDocs.Viewer pro Javu.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Jak renderovat CAD výkresy jako PNG s vlastní velikostí a barvou pozadí pomocí
  GroupDocs.Viewer pro Javu
type: docs
url: /cs/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Jak vykreslit CAD výkresy jako PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer pro Java

Máte potíže převést své CAD výkresy na vysoce kvalitní obrázky při zachování konkrétních rozměrů a estetického vzhledu? V tomto tutoriálu vám ukážeme **jak vykreslit CAD** soubory jako PNG s vlastní velikostí a barvou pozadí, abyste získali přesně ten vzhled, který potřebujete pro zprávy, prezentace nebo webové náhledy.

## Rychlé odpovědi
- **Co znamená „jak vykreslit CAD“?** Jedná se o převod CAD souborů (např. DWG) do formátů obrázků jako PNG pomocí kódu.  
- **Mohu nastavit vlastní šířku?** Ano – použijte `CadOptions.forRenderingByWidth(int width)`.  
- **Jak změním pozadí?** Zavolejte `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Která knihovna je vyžadována?** GroupDocs.Viewer pro Java (verze 25.2 nebo novější).  
- **Potřebuji licenci?** Dočasná nebo zakoupená licence odstraňuje omezení evaluační verze.

![Vykreslit CAD výkresy jako PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Jak vykreslit CAD výkresy – Přehled
Tato sekce rozšiřuje hlavní cíl: **jak vykreslit CAD** výkresy do PNG souborů při řízení velikosti a pozadí. Provedeme vás kompletním nastavením, ukázkami kódu a praktickými tipy.

## Co se naučíte
- Nastavení GroupDocs.Viewer pro Java ve vašem projektu  
- **Převod DWG na PNG** s vlastními rozměry  
- **Nastavení barvy pozadí PNG** během vykreslování pro vylepšený vzhled  
- Reálné scénáře, kde vlastní vykreslování přináší hodnotu  

## Předpoklady

### Požadované knihovny a závislosti
- Java Development Kit (JDK) 8+  
- Maven pro správu závislostí  

### Požadavky na nastavení prostředí
- IDE jako IntelliJ IDEA nebo Eclipse  
- Základní znalost Javy  

### Předchozí znalosti
- Znalost práce se soubory v Javě  

## Nastavení GroupDocs.Viewer pro Java
Přidejte repozitář GroupDocs a závislost do vašeho Maven `pom.xml`:

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
Získejte dočasnou nebo plnou licenci k odstranění omezení evaluační verze.

### Základní inicializace a nastavení
Vytvořte instanci `Viewer`, která ukazuje na váš CAD soubor:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Průvodce implementací

### Funkce 1: Vykreslování CAD výkresů s vlastní velikostí obrázku a barvou pozadí

#### Přehled
Tato funkce vám umožní **převést DWG na PNG** při specifikaci šířky obrázku a odstínu pozadí.

#### Krok‑za‑krokem implementace

##### Import požadovaných balíčků
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Nastavte výstupní adresář a formát cesty souboru
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inicializujte Viewer s vlastními možnostmi vykreslování
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
- `PngViewOptions` – definuje výstupní formát a pojmenování.  
- `forRenderingByWidth(int width)` – nastavuje vlastní šířku obrázku.  
- `setBackgroundColor(Color color)` – **aplikuje vykreslení barvy pozadí** na PNG.

#### Tipy pro řešení problémů
- Ověřte, že výstupní složka existuje; pokud ne, vytvořte ji.  
- Zkontrolujte znovu cestu vstupního souboru a oprávnění.  

### Funkce 2: Nastavení barvy pozadí v možnostech vykreslování

#### Přehled
Zde se zaměřujeme na **nastavení barvy pozadí PNG** pro zlepšení vizuální konzistence.

#### Krok‑za‑krokem implementace

##### Import požadovaných balíčků
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Konfigurace možností vykreslování s barvou pozadí
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
- Upravte `forRenderingByWidth(int width)` pro různé rozměry.  
- Použijte libovolnou konstantu `Color` nebo vlastní `new Color(r,g,b)` pro zakázkové pozadí.  

## Praktické aplikace

### 1. Inženýrská dokumentace
Vlastní vykreslování zajišťuje, že inženýrské výkresy odpovídají firemním stylovým příručkám.

### 2. Architektonická vizualizace
Prezentujte plány s čistým pozadím, které odpovídá prezentacím.

### 3. Výroba prototypů
Generujte přesné PNG pro workflow rychlého prototypování.

### Možnosti integrace
Kombinujte tento vykreslovací řetězec s dokumentačními systémy pro automatizaci generování vizuálních aktiv.

## Úvahy o výkonu

### Optimalizace výkonu
- **Dávkové zpracování:** Vykreslete více CAD souborů ve smyčce.  
- **Správa zdrojů:** Nastavte velikost haldy JVM pro velké výkresy.

### Pokyny pro využití zdrojů
Sledujte CPU a paměť; uvolněte instance `Viewer` okamžitě.

### Nejlepší postupy pro správu paměti v Javě
- Používejte try‑with‑resources (jak je ukázáno) pro automatické uzavření `Viewer`.  
- Vyhněte se držení velkých objektů `Path` déle, než je potřeba.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Výstupní složka nenalezena** | Vytvořte složku předem nebo přidejte `Files.createDirectories(outputDirectory);` |
| **Prázdný obrázek** | Ujistěte se, že `cadOptions.setBackgroundColor` je nastaven po `forRenderingByWidth`. |
| **Chyby nedostatku paměti** | Zvyšte volbu JVM `-Xmx` nebo zpracovávejte soubory v menších dávkách. |

## Často kladené otázky

**Q: Můžete vykreslovat jiné CAD formáty kromě DWG?**  
A: Ano, GroupDocs.Viewer podporuje DXF, DWF a několik dalších typů CAD souborů.

**Q: Jak použít vlastní RGB barvu místo předdefinované konstanty?**  
A: Vytvořte novou instanci `Color`, např. `new Color(123, 45, 67)` a předávejte ji metodě `setBackgroundColor`.

**Q: Je možné vykreslit pouze konkrétní rozvržení nebo vrstvu?**  
A: Můžete specifikovat možnosti rozvržení nebo vrstvy pomocí `CadOptions` před voláním `viewer.view`.

**Q: Podporuje knihovna průhledná pozadí?**  
A: Nastavte barvu pozadí na `new Color(0,0,0,0)` pro plnou průhlednost, pokud cílový formát podporuje průhlednost.

**Q: Jaká verze GroupDocs.Viewer je vyžadována?**  
A: Tutoriál používá verzi 25.2, ale novější verze zachovávají stejné API.

## Závěr
Nyní víte **jak vykreslit CAD** výkresy do PNG souborů s vlastními rozměry a barvami pozadí pomocí GroupDocs.Viewer pro Java. Použijte tyto techniky k vytvoření profesionálně vypadajících vizuálních aktiv pro inženýrské, architektonické nebo výrobní workflow.

### Další kroky
- Experimentujte s různými šířkami obrázku a barvami.  
- Integrujte kód vykreslování do služby dávkového zpracování.  
- Prozkoumejte další možnosti Vieweru, jako je konverze do PDF nebo vícestránkové vykreslování.

---

**Poslední aktualizace:** 2026-01-08  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs