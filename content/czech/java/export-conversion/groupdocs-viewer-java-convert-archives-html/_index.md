---
date: '2026-02-23'
description: Naučte se, jak nastavit počet položek na stránku, vložit HTML zdroje
  a hromadně převádět archivy na jednostránkové nebo vícestránkové HTML pomocí GroupDocs.Viewer
  Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Nastavit počet položek na stránku: Převést archivy do HTML pomocí GroupDocs.Viewer
  Java'
type: docs
url: /cs/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Nastavit položky na stránku: Převod archivů do HTML pomocí GroupDocs.Viewer Java

Převod archivních souborů, jako jsou ZIP nebo RAR, do web‑přátelského HTML je častá potřeba, když chcete sdílet nebo prohlížet dokumenty přímo v prohlížeči. V tomto průvodci se naučíte **jak nastavit položky na stránku** při vykreslování archivů, jak vložit zdroje HTML pro samostatný výstup a jak efektivně hromadně převádět archivy pomocí GroupDocs.Viewer Java.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Rychlé odpovědi
- **Co řídí „set items per page“?** Určuje, kolik souborů nebo složek z archivu se zobrazí na každé vygenerované HTML stránce.  
- **Mohu vložit obrázky a CSS přímo do HTML?** Ano – použijte možnost `forEmbeddedResources` pro vložení zdrojů HTML.  
- **Je hromadný převod možný?** Rozhodně; můžete projít kolekci archivů a vykreslit každý s těmi samými nastaveními.  
- **Potřebuji Maven pro použití GroupDocs.Viewer?** Ano, přidejte závislost `maven groupdocs viewer` jak je ukázáno níže.  
- **Jaké výstupní formáty jsou podporovány?** Single‑page HTML Java i multi‑page HTML Java jsou k dispozici.

## Co je „set items per page“ v GroupDocs.Viewer?
Nastavení **set items per page** patří mezi možnosti vykreslování archivů. Říká prohlížeči, kolik položek archivu (souborů nebo složek) má být zobrazeno na každé HTML stránce při generování více‑stránkového HTML dokumentu. Úprava této hodnoty vám pomůže vyvážit velikost stránky a rychlost navigace, zejména u velkých archivů.

## Proč vložit zdroje HTML?
Vložení zdrojů (obrázků, CSS, fontů) přímo do souboru HTML vytvoří jediný, přenosný dokument, který lze otevřít bez externích souborů. To je ideální pro e‑mailové přílohy, offline prohlížení nebo vložení výstupu do jiných webových stránek.

## Předpoklady
- **Požadované knihovny:** Zahrňte GroupDocs.Viewer verze 25.2 nebo novější.  
- **Prostředí:** Nainstalovaný a nakonfigurovaný Java Development Kit (JDK).  
- **Znalosti:** Základní Java a správa Maven závislostí.  

## Nastavení Maven GroupDocs Viewer
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer nabízí **odkaz na bezplatnou zkušební verzi**, dočasnou licenci nebo možnost plné zakoupení. Vyberte tu, která vyhovuje časovému plánu vašeho projektu.

### Základní inicializace
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Jak vykreslit archivy do jednostránkového HTML

### Krok 1: Definujte výstupní adresář
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Nastavte název souboru pro jednostránkový výstup
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Krok 3: Inicializujte Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Krok 4: Nakonfigurujte možnosti vykreslování (vložit zdroje HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Vykreslete jako jednostránkový výstup
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Jak vykreslit archivy do více‑stránkového HTML a nastavit položky na stránku

### Krok 1: Znovu použijte výstupní adresář
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Definujte formát názvu souboru pro více stránek
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Krok 3: Znovu inicializujte Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Krok 4: Nakonfigurujte možnosti více stránek (vložit zdroje HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Nastavte položky na stránku (hlavní klíčové slovo v akci)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktické aplikace
- **Systémy správy dokumentů:** Přidejte funkci náhledu archivu bez instalace dalších prohlížečů.  
- **Webové portály:** Nabídněte uživatelům rychlý způsob prozkoumání balíčkových dokumentů bez stahování.  
- **Nástroje pro spolupráci:** Umožněte týmům kontrolovat sdílené archivy přímo v prohlížeči.

## Úvahy o výkonu
- **Správa zdrojů:** Sledujte využití paměti; zvažte ladění garbage‑collectoru JVM pro velké dávky.  
- **Hromadný převod archivů:** Procházejte seznam archivních souborů a volajte stejnou logiku vykreslování pro maximalizaci propustnosti.  
- **Strategie cachování:** Ukládejte vykreslené HTML do cache, pokud je stejný archiv často přistupován.

## Často kladené otázky
**Q: Co je GroupDocs.Viewer Java?**  
A: Univerzální knihovna pro vykreslování dokumentů—včetně archivů—do formátů jako HTML, PDF a obrázky.

**Q: Jak mohu získat bezplatnou zkušební verzi GroupDocs.Viewer?**  
A: Navštivte [odkaz na bezplatnou zkušební verzi](https://releases.groupdocs.com/viewer/java/), kde si můžete stáhnout a vyzkoušet.

**Q: Mohu převádět i jiné typy dokumentů než archivy?**  
A: Ano, prohlížeč podporuje PDF, Word, Excel a mnoho dalších formátů.

**Q: Co mám dělat, když je vykreslování pomalé?**  
A: Snižte počet položek na stránku, povolte streamování nebo zpracovávejte archivy v menších dávkách.

**Q: Kde mohu získat pomoc nebo podporu?**  
A: Obrátit se můžete prostřednictvím [fóra podpory](https://forum.groupdocs.com/c/viewer/9).

**Q: Je možné vložit CSS a obrázky přímo do HTML?**  
A: Rozhodně—použijte `HtmlViewOptions.forEmbeddedResources`, jak je ukázáno v příkladech.

**Q: Jak hromadně převést složku archivů?**  
A: Procházejte každý soubor pomocí `for` smyčky a použijte stejnou konfiguraci `Viewer` a `HtmlViewOptions` pro každou iteraci.

## Zdroje
- **Dokumentace:** Prozkoumejte podrobněji funkce v [GroupDocs dokumentaci](https://docs.groupdocs.com/viewer/java/).  
- **Reference API:** Prozkoumejte kompletní API na [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Stáhnout:** Získejte nejnovější binární soubory ze [stránky ke stažení](https://releases.groupdocs.com/viewer/java/).  
- **Nákup a licence:** Prohlédněte si možnosti na [stránce nákupu](https://purchase.groupdocs.com/buy).  
- **Podpora a komunita:** Připojte se k diskuzím na [GroupDocs fóru](https://forum.groupdocs.com/c/viewer/9).

---

**Poslední aktualizace:** 2026-02-23  
**Testováno s:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs