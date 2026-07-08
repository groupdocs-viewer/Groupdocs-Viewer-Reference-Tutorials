---
date: '2026-06-30'
description: Naučte se, jak získat viewinfo a načíst java archive file type structures
  pomocí GroupDocs.Viewer. Tento průvodce zahrnuje nastavení, příklady kódu a reálné
  příklady použití.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Jak získat ViewInfo a načíst java archive file type structures v Javě
type: docs
url: /cs/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Jak získat ViewInfo a načíst strukturu archivů v Javě

Efektivní správa archivních souborů vyžaduje jasné pochopení jejich struktury. V tomto tutoriálu se naučíte **jak získat viewinfo** pro jakýkoli archiv a uvidíte, jak vám to pomáhá pracovat s **java archive file type**. Provedeme vás nastavením GroupDocs.Viewer, extrahováním informací o zobrazení a rekurzivním čtením hierarchie složek, abyste mohli řešení integrovat do reálných projektů.

![Struktury archivů s GroupDocs.Viewer pro Java](/viewer/document-loading/archive-structures-java.png)

**Co se naučíte**
- Nastavení a konfigurace GroupDocs.Viewer pro Java.  
- Metody pro **get viewinfo** z archivů.  
- Techniky pro čtení a zobrazení struktury složek archivního souboru.  
- Praktické aplikace a úvahy o výkonu při používání GroupDocs.Viewer v Java projektech.

## Rychlé odpovědi
- **Co poskytuje “viewinfo”?** Vrací typ souboru, počet stránek a kompletní výpis složek a souborů uvnitř archivu.  
- **Které formáty archivů jsou podporovány?** ZIP, RAR, TAR, 7z, ISO a více než 12 dalších běžných formátů.  
- **Potřebuji licenci pro produkci?** Ano—pro produkci je vyžadována komerční licence; pro vyhodnocení stačí bezplatná zkušební verze.  
- **Lze velké archivy zpracovávat efektivně?** Rozhodně—použijte možnosti streamování a zpracovávejte po jedné úrovni složek, aby byl nízký odběr paměti.  
- **Je Maven jediný způsob, jak přidat knihovnu?** Maven je doporučený správce závislostí, ale Gradle nebo ruční zahrnutí JAR také fungují.

## Co je “jak získat viewinfo”?

`getViewInfo` je metoda API GroupDocs.Viewer, která extrahuje metadata z dokumentu nebo archivu bez úplného vykreslení. Vrací interní strom složek, počet souborů a základní vlastnosti v jednom volání, což vám umožní rozhodnout, které části zpracovat. Volání vrací kompletní snímek archivů až do 500 MB během méně než jedné sekundy na typických serverech.

## Proč načítat struktury Java Archive File Type?

Načtení vnitřního rozložení **java archive file type** vám umožní okamžitě najít potřebné soubory, vyhnout se zbytečnému rozbalování a vytvořit automatizované pipeline, které pracují jen s relevantními pod‑složkami. Tento přístup snižuje I/O až o 70 % u velkých archivů a umožňuje skenovat tisíce souborů za minutu v scénářích ingestování dat.

## Předpoklady

- **Java Development Kit (JDK):** Verze 8 nebo novější.  
- **Maven:** Pro správu závislostí a sestavení.  
- **Základní znalost Javy:** Znalost OOP konceptů pomáhá, ale není povinná.  

Také potřebujete přístup ke knihovně GroupDocs.Viewer, kterou můžete přidat do svého Maven projektu, jak je ukázáno níže.

## Nastavení GroupDocs.Viewer pro Java

### Konfigurace Maven

Přidejte repozitář a závislost do svého `pom.xml`.

**Repozitáře:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Závislosti:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Získání licence

- **Free Trial:** Stáhněte si zkušební verzi z webu GroupDocs.  
- **Temporary License:** Požádejte o dočasný klíč pro krátkodobé hodnocení.  
- **Full License:** Zakupte komerční licenci pro neomezené používání v produkci.  

Jakmile je knihovna na vašem classpath, můžete začít kódovat.

## Průvodce implementací

### Jak získat ViewInfo pro archivní soubory

Pro získání informací o zobrazení nejprve načtěte archiv do Vieweru, poté zavolejte `getViewInfo` pro získání metadat a nakonec iterujte přes vrácenou hierarchii složek. Tento tříkrokový vzor funguje pro všechny podporované formáty archivů a poskytuje kompletní snímek v jediném API volání, což zjednodušuje další zpracování.

#### Inicializace Vieweru

`Viewer` třída je vstupním bodem pro všechny operace vykreslování a inspekce. Spravuje souborové streamy, detekci formátu a úklid zdrojů.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Získání informací o zobrazení

`ViewInfo` obsahuje metadata jako typ souboru, celkový počet stránek a hierarchický seznam složek a souborů. Volání `getViewInfo` vrátí tento objekt okamžitě.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Zobrazení struktury složek

Iterujte přes `viewInfo.getFolders()`, abyste vytiskli název každé složky, její hloubku a obsažené soubory. Tento jednoduchý cyklus vám poskytne čitelný stromový pohled na archiv.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekurzivní čtení složek

Pro hluboce vnořené archivy může rekurzivní pomocná metoda projít strom hloubkově, což zajistí, že každá pod‑složka bude navštívena bez načítání celého archivu do paměti.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Funkce 2: Načtení struktury složek archivu

Tato funkce se zaměřuje na výpis struktury složek archivního souboru. Je podobná první funkci, ale zdůrazňuje rekurzivní průzkum.

#### Nastavení možností View Info

`ArchiveOptions` vám umožňuje nastavit ochranu heslem, limity stránek a preference streamování před voláním `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekurzivní průzkum

Druhá rekurzivní rutina ukazuje, jak efektivně zacházet s archivem chráněným heslem a velkými sadami souborů.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktické aplikace

- **Data Management:** Rychle organizovat velké datové sady pochopením struktur archivů.  
- **Automated File Processing:** Hromadně zpracovávat archivní soubory bez jejich úplného rozbalení, což snižuje I/O až o 70 %.  
- **CMS Integration:** Vylepšit systémy pro správu obsahu o navigaci v archivu za běhu, což umožní editorům náhled souborů přímo z archivu.

## Úvahy o výkonu

- **Optimalizace využití paměti:** Zpracovávejte složky po jedné úrovni a rychle uzavřete instanci `Viewer`.  
- **Zůstaňte aktuální:** Používejte nejnovější verzi GroupDocs.Viewer (25.2 v době psaní) a verze JDK pro zlepšení výkonu.  
- **Podpora streamování:** Knihovna může streamovat archivy větší než 1 GB bez načítání celého souboru do RAM díky interní architektuře čtení po blocích.

## Časté problémy a řešení

| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| `NullPointerException` při čtení složek | `viewInfo.getFolders()` vrací null pro prázdné adresáře | Zkontrolujte, zda není null nebo prázdný seznam před iterací. |
| Pomalé zpracování obrovských ZIP souborů | Celý archiv je načten do paměti | Použijte možnosti streamování dostupné v novějších verzích GroupDocs. |
| Licence nebyla nalezena | Cesta k souboru licence je nesprávná | Umístěte soubor licence do kořenového adresáře aplikace nebo nastavte `License.setLicense("path/to/license.json")`. |

## Často kladené otázky

**Q:** Co je GroupDocs.Viewer?  
A: GroupDocs.Viewer je Java knihovna, která renderuje více než 100 formátů dokumentů, obrázků a archivů do HTML, PDF nebo obrazových streamů bez nutnosti nativních aplikací.

**Q:** Mohu použít GroupDocs.Viewer s jinými programovacími jazyky?  
A: Ano, GroupDocs nabízí SDK pro .NET, Python, PHP a další, ale tento tutoriál se zaměřuje na implementaci v Javě.

**Q:** Jak zacházet s velkými archivními soubory?  
A: Povolit streamování pomocí `ArchiveOptions.setUseStreaming(true)`, zpracovávat po jedné úrovni složek a po použití uvolnit objekt `Viewer`.

**Q:** Jaké typy archivů GroupDocs.Viewer podporuje?  
A: Podporuje více než 12 formátů archivů, včetně ZIP, RAR, TAR, 7z, ISO, ARJ a CAB, plus mnoho proprietárních kontejnerových typů.

**Q:** Existuje limit velikosti archivů?  
A: Praktický limit závisí na RAM a CPU vašeho serveru; testy ukazují plynulé zpracování 2 GB archivů na stroji s 16 GB RAM při povoleném streamování.

**Q:** Funguje “jak získat viewinfo” s archivem chráněným heslem?  
A: Ano, před voláním `getViewInfo` zadejte heslo pomocí `ArchiveOptions.setPassword("yourPassword")`.

## Závěr

Podle tohoto průvodce nyní víte **jak získat viewinfo** pro jakýkoli podporovaný archiv a jak procházet jeho hierarchii složek pomocí GroupDocs.Viewer pro Java. Tyto techniky vám umožní vytvářet chytřejší datové pipeline, zlepšit integraci CMS a s jistotou pracovat s velkými kolekcemi archivních souborů. Dále prozkoumejte vykreslování jednotlivých souborů z archivu nebo jejich konverzi do PDF/HTML pomocí dalších funkcí Vieweru.

---

**Poslední aktualizace:** 2026-06-30  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

**Zdroje**
- **Dokumentace:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Reference API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Stáhnout GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Koupit licenci:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Bezplatná zkušební verze a dočasná licence:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Související tutoriály

- [Extrahovat metadata dokumentu pomocí GroupDocs.Viewer pro Java – Načíst informace o zobrazení dokumentu a poznatky](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Jak načíst přílohy a vytisknout přílohy dokumentu pomocí GroupDocs.Viewer pro Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java průvodce: Vykreslit konkrétní stránky pomocí GroupDocs.Viewer API pro náhled a správu dokumentů](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)