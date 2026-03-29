---
date: '2026-03-29'
description: Naučte se, jak vytvořit HTML zobrazení MPP pomocí GroupDocs Viewer v
  Javě, renderovat projektové dokumenty podle časových intervalů s krok‑za‑krokem
  kódem.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Vytvořte HTML zobrazení MPP pomocí GroupDocs Viewer (Java)
type: docs
url: /cs/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Jak používat GroupDocs Viewer k vykreslení projektových dokumentů podle časových intervalů v Javě

V tomto tutoriálu se naučíte, jak **create html view mpp** pomocí GroupDocs Viewer pro Java, což vám umožní vykreslit pouze části souboru Microsoft Project, které spadají do konkrétního časového intervalu. Provedeme vás nastavením Maven, konfigurací kódu a reálnými scénáři, abyste mohli vložit přesné časové osy přímo do svých aplikací.

![Vykreslení projektových dokumentů podle časových intervalů pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Rychlé odpovědi
- **Co funkce dělá?** Vykresluje pouze část souboru Microsoft Project, která spadá mezi počáteční a koncové datum.  
- **Jaký výstupní formát se používá?** HTML s vloženými zdroji, ideální pro webovou integraci.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; pro produkční nasazení je vyžadována plná licence.  
- **Mohu změnit časový rozsah za běhu?** Ano—upravením hodnot `setStartDate` a `setEndDate` v možnostech vykreslování.  
- **Je to podporováno ve všech verzích Javy?** Funguje s Java 8+ za předpokladu, že používáte GroupDocs.Viewer 25.2 nebo novější.

## Jak vytvořit html view mpp pro projektové dokumenty
GroupDocs Viewer může převést soubory Microsoft Project (`.mpp`, `.mpt`) na HTML stránky. Nastavením počátečního a koncového data v možnostech vykreslování omezíte výstup na časový úsek, který vás zajímá, což snižuje velikost souboru a urychluje načítání stránek.

## Co znamená „How to Use GroupDocs“ v tomto kontextu?
GroupDocs Viewer je knihovna pro Javu, která převádí více než 100 formátů souborů na webové reprezentace. Když **how to use GroupDocs** pro projektové soubory, získáte možnost extrahovat, vizualizovat a sdílet data harmonogramu bez nutnosti mít Microsoft Project na straně klienta.

## Proč vykreslovat projektové dokumenty s časovými intervaly?
- **Zaměřená analýza:** Zobrazí pouze fázi, která vás zajímá (např. Q3 2024).  
- **Výkon:** Menší HTML výstup znamená rychlejší načítání stránek.  
- **Integrace:** Vložte časové osy do dashboardů, portálů pro reportování nebo vlastních nástrojů pro řízení projektů.  

## Požadavky
- **GroupDocs.Viewer pro Java** verze 25.2 nebo vyšší.  
- Java Development Kit (JDK) 8 nebo novější.  
- IDE, jako je IntelliJ IDEA nebo Eclipse.  
- Základní znalost Maven.  

## Nastavení GroupDocs.Viewer pro Java

### Maven závislost

Přidejte repozitář a závislost do souboru `pom.xml`:

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
3. **Purchase** – Pro neomezené používání v produkci zakupte licenci na [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

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

## Průvodce implementací krok po kroku

### 1. Definujte výstupní adresář

Vytvořte složku, do které budou uloženy vygenerované HTML stránky:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Proč?* Udržování vykreslených souborů uspořádaných usnadňuje jejich poskytování z webového serveru nebo vložení do uživatelského rozhraní.

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

*Proč?* `ProjectManagementViewInfo` poskytuje počáteční a koncové datum harmonogramu, které později použijete k omezení rozsahu vykreslování.

### 4. Nakonfigurujte možnosti HTML vykreslování (Generování HTML z projektu)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Proč?* Nastavením `StartDate` a `EndDate` řeknete GroupDocs, aby **generate html view mpp** data pouze v tomto okně.

### 5. Spusťte proces vykreslování

```java
viewer.view(viewOptions);
```

*Proč?* Toto volání vytvoří sérii samostatných HTML stránek, které představují vybraný časový úsek vašeho projektového harmonogramu.

## Časté problémy a řešení
- **Nesprávné cesty k souborům** – Zkontrolujte, že existuje jak zdrojový soubor `.mpp`, tak výstupní adresář.  
- **Nepodporovaný typ souboru** – Ujistěte se, že dokument je ve podporovaném formátu Project (např. `.mpp`, `.mpt`).  
- **Chyby licence** – Zkušební licence může ukládat omezení vykreslování; přepněte na plnou licenci pro neomezené používání.  

## Praktické aplikace
1. **Analýza časové osy projektu** – Zobrazte zúčastněným stranám pouze aktuální fázi.  
2. **Automatizované reportování** – Generujte časově omezené HTML zprávy pro týdenní aktualizace stavu.  
3. **Integrace s dashboardy** – Vložte vykreslené stránky do BI nástrojů nebo vlastních portálů.  
4. **Archivace** – Uložte webově přátelský snímek harmonogramu projektu pro budoucí reference.  

## Tipy pro výkon
- Použijte možnost *embedded resources* k tomu, aby každá HTML stránka byla samostatná, čímž snížíte počet HTTP požadavků.  
- Pro velmi velké projekty zvažte vykreslování v menších časových úsecích, aby se udržela nízká spotřeba paměti.  
- Po jejich nasazení odstraňte dočasné soubory, aby nedošlo k zaplnění disku.  

## Závěr
Nyní víte, **how to use GroupDocs** Viewer k vykreslení projektových dokumentů v konkrétním časovém intervalu a **generate HTML from project** data v Javě. Tato schopnost zjednodušuje vizualizaci časových os, zlepšuje efektivitu reportování a hladce se integruje s moderními webovými aplikacemi.

### Další kroky
- Prozkoumejte další funkce Vieweru, jako je vodoznak, ochrana heslem nebo vlastní stylování CSS.  
- Kombinujte tento vykreslovací pipeline s REST API pro poskytování časových os na vyžádání.  

## Často kladené otázky
**Q: Jaké formáty souborů GroupDocs.Viewer podporuje?**  
A: GroupDocs.Viewer podporuje širokou škálu formátů včetně Microsoft Project (MPP), PDF, Word, Excel, PowerPoint a mnoho dalších.

**Q: Jak začít s bezplatnou zkušební verzí GroupDocs.Viewer?**  
A: Zkušební verzi můžete stáhnout z [zde](https://releases.groupdocs.com/viewer/java/).

**Q: Mohu vykreslovat dokumenty bez vkládání zdrojů?**  
A: Ano, můžete zvolit jinou možnost HTML view, která odkazuje na externí zdroje místo jejich vkládání.

**Q: Co když je můj dokument příliš velký pro vykreslení?**  
A: Zvažte rozdělení dokumentu na menší sekce nebo vykreslení pouze požadovaného časového rozsahu, jak bylo ukázáno výše.

**Q: Jak řešit chyby při vykreslování?**  
A: Ověřte všechna nastavení konfigurace, ujistěte se, že máte platnou licenci, a konzultujte dokumentaci GroupDocs pro podrobné chybové kódy.

## Zdroje
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-03-29  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs