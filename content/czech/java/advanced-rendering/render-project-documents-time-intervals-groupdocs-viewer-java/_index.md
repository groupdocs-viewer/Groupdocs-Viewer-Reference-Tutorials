---
date: '2026-09-25'
description: Zjistěte, jak vytvořit html view mpp pomocí GroupDocs Viewer pro Java,
  renderovat projektové dokumenty po časových intervalech pomocí krok‑po‑kroku kódu.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Vytvořte html view mpp pomocí GroupDocs Viewer pro Java pro renderování
  souborů Microsoft Project podle konkrétních časových intervalů. Postupujte podle
  krok‑po‑kroku nastavení, licencování a ukázek kódu pro přesnou vizualizaci časové
  osy.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Vytvořte html view mpp pomocí GroupDocs Viewer pro Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Vytvořte html view mpp pomocí GroupDocs Viewer (Java)
type: docs
url: /cs/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Jak použít GroupDocs Viewer k vykreslení projektových dokumentů podle časových intervalů v Javě

V tomto tutoriálu se naučíte, jak **create html view mpp** s GroupDocs Viewer pro Java, což vám umožní vykreslit pouze části souboru Microsoft Project, které spadají do konkrétního intervalu počátečního a koncového data. Provedeme vás nastavením Maven, licencováním a přesnými voláními API, která potřebujete k vložení přesných časových os přímo do vašich aplikací.

![Vykreslit projektové dokumenty podle časových intervalů pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Pro náhled viz [Vykreslit projektové dokumenty podle časových intervalů pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Rychlé odpovědi
- **Co funkce dělá?** Vykresluje pouze část souboru Microsoft Project, která spadá mezi počáteční a koncové datum.  
- **Jaký výstupní formát se používá?** HTML s vloženými zdroji, ideální pro webovou integraci.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Mohu změnit časový interval za běhu?** Ano—upravit hodnoty `setStartDate` a `setEndDate` v možnostech vykreslování.  
- **Je to podporováno ve všech verzích Javy?** Funguje s Javou 8+ za předpokladu, že používáte GroupDocs.Viewer 25.2 nebo novější.

## Co je create html view mpp?
`create html view mpp` je proces převodu souboru Microsoft Project (`.mpp` nebo `.mpt`) na sadu HTML stránek, které představují plán. GroupDocs Viewer provádí konverzi na straně serveru, takže můžete časovou osu zobrazit v libovolném prohlížeči bez instalace Microsoft Project.

## Proč vykreslovat projektové dokumenty s časovými intervaly?
Vykreslování pouze požadovaného časového intervalu snižuje velikost generovaného HTML, zrychluje načítání stránky a umožňuje soustředit se na konkrétní fázi projektu, kterou potřebujete analyzovat. Tento cílený pohled je ideální pro dashboardy, stavové zprávy nebo vložení do vlastních nástrojů pro řízení projektů, kde by kompletní data projektu byla nepřehledná.

## Předpoklady
- **GroupDocs.Viewer for Java** verze 25.2 nebo vyšší.  
- Java Development Kit (JDK) 8 nebo novější.  
- IDE, například IntelliJ IDEA nebo Eclipse.  
- Základní znalost Maven.

## Nastavení GroupDocs.Viewer pro Java

### Maven závislost

Add the repository and dependency to your `pom.xml`:

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

1. **Free trial** – Stáhněte si zkušební verzi z [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary license** – Získejte dočasnou licenci pro rozšířené testování prostřednictvím [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Pro neomezené použití v produkci zakupte licenci na [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Základní inicializace vieweru

`Viewer` je hlavní třída v GroupDocs.Viewer pro Java, která načítá dokument a poskytuje možnosti vykreslování.

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

## Získání informací o zobrazení pro projektové soubory

`ProjectManagementViewInfo` poskytuje metadata o souboru Microsoft Project, včetně celkových dat začátku a konce plánu.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Konfigurace možností HTML vykreslování (generovat HTML z projektu)

`HtmlViewOptions` konfiguruje, jak GroupDocs vykresluje HTML, umožňuje nastavit časový interval, vložit zdroje a přizpůsobit vzhled.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Spuštění procesu vykreslování

`viewer.render` provádí konverzi na základě poskytnutých možností a zapisuje výsledné HTML soubory do cílové složky.

```java
viewer.view(viewOptions);
```

## Časté problémy a řešení
- **Incorrect file paths** – Zkontrolujte, že existuje jak zdrojový soubor `.mpp`, tak výstupní adresář.  
- **Unsupported file type** – Ujistěte se, že dokument je ve podporovaném formátu Project (např. `.mpp`, `.mpt`).  
- **License errors** – Zkušební licence může mít omezení vykreslování; přepněte na plnou licenci pro neomezené použití.  

## Praktické aplikace
1. **Project timeline analysis** – Zobrazit zúčastněným stranám pouze aktuální fázi.  
2. **Automated reporting** – Generovat časově omezené HTML zprávy pro týdenní aktualizace stavu.  
3. **Integration with dashboards** – Vložit vykreslené stránky do BI nástrojů nebo vlastních portálů.  
4. **Archival** – Uložit webově přátelský snímek plánu projektu pro budoucí reference.  

## Tipy pro výkon
- Použijte možnost *embedded resources* k tomu, aby každá HTML stránka byla samostatná, čímž snížíte počet HTTP požadavků.  
- U velkých projektů zvažte vykreslování v menších časových úsecích, aby byl nízký odběr paměti. Vykreslení ročního úseku může zmenšit velikost HTML až o 80 % ve srovnání s exportem celého projektu, což zkrátí dobu načítání z několika sekund na méně než jednu sekundu na typických serverech.  
- Po obsloužení souborů odstraňte dočasné soubory, aby nedošlo k zaplnění disku.  

## Závěr
Nyní víte, **jak použít GroupDocs** Viewer k vykreslení projektových dokumentů v konkrétním časovém intervalu a **generovat HTML z projektových** dat v Javě. Tato funkce zjednodušuje vizualizaci časových os, zvyšuje efektivitu reportování a hladce se integruje s moderními webovými aplikacemi.

### Další kroky
- Prozkoumejte další funkce Vieweru, jako je vodoznak, ochrana heslem nebo vlastní stylování CSS.  
- Kombinujte tento vykreslovací proces s REST API pro poskytování časových os na vyžádání.  

## Často kladené otázky

**Q: Jaké souborové formáty GroupDocs.Viewer podporuje?**  
A: GroupDocs.Viewer podporuje více než 100 vstupních formátů, včetně PDF, DOCX, XLSX, PPTX a souborů Microsoft Project, což umožňuje univerzální vizualizaci dokumentů.

**Q: Jak začít s bezplatnou zkušební verzí GroupDocs.Viewer?**  
A: Můžete si stáhnout zkušební verzi ze [GroupDocs Viewer Java download page](https://releases.groupdocs.com/viewer/java/).

**Q: Mohu vykreslovat dokumenty bez vkládání zdrojů?**  
A: Ano, můžete zvolit jinou možnost HTML zobrazení, která odkazuje na externí zdroje místo jejich vkládání.

**Q: Co když je můj dokument příliš velký pro vykreslení?**  
A: Zvažte rozdělení dokumentu na menší části nebo vykreslení pouze požadovaného časového intervalu, jak je ukázáno výše.

**Q: Jak řešit chyby při vykreslování?**  
A: Ověřte všechna nastavení konfigurace, ujistěte se, že máte platnou licenci, a konzultujte dokumentaci GroupDocs pro podrobné chybové kódy.

## Zdroje
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Free trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-09-25  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Související tutoriály

- [Jak vykreslit soubory MS Project jako HTML, JPG, PNG a PDF s poznámkami pomocí GroupDocs.Viewer pro Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Export HTML z MS Project: Úprava časových jednotek pomocí GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Groupdocs Viewer Java Responsivní HTML vykreslování](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)