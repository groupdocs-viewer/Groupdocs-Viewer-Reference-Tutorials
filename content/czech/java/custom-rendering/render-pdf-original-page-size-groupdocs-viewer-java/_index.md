---
date: '2026-01-31'
description: Naučte se, jak v Javě převádět PDF na PNG při zachování původní velikosti
  stránky pomocí GroupDocs.Viewer. Obsahuje tipy a řešení problémů při převodu PDF
  na PNG v Javě.
keywords:
- Render PDF Original Size
- GroupDocs Viewer Java API
- PDF Rendering with Java
title: Jak vykreslit PDF v původní velikosti pomocí GroupDocs.Viewer pro Java – komplexní
  průvodce
type: docs
url: /cs/java/custom-rendering/render-pdf-original-page-size-groupdocs-viewer-java/
weight: 1
---

# Jak vykreslit PDF v původní velikosti pomocí GroupDocs.Viewer pro Java

Vykreslení PDF **how to render pdf** při zachování jeho přesných rozměrů je nezbytné pro přesné zobrazení na jakémkoli zařízení. V tomto průvodci zjistíte, proč je důležité zachovat původní velikost stránky, jak nastavit GroupDocs.Viewer pro Java a přesné kroky k převodu PDF na PNG java bez jakéhokoli škálování. Na konci budete schopni spolehlivě vykreslovat PDF v jejich původní velikosti a vyhnout se běžným problémům s laděním vykreslování PDF.

![Vykreslit PDF v původní velikosti pomocí GroupDocs.Viewer pro Java](/viewer/custom-rendering/render-pdfs-in-original-size.png)

## Rychlé odpovědi
- **Která knihovna může převést PDF na PNG v Javě?** GroupDocs.Viewer pro Java poskytuje jednoduché API pro pdf to png java conversion.  
- **Jak zachovat původní velikost stránky?** Povolit `setRenderOriginalPageSize(true)` na objektu `PdfOptions`.  
- **Potřebuji licenci pro produkci?** Ano – pro ne‑zkušební použití je vyžadována trvalá nebo dočasná licence GroupDocs.  
- **Mohu vykreslovat PDF chráněné heslem?** Ano, stačí při vytváření instance `Viewer` zadat heslo.  
- **Jaká verze Javy je vyžadována?** Je podporována JDK 8 neboreslit PDF v původní velikosti“?
Když vykreslujete PDF, prohlížeč může buď škálovat stránky tak, aby se vešly do cílového formátu, nebo zachovat přesné rozměry definované ve zdrojovém souboru. Vykreslení v původní velikosti znamená, že každána pixel‑perfektně, což je zásadní pro právní dokumenty, archivní materiály a jakýkoli scénář, kde nelze kompromitovat věrnost rozvržení.

## Proč zachovat velikost stránky PDF?
- **Právní soulad:** Soudy často vyžadují, aby dokumenty vypadaly přesně tak, jak byly původně podány.  
ovávají svůj designový záměr.  
- **Technická přesnost:** Měření, diagramy a formuláře zůstávají po konverzi použitelné.

## Předpoklady
-  
- **GroupDocs.Viewer pro Java:** Přidejte knihovnu pomocí Maven (IDE:** IntelliJ IDEA, Eclipse nebo jakýkoli editor kompatibilní s Javou.

## Nastavení GroupDocs.Viewer pro Java

### Maven konfigurace
Přidejte oficiální repozitářstat přesně tak, jak je zobrazen.)*

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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

#### Získání licence
GroupDocs nabízí několik licenčních možností:
- **Free Trial:** Prozkoumejte všechny funkce bez časového omezení počtu stránek.  
- **Temporary License:** Plná funkčnost po krátkou zkušební dobu.  
- Průvodce implementací

te instanci `Viewer` a nakonfigurujte `PngViewOptions` pro výstup PNG souborů. Klíčové volání `viewOptions.getPdfOptions().setRenderOriginalPageSize(true);` říká enginu **nastavit původní velikost stránky**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

import java.nio.file.Path;

public class RenderOriginalPageSize {
    public static void main(String[] args) {
        // Define output directory path for rendered pages
        Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
        
        // Format for the output page file paths
        String pageFilePathFormat = "page_{0}.png";
        Path pageFilePath = outputDirectory.resolve(pageFilePathFormat);
        
        // Initialize PngViewOptions with the path format
        PngViewOptions viewOptions = new PngViewOptions(pageFilePath.toString());
        
        // Set option to render original page size for PDF documents
        viewOptions.getPdfOptions().setRenderOriginalPageSize(true);
        
        // Create a Viewer instance for the source PDF document
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF")) {
            // Render the PDF using the specified options
            viewer.view(viewOptions);
        }
    }
}
```

**Vysvětlení klíčových řádků**  
- **Konfigurace cesty:** Určuje, kde bude každé vykreslené PNG uloženo.  
- **PngViewOptions:** Volupní formát (klasický scénář *pdf to png java*).  
- **Render Original Page Size:** Zajišťuje, že nedochází ke škálování, a zachovává přesné rozměry každé stránky PDF.

### Krok 2: Spusťte a ověřte
Spusťte metodu `main`. Po dokončení otevřete vygenerované PNG soubory; měly by odpovídat původním rozměrům stránek PDF pixel po pixelu. Pokud se obrázky jeví jako natažené, zkontrolujte, že je přítomno `setRenderOriginalPageSize(true)` a že používáte nejnovější verzi GroupDocs.Viewer.

## Řešení problémů a běžné úskalí
- ** se, že `outputDirectory` i cesta ke zdrojovému PDF jsou absolutní nebo správně relativní k vašemu projektu.  
- **Chybějící licence:** Bez platné licence může vykreslování přejít do zkušebního režimuvyšte haldu JVM (`-Xmx2g` nebo více) nebo povolte lazy loading stránek.  
- **Šifrované PDF:** Při vytváření instance `Viewer` zadejte heslo, aby se předešlo chybám *pdf rendering troubleshooting*.

## Praktické příklady použití
1. **ovat historické skeny bez jakéhokoli zkreslení.  
2. **Portály právních dokumentů:** Nabídnout soud jak byly podány.  
3. **E‑learningové platformy:** Převést učebnice do obrazového formátu při zachování rozvržení.  
4. **Automatizace faktur:** Zajistit, aby položky a součty zůstaly po konverzi čitelné.

## Tipy pro výkon
- **Správa paměti:** Přidělte dostatečnou haldu pro velké dokumenty.  
- **Lazy loading:** Vykreslujte pouze stránky, které potřebujete, místo celého souboru, pokud je to možné.  
- **Caching:** Ukládejte vykreslené PNG pro často přistupované PDF, aby se předešlo opakovan Boot?**  
A: Zaregistrujte `Viewer` jako bean a injektujte jej tam, kde je potřeba; to vám umožní spravovat životní cyklus pomocí kontejneru Spring.

**Q: Mohu vykreslovat PDF do formátů jiných než PNG?**  
A: Ano, GroupDocs.Viewer také podporuje konverze do JPEG, SVG a PDF‑to‑HTML.

**Q: Co mám dělat, pokud proces vykreslování selže s výjimkou?**  
A: Zkontrolujte stack trace na chybějící cesty k souborům nebo problémy s licencí a ověřte, že PDF není poškozené.

**Q: Existuje limit velikosti pro PDF, které lze vykreslit?**  
A: Technicky ne, ale velmi velké soubory mohou vyžadovat zvýšenou paměť JVM a mohou mít prospěch z rozdělení na menší sekce.

**Q: Zvládá GroupDocs.Viewer PDF chráněné heslem?**  
A: Rozhodně – stačí předat heslo konstruktoru `Viewer` nebo přes objekt `LoadOptions`.

## Zdroje
- **Dokumentace:** [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **API Reference:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)  
- **Stáhnout GroupDocs.Viewer:** [Official Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Nákup a licence:** [Buy GroupDocs Products](https://purchase.groupdocs.com/buy)  
- **Free Trial:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License:** [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support Forum:** [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-01-31  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

---