---
date: '2026-02-21'
description: Naučte se, jak nastavit maximální počet položek na složku při vykreslování
  souborů Outlook pomocí GroupDocs.Viewer pro Javu, což zlepšuje výkon u velkých souborů
  PST/OST.
keywords:
- GroupDocs.Viewer Java
- Outlook item rendering
- PST file rendering
title: Jak nastavit maximální počet položek na složku při vykreslování Outlooku pomocí
  GroupDocs.Viewer pro Java
type: docs
url: /cs/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Omezení vykreslování položek Outlook v Javě pomocí GroupDocs.Viewer

Správa obrovských souborů s daty Outlook (PST nebo OST) může rychle představovat úzké hrdlo výkonu. V tomto průvodci se dozvíte, jak **nastavit maximální počet položek** na složku při vykreslování pomocí GroupDocs.Viewer pro Java, abyste zpracovávali pouze data, která skutečně potřebujete. Použitím techniky **omezení položek na složku** zůstane vaše aplikace responzivní i při gigabajtech e‑mailových dat.

![Omezení vykreslování položek Outlook pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Co se naučíte
- Nastavení GroupDocs.Viewer pro Java  
- Konfigurace knihovny pro **nastavení maximálního počtu položek** na složku v souborech Outlook  
- Reálné scénáře, kde omezení položek na složku zvyšuje rychlost a snižuje využití paměti  

## Rychlé odpovědi
- **Co dělá “nastavit maximální počet položek na složku”?** Omezuje vykreslování na definovaný počet e‑mailových položek v každé složce Outlook.  
- **Proč omezovat položky Outlook?** Snížit dobu zpracování a spotřebu paměti u velkých poštovních schránek.  
- **Která verze tuto funkci podporuje?** GroupDocs.Viewer 25.2 a novější.  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována zkušební nebo zakoupená licence.  
- **Mohu limit změnit za běhu?** Ano – stačí upravit hodnotu `setMaxItemsInFolder` před vykreslením.  

## Jak nastavit maximální počet položek na složku při vykreslování Outlook
Níže najdete podrobný návod, který vysvětluje **proč** byste mohli chtít omezit položky Outlook, **co** nastavení dělá a **jak** jej nakonfigurovat ve vašem Java projektu.

### Co je “nastavit maximální počet položek na složku”?
Možnost **set max items** říká prohlížeči, aby zastavil po vykreslení konkrétního počtu položek v každé složce. To je zvláště užitečné, když potřebujete pouze náhled nedávných e‑mailů nebo když generujete zprávy, které nevyžadují celou poštovní schránku.

### Proč použít přístup omezení položek na složku?
- **Výkon:** Rychlejší doby vykreslování a nižší využití CPU.  
- **Škálovatelnost:** Zpracovávejte větší poštovní schránky bez vyčerpání paměti JVM.  
- **Flexibilita:** Přizpůsobte limit podle preferencí uživatele nebo schopností zařízení.  

## Požadavky
Ujistěte se, že máte před zahájením následující:

### Požadované knihovny a závislosti
1. **Java Development Kit (JDK)** – Nainstalujte JDK 8 nebo novější.  
2. **GroupDocs.Viewer for Java** – Přidejte jako závislost do svého projektu.

### Požadavky na nastavení prostředí
- Vhodné IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.  
- Maven nainstalovaný, pokud spravujete závislosti pomocí něj.

### Předpoklady znalostí
- Základní pochopení programování v Javě a práce se soubory.  
- Znalost Maven projektů je výhodná, ale není vyžadována.

## Nastavení GroupDocs.Viewer pro Java
Nastavte GroupDocs.Viewer ve svém projektu pomocí Maven:

**Konfigurace Maven:**
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

### Kroky získání licence
- **Free Trial**: Stáhněte si bezplatnou zkušební verzi z [GroupDocs](https://releases.groupdocs.com/viewer/java/) a prozkoumejte funkce knihovny.  
- **Temporary License**: Získejte dočasnou licenci pro plný přístup bez omezení hodnocení na [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase**: Pro dlouhodobé používání zvažte zakoupení licence na [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Základní inicializace a nastavení
Po nakonfigurování Maven inicializujte GroupDocs.Viewer ve své Java aplikaci nastavením objektu viewer. To vám umožní načíst a vykreslit dokumenty.

## Průvodce implementací

### Omezení vykreslovaných položek ze souborů Outlook
Tato sekce podrobně popisuje, jak omezit vykreslované položky ze souborů s daty Outlook pomocí GroupDocs.Viewer pro Java.

#### Přehled
Konfigurací konkrétních možností můžete omezit vykreslování na určitý počet položek na složku. Tato funkce zvyšuje výkon a efektivitu při práci s velkými soubory e‑mailů.

**Krok 1: Nastavení cesty výstupního adresáře**
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```
Tento kód nastaví adresář, kde budou uloženy vykreslené HTML soubory. Nahraďte `"LimitCountOfItemsToRender"` požadovaným názvem cesty.

**Krok 2: Definice formátu cesty souboru pro HTML stránky**
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
Vytvořte jednotný formát pojmenování HTML stránek generovaných během vykreslování, což usnadní přístup a správu.

**Krok 3: Konfigurace HtmlViewOptions s vloženými zdroji**
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
Tato možnost určuje, jak jsou dokumenty vykreslovány s vloženými zdroji, což umožňuje lepší integraci obrázků a stylů.

**Krok 4: Nastavení Outlook možností pro omezení položek na složku**
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```
Zde **nastavujeme maximální počet položek** na tři. Přizpůsobte číslo podle vašich požadavků pro scénář **limit items per folder**.

**Krok 5: Načtení a vykreslení dokumentu**
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```
Použijte třídu `Viewer` k načtení souboru OST a jeho vykreslení podle definovaných možností zobrazení. Příkaz try‑with‑resources zajišťuje, že zdroje jsou po použití řádně uzavřeny.

### Tipy pro řešení problémů
- Ujistěte se, že všechny cesty a adresáře existují před spuštěním kódu.  
- Ověřte, že závislosti GroupDocs.Viewer jsou Mavenem správně vyřešeny.  
- Zkontrolujte případné výjimky během vykreslování, které mohou naznačovat problémy s formáty souborů nebo oprávněními.

## Praktické aplikace
1. **Email Archiving** – Omezení vykreslování položek je ideální pro aplikace zaměřené na archivaci konkrétních e‑mailů místo celých datových sad.  
2. **Data Migration** – Při migraci dat mezi systémy vykreslete pouze potřebné položky pro optimalizaci výkonu a snížení doby zpracování.  
3. **Custom Reporting** – Generujte zprávy výběrem požadovaného e‑mailového obsahu bez načítání celých složek.

## Úvahy o výkonu
### Tipy pro optimalizaci výkonu
- Omezte počet položek na složku pro snížení využití paměti.  
- Efektivně používejte vložené zdroje, aby se předešlo dalším síťovým voláním během vykreslování.

### Pokyny pro využití zdrojů
- Sledujte paměť JVM a upravujte nastavení podle velikosti zpracovávaných souborů Outlook.

### Nejlepší postupy pro správu paměti v Javě
- Využívejte try‑with‑resources pro automatickou správu zdrojů.  
- Profilujte aplikaci, abyste identifikovali úzká místa související se zpracováním velkých souborů.

## Běžné úskalí a jak se jim vyhnout
| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Žádné výstupní soubory nebyly vytvořeny | Cesta výstupního adresáře je nesprávná nebo chybí oprávnění | Ověřte, že `outputDirectory` existuje a je zapisovatelný |
| Vykreslování se zastaví po několika položkách | `setMaxItemsInFolder` nastaven příliš nízko | Zvyšte limit nebo jej učinte konfigurovatelným |
| OutOfMemoryError u velkého PST | Výchozí nastavení paměti nedostatečné | Zvyšte haldu JVM (`-Xmx`) a udržujte limit nízký |

## Závěr
V tomto tutoriálu jste se naučili, jak **nastavit maximální počet položek na složku** v souborech Outlook pomocí GroupDocs.Viewer pro Java. Dodržením kroků a použitím tipů pro výkon můžete vytvořit efektivní aplikace přizpůsobené vašim konkrétním potřebám.

### Další kroky
- Prozkoumejte další funkce GroupDocs.Viewer v [oficiální dokumentaci](https://docs.groupdocs.com/viewer/java/).  
- Experimentujte s různými možnostmi vykreslování, abyste našli nejlepší nastavení pro požadavky vaší aplikace.

Jste připraveni to vyzkoušet? Začněte dnes implementovat toto řešení ve svých projektech a osobně zažijte zvýšenou efektivitu.

## Často kladené otázky

**Q: K čemu se používá GroupDocs.Viewer Java?**  
A: Jedná se o univerzální knihovnu určenou k vykreslování různých formátů dokumentů, včetně souborů s daty Outlook, do HTML nebo obrazových formátů.

**Q: Jak získám bezplatnou zkušební verzi GroupDocs.Viewer?**  
A: Navštivte [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) pro přístup a možnosti stažení.

**Q: Mohu omezit vykreslování položek i v souborech PST?**  
A: Ano, stejná konfigurace platí pro formáty OST i PST.

**Q: Co mám dělat, když je moje aplikace během vykreslování pomalá?**  
A: Přezkoumejte limity položek a nastavení zdrojů; zvažte optimalizaci postupů správy paměti.

**Q: Kde mohu najít podporu pro problémy s GroupDocs.Viewer?**  
A: Pro pomoc navštivte [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).

## Další zdroje
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout GroupDocs.Viewer pro Java](https://releases.groupdocs.com/viewer/java/)
- [Koupit licenci](https://purchase.groupdocs.com/buy)
- [Verze Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Žádost o dočasnou licenci](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory](https://forum.groupdocs.com/c/viewer/9)

**Poslední aktualizace:** 2026-02-21  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs