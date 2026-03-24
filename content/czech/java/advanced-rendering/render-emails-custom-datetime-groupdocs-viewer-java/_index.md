---
date: '2026-03-24'
description: Naučte se, jak převést EML na HTML s vlastním formátem data a času a
  nastavit posun časového pásma v Javě pomocí GroupDocs.Viewer. Ideální pro archivaci
  e‑mailů a podpůrné systémy.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Převod EML na HTML s vlastním datumem a časem v Javě pomocí GroupDocs.Viewer
type: docs
url: /cs/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Převod EML na HTML s vlastním DateTime v Javě pomocí GroupDocs.Viewer

V dnešním rychle se rozvíjejícím digitálním světě je schopnost **převést EML na HTML** rychle a se správným zobrazením data‑času nezbytná pro archivaci, portály podpory a právní soulad. Tento tutoriál vás provede vykreslováním e‑mailových zpráv do HTML při aplikaci **vlastního formátu data‑času** a **posunu časového pásma** pomocí GroupDocs.Viewer pro Javu. Na konci budete mít znovupoužitelný řešení, které udržuje časové značky přesné a čitelné, ideální pro jakýkoli **email to HTML Java** workflow.

![Vykreslení e‑mailů s vlastním DateTime pomocí GroupDocs.Viewer pro Javu](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Co se naučíte**
- Jak nastavit GroupDocs.Viewer v Java projektu  
- Jak vykreslit e‑maily do HTML s vloženými zdroji  
- Jak **přizpůsobit formát data‑času** vašich e‑mailových zpráv (custom datetime java)  
- Jak **nastavit posun časového pásma** pro správné časové značky (timezone offset java)  

## Quick Answers
- **Může GroupDocs.Viewer převést EML na HTML?** Ano, přímo vykresluje soubory EML do HTML.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována placená licence.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo novější.  
- **Jak změním zobrazený formát data?** Použijte `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Mohu upravit časové pásmo?** Ano, pomocí `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.  

## Co je “convert EML to HTML”?
Převod souboru EML na HTML transformuje surový e‑mail (včetně hlaviček, těla a příloh) do web‑přátelského formátu, který prohlížeče mohou zobrazit bez dalších pluginů. To usnadňuje vkládání e‑mailů do webových aplikací, archivů nebo řídicích panelů podpory.

## Why Use GroupDocs.Viewer for This Task?
- **Vykreslování bez závislostí** – není potřeba Outlook ani externí mailové parsery.  
- **Vestavěná podpora pro vložené zdroje** (obrázky, přílohy).  
- **Detailní kontrola** nad formátováním data‑času a manipulací s časovým pásmem.  

## Prerequisites
- **GroupDocs.Viewer pro Javu** verze 25.2 nebo novější.  
- **Java Development Kit (JDK)** 8+ a IDE (IntelliJ IDEA, Eclipse, atd.).  
- Základní znalost Javy a zkušenost s Mavenem.

## Setting Up GroupDocs.Viewer for Java

### Maven Configuration
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

### License Acquisition
Start with a free trial or request a temporary license for extended testing. Purchase a full license for production use.

### Basic Initialization
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Convert EML to HTML with Custom DateTime in Java

The following step‑by‑step guide shows how to **convert EML to HTML** while applying a custom datetime format and timezone offset.

### Step 1: Set Up Output Directory and File Path
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Vysvětlení:* `Path.of()` vytvoří odkaz na složku, kde bude HTML uloženo. `resolve()` přidá název souboru.

### Step 2: Initialize Viewer with Email File
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Vysvětlení:* Instance `Viewer` ukazuje na soubor EML, který chcete převést.

### Step 3: Configure HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Vysvětlení:* `forEmbeddedResources()` zahrnuje obrázky a další zdroje přímo do výstupního HTML.

### Step 4: Set Custom DateTime Format *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Vysvětlení:* Tento vzor zobrazuje měsíc, den, rok, hodinu, minutu, AM/PM značku a posun časového pásma (`zzz`).

### Step 5: Set TimeZone Offset *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Vysvětlení:* Upravit vykreslené časové značky na požadované časové pásmo. Nahraďte `"GMT+1"` libovolným platným identifikátorem zóny.

### How to Adjust Email Timezone in Java
Pokud potřebujete **upravit časové pásmo e‑mailu** nad rámec jednoduchých posunů – například při změnách letního času – můžete získat odpovídající objekt `TimeZone` z API `java.util.TimeZone` pomocí regionálních ID jako `"Europe/Paris"` nebo `"America/New_York"` a předat jej metodě `setTimeZoneOffset`. To zajistí, že časové značky e‑mailu vždy odrážejí správný místní čas.

### Step 6: Render Document
```java
viewer.view(options);
```
*Vysvětlení:* Spustí převod a vytvoří HTML soubor s vašimi nastaveními vlastního data‑času.

## Troubleshooting Tips
- **FileNotFoundException:** Zkontrolujte cesty použité v `Viewer` a `Path.of()`.  
- **Nesprávné časové značky:** Ověřte, že ID `TimeZone` odpovídá vaší cílové oblasti.  
- **Chybějící obrázky:** Ujistěte se, že jste použili `HtmlViewOptions.forEmbeddedResources()`; jinak nemusí být zahrnuty externí zdroje.  

## Practical Applications
1. **Archivace e‑mailů:** Ukládejte prohledávatelné HTML snímky e‑mailů pro soulad.  
2. **Portály zákaznické podpory:** Zobrazte příchozí tikety s přesnými místními časy.  
3. **Právní dokumentace:** Vytvořte soudně připravené záznamy e‑mailů se standardizovanými časovými značkami.  

## Performance Considerations
- Nasazujte na dedikovaný server pro hromadné převody.  
- Sledujte využití haldy Javy; zvýšte `-Xmx`, pokud narazíte na `OutOfMemoryError`.  
- Ukládejte vykreslené HTML do cache, pokud je stejný e‑mail požadován opakovaně.  

## Conclusion
Nyní máte kompletní, připravenou metodu pro **převod EML na HTML** s vlastním formátem data‑času a posunem časového pásma pomocí GroupDocs.Viewer pro Javu. To zvyšuje čitelnost, zajišťuje přesnost časových značek a hladce zapadá do archivních nebo podporných pracovních postupů.

**Další kroky:** Prozkoumejte další možnosti Vieweru, jako je stylování CSS, stránkování nebo převod do PDF, abyste výstup dále přizpůsobili svým potřebám.

## Frequently Asked Questions

**Q: Jak zacházím se soubory EML s přílohami?**  
A: Přílohy jsou automaticky vloženy, když použijete `HtmlViewOptions.forEmbeddedResources()`. V případě potřeby je můžete také extrahovat pomocí Viewer API.

**Q: Mohu změnit HTML šablonu nebo přidat vlastní CSS?**  
A: Ano, po vykreslení můžete upravit vygenerovaný HTML soubor nebo programově vložit CSS před uložením.

**Q: Je možné vykreslit více souborů EML najednou?**  
A: Zabalte logiku vykreslování do smyčky a pro každý soubor znovu použijte stejnou instanci `HtmlViewOptions`.

**Q: Co když potřebuji podporovat jiné formáty e‑mailů, jako je MSG?**  
A: GroupDocs.Viewer také podporuje MSG, PST a další e‑mailové kontejnery – stačí změnit příponu souboru v konstruktoru `Viewer`.

**Q: Potřebuji samostatnou licenci pro každý server?**  
A: Licence je na nasazení; konzultujte průvodce licencováním GroupDocs pro scénáře s více servery.

## Resources

- [Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout](https://releases.groupdocs.com/viewer/java/)
- [Koupit](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/java/)
- [Dočasná licence](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-03-24  
**Testováno s:** GroupDocs.Viewer 25.2 (Java)  
**Autor:** GroupDocs