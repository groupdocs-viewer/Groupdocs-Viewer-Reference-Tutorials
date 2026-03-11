---
date: '2026-01-15'
description: Naučte se, jak používat GroupDocs Viewer k generování HTML z projektových
  dokumentů v konkrétních časových intervalech. Tento průvodce zahrnuje nastavení,
  kód a reálné příklady použití.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Jak použít GroupDocs Viewer k vykreslení projektových dokumentů podle časových
  intervalů v Javě
type: docs
url: /cs/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Jak používat GroupDocs Viewer k vykreslení projektových dokumentů po časových intervalech v Javě

Pokud hledáte **jak používat GroupDocs** pro vykreslení projektových plánů v konkrétním časovém okně, jste na správném místě. V tomto tutoriálu vás provedeme celým procesem – od nastavení Maven až po generování HTML z projektových dokumentů – abyste mohli vložit přesné časové osy přímo do svých aplikací.

![Vykreslit projektové dokumenty po časových intervalech pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Rychlé odpovědi
- **Co tato funkce dělá?** Vykresluje pouze část souboru Microsoft Project, která spadá mezi počáteční a koncové datum.  
- **Jaký výstupní formát se používá?** HTML s vloženými zdroji, ideální pro webovou integraci.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; pro produkční použití je vyžadována plná licence.  
- **Mohu měnit časový rozsah za běhu?** Ano – upravte hodnoty `setStartDate` a `setEndDate` v možnostech vykreslování.  
- **Je to podporováno ve všech verzích Javy?** Funguje s Javou 8+ za předpokladu, že používáte GroupDocs.Viewer 25.2 nebo novější.

## Co znamená „How to Use GroupDocs“ v tomto kontextu?
GroupDocs Viewer je knihovna pro Javu, která převádí více než 100 formátů souborů na web‑přátelské reprezentace. Když **jak používat GroupDocs** pro projektové soubory, získáte možnost extrahovat, vizualizovat a sdílet data plánu bez nutnosti Microsoft Project na straně klienta.

## Proč vykreslovat projektové dokumenty s časovými intervaly?
- **Zaměřená analýza:** Zobrazte pouze fázi, která vás zajímá (např. Q3 2024).  
- **Výkon:** Menší HTML výstup znamená rychlejší načítání stránek.  
- **Integrace:** Vložte zobrazení časové osy do dashboardů, portálů pro reportování nebo vlastních nástrojů pro řízení projektů.  

## Požadavky
- **GroupDocs.Viewer for Java** verze 25.2 nebo vyšší.  
- Java Development Kit (JDK) 8 nebo novější.  
- IDE, např. IntelliJ IDEA nebo Eclipse.  
- Základní znalost Maven.  

## Nastavení GroupDocs.Viewer pro Java

### Maven závislost
Přidejte repozitář a závislost do svého `pom.xml`:

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
1. **Free Trial** – Stáhněte si zkušební verzi z [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Získejte dočasnou licenci pro rozšířené testování prostřednictvím [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Pro neomezené produkční použití zakupte licenci na [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Základní inicializace Vieweru
Následující úryvek ukazuje, jak vytvořit instanci `Viewer`, která ukazuje na soubor Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Průvodce implementací krok za krokem

### 1. Definujte výstupní adresář
Vytvořte složku, kam budou uloženy generované HTML stránky:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Proč?* Udržování vykreslených souborů organizovaných usnadňuje jejich poskytování z webového serveru nebo vložení do uživatelského rozhraní.

### 2. Inicializujte Viewer s vaším projektovým souborem
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Proč?* Načtení dokumentu připraví interní parser a zpřístupní metadata specifická pro projekt.

### 3. Získejte informace o zobrazení pro projektové soubory
```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Proč?* `ProjectManagementViewInfo` poskytuje počáteční a koncová data plánu, která později použijete k omezení rozsahu vykreslování.

### 4. Nakonfigurujte možnosti HTML vykreslování (Generovat HTML z projektu)
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Proč?* Nastavení `StartDate` a `EndDate` říká GroupDocs, aby **generoval HTML z projektu** pouze v tomto časovém okně.

### 5. Spusťte proces vykreslování
```java
viewer.view(viewOptions);
```

*Proč?* Toto volání vytvoří sérii samostatných HTML stránek, které představují vybraný časový úsek vašeho projektového plánu.

## Časté problémy a řešení
- **Nesprávné cesty k souborům** – Zkontrolujte, že existuje jak zdrojový soubor `.mpp`, tak výstupní adresář.  
- **Nepodporovaný typ souboru** – Ujistěte se, že dokument je ve podporovaném formátu Project (např. `.mpp`, `.mpt`).  
- **Chyby licence** – Zkušební licence může ukládat omezení vykreslování; přepněte na plnou licenci pro neomezené použití.  

## Praktické aplikace
1. **Project Timeline Analysis** – Zobrazte stakeholderům pouze aktuální fázi.  
2. **Automated Reporting** – Generujte časově omezené HTML zprávy pro týdenní aktualizace stavu.  
3. **Integration with Dashboards** – Vložte vykreslené stránky do BI nástrojů nebo vlastních portálů.  
4. **Archival** – Uložte web‑přátelskou snímkovou podobu projektového plánu pro budoucí referenci.  

## Tipy pro výkon
- Použijte možnost *embedded resources* k tomu, aby každá HTML stránka byla samostatná, což snižuje počet HTTP požadavků.  
- U velmi velkých projektů zvažte vykreslování v menších časových úsecích, aby se snížila spotřeba paměti.  
- Po jejich poskytnutí odstraňte dočasné soubory, aby nedošlo k zaplnění disku.  

## Závěr
Nyní víte **jak používat GroupDocs** Viewer k vykreslení projektových dokumentů v konkrétním časovém intervalu a **generovat HTML z projektových** dat v Javě. Tato funkce zjednodušuje vizualizaci časových os, zlepšuje efektivitu reportování a hladce se integruje s moderními webovými aplikacemi.

### Další kroky
- Prozkoumejte další funkce Vieweru, jako je vodoznak, ochrana heslem nebo vlastní stylování CSS.  
- Spojte tento vykreslovací pipeline s REST API pro poskytování požadovaných zobrazení časových os.  

## Často kladené otázky

**Q: Jaké formáty souborů GroupDocs.Viewer podporuje?**  
A: GroupDocs.Viewer podporuje širokou škálu formátů včetně Microsoft Project (MPP), PDF, Word, Excel, PowerPoint a mnoho dalších.

**Q: Jak začít s bezplatnou zkušební verzí GroupDocs.Viewer?**  
A: Zkušební verzi můžete stáhnout z [zde](https://releases.groupdocs.com/viewer/java/).

**Q: Mohu vykreslovat dokumenty bez vkládání zdrojů?**  
A: Ano, můžete zvolit jinou možnost HTML zobrazení, která odkazuje na externí zdroje místo jejich vkládání.

**Q: Co když je můj dokument příliš velký pro vykreslení?**  
A: Zvažte rozdělení dokumentu na menší sekce nebo vykreslení pouze požadovaného časového rozsahu, jak je ukázáno výše.

**Q: Jak řešit chyby při vykreslování?**  
A: Ověřte všechna nastavení konfigurace, ujistěte se, že máte platnou licenci, a konzultujte dokumentaci GroupDocs pro podrobné kódy chyb.

## Zdroje
- **Dokumentace**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Reference API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Stáhnout**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Nákup**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Bezplatná zkušební verze**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Dočasná licence**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Podpora**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-01-15  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs