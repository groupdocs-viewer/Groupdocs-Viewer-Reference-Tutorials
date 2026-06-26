---
date: '2026-03-16'
description: Naučte se, jak převést DWG na PNG s vlastní velikostí a barvou pozadí
  pomocí GroupDocs.Viewer pro Javu.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Jak převést DWG na PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer
  pro Javu
type: docs
url: /cs/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Jak převést DWG na PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer pro Java

Pokud hledáte **convert DWG to PNG** a chcete mít plnou kontrolu nad rozměry obrázku a stylem pozadí, jste na správném místě. V tomto tutoriálu vás provedeme vykreslováním CAD souborů jako PNG, přizpůsobením šířky a změnou barvy pozadí, aby výstup odpovídal vašim požadavkům na zprávu, prezentaci nebo web‑preview.

## Rychlé odpovědi
- **Co znamená „convert DWG to PNG“?** Jedná se o proces převodu souboru DWG CAD na PNG obrázek pomocí kódu.  
- **Mohu nastavit vlastní šířku?** Ano – použijte `CadOptions.forRenderingByWidth(int width)`.  
- **Jak změním barvu pozadí?** Zavolejte `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Která knihovna je vyžadována?** GroupDocs.Viewer for Java (verze 25.2 nebo novější).  
- **Potřebuji licenci?** Dočasná nebo zakoupená licence odstraňuje omezení hodnocení.

![Vykreslit CAD výkresy jako PNG s vlastní velikostí a barvou pozadí pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Jak převést DWG na PNG – Přehled
V této sekci rozvedeme hlavní cíl: **how to convert DWG to PNG** při řízení velikosti a pozadí. Uvidíte kompletní nastavení, přesný kód, který potřebujete, a praktické tipy, jak se vyhnout běžným úskalím.

## Co se naučíte
- Nastavení GroupDocs.Viewer pro Java v Maven projektu  
- **Convert DWG to PNG** s vlastními rozměry  
- **Change CAD background color** během vykreslování pro vylepšený vzhled  
- Reálné scénáře, kde vlastní vykreslování přináší hodnotu  

## Předpoklady

### Požadované knihovny a závislosti
- Java Development Kit (JDK) 8+  
- Maven pro správu závislostí  

### Požadavky na nastavení prostředí
- IDE jako IntelliJ IDEA nebo Eclipse  
- Základní znalosti Javy  

### Předpoklady znalostí
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
Získejte dočasnou nebo plnou licenci k odstranění omezení hodnocení.

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

## Funkce 1: Vykreslování CAD výkresů s vlastní velikostí obrázku a barvou pozadí

### Jak změnit barvu pozadí CAD
Tato funkce vám umožní **convert DWG to PNG** při specifikaci vlastní šířky a aplikaci nového odstínu pozadí.

#### Implementace krok za krokem

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
- `setBackgroundColor(Color color)` – **set PNG background color** pro zlepšení vizuální konzistence.

#### Tipy pro řešení problémů
- Ověřte, že výstupní složka existuje; pokud ne, vytvořte ji.  
- Zkontrolujte znovu vstupní cestu k souboru a oprávnění.  

## Funkce 2: Nastavení barvy pozadí v možnostech vykreslování

### Jak nastavit barvu pozadí PNG
Zde se zaměříme na možnost **set background color PNG**, aby každá vykreslená obrázek odpovídal vaší firemní paletě.

#### Implementace krok za krokem

##### Import požadovaných balíčků
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Nakonfigurujte možnosti vykreslování s barvou pozadí
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
Vlastní vykreslování zajišťuje, že inženýrské výkresy splňují firemní stylové směrnice.

### 2. Architektonická vizualizace
Prezentujte plány s čistým pozadím, které ladí s prezentacemi.

### 3. Výroba prototypů
Vytvořte přesné PNG pro workflow rychlého prototypování.

### Možnosti integrace
Kombinujte tento vykreslovací pipeline s dokumentovými systémy pro automatizaci generování vizuálních aktiv.

## Úvahy o výkonu

### Optimalizace výkonu
- **Batch Processing:** Vykreslete více CAD souborů ve smyčce.  
- **Resource Management:** Nastavte velikost haldy JVM pro velké výkresy.

### Pokyny pro využití zdrojů
Sledujte CPU a paměť; uvolněte instance `Viewer` okamžitě.

### Nejlepší postupy pro správu paměti v Javě
- Používejte try‑with‑resources (jak je ukázáno) k automatickému uzavření `Viewer`.  
- Vyhněte se dlouhodobému držení velkých objektů `Path`.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Výstupní složka nenalezena** | Vytvořte adresář předem nebo přidejte `Files.createDirectories(outputDirectory);` |
| **Prázdný obrázek** | Ujistěte se, že `cadOptions.setBackgroundColor` je nastaven po `forRenderingByWidth`. |
| **Chyby nedostatku paměti** | Zvyšte volbu JVM `-Xmx` nebo zpracovávejte soubory v menších dávkách. |

## Často kladené otázky

**Q: Můžu vykreslovat jiné CAD formáty kromě DWG?**  
A: Ano, GroupDocs.Viewer podporuje DXF, DWF a několik dalších typů CAD souborů.

**Q: Jak použít vlastní RGB barvu místo předdefinované konstanty?**  
A: Vytvořte novou instanci `Color`, např. `new Color(123, 45, 67)` a předávejte ji do `setBackgroundColor`.

**Q: Je možné vykreslit jen konkrétní rozvržení nebo vrstvu?**  
A: Můžete specifikovat možnosti rozvržení nebo vrstvy pomocí `CadOptions` před voláním `viewer.view`.

**Q: Podporuje knihovna transparentní pozadí?**  
A: Nastavte barvu pozadí na `new Color(0,0,0,0)` pro plnou transparentnost, pokud cílový formát podporuje.

**Q: Jaká verze GroupDocs.Viewer je vyžadována?**  
A: Tutoriál používá verzi 25.2, ale novější verze zachovávají stejné API.

---

**Poslední aktualizace:** 2026-03-16  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs