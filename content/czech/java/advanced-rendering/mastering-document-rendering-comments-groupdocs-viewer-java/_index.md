---
categories:
- Java Development
date: '2026-01-28'
description: Naučte se, jak převést Word do HTML a vykreslit dokumenty s komentáři
  pomocí GroupDocs Viewer pro Java. Průvodce krok za krokem, řešení problémů a osvědčené
  postupy.
keywords: GroupDocs Viewer Java tutorial, Java document rendering with comments, HTML
  document viewer Java, GroupDocs Java integration, Java document conversion HTML
lastmod: '2026-01-28'
linktitle: GroupDocs Viewer Java Tutorial
tags:
- groupdocs-viewer
- java-tutorial
- document-rendering
- html-conversion
title: 'Návod GroupDocs Viewer Java - Převod Wordu do HTML a vykreslení dokumentů s
  komentáři'
type: docs
url: /cs/java/advanced-rendering/mastering-document-rendering-comments-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer Java Tutoriál: Převod Word na HTML a vykreslení dokumentů s komentáři

## Úvod

Už jste někdy zkoušeli převést dokument Word do HTML a přitom ztratili všechny důležité komentáře a anotace? Nejste v tom sami. Mnoho Java vývojářů má potíže se zachováním formátování dokumentu a vloženého obsahu během konverzních procesů.

Tento komplexní GroupDocs Viewer Java tutoriál řeší právě tento problém. Naučíte se, jak **převést Word na HTML**, přičemž dokumenty (Word, Excel, PowerPoint a další) budou vykresleny do čistého HTML se všemi komentáři, anotacemi a zpětnou vazbou zachovanou.

Ať už budujete systém pro správu dokumentů, vytváříte platformu pro kolaborativní recenze, nebo jen potřebujete zobrazit anotované dokumenty na webu, tento návod vás provede.

![Render Documents with Comments with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-documents-with-comments.png)

**Co se v tomto tutoriálu naučíte:**
- Kompletní nastavení a konfigurace GroupDocs Viewer
- Krok za krokem **převod Word na HTML** s zachovanými komentáři
- Běžná řešení problémů a tipy, kterým se vyhnout
- Reálné implementační vzory a osvědčené postupy
- Techniky optimalizace výkonu pro produkční nasazení

## Rychlé odpovědi
- **Může GroupDocs Viewer převést Word na HTML?** Ano, stačí povolit vykreslování HTML a podporu komentářů.  
- **Zůstávají komentáře v HTML výstupu?** Naprosto—`setRenderComments(true)` je zachová.  
- **Jaká verze Javy je vyžadována?** JDK 8 nebo vyšší.  
- **Je pro produkci potřeba licence?** Plná licence odstraňuje vodoznaky a odemyká všechny funkce.  
- **Jak zlepšit rychlost vykreslování?** Vykreslujte konkrétní stránky, používejte externí zdroje a zvyšte velikost haldy JVM.

## Proč zvolit GroupDocs Viewer pro Java?

Než se pustíme do kódu, rychle pochopíme, proč GroupDocs Viewer vyniká při vykreslování Java dokumentů:

**Klíčové výhody:**
- Podporuje více než 170 formátů souborů ihned po instalaci
- Není potřeba Microsoft Office ani jiný software třetích stran
- Zachovává původní formátování a vložené prvky
- Lehký a rychlý vykreslovací engine
- Vynikající dokumentace a podpora komunity

**Kdy použít tento přístup:**
- Vytváření webových prohlížečů dokumentů
- Vytváření kolaborativních recenzních systémů
- Vývoj portálů pro správu dokumentů
- Převod starých dokumentů pro webové zobrazení
- Budování vzdělávacích platforem s anotovaným obsahem

## Předpoklady a nastavení prostředí

### Co budete potřebovat

Před zahájením tohoto GroupDocs Viewer Java tutoriálu se ujistěte, že máte:

**Základní požadavky:**
- Java Development Kit (JDK) 8 nebo vyšší
- Maven 3.6+ pro správu závislostí
- Váš oblíbený IDE (IntelliJ IDEA, Eclipse nebo VS Code)
- Základní pochopení konceptů Java a Maven

**Volitelné, ale užitečné:**
- Ukázkové dokumenty s komentáři (Word, Excel, PowerPoint soubory)
- Základní znalost HTML a webového vývoje
- Pochopení operací souborového I/O v Javě

### Nastavení vývojového prostředí

**Krok 1: Ověření instalace Javy**  
```bash
java -version
javac -version
```

**Krok 2: Kontrola instalace Maven**  
```bash
mvn -version
```

Pokud některý chybí, stáhněte jej z oficiálních webových stránek a postupujte podle instalačních návodů.

**Krok 3: Vytvoření nového Maven projektu**  
```bash
mvn archetype:generate -DgroupId=com.example.documentviewer -DartifactId=groupdocs-viewer-demo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

Nyní jste připraveni přidat GroupDocs Viewer do svého projektu!

## Nastavení GroupDocs.Viewer pro Java

### Přidání závislosti

Prvním krokem v jakémkoli GroupDocs Viewer Java tutoriálu je získání knihovny do vašeho projektu. Přidejte tuto konfiguraci do souboru `pom.xml`:

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

**Tip:** Vždy zkontrolujte [GroupDocs releases page](https://releases.groupdocs.com/viewer/java/) pro nejnovější verzi. Knihovna je aktivně udržována s pravidelnými aktualizacemi a opravami chyb.

### Porozumění licenčním možnostem

GroupDocs nabízí flexibilní licencování, které vyhovuje různým potřebám projektů:

**Bezplatná zkušební verze (Ideální pro učení):**
- 30‑denní evaluační období
- Plný přístup ke všem funkcím s evaluačními vodoznaky
- Skvělé pro sledování tohoto tutoriálu a testování konceptů

**Dočasná licence (Pro vývoj):**
- Rozšířená evaluace bez vodoznaků
- Ideální pro projekty proof‑of‑concept
- Požádejte na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/)

**Plná licence (Pro produkci):**
- Žádná omezení ani vodoznaky
- Komerní použití povoleno
- K dispozici na [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy)

### Základní vzor inicializace

Zde je základní vzor, který budete během tohoto tutoriálu používat:

```java
import com.groupdocs.viewer.Viewer;

// The try-with-resources pattern ensures proper cleanup
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // All rendering operations happen here
    // Resources are automatically closed when done
} catch (Exception e) {
    System.err.println("Error rendering document: " + e.getMessage());
    e.printStackTrace();
}
```

**Proč tento vzor funguje:**
- Automatická správa zdrojů zabraňuje únikům paměti
- Zpracování výjimek zachytává běžné problémy s přístupem k souborům
- Čistý, čitelný kód, který se snadno udržuje

## Hlavní implementace: Vykreslování dokumentů s komentáři

A teď hlavní část! Projděme si vykreslení dokumentu se všemi zachovanými komentáři.

### Porozumění procesu

Když vykreslíte dokument pomocí GroupDocs Viewer, děje se v pozadí následující:

1. **Analýza dokumentu:** Knihovna načte a parsuje váš vstupní soubor  
2. **Extrahování komentářů:** Komentáře a anotace jsou identifikovány a zachovány  
3. **Generování HTML:** Vytvoří se čisté, standardy‑kompatibilní HTML (zde se **převádí Word na HTML**)  
4. **Správa zdrojů:** Obrázky, styly a další aktiva jsou spravovány  
5. **Vytvoření výstupu:** Konečné HTML soubory jsou zapsány do určeného adresáře  

### Krok‑za‑krokem implementace

**Krok 1: Nastavení cest k souborům**  
Nejprve uspořádejme, kam naše soubory půjdou. Může se to zdát základní, ale správná správa cest předchází 90 % běžných problémů:

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Create a descriptive output directory
Path outputDirectory = Paths.get("rendered-documents");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Proč tento přístup:**
- Používá moderní Java NIO.2 `Path` API (spolehlivější než stará třída `File`)
- Popisné pojmenování usnadňuje ladění
- Zástupný znak `{0}` se automaticky nahradí čísly stránek

**Krok 2: Konfigurace možností vykreslování HTML**  
Zde se děje magie. Řekneme GroupDocs přesně, jak má být dokument vykreslen:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

// Create HTML options with embedded resources
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);

// The crucial setting – enable comment rendering!
viewOptions.setRenderComments(true);
```

**Klíčové detaily konfigurace:**
- `forEmbeddedResources()`: Zahrnuje všechny CSS, obrázky a fonty přímo do HTML (skvělé pro přenositelnost)
- `setRenderComments(true)`: Zachovává každý komentář a anotaci (jádro **převodu Word na HTML** s komentáři)
- Alternativa: `forExternalResources()` pokud dáváte přednost samostatným souborům zdrojů

**Krok 3: Spuštění vykreslování**  
Nyní to spojíme dohromady:

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Create output directory if it doesn't exist
    if (!outputDirectory.toFile().exists()) {
        outputDirectory.toFile().mkdirs();
    }
    
    // Perform the actual rendering
    viewer.view(viewOptions);
    
    System.out.println("Document rendered successfully!");
    System.out.println("Output location: " + outputDirectory.toAbsolutePath());
    
} catch (Exception e) {
    System.err.println("Rendering failed: " + e.getMessage());
    e.printStackTrace();
}
```

### Kompletní funkční příklad

Zde je vše spojeno v jedné spustitelné třídě:

```java
package com.example.documentviewer;

import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class DocumentRenderer {
    
    public static void main(String[] args) {
        renderDocumentWithComments("sample-document.docx", "output");
    }
    
    public static void renderDocumentWithComments(String inputFile, String outputDir) {
        // Set up paths
        Path outputDirectory = Paths.get(outputDir);
        Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
        
        // Configure rendering options
        HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
        viewOptions.setRenderComments(true);
        
        // Render the document
        try (Viewer viewer = new Viewer(inputFile)) {
            // Ensure output directory exists
            outputDirectory.toFile().mkdirs();
            
            // Execute rendering
            viewer.view(viewOptions);
            
            System.out.println("✓ Document rendered with comments preserved");
            System.out.println("📂 Output directory: " + outputDirectory.toAbsolutePath());
            
        } catch (Exception e) {
            System.err.println("❌ Rendering failed: " + e.getMessage());
            e.printStackTrace();
        }
    }
}
```

## Pokročilá konfigurace a možnosti

### Nastavení dynamických výstupních adresářů

Pro větší aplikace budete chtít pokročilejší správu cest:

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class PathManager {
    
    /**
     * Creates a structured output path based on document name and timestamp
     */
    public static Path getOutputDirectoryPath(String documentName) {
        String timestamp = String.valueOf(System.currentTimeMillis());
        String cleanDocName = documentName.replaceAll("[^a-zA-Z0-9]", "_");
        
        return Paths.get("rendered-docs")
                   .resolve(cleanDocName)
                   .resolve(timestamp);
    }
    
    /**
     * Simple output directory for basic use cases
     */
    public static Path getSimpleOutputPath(String folderName) {
        return Paths.get("output").resolve(folderName);
    }
}
```

### Běžné problémy a řešení

#### Problém 1: Chyby „Soubor nenalezen“
```java
// Always check if file exists before processing
Path inputPath = Paths.get("your-document.docx");
if (!inputPath.toFile().exists()) {
    throw new IllegalArgumentException("Input file not found: " + inputPath.toAbsolutePath());
}

// Check if file is readable
if (!inputPath.toFile().canRead()) {
    throw new IllegalArgumentException("Cannot read input file: " + inputPath.toAbsolutePath());
}
```

#### Problém 2: Komentáře se neobjevují ve výstupu
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
// This line is crucial – don't forget it!
viewOptions.setRenderComments(true);

// For debugging, you can verify the setting:
System.out.println("Comments enabled: " + viewOptions.isRenderComments());
```

#### Problém 3: Chyby nedostatku paměti u velkých dokumentů
```java
// Increase JVM heap size when running
// java -Xmx2g -Xms1g YourApplication

// Or process documents page by page for very large files
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setRenderComments(true);

// Render only specific pages if needed
viewer.view(viewOptions, 1, 2, 3); // Renders only pages 1, 2, and 3
```

#### Problém 4: Pomalejší výkon vykreslování
```java
// Use external resources for faster processing of multiple pages
HtmlViewOptions viewOptions = HtmlViewOptions.forExternalResources(
    pageFilePathFormat, 
    "resources/page_{0}/", 
    "resources/page_{0}/{0}"
);

// Enable caching if processing the same document multiple times
// (Note: Implement caching at application level)
```

## Reálné implementační vzory

### Vzor 1: Integrace webové aplikace

Zde je, jak můžete integrovat toto do Spring Boot kontroleru:

```java
@RestController
@RequestMapping("/api/documents")
public class DocumentController {
    
    @PostMapping("/render")
    public ResponseEntity<String> renderDocument(
            @RequestParam("file") MultipartFile file) {
        
        try {
            // Save uploaded file temporarily
            Path tempFile = Files.createTempFile("upload", ".tmp");
            file.transferTo(tempFile.toFile());
            
            // Render with comments
            String outputDir = renderDocumentWithComments(
                tempFile.toString(), 
                "web-output"
            );
            
            return ResponseEntity.ok("Document rendered: " + outputDir);
            
        } catch (Exception e) {
            return ResponseEntity.badRequest()
                .body("Rendering failed: " + e.getMessage());
        }
    }
}
```

### Vzor 2: Dávkové zpracování více dokumentů

```java
public class BatchDocumentProcessor {
    
    public void processFolderWithComments(String inputFolder) {
        File folder = new File(inputFolder);
        File[] files = folder.listFiles((dir, name) -> 
            name.toLowerCase().endsWith(".docx") || 
            name.toLowerCase().endsWith(".xlsx") ||
            name.toLowerCase().endsWith(".pptx")
        );
        
        if (files == null) return;
        
        for (File file : files) {
            try {
                String outputDir = file.getName().replace(".", "_") + "_output";
                renderDocumentWithComments(file.getAbsolutePath(), outputDir);
                System.out.println("✓ Processed: " + file.getName());
                
            } catch (Exception e) {
                System.err.println("❌ Failed to process " + file.getName() + ": " + e.getMessage());
            }
        }
    }
}
```

## Optimalizace výkonu a osvědčené postupy

### Tipy pro správu paměti

Při práci s GroupDocs Viewer v produkci je efektivní správa paměti klíčová:

**Nejlepší postupy**
1. **Vždy používejte try‑with‑resources** pro automatické uvolnění zdrojů  
2. **Zpracovávejte velké dokumenty po dávkách** místo najednou  
3. **Monitorujte využití haldy JVM** a upravujte podle potřeby  
4. **Implementujte správné cachování** pro často přistupované dokumenty  

### Pokyny pro využití zdrojů

**Pro malé aplikace (< 100 dokumentů/den):**
```java
// Simple approach works fine
try (Viewer viewer = new Viewer(documentPath)) {
    viewer.view(viewOptions);
}
```

**Pro aplikace s vysokým objemem (1000+ dokumentů/den):**
```java
public class DocumentRenderingService {
    private final ExecutorService executorService = 
        Executors.newFixedThreadPool(4); // Limit concurrent renderings
    
    public CompletableFuture<String> renderAsync(String documentPath) {
        return CompletableFuture.supplyAsync(() -> {
            try (Viewer viewer = new Viewer(documentPath)) {
                // Rendering logic here
                return "success";
            } catch (Exception e) {
                throw new RuntimeException(e);
            }
        }, executorService);
    }
}
```

### Strategie cachování

```java
public class CachedDocumentRenderer {
    private final Map<String, String> renderCache = new ConcurrentHashMap<>();
    
    public String renderWithCaching(String documentPath) {
        String cacheKey = generateCacheKey(documentPath);
        
        return renderCache.computeIfAbsent(cacheKey, key -> {
            // Only render if not already cached
            return performActualRendering(documentPath);
        });
    }
    
    private String generateCacheKey(String documentPath) {
        // Include file modification time in cache key
        File file = new File(documentPath);
        return documentPath + "_" + file.lastModified();
    }
}
```

## Kdy použít GroupDocs Viewer vs alternativy

### GroupDocs Viewer je ideální pro

- **Systémy pro správu dokumentů:** Potřeba zobrazit různé typy souborů s anotacemi  
- **Kolaborativní platformy:** Komentáře a zpětná vazba musí být viditelné  
- **Vzdělávací nástroje:** Anotace instruktorů musí být zobrazeny studentům  
- **Právní aplikace:** Revize smluv s komentáři právníků  

### Zvažte alternativy, když

- **Jednoduché zobrazení PDF:** Vestavěný PDF prohlížeč v prohlížeči může stačit  
- **Základní konverze obrázků:** `ImageIO` nebo podobné knihovny mohou být lehčí  
- **Čisté získávání textu:** Apache POI nebo iText mohou být vhodnější  

## Rozšířená sekce FAQ

### Technické otázky k implementaci

**Q: Můžu vykreslovat dokumenty bez komentářů?**  
A: Samozřejmě! Stačí vynechat `setRenderComments(true)` nebo nastavit na `false`.

**Q: Jaké formáty souborů podporují vykreslování komentářů?**  
A: Většina hlavních formátů—včetně DOC/DOCX, XLS/XLSX, PPT/PPTX, PDF a mnoha dalších. Kompletní seznam najdete v [oficiální dokumentaci](https://docs.groupdocs.com/viewer/java/).

**Q: Můžu přizpůsobit stylování výstupního HTML?**  
A: Ano! Použijte `HtmlViewOptions.setEmbedResources(false)` pro práci s externími styly, nebo po vykreslení vložte vlastní CSS.

**Q: Jak zacházet s dokumenty chráněnými heslem?**  
A: Použijte třídu `LoadOptions`:
```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setPassword("your-password");
try (Viewer viewer = new Viewer("protected-doc.docx", loadOptions)) {
    // Render as usual
}
```

**Q: Je možné vykreslit jen konkrétní stránky?**  
A: Ano! Použijte přetíženou metodu `view()`:
```java
viewer.view(viewOptions, 1, 3, 5); // Renders only pages 1, 3, and 5
```

### Řešení problémů a výkon

**Q: Proč je vykreslování pomalé u velkých dokumentů?**  
A: Velké soubory vyžadují více času na zpracování. Zvažte:
- Vykreslování konkrétních stránek místo celého dokumentu  
- Použití externích zdrojů místo vložených  
- Zvýšení velikosti haldy JVM  
- Implementaci asynchronního zpracování  

**Q: Jak mohu sledovat průběh vykreslování?**  
A: GroupDocs Viewer neposkytuje vestavěné zpětné volání, ale můžete měřit čas operace:
```java
System.out.println("Starting render for: " + documentName);
long startTime = System.currentTimeMillis();
viewer.view(viewOptions);
long endTime = System.currentTimeMillis();
System.out.println("Rendering completed in: " + (endTime - startTime) + "ms");
```

**Q: Co se stane, pokud je zdrojový dokument poškozený?**  
A: GroupDocs Viewer vyhodí výjimku. Vždy implementujte robustní zpracování chyb:
```java
try (Viewer viewer = new Viewer(documentPath)) {
    viewer.view(viewOptions);
} catch (CorruptOrDamagedFileException e) {
    System.err.println("Document is corrupted: " + e.getMessage());
} catch (Exception e) {
    System.err.println("General error: " + e.getMessage());
}
```

### Obchodní a licenční otázky

**Q: Můžu použít GroupDocs Viewer v komerční aplikaci?**  
A: Ano, ale potřebujete komerční licenci. Bezplatná zkušební verze obsahuje evaluační vodoznaky, které je třeba odstranit pro produkční použití.

**Q: Existují nějaká omezení používání?**  
A: Samotná knihovna neklade žádná omezení, ale vaše licenční smlouva může mít specifické podmínky. Přezkoumejte své konkrétní podmínky.

**Q: Můžu redistribuovat aplikace, které zahrnují GroupDocs Viewer?**  
A: Obecně můžete distribuovat svou aplikaci, ale nesmíte redistribuovat samotnou knihovnu GroupDocs. Zkontrolujte podrobnosti licence.

## Další kroky a pokročilá témata

Gratulujeme! Nyní máte pevný základ v používání GroupDocs Viewer pro Java. Zde jsou některé oblasti, které můžete dále prozkoumat:

### Pokročilé funkce k prozkoumání
1. **Vodoznakování:** Přidání vlastních vodoznaků do vykreslených dokumentů  
2. **Extrahování informací o dokumentu:** Získání metadat, počtu stránek a detailů souboru  
3. **Vlastní prohlížeče:** Vytvoření specializovaných prohlížečů pro konkrétní typy dokumentů  
4. **Integrace cloudového úložiště:** Vykreslování přímo z AWS S3, Google Drive atd.

### Doporučená cesta učení
1. **Procvičujte s různými typy souborů:** Vyzkoušejte Excel, PowerPoint a PDF soubory  
2. **Vytvořte jednoduchý webový prohlížeč:** Vytvořte základní UI, který zobrazí vykreslené HTML  
3. **Prozkoumejte ekosystém GroupDocs:** Podívejte se na další produkty GroupDocs pro kompletní správu dokumentů  
4. **Připojte se ke komunitě:** Zapojte se do [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) pro tipy a podporu

## Získání pomoci a podpora

**Oficiální zdroje**
- [GroupDocs.Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://apireference.groupdocs.com/viewer/java)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)
- [GitHub Examples](https://github.com/groupdocs-viewer/GroupDocs.Viewer-for-Java)

**Komunitní zdroje**
- Stack Overflow (tag: `groupdocs-viewer`)
- Reddit programming communities
- Java developer forums and Discord servers

## Závěr

Úspěšně jste zvládli základy **převodu Word na HTML** při zachování komentářů pomocí GroupDocs Viewer pro Java. Od základního nastavení a konfigurace po pokročilé řešení problémů a ladění výkonu, nyní máte znalosti k implementaci robustního vykreslování dokumentů v reálných aplikacích.

**Klíčové poznatky**
- GroupDocs Viewer zjednodušuje složité úkoly vykreslování dokumentů  
- Zachování komentářů vyžaduje jediný konfigurační řádek (`setRenderComments(true)`)  
- Správné zpracování chyb a správa zdrojů jsou nezbytné pro produkci  
- Knihovna škáluje od jednoduchých utilit po enterprise řešení  

**Vaše další kroky**
1. **Spusťte příklady** s vlastními dokumenty  
2. **Vytvořte malý projekt**, který ukáže vykreslené HTML na webové stránce  
3. **Ponořte se hlouběji** do možností přizpůsobení, jako je vodoznakování a extrakce metadat  
4. **Sdílejte své zkušenosti** s komunitou, aby pomohli ostatním  

Začněte dnes budovat úžasné zážitky ze zobrazování dokumentů a pamatujte — komunita GroupDocs je vždy připravena pomoci, když to potřebujete!

---

**Last Updated:** 2026-01-28  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs