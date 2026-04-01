---
date: '2026-04-01'
description: Naučte se, jak rozdělit CAD výkresy na dlaždice pomocí GroupDocs Viewer
  pro Javu, čímž zvýšíte výkon vykreslování a zjednodušíte práci s velkými soubory.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Jak rozdělit CAD výkresy na dlaždice pomocí GroupDocs Viewer
type: docs
url: /cs/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Jak rozdělit CAD výkresy na dlaždice pomocí GroupDocs Viewer

Pokud se zajímáte **jak rozdělit CAD** soubory na menší, lépe ovladatelné části, jste na správném místě. V tomto tutoriálu projdeme přesně kroky potřebné k rozdělení velkých CAD výkresů na dlaždice pomocí **GroupDocs Viewer for Java**. Na konci budete mít připravené řešení, které zvyšuje rychlost vykreslování, snižuje spotřebu paměti a usnadňuje zobrazování výkresů ve webových nebo mobilních aplikacích.

![Rozdělení CAD výkresů pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Rychlé odpovědi
- **Co dosahuje „rozdělení CAD“?** Rozděluje obrovský výkres na menší obrázky (dlaždice), které se načítají rychleji a spotřebovávají méně paměti.  
- **Jaký formát se používá pro dlaždice?** Ve výchozím nastavení se generují soubory PNG, ale jiné formáty jsou podporovány pomocí možností Vieweru.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; placená licence je vyžadována pro produkci.  
- **Mohu změnit velikost dlaždice?** Ano – upravte výpočty `tileWidth` a `tileHeight` podle svých potřeb.  
- **Je tento přístup thread‑safe?** Vykreslování každé dlaždice ve vlastní instanci `Viewer` s try‑with‑resources je bezpečné pro souběžné provádění.

## Co je „rozdělení CAD“?
Rozdělení CAD označuje rozdělení jednoho, často obrovského, CAD výkresu na více obdélníkových částí (dlaždic). Každá dlaždice je vykreslena nezávisle, což umožňuje načíst pouze ty části, které uživatel skutečně potřebuje — ideální pro webové mapy, dokumentové portály a mobilní prohlížeče.

## Proč používat GroupDocs Viewer pro Java?
GroupDocs Viewer poskytuje okamžitou podporu pro více než 100 formátů souborů, včetně DWG, DXF a DWF. Jeho tile API vám umožňuje zadat přesné souřadnice, takže můžete vykreslit přesně oblast, o kterou máte zájem, aniž byste nejprve zpracovávali celý soubor. To šetří cykly CPU, snižuje šířku pásma a poskytuje plynulejší uživatelský zážitek.

## Požadavky
- **Knihovny**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Jakýkoli recentní Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse nebo jiné Java‑kompatibilní IDE.  
- **Nástroj pro sestavení**: Maven (ostatní nástroje fungují, pokud je přidána závislost).  

## Nastavení GroupDocs.Viewer pro Java
Přidejte repozitář GroupDocs a závislost do vašeho `pom.xml`:

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
GroupDocs Viewer nabízí bezplatnou zkušební licenci pro hodnocení:

- **Bezplatná zkušební verze**: Navštivte [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) a stáhněte knihovnu.  
- **Dočasná licence**: Požádejte na [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Plná licence**: Zakupte produkční licenci na [Purchase Page](https://purchase.groupdocs.com/buy).

### Základní inicializace
Vytvořte jednoduchou instanci `Viewer`, abyste ověřili, že se knihovna načte správně:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Průvodce krok za krokem k rozdělení CAD výkresů na dlaždice

### Krok 1: Definujte výstupní adresář
Uložíme každou dlaždici jako samostatný PNG soubor. Použití pomocné metody udržuje logiku cesty čistou a znovupoužitelnou.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Krok 2: Nakonfigurujte možnosti zobrazení
Nastavte formát vykreslování na PNG a řekněte prohlížeči, aby nepřednačítal každou stránku (což šetří paměť).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Krok 3: Vypočítejte rozměry dlaždic
Nejprve získáme původní šířku a výšku výkresu, poté jej rozdělíme na čtyři stejné kvadranty.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Krok 4: Vykreslete a uložte dlaždice
Přidejte vypočítané dlaždice do možností vykreslování a nechte `Viewer` vygenerovat PNG soubory.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Tipy pro řešení problémů
- **Cesta sestavení** – Ujistěte se, že soubory GroupDocs JAR jsou na classpath.  
- **Oprávnění** – Výstupní složka musí být zapisovatelná procesem Java.  
- **Výjimky** – Pokud vidíte `ViewerException`, zkontrolujte, že soubor DWG není poškozený a že je použita správná licence.

## Běžné případy použití pro rozdělení CAD dlaždic
1. **Webové mapování** – Načíst pouze viditelnou část půdorysu, když uživatel posouvá/zoomuje.  
2. **Správa dokumentů** – Ukládat každou dlaždici samostatně pro rychlejší generování náhledů.  
3. **Mobilní prohlížení** – Snížit šířku pásma stažením pouze těch dlaždic, které jsou potřeba pro aktuální obrazovku.

## Úvahy o výkonu
- **Velikost dlaždice** – Větší dlaždice znamenají méně souborů, ale pomalejší vykreslování; najděte rovnováhu podle potřeb UI.  
- **Monitorování paměti** – Použijte nástroje pro profilování Java (např. VisualVM) ke sledování využití haldy při zpracování velmi velkých výkresů.  
- **Uklízení zdrojů** – Vzor try‑with‑resources uvedený výše automaticky uvolňuje nativní zdroje.

## Často kladené otázky

**Q: Mohu rozdělit i jiné typy souborů (PDF, obrázky) na dlaždice pomocí stejného přístupu?**  
A: Ano. GroupDocs Viewer podporuje mnoho formátů; stačí použít odpovídající třídu možností (např. `PdfViewOptions`).

**Q: Jak změním kvalitu výstupního obrázku?**  
A: Upravit `viewOptions.setResolution(int dpi)` nebo nastavit kompresní parametry na objektu `PngOptions`.

**Q: Moje aplikace končí nedostatkem paměti u velmi velkých DWG souborů — co mohu udělat?**  
A: Snižte rozměry dlaždic, zvětšete haldu JVM (`-Xmx`) nebo vykreslujte dlaždice sekvenčně v samostatných instancích `Viewer`.

**Q: Je možné vykreslovat dlaždice asynchronně?**  
A: Rozhodně. Zabalte každý volání vykreslení dlaždice do `CompletableFuture` nebo použijte executor service k paralelizaci úlohy.

**Q: Potřebuji samostatnou licenci pro každou dlaždici?**  
A: Ne. Jedna platná licence GroupDocs Viewer pokrývá všechny operace vykreslování ve vaší aplikaci.

## Zdroje
- [Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [Reference API](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Zakoupit licenci](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/java/)
- [Dočasná licence](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-04-01  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

---