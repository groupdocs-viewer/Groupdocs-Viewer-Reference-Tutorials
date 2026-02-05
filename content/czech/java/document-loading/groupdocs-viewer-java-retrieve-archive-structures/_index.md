---
date: '2026-02-05'
description: Naučte se, jak získat viewinfo a načíst struktury souborů typu Java archiv
  pomocí GroupDocs.Viewer. Tento průvodce zahrnuje nastavení, ukázky kódu a reálné
  příklady použití.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Jak získat ViewInfo a načíst struktury archivu v Javě
type: docs
url: /cs/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Jak získat ViewInfo a načíst struktury archivů v Javě

Efektivní správa archivních souborů vyžaduje jasné pochopení jejich struktury. V tomto tutoriálu se naučíte **jak získat viewinfo** pro jakýkoli archiv a uvidíte, jak vám to pomáhá pracovat s **typem archivního souboru Java**. Provedeme vás nastavením GroupDocs.Viewer, získáním informací o zobrazení a rekurzivním čtením hierarchie složek, abyste mohli řešení integrovat do reálných projektů.

![Struktury archivů s GroupDocs.Viewer pro Javu](/viewer/document-loading/archive-structures-java.png)

**Co se naučíte**
- Nastavení a konfigurace GroupDocs.Viewer pro Java.  
- Metody k **získání viewinfo** z archivů.  
- Techniky pro čtení a zobrazení struktury složek archivního souboru.  
- Praktické aplikace a úvahy o výkonu při používání GroupDocs.Viewer v Java projektech.

## Rychlé odpovědi
- **Co poskytuje “viewinfo”?** Vrací typ souboru, počet stránek a výpis složek v archivu.  
- **Které archivy jsou podporovány?** ZIP, RAR, TAR a další běžné formáty.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu zpracovávat velké archivy?** Ano – použijte streamování a správnou správu paměti, jak je ukázáno níže.  
- **Je Maven vyžadován?** Maven je doporučený způsob správy závislosti GroupDocs.Viewer.

## Co je “jak získat viewinfo”?
`getViewInfo` je metoda v API GroupDocs.Viewer, která extrahuje metadata o dokumentu nebo archivu bez vykreslení celého obsahu. Pro archivy odhaluje vnitřní strom složek, což vám umožní rozhodnout, které části vykreslit nebo dále zpracovat.

## Proč načítat struktury archivních souborů Java?
Porozumění vnitřnímu uspořádání **typu archivního souboru Java** (např. ZIP, RAR) vám umožní:
- Rychle najít potřebné soubory bez rozbalení všeho.  
- Vytvořit automatizované pipeline, které zpracovávají jen relevantní pod‑složky.  
- Integrovat navigaci v archivu do systémů pro správu obsahu nebo ingestování dat.

## Předpoklady

- **Java Development Kit (JDK):** Verze 8 nebo novější.  
- **Maven:** Pro správu závislostí a sestavení.  
- **Základní znalost Javy:** Znalost OOP konceptů pomáhá, ale není povinná.

Také potřebujete přístup k knihovně GroupDocs.Viewer, kterou můžete přidat do svého Maven projektu, jak je uvedeno níže.

## Nastavení GroupDocs.Viewer pro Java

### Maven konfigurace

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

- **Bezplatná zkušební verze:** Stáhněte si zkušební verzi z webu GroupDocs.  
- **Dočasná licence:** Požádejte o dočasný klíč pro krátkodobé hodnocení.  
- **Plná licence:** Zakupte komerční licenci pro neomezené používání v produkci.

Jakmile je knihovna na vaší classpath, můžete začít programovat.

## Průvodce implementací

### Jak získat ViewInfo pro archivní soubory

Tato sekce ukazuje přesné kroky pro volání `getViewInfo` a čtení hierarchie složek.

#### Inicializace Vieweru

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Získání informací o zobrazení

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Zobrazení struktury složek

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekurzivní čtení složek

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

#### Nastavení možností ViewInfo

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekurzivní průzkum

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktické aplikace

1. **Správa dat:** Rychle organizovat velké datové sady pochopením struktur archivů.  
2. **Automatizované zpracování souborů:** Hromadně zpracovávat archivované soubory bez jejich úplného rozbalení.  
3. **Integrace CMS:** Vylepšit systémy pro správu obsahu o dynamickou navigaci v archivu.

## Úvahy o výkonu

- **Optimalizace využití paměti:** Zpracovávejte složky po jedné úrovni a okamžitě uzavřete instanci `Viewer`.  
- **Zůstaňte aktualizováni:** Používejte nejnovější verzi GroupDocs.Viewer a JDK pro zlepšení výkonu.

## Časté problémy a řešení

| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| `NullPointerException` při čtení složek | `viewInfo.getFolders()` vrací null pro prázdné adresáře | Zkontrolujte, zda není null nebo prázdný seznam před iterací. |
| Pomalé zpracování obrovských ZIP souborů | Celý archiv je načten do paměti | Použijte možnosti streamování dostupné v novějších verzích GroupDocs. |
| Licence nebyla nalezena | Cesta k souboru licence je nesprávná | Umístěte soubor licence do kořenového adresáře aplikace nebo nastavte `License.setLicense("path/to/license.json")`. |

## Často kladené otázky

**Q: Co je GroupDocs.Viewer?**  
A: Jedná se o výkonnou Java knihovnu pro vykreslování dokumentů, včetně archivů, do formátů jako HTML, obrázek a PDF.

**Q: Mohu použít GroupDocs.Viewer s jinými programovacími jazyky?**  
A: Ano, GroupDocs nabízí SDK pro různé platformy, ale tento tutoriál se zaměřuje na implementaci v Javě.

**Q: Jak zacházet s velkými archivními soubory?**  
A: Používejte efektivní postupy správy paměti a v případě potřeby zvažte rozdělení archivů.

**Q: Jaké typy archivů GroupDocs.Viewer podporuje?**  
A: Podporuje různé formáty včetně ZIP, RAR, TAR a dalších.

**Q: Existuje limit na velikost archivů, které mohu zpracovat?**  
A: Limity závisí na zdrojích vašeho systému. Otestujte ve vašem cílovém prostředí, abyste určili praktické limity.

**Q: Funguje “jak získat viewinfo” s archivem chráněným heslem?**  
A: Ano, můžete před voláním `getViewInfo` zadat heslo pomocí `ArchiveOptions.setPassword("yourPassword")`.

## Závěr

Díky tomuto průvodci nyní víte **jak získat viewinfo** pro jakýkoli podporovaný archiv a jak procházet jeho hierarchii složek pomocí GroupDocs.Viewer pro Java. Tyto techniky vám umožní vytvářet chytřejší pipeline pro zpracování dat, zlepšit integraci CMS a s jistotou pracovat s velkými kolekcemi archivovaných souborů. Dále můžete zkoumat vykreslování jednotlivých souborů z archivu nebo jejich převod do PDF/HTML pomocí dalších funkcí Vieweru.

---

**Poslední aktualizace:** 2026-02-05  
**Testováno s:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

**Zdroje**
- **Dokumentace:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Reference API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Stáhnout GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Zakoupit licenci:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Bezplatná zkušební verze a dočasná licence:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)