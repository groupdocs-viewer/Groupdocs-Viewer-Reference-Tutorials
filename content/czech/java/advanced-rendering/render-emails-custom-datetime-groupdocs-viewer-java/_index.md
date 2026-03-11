---
date: '2026-01-10'
description: Naučte se, jak převést EML na HTML s vlastním formátem data a času a
  nastavit posun časového pásma v Javě pomocí GroupDocs.Viewer. Ideální pro archivaci
  e‑mailů a podpůrné systémy.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Převod EML na HTML s vlastním datem a časem v Javě pomocí GroupDocs.Viewer
type: docs
url: /cs/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Převod EML na HTML s vlastním DateTime v Javě pomocí GroupDocs.Viewer

## Úvod

V dnešním rychle se rozvíjejícím digitálním světě je schopnost **převést EML na HTML** rychle a se správnou prezentací data‑času nezbytná pro archivaci, portály podpory a právní soulad. Tento tutoriál vás provede vykreslováním e‑mailových zpráv do HTML při aplikaci **vlastního formátu data‑času** a **posunu časového pásma** pomocí GroupDocs.Viewer pro Javu. Na konci budete mít znovupoužitelný řešení, které udržuje časové značky přesné a čitelné.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Co se naučíte**
- Jak nastavit GroupDocs.Viewer v Java projektu  
- Jak vykreslit e‑maily do HTML s vloženými zdroji  
- Jak **přizpůsobit formát data‑času** vašich e‑mailových zpráv (custom datetime format java)  
- Jak **nastavit posun časového pásma** pro správné časové značky (set timezone offset java)  

## Rychlé odpovědi
- **Může GroupDocs.Viewer převést EML na HTML?** Ano, přímo vykresluje soubory EML do HTML.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována placená licence.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo novější.  
- **Jak změním zobrazený formát data?** Použijte `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Mohu upravit časové pásmo?** Ano, pomocí `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## Co je „převod EML na HTML“?
Převod souboru EML na HTML transformuje surový e‑mail (včetně hlaviček, těla a příloh) do web‑přátelského formátu, který prohlížeče mohou zobrazit bez dalších pluginů. To usnadňuje vkládání e‑mailů do webových aplikací, archivů nebo řídicích panelů podpory.

## Proč použít GroupDocs.Viewer pro tento úkol?
- **Vykreslování bez závislostí** – není potřeba Outlook ani externí parsery e‑mailů.  
- **Vestavěná podpora pro vložené zdroje** (obrázky, přílohy).  
- **Detailní kontrola** nad formátováním data‑času a manipulací s časovým pásmem.  

## Požadavky

- **GroupDocs.Viewer pro Javu** verze 25.2 nebo novější.  
- **Java Development Kit (JDK)** 8+ a IDE (IntelliJ IDEA, Eclipse, atd.).  
- Základní znalost Javy a seznámení s Mavenem.

## Nastavení GroupDocs.Viewer pro Javu

### Maven konfigurace
Add the GroupDocs repository and dependency to your `pom.xml`:

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
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Převod EML na HTML s vlastním DateTime v Javě

Následující krok‑za‑krokem průvodce ukazuje, jak **převést EML na HTML** při aplikaci vlastního formátu data‑času a posunu časového pásma.

### Krok 1: Nastavení výstupního adresáře a cesty k souboru
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Vysvětlení:* `Path.of()` vytváří odkaz na složku, kde bude HTML uloženo. `resolve()` přidá název souboru.

### Krok 2: Inicializace Vieweru s e‑mailovým souborem
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Vysvětlení:* Instance `Viewer` ukazuje na soubor EML, který chcete převést.

### Krok 3: Konfigurace HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Vysvětlení:* `forEmbeddedResources()` zahrnuje obrázky a další zdroje přímo do výstupu HTML.

### Krok 4: Nastavení vlastního formátu DateTime *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Vysvětlení:* Tento vzor zobrazuje měsíc, den, rok, hodinu, minutu, označení AM/PM a posun časového pásma (`zzz`).

### Krok 5: Nastavení posunu časového pásma *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Vysvětlení:* Upravit vykreslené časové značky na požadované časové pásmo. Nahraďte `"GMT+1"` libovolným platným identifikátorem zóny.

### Krok 6: Vykreslení dokumentu
```java
viewer.view(options);
```
*Vysvětlení:* Provede převod a vytvoří HTML soubor s vašimi vlastními nastaveními data‑času.

## Tipy pro řešení problémů
- **FileNotFoundException:** Zkontrolujte znovu cesty použité v `Viewer` a `Path.of()`.  
- **Nesprávné časové značky:** Ověřte, že ID `TimeZone` odpovídá vaší cílové oblasti.  
- **Chybějící obrázky:** Ujistěte se, že jste použili `HtmlViewOptions.forEmbeddedResources()`; jinak externí zdroje nemusí být zahrnuty.  

## Praktické aplikace
1. **Archivace e‑mailů:** Ukládejte prohledávatelné HTML snímky e‑mailů pro soulad.  
2. **Portály zákaznické podpory:** Zobrazujte příchozí ticketů s přesnými místními časy.  
3. **Právní dokumentace:** Vytvářejte soudně připravené záznamy e‑mailů se standardizovanými časovými značkami.  

## Úvahy o výkonu
- Nasazujte na dedikovaný server pro hromadné převody.  
- Sledujte využití haldy Javy; zvýšte `-Xmx`, pokud narazíte na `OutOfMemoryError`.  
- Ukládejte vykreslené HTML do cache, když je stejný e‑mail požadován opakovaně.  

## Závěr
Nyní máte kompletní, připravenou metodu pro **převod EML na HTML** s vlastním formátem data‑času a posunem časového pásma pomocí GroupDocs.Viewer pro Javu. To zvyšuje čitelnost, zajišťuje přesnost časových značek a hladce zapadá do archivních nebo podporných pracovních postupů.

**Další kroky:** Prozkoumejte další možnosti Vieweru, jako je stylování CSS, stránkování nebo převod do PDF, abyste výstup ještě lépe přizpůsobili svým potřebám.

## Často kladené otázky

**Q: Jak zacházet se soubory EML s přílohami?**  
A: Přílohy jsou automaticky vloženy, když použijete `HtmlViewOptions.forEmbeddedResources()`. V případě potřeby je můžete také extrahovat pomocí Viewer API.

**Q: Mohu změnit HTML šablonu nebo přidat vlastní CSS?**  
A: Ano, po vykreslení můžete upravit vygenerovaný HTML soubor nebo programově vložit CSS před uložením.

**Q: Je možné vykreslit více souborů EML najednou (batch)?**  
A: Zabalte logiku vykreslování do smyčky a pro každý soubor použijte stejnou instanci `HtmlViewOptions`.

**Q: Co když potřebuji podporovat jiné formáty e‑mailů, jako je MSG?**  
A: GroupDocs.Viewer také podporuje MSG, PST a další e‑mailové kontejnery – stačí změnit příponu souboru v konstruktoru `Viewer`.

**Q: Potřebuji samostatnou licenci pro každý server?**  
A: Licence je na nasazení; pro scénáře s více servery se podívejte do licenčního průvodce GroupDocs.

## Zdroje

- [Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [API reference](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout](https://releases.groupdocs.com/viewer/java/)
- [Koupit](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/java/)
- [Dočasná licence](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-01-10  
**Testováno s:** GroupDocs.Viewer 25.2 (Java)  
**Autor:** GroupDocs