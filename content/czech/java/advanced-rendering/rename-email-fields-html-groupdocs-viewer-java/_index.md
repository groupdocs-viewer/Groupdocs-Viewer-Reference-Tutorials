---
date: '2026-03-24'
description: Naučte se, jak převést e‑mail na HTML a přejmenovat pole e‑mailu pomocí
  GroupDocs Viewer pro Javu. Tento průvodce ukazuje, jak vykreslit e‑mail jako HTML
  s vlastními hlavičkami.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Převést e‑mail na HTML a přejmenovat pole – GroupDocs Viewer Java
type: docs
url: /cs/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Převod e‑mailu na HTML a přejmenování polí – GroupDocs Viewer Java

Pokud potřebujete **převést e‑mail na HTML** a zároveň dát hlavičkám e‑mailu vlastní vzhled, jste na správném místě. V tomto tutoriálu projdeme přesně kroky, jak přejmenovat pole e‑mailu, **převést e‑mail na HTML** a přizpůsobit hlavičky e‑mailu pomocí GroupDocs.Viewer pro Java. Na konci budete mít čistou HTML reprezentaci s názvy hlaviček, které preferujete, což usnadní čtení výstupu a jeho integraci do vašich aplikací.

![Přejmenování polí e‑mailu při převodu e‑mailů na HTML pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Co se naučíte
- Jak použít GroupDocs.Viewer pro Java k **převodu e‑mailu na HTML**.  
- Techniky k **přejmenování polí e‑mailu** jako jsou „From“, „To“, „Sent“ a „Subject“.  
- Nejlepší postupy pro nastavení Maven a licencování.  
- Reálné scénáře, kde **přizpůsobení hlaviček e‑mailu** přináší hodnotu.

## Rychlé odpovědi
- **Co znamená “převést e‑mail na HTML”?** Znamená to vykreslení souboru e‑mailu (MSG/EML) jako web‑připraveného HTML dokumentu.  
- **Která knihovna provádí převod?** GroupDocs.Viewer pro Java (v25.2+).  
- **Potřebuji licenci?** Zkušební verze funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Mohu změnit libovolný název hlavičky?** Ano, jakákoli standardní hlavička e‑mailu může být přemapována pomocí `fieldTextMap`.  
- **Je výstup HTML nebo vložené zdroje?** Můžete zvolit vložené zdroje pro jeden samostatný soubor.

## Co znamená “převést e‑mail na HTML” v kontextu GroupDocs.Viewer?
Převod e‑mailu na HTML znamená vzít surový soubor e‑mailu a vytvořit HTML stránku, která zobrazuje tělo zprávy spolu s jejími metadaty. Když také **přejmenujete pole e‑mailu**, výchozí štítky (např. „From“) jsou nahrazeny vlastním textem (např. „Sender“), což vám pomůže sladit terminologii společnosti nebo zlepšit konzistenci uživatelského rozhraní.

## Proč převádět e‑mail na HTML a přejmenovávat pole e‑mailu?
- **Konzistentní branding:** Přizpůsobte výstup jazyku vaší organizace.  
- **Zlepšená vyhledatelnost:** Vlastní hlavičky mohou být efektivněji indexovány v archivních systémech.  
- **Lepší integrace UI:** Přizpůsobte HTML úryvek tak, aby se bez problémů začlenil do webových portálů nebo řídicích panelů podpory.

## Požadavky

### Požadované knihovny, verze a závislosti
- **GroupDocs.Viewer pro Java** – verze 25.2 nebo novější.  
- **Java Development Kit (JDK)** – verze 8+.

### Požadavky na nastavení prostředí
- **Maven** pro správu závislostí.  
- IDE jako IntelliJ IDEA, Eclipse nebo VS Code.

### Předpoklady znalostí
Základní znalost Javy a Maven vám pomůže rychle sledovat postup.

## Nastavení GroupDocs.Viewer pro Java

### Maven konfigurace
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
- **Free Trial:** Stáhněte si bezplatnou zkušební verzi z [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** Získejte dočasnou licenci pro prozkoumání všech funkcí bez omezení na [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** Pro dlouhodobé používání zvažte zakoupení licence přes [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Základní inicializace a nastavení
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Upravte cestu k souboru tak, aby ukazovala na váš soubor `.msg`.

## Jak převést e‑mail na HTML a přejmenovat pole – krok za krokem

### 1. Nastavte cestu výstupního adresáře
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Nahraďte `"YOUR_OUTPUT_DIRECTORY"` složkou, kam chcete ukládat HTML soubory.*

### 2. Definujte formát cesty souboru stránky
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` bude během vykreslování nahrazeno číslem stránky.*

### 3. Vytvořte mapování polí e‑mailu na nové názvy
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Zde měníme výchozí štítky na vlastní.*

### 4. Nakonfigurujte HTML View Options
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` zahrnuje CSS/JS do HTML, zatímco `setFieldTextMap` aplikuje vlastní názvy hlaviček.*

### 5. Vykreslete e‑mail do HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Nahraďte `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` skutečnou cestou k vašemu souboru MSG.*

#### Tipy pro řešení problémů
- Ověřte, že výstupní adresář je zapisovatelný.  
- Ujistěte se, že vstupní soubor MSG existuje a cesta je správná.  
- Použijte stejnou verzi GroupDocs.Viewer (25.2) jako je deklarována v Maven.

## Praktické aplikace
1. **Vlastní e‑mailové zprávy:** Přizpůsobte hlavičky e‑mailu terminologii společnosti pro přehlednější zprávy.  
2. **Systémy archivace e‑mailů:** Zlepšete vyhledatelnost pomocí standardizovaných názvů hlaviček.  
3. **Platformy zákaznické podpory:** Zobrazte tickety s personalizovanými štítky hlaviček pro lepší zkušenost operátorů.

## Úvahy o výkonu
- Uvolněte objekty `Viewer` pomocí try‑with‑resources, aby se paměť rychle uvolnila.  
- Profilujte velké dávky a v případě potřeby zvažte zpracování e‑mailů v paralelních streamech.

## Závěr
Nyní víte **jak převést e‑mail na HTML** při **přejmenování polí e‑mailu** a **přizpůsobení hlaviček e‑mailu** pomocí GroupDocs.Viewer pro Java. Tato technika vám poskytuje plnou kontrolu nad prezentací metadat e‑mailu v HTML výstupech.

### Další kroky
- Experimentujte s dalšími mapováními polí (např. CC, BCC).  
- Prozkoumejte další formáty vykreslování, jako PDF nebo PNG.  
- Navštivte [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) pro podrobnější informace o API.

## Často kladené otázky

**Q: Funguje tento přístup i s jinými formáty e‑mailu, jako je EML?**  
A: Ano, GroupDocs.Viewer podporuje jak soubory MSG, tak EML; stejná logika mapování polí se použije.

**Q: Můžu získat HTML bez vložených zdrojů?**  
A: Můžete použít `HtmlViewOptions.forExternalResources(...)`, pokud preferujete samostatné soubory CSS/JS.

**Q: Jaká verze GroupDocs.Viewer byla testována?**  
A: Kód byl testován s GroupDocs.Viewer **25.2**.

**Q: Je možné změnit font nebo styl vlastních hlaviček?**  
A: Stylování lze aplikovat pomocí CSS po vykreslení, nebo můžete vložit vlastní CSS pomocí `HtmlViewOptions.getResourcesPath()`.

**Q: Jak programově získám cestu k vygenerovanému souboru HTML?**  
A: Cesta souboru následuje vzor definovaný v `pageFilePathFormat`; můžete ji sestavit pomocí `String.format` s číslem stránky.

## Zdroje
- **Dokumentace:** Komplexní průvodce jsou k dispozici na [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Podrobné informace o API najdete na [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Stáhnout GroupDocs.Viewer:** Přístup k nejnovější verzi získáte na [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Poslední aktualizace:** 2026-03-24  
**Testováno s:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs