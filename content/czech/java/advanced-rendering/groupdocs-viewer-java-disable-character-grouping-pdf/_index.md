---
date: '2026-03-22'
description: Naučte se, jak generovat HTML z PDF a zakázat seskupování znaků pomocí
  GroupDocs Viewer pro Javu pro přesné zobrazení textu.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Generovat HTML z PDF a zakázat seskupování – GroupDocs Java
type: docs
url: /cs/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Generovat HTML z PDF a zakázat seskupování pomocí GroupDocs Viewer pro Java

V mnoha projektech potřebujete **generovat HTML z PDF**, přičemž zachovat každý glyf přesně na svém místě. To je zvláště pravda u složitých skriptů, starověkých jazyků nebo právních dokumentů, kde může jediný špatně umístěný znak změnit význam. V tomto tutoriálu vás provedeme kompletním procesem převodu PDF do HTML pomocí GroupDocs Viewer pro Java a ukážeme vám **jak zakázat seskupování**, aby byl každý znak považován za samostatný prvek.

![Přesné techniky vykreslování s GroupDocs.Viewer pro Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Rychlé odpovědi
- **Co dělá „zakázat seskupování“?** Vynutí, aby vykreslovací engine zacházel s každým znakem jako s samostatným prvkem, čímž zachová přesné rozložení.  
- **Která možnost API to řídí?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Potřebuji licenci?** Zkušební verze funguje pro testování, ale pro produkci je vyžadována plná licence.  
- **Mohu současně generovat HTML z PDF?** Ano—použijte `HtmlViewOptions` k vytvoření HTML výstupu při zakázání seskupování.  
- **Je tato funkce omezena na PDF?** Je primárně určena pro PDF, ale prohlížeč podporuje mnoho dalších formátů.

## Úvod

Při práci s PDF dokumenty je přesnost vykreslování klíčová—zejména při zacházení se složitými textovými strukturami, jako jsou hieroglyfy nebo jazyky, které vyžadují přesné znakovou reprezentaci. Funkce „Seskupování znaků“ často způsobuje problémy nesprávným seskupováním znaků, což vede k nesprávnému výkladu obsahu dokumentu. To může být zvláště problematické pro uživatele, kteří potřebují přesnou replikaci rozložení textu ve svých dokumentech.

### Předpoklady

Předtím, než se ponoříte do implementace kódu, ujistěte se, že splňujete následující požadavky:
- **Knihovny a závislosti**: Budete potřebovat GroupDocs.Viewer pro Java verze 25.2 nebo novější.  
- **Nastavení prostředí**: Ujistěte se, že máte nainstalovaný Java Development Kit (JDK) a vaše IDE je nastavené pro práci s Maven projekty.  
- **Předpoklady znalostí**: Základní znalost programování v Javě, zejména práce s cestami k souborům a používání externích knihoven.

## Jak generovat HTML z PDF pomocí GroupDocs Viewer

Generování HTML z PDF je dvoustupňový proces: nejprve nakonfigurujete prohlížeč, poté vykreslíte dokument. Klíčové je vypnout seskupování znaků před vykreslením, aby výstupní HTML odrážel původní rozložení PDF znak po znaku.

### Nastavení GroupDocs.Viewer pro Java

#### Instalace pomocí Maven

Nejprve integrujte potřebnou knihovnu do svého projektu. Přidejte následující konfiguraci do souboru `pom.xml`:

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

#### Získání licence

Pro plné využití GroupDocs.Viewer zvažte získání licence:
- **Bezplatná zkušební verze**: Začněte s bezplatnou zkušební verzí k otestování funkcí.  
- **Dočasná licence**: Požádejte o dočasnou licenci, pokud potřebujete více času.  
- **Nákup**: Pro dlouhodobé projekty se doporučuje zakoupit licenci.

#### Základní inicializace a nastavení

Níže je připravený úryvek kódu, který ukazuje celý pracovní postup—od nastavení výstupní složky po vykreslení PDF jako HTML při zakázání seskupování znaků:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Průvodce implementací

#### Funkce: Zakázat seskupování znaků

Níže rozebíráme každý řádek příkladu, abyste pochopili **proč** to děláme a **jak** to přispívá k generování HTML z PDF bez nechtěného sloučení znaků.

##### Krok 1: Definovat výstupní adresář  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Proč?** To zajišťuje, že vykreslené HTML soubory jsou uloženy v samostatné složce, což usnadňuje jejich pozdější vyhledání a správu.

##### Krok 2: Nakonfigurovat formát cesty k souboru  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Proč?** Použití zástupného symbolu (`{0}`) umožňuje prohlížeči vytvořit samostatný HTML soubor pro každou stránku PDF, čímž udržuje výstup organizovaný.

##### Krok 3: Inicializovat HTML View Options  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Proč?** Vložené zdroje balí obrázky, fonty a CSS přímo s každou HTML stránkou, což je ideální pro webové prohlížeče nebo e‑learningové platformy.

##### Krok 4: Zakázat seskupování znaků  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Proč?** Toto je klíčový řádek, který říká vykreslovacímu enginu, aby **neslučoval** sousední znaky, což zaručuje, že generované HTML odráží přesné umístění glyfů ze zdrojového PDF.

##### Krok 5: Vykreslit dokument  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Proč?** Zabalit `Viewer` do bloku try‑with‑resources zaručuje, že všechny nativní zdroje jsou automaticky uvolněny, čímž se předchází únikům paměti v dlouhodobých aplikacích.

### Generování Java HTML z PDF bez seskupování

Třída `HtmlViewOptions` vám umožní vytvořit **HTML z PDF** při zachování každého znaku odděleně. To je zvláště užitečné, když potřebujete vložit vykreslené stránky do webového portálu nebo e‑learningové platformy, kde je důležité přesné umístění glyfů.

### Časté problémy a řešení

- **FileNotFoundException** – Zkontrolujte znovu cestu, kterou předáváte do `new Viewer(...)`. Použijte absolutní cesty nebo `Path.of(...)` pro přehlednost.  
- **Write Permissions** – Ujistěte se, že výstupní adresář je zapisovatelný procesem Java; na Linuxu možná budete muset upravit oprávnění složky (`chmod 775`).  
- **Version Mismatch** – Volba `setDisableCharsGrouping` je k dispozici od verze 25.2. Ověřte, že váš `pom.xml` obsahuje správnou verzi.  

### Praktické aplikace

1. **Zachování jazyků** – Ideální pro vykreslování dokumentů v čínštině, japonštině, arabštině nebo starověkých skriptech, kde rozestup znaků nese význam.  
2. **Právní a finanční dokumenty** – Zajišťuje přesnou replikaci textu pro dokumenty s vysokými požadavky na shodu.  
3. **Vzdělávací materiály** – Perfektní pro učebnice, které obsahují složité diagramy, anotace nebo vícejazyčný obsah.

### Úvahy o výkonu

- **Optimalizace využití zdrojů** – Velké PDF mohou spotřebovat značnou paměť. Zvažte zpracování stránek po dávkách a včasné uvolňování instancí `Viewer`.  
- **Správa paměti v Javě** – Nastavte velikost haldy JVM (`-Xmx2g` nebo vyšší), pokud očekáváte zpracování PDF s několika stovkami stránek.  
- **Paralelní vykreslování** – Pro hromadné konverze vytvořte samostatná vlákna, každé s vlastní instancí `Viewer`, abyste využili vícejádrové procesory.

## Často kladené otázky

**Q:** *Proč bych vůbec potřeboval zakázat seskupování znaků?*  
**A:** Zakázání seskupování zabraňuje vykreslovacímu enginu sloučovat znaky, které patří k odlišným glyfům, což je nezbytné pro skripty, kde rozestup a pořadí nesou význam.

**Q:** *Je nastavení `setDisableCharsGrouping` použitelné jen pro výstup HTML?*  
**A:** Ne, ovlivňuje podkladový PDF vykreslovací engine, takže jakýkoli výstupní formát (HTML, PNG, JPEG atd.) bude odrážet změnu.

**Q:** *Mohu toto nastavení kombinovat s vlastními fonty?*  
**A:** Ano—načtěte své vlastní fonty před inicializací `Viewer` a pravidlo seskupování bude i nadále platit.

**Q:** *Ovlivňuje zakázání seskupování výkon?*  
**A:** Mírně, protože engine zpracovává každý znak samostatně, ale dopad je pro většinu dokumentů minimální.

**Q:** *Existuje způsob, jak přepínat seskupování na úrovni jednotlivých stránek?*  
**A:** V současnosti je volba globální pro každou instanci `PdfOptions`; pokud potřebujete smíšené chování, musíte použít samostatné instance `Viewer` pro různé stránky.

## Zdroje

- [GroupDocs Dokumentace](https://docs.groupdocs.com/viewer/java/)
- [Reference API](https://reference.groupdocs.com/viewer/java/)
- [Stáhnout GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Koupit licenci](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/java/)
- [Žádost o dočasnou licenci](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-03-22  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs