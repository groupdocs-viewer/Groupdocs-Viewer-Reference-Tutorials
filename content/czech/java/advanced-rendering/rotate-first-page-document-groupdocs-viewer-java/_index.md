---
date: '2026-03-29'
description: Naučte se, jak v Javě pomocí GroupDocs Viewer otočit stránku o 90 stupňů,
  včetně nastavení, kódu a tipů na výkon.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Otočte stránku o 90 stupňů pomocí GroupDocs Viewer pro Java
type: docs
url: /cs/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Otočit stránku o 90 stupňů pomocí GroupDocs Viewer pro Java

Když potřebujete **otočit stránku o 90 stupňů** v dokumentu — ať už jde o PDF, Word soubor nebo tabulku — provedení toho programově šetří čas a eliminuje ruční chyby. V tomto pokročilém průvodci vás provedeme přesné kroky k otočení první stránky libovolného podporovaného dokumentu pomocí **GroupDocs Viewer for Java**. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do svých projektů.  
Také se podíváme, proč je otáčení stránek v Javě důležité, na běžné scénáře, kde tato technika vyniká, a jak udržet operaci nenáročnou.

![Otočit první stránku dokumentu pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Rychlé odpovědi
- **Co znamená „otočit stránku o 90 stupňů“?** Otočí vybranou stránku po směru hodinových ručiček o čtvrt otáčky.  
- **Která knihovna provádí otáčení?** GroupDocs Viewer for Java poskytuje metodu `rotatePage`.  
- **Mohu otáčet PDF stránky pomocí Javy?** Ano — použijte stejný volání `rotatePage`; funguje pro PDF, DOCX, XLSX a další.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; placená licence je vyžadována pro produkci.  
- **Je operace náročná na paměť?** Ne, pokud rychle uzavřete instanci `Viewer`; viz tipy na výkon níže.

## Co je „otočit stránku o 90 stupňů“?
Otočení stránky o 90 stupňů přesměruje stránku z portrétu na krajinu (nebo naopak) bez změny podkladového obsahu. To je zvláště užitečné pro prezentace, tisk grafiky určené pouze na krajinu nebo opravu naskenovaných dokumentů, které byly zachyceny šikmo.

## Proč otáčet stránky programově pomocí GroupDocs Viewer pro Java?
GroupDocs Viewer abstrahuje složitosti práce s desítkami formátů souborů. Umožňuje vám aplikovat transformace na úrovni stránky — jako je otáčení — a přitom zachovat původní soubor nedotčený. API je plynulé, thread‑safe a funguje na jakémkoli runtime Java 8+, což z něj činí spolehlivou volbu pro automatizaci na úrovni podniku.

## Požadavky
- **GroupDocs.Viewer for Java** (nejnovější verze)
- **JDK 8** nebo novější
- **Maven** (nebo Gradle) pro správu závislostí
- IDE, jako je IntelliJ IDEA nebo Eclipse
- Základní znalost Java I/O

## Nastavení GroupDocs.Viewer pro Java
Přidejte repozitář GroupDocs a závislost do vašeho `pom.xml`. Tento úryvek zůstává nezměněn oproti původnímu tutoriálu:

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

### Získání licence
- **Free trial** – stáhněte z webu GroupDocs.  
- **Temporary license** – požádejte, pokud potřebujete prodloužené zkušební období.  
- **Full license** – zakupte pro produkční nasazení.

### Základní inicializace Vieweru
Následující kód ukazuje minimální způsob vytvoření instance `Viewer`. Uchovejte jej přesně tak, jak je uvedeno:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Jak otočit PDF stránku v Javě pomocí GroupDocs Viewer
I když API funguje napříč mnoha formáty, PDF je nejčastějším případem použití pro otáčení stránek. Používá se stejná metoda `rotatePage`, takže stačí nasměrovat Viewer na PDF soubor a zadat číslo stránky.

## Implementace krok za krokem: Otočit první stránku o 90 stupňů

### 1. Importujte požadované balíčky
Tyto importy vám poskytují přístup k možnostem renderování PDF a výčtu rotace.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definujte výstupní umístění a vytvořte Viewer
Nahraďte zástupné cesty vašimi skutečnými adresáři.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Nakonfigurujte možnosti zobrazení PDF a aplikujte otáčení
Metoda `rotatePage` přijímá číslo stránky (číslování od 1) a hodnotu výčtu `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Vykreslete dokument
Nakonec zavolejte `view` pro vygenerování otočeného PDF.

```java
viewer.view(viewOptions);
```

#### Jak to funguje
- **PdfViewOptions** říká Vieweru, aby výstupem byl PDF soubor.  
- **rotatePage(int, Rotation)** otáčí pouze stránku, kterou specifikujete, a zbytek zůstane nedotčen.  
- Metoda podporuje `ON_90_DEGREE`, `ON_180_DEGREE` a `ON_270_DEGREE`.

## Časté problémy a řešení
| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| **FileNotFoundException** | Nesprávná cesta nebo chybějící složka | Ověřte, že `YOUR_OUTPUT_DIRECTORY` a `YOUR_DOCUMENT_DIRECTORY` existují a jsou čitelné. |
| **Unsupported file format** | Pokus o otáčení formátu, který Viewer nepodporuje | Zkontrolujte stránku [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Použití špatného čísla stránky (číslování od 0) | Pamatujte, že `rotatePage` používá **číslování od 1**. |
| **Out‑of‑memory errors on large docs** | Renderování mnoha velkých souborů v jednom vlákně | Zpracovávejte dokumenty sekvenčně nebo použijte thread pool s omezenou souběžností. |

## Praktické aplikace

1. **Úpravy prezentací** – Převést portrétní snímek na krajinu za běhu.  
2. **Hromadná oprava dokumentů** – Automatizovat opravu naskenovaných PDF, které byly zachyceny šikmo.  
3. **Výstup připravený k tisku** – Zajistit, aby grafika v krajině tiskla správně na papír orientovaný na portrét.

## Tipy pro výkon

- **Uzavřete zdroje rychle** – Blok `try‑with‑resources` automaticky uvolní `Viewer`.  
- **Dávkové zpracování** – Při práci s mnoha soubory znovu použijte jednu instanci `Viewer` na vlákno, aby se snížila zátěž.  
- **Sledujte paměť** – Pro dokumenty větší než 100 MB zvažte streamování výstupu na disk místo udržování v paměti.

## Často kladené otázky

**Q: Mohu otáčet více stránek najednou?**  
A: Ano — zavolejte `rotatePage()` pro každé číslo stránky, kterou potřebujete otočit.

**Q: Existuje způsob, jak po renderování otáčení vrátit zpět?**  
A: Ne přímo. Museli byste dokument znovu renderovat bez možností otáčení.

**Q: Které formáty souborů podporují otáčení stránek v GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX a mnoho dalších formátů uvedených v oficiální dokumentaci.

**Q: Jak mohu automaticky otáčet stránky ve skupině dokumentů?**  
A: Zabalte kód do smyčky, která prochází kolekci cest k souborům a na každém použije stejnou logiku `rotatePage`.

**Q: Jaká je nejlepší praxe pro zpracování chyb během otáčení?**  
A: Uzavřete používání Vieweru do bloku `try‑catch`, zaznamenejte výjimku a volitelně pokračujte ve zpracování dalšího souboru.

## Zdroje

- **Dokumentace**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Stáhnout**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Koupit**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Bezplatná zkušební verze**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Dočasná licence**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Podpora**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-03-29  
**Testováno s:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs