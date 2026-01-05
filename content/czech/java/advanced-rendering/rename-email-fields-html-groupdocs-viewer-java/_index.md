---
date: '2026-01-05'
description: Naučte se, jak přejmenovat pole e‑mailu, převést e‑mail do HTML a přizpůsobit
  hlavičky e‑mailu pomocí GroupDocs.Viewer pro Javu.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Jak přejmenovat pole e‑mailu při renderování e‑mailů do HTML pomocí GroupDocs.Viewer
  Java
type: docs
url: /cs/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Jak přejmenovat pole e‑mailu při vykreslování e‑mailů do HTML pomocí GroupDocs.Viewer Java

Zajímá vás **jak přejmenovat pole e‑mailu** při převodu e‑mailu do HTML? V tomto průvodci vás provede přesnými kroky, jak přejmenovat pole e‑mailu, **převést e‑mail do HTML** a **přizpůsobit hlavičky e‑mailu** pomocí GroupDocs.Viewer for Java. Na konci budete mít čistou HTML reprezentaci s vámi preferovanými názvy hlaviček, což usnadní čtení výstupu a jeho integraci do vašich aplikací.

![Přejmenování polí e‑mailu při převodu e‑mailů do HTML pomocí GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Co se naučíte
- Jak použít GroupDocs.Viewer for Java k **převodu e‑mailu do HTML**.  
- Techniky pro **přejmenování polí e‑mailu** jako jsou „From“, „To“, „Sent“ a „Subject“.  
- Nejlepší postupy pro nastavení Maven a licencování.  
- Reálné scénáře, kde **přizpůsobení hlaviček e‑mailu** přináší hodnotu.

## Rychlé odpovědi
- **Co znamená “how to rename email”?** Odkazuje na mapování výchozích názvů hlaviček e‑mailu na vlastní štítky během vykreslování.  
- **Která knihovna provádí převod?** GroupDocs.Viewer for Java (v25.2+).  
- **Potřebuji licenci?** Zkušební verze funguje pro hodnocení; pro produkci je vyžadována plná licence.  
- **Mohu změnit libovolný název hlavičky?** Ano, jakákoli standardní hlavička e‑mailu může být přemapována pomocí `fieldTextMap`.  
- **Je výstup HTML nebo vložené zdroje?** Můžete zvolit vložené zdroje pro jeden samostatný soubor.

## Co znamená “how to rename email” v kontextu GroupDocs.Viewer?
Přejmenování polí e‑mailu znamená nahrazení výchozích štítků (např. „From“) vlastním textem (např. „Sender“) při vykreslování e‑mailu do HTML. To je užitečné pro sladění výstupu s firemní terminologií nebo pro zlepšení čitelnosti pro koncové uživatele.

## Proč převádět e‑mail do HTML a přizpůsobovat hlavičky e‑mailu?
- **Konzistentní branding:** Přizpůsobte jazyk vaší organizace ve všech komunikacích.  
- **Zlepšená prohledatelnost:** Vlastní hlavičky mohou být efektivněji indexovány v archivních systémech.  
- **Lepší integrace UI:** Přizpůsobte HTML úryvek tak, aby se bez problémů začlenil do webových portálů nebo řídicích panelů podpory.

## Předpoklady

### Požadované knihovny, verze a závislosti
- **GroupDocs.Viewer for Java** – verze 25.2 nebo novější.  
- **Java Development Kit (JDK)** – verze 8+.

### Požadavky na nastavení prostředí
- **Maven** pro správu závislostí.  
- IDE jako IntelliJ IDEA, Eclipse nebo VS Code.

### Předpoklady znalostí
Základní znalost Javy a Maven vám pomůže rychle sledovat postup.

## Nastavení GroupDocs.Viewer pro Java

### Konfigurace Maven
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
- **Free Trial:** Stáhněte si zkušební verzi z [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** Získejte dočasnou licenci pro prozkoumání všech funkcí bez omezení na [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** Pro trvalé používání zvažte zakoupení licence přes [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

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

## Průvodce implementací

### Přejmenování polí e‑mailu – krok za krokem

#### 1. Nastavte cestu výstupního adresáře
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Nahraďte `"YOUR_OUTPUT_DIRECTORY"` složkou, kam chcete ukládat HTML soubory.*

#### 2. Definujte formát cesty souboru stránky
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` bude během vykreslování nahrazeno číslem stránky.*

#### 3. Vytvořte mapování polí e‑mailu na nové názvy
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

#### 4. Nakonfigurujte možnosti zobrazení HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` zahrnuje CSS/JS do HTML, zatímco `setFieldTextMap` aplikuje vlastní názvy hlaviček.*

#### 5. Vykreslete e‑mail do HTML
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
1. **Custom Email Reports:** Přizpůsobte hlavičky e‑mailu firemní terminologii pro přehlednější zprávy.  
2. **Email Archiving Systems:** Zlepšete prohledatelnost pomocí standardizovaných názvů hlaviček.  
3. **Customer Support Platforms:** Zobrazte tickety s personalizovanými štítky hlaviček pro lepší zkušenost agentů.

## Úvahy o výkonu
- Uvolněte objekty `Viewer` pomocí try‑with‑resources, aby se paměť rychle uvolnila.  
- Profilujte velké dávky a v případě potřeby zvažte zpracování e‑mailů v paralelních streamech.

## Závěr
Nyní víte **jak přejmenovat pole e‑mailu** při **převodu e‑mailu do HTML** a **přizpůsobení hlaviček e‑mailu** pomocí GroupDocs.Viewer for Java. Tato technika vám poskytuje plnou kontrolu nad prezentací metadat e‑mailu v HTML výstupech.

### Další kroky
- Experimentujte s dalšími mapováními polí (např. CC, BCC).  
- Prozkoumejte další formáty vykreslování, jako PDF nebo PNG.  
- Navštivte [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) pro podrobnější informace o API.

## Sekce FAQ
1. **Mohu přejmenovat všechny hlavičky e‑mailu pomocí této metody?**  
   - Ano, můžete mapovat jakoukoli standardní hlavičku e‑mailu na nový název podle vašich požadavků.
2. **Je možné použít GroupDocs.Viewer bez licence?**  
   - Zkušební verze je k dispozici pro testování, ale plnohodnotná verze vyžaduje platnou licenci.
3. **Jak efektivně zvládnout velké objemy e‑mailů pomocí GroupDocs.Viewer?**  
   - Zvažte dávkové zpracování a optimalizujte systémové zdroje pro efektivní správu větších datových sad.
4. **Mohu tuto řešení integrovat do existující Java aplikace?**  
   - Rozhodně, integrace je jednoduchá pomocí Maven závislostí.
5. **Kde mohu najít podporu, pokud narazím na problémy?**  
   - Navštivte [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) pro komunitní a oficiální pomoc.

## Často kladené otázky

**Q: Funguje tento přístup i s jinými formáty e‑mailu, jako je EML?**  
A: Ano, GroupDocs.Viewer podporuje soubory MSG i EML; stejná logika mapování polí se použije.

**Q: Mohu získat HTML bez vložených zdrojů?**  
A: Můžete použít `HtmlViewOptions.forExternalResources(...)`, pokud dáváte přednost samostatným souborům CSS/JS.

**Q: Jaká verze GroupDocs.Viewer byla testována?**  
A: Kód byl testován s GroupDocs.Viewer **25.2**.

**Q: Je možné změnit font nebo styl vlastních hlaviček?**  
A: Stylování lze aplikovat pomocí CSS po vykreslení, nebo můžete vložit vlastní CSS pomocí `HtmlViewOptions.getResourcesPath()`.

**Q: Jak programově získat cestu k vygenerovanému HTML souboru?**  
A: Cesta k souboru následuje vzor definovaný v `pageFilePathFormat`; můžete ji vytvořit pomocí `String.format` s číslem stránky.

## Zdroje
- **Documentation:** Komplexní průvodce jsou k dispozici na [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Podrobné informace o API najdete na [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Získejte nejnovější verzi na [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Last Updated:** 2026-01-05  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs