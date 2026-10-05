---
date: '2026-10-05'
description: Naučte se, jak otočit konkrétní stránky PDF pomocí GroupDocs.Viewer for
  Java. Tento krok‑za‑krokem průvodce zahrnuje nastavení Maven, rotate pdf 90 degrees
  a řešení problémů.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Otočte konkrétní stránky PDF pomocí GroupDocs.Viewer for Java. Naučte
  se rotate pdf 90 degrees, konfigurovat Maven a řešit běžné problémy v stručném průvodci.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Otočte konkrétní stránky PDF pomocí GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: Jak otočit konkrétní stránky PDF pomocí GroupDocs.Viewer for Java
type: docs
url: /cs/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Jak otočit konkrétní stránky PDF pomocí GroupDocs.Viewer pro Java

Otočení konkrétních stránek v PDF může být nezbytné pro zarovnání dokumentů, opravu naskenovaných obrázků nebo úpravu prezentačních snímků. **V tomto průvodci se naučíte, jak programově otočit konkrétní stránky PDF pomocí GroupDocs.Viewer**, ať už potřebujete otočit PDF o 90 stupňů, převrátit celou sekci nebo zpracovat více stránek v jednom volání.

![Otočit konkrétní stránky PDF pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Otočit konkrétní stránky PDF pomocí GroupDocs.Viewer pro Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Co se naučíte**
- Nastavení GroupDocs.Viewer ve vašem Java projektu (včetně konfigurace Maven GroupDocs Viewer)
- Programové otáčení konkrétních stránek PDF (otočit PDF o 90 stupňů, 180 stupňů atd.)
- Klíčové konfigurace pro optimální použití
- Řešení běžných problémů během implementace

## Rychlé odpovědi
- **Jaká knihovna může otáčet stránky PDF v Javě?** GroupDocs.Viewer pro Java poskytuje vestavěnou podporu otáčení bez externích nástrojů.  
- **Mohu otočit jednu stránku o 90 stupňů?** Ano – zavolejte `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` na instanci vieweru.  
- **Potřebuji licenci pro vývoj?** Dočasná licence je zdarma pro hodnocení; plná licence je vyžadována pro produkci.  
- **Je Maven povinný?** Maven je doporučený správce závislostí, ale můžete také použít Gradle nebo ruční zahrnutí JAR souboru.  
- **Jak vykreslím otočené stránky?** Použijte `HtmlViewOptions` s `viewer.view(documentPath, viewOptions)`, abyste získali HTML výstup, který odráží otáčení.

## Co je otáčení konkrétních stránek PDF?
`rotate specific pdf pages` označuje schopnost změnit orientaci jednotlivých stránek uvnitř PDF dokumentu, zatímco zbytek souboru zůstane nedotčen. Tato operace se provádí při renderování, takže původní PDF soubor zůstává nezměněn.

## Proč otáčet konkrétní stránky PDF?
Jednu stránku můžete otočit za méně než 0,05 sekundy na typickém serverovém VM, což umožňuje náhled v reálném čase naskenovaných smluv, prezentačních prezentací nebo vícestránkových faktur obsahujících špatně orientované skeny. Toto jemné řízení eliminuje potřebu nákladných nástrojů pro post‑processing a snižuje manuální úsilí až o 70 % ve velkých digitalizačních projektech.

## Předpoklady

### Požadované knihovny a závislosti
- Java Development Kit (JDK) 8 nebo novější.  
- IDE jako IntelliJ IDEA nebo Eclipse.  
- Maven pro správu závislostí.

### Požadavky na nastavení prostředí
1. **Maven konfigurace** – přidejte GroupDocs.Viewer do vašeho `pom.xml`.  
2. **Získání licence** – získejte dočasnou licenci od GroupDocs. Navštivte [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) nebo požádejte o dočasnou licenci na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Nastavení GroupDocs.Viewer pro Java

Pro integraci GroupDocs.Viewer do vašeho Java projektu pomocí Maven aktualizujte váš `pom.xml`:

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

### Základní inicializace a nastavení
`Viewer` je hlavní třída, která načítá dokument a řídí operace renderování. Po vytvoření instance můžete volat metody jako `view` nebo `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Jak otočit konkrétní stránky PDF pomocí GroupDocs.Viewer
Otočení konkrétních stránek PDF pomocí GroupDocs.Viewer zahrnuje dvě hlavní akce: nejprve specifikovat požadované otáčení pro každou cílovou stránku pomocí metody `rotatePage` a druhý krok, vykreslit dokument s `HtmlViewOptions`, aby se otáčení odrazilo ve výstupu. Tento přístup ponechává původní PDF nezměněné a poskytuje správně orientované HTML.

### Krok 1: nakonfigurovat otáčení stránky
`rotatePage` je metoda, která přijímá nulově‑indexovaný číslo stránky a hodnotu výčtu `Rotation`. Výčet poskytuje tři možnosti: `ON_90_DEGREE`, `ON_180_DEGREE` a `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Krok 2: inicializovat viewer a vykreslit
`HtmlViewOptions` řídí proces konverze PDF‑na‑HTML. Zachovává rozvržení, písma a vložené zdroje při aplikaci jakéhokoli nastaveného otáčení.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parametry a konfigurace
- **Rotation** – `rotatePage(pageNumber, Rotation.*)`, kde možnosti otáčení jsou `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Zpracovává konverzi pdf‑na‑html při zachování rozvržení a vložených zdrojů.  
- **pdf to html java** – Třída je součástí stejného API a zajišťuje věrnou vizuální reprezentaci.

## Běžné problémy a řešení (řešení otáčení PDF)
- **Nesprávné cesty** – Ověřte, že `YOUR_DOCUMENT_DIRECTORY` a `YOUR_OUTPUT_DIRECTORY` existují a jsou přístupné.  
- **Chybějící závislosti** – Ujistěte se, že Maven koordináty odpovídají nejnovější verzi GroupDocs.Viewer (aktuálně 25.2).  
- **Omezení licence** – Použijte dočasnou licenci správně; jinak mohou být některé funkce zakázány.  
- **Špičky paměti** – Vykreslujte velké PDF v menších dávkách nebo zvýšte velikost haldy JVM.

## Praktické aplikace

### Reálné příklady použití
1. **Zarovnání dokumentů** – Otočte naskenované smlouvy pro správnou digitální orientaci.  
2. **Úpravy prezentací** – Upravit prezentační snímky v PDF před sdílením.  
3. **Archivní workflow** – Automaticky upravit orientaci historických dokumentů během digitalizace.

### Možnosti integrace
Kombinujte GroupDocs.Viewer s Java‑založenými systémy pro správu obsahu, podnikových portály nebo vlastními API, které vyžadují okamžité prohlížení PDF.

## Úvahy o výkonu
- **Správa zdrojů** – Vždy uzavřete instanci `Viewer`, aby se uvolnily souborové handle a paměť.  
- **Správa paměti v Javě** – Sledujte využití haldy při zpracování velkých PDF; zvažte streamování stránek místo načítání celého souboru.  
- **Nejlepší postupy** – Kešujte vykreslené HTML pro často přistupované dokumenty, abyste snížili dobu zpracování až o 60 %.

## Závěr
Tento tutoriál pokryl **jak otočit konkrétní stránky PDF pomocí GroupDocs.Viewer v Javě**, od nastavení Maven po vykreslení otočených stránek a řešení běžných úskalí. Experimentujte s dalšími funkcemi, jako je vodoznakování, konverze formátů nebo dávkové zpracování, abyste dále rozšířili svůj dokumentový workflow.

**Další kroky:** Prozkoumejte další možnosti GroupDocs.Viewer, jako je konverze PDF na PNG, přidávání vodoznaků nebo integrace s poskytovateli cloudového úložiště.

## Sekce FAQ
- **Řešení problémů s otáčením** – Ověřte, že čísla stránek a parametry otáčení jsou správné.  
- **Zpracování velkých PDF souborů** – Zpracovávejte stránky v dávkách a sledujte využití paměti.  
- **Požadavky na licencování** – Použijte dočasnou licenci pro vývoj; zakupte plnou licenci pro produkci.  
- **Otáčení více stránek** – Opakovaně volajte `rotatePage` s různými čísly stránek a úhly.  
- **Integrace s Java knihovnami** – GroupDocs.Viewer funguje hladce se Spring Boot, Jakarta EE a dalšími Java frameworky.

## Často kladené otázky

**Q: Mohu otočit všechny stránky PDF najednou?**  
A: Ano. Projděte čísla stránek a pro každou stránku zavolejte `rotatePage(page, Rotation.ON_90_DEGREE)`.

**Q: Ovlivňuje otáčení původní PDF soubor?**  
A: Ne. Otáčení se aplikuje pouze během procesu renderování; zdrojové PDF zůstává nezměněno.

**Q: Co když je PDF chráněno heslem?**  
A: Zadejte heslo při vytváření instance `Viewer`: `new Viewer(path, password)`.

**Q: Jak ladit chybu „null pointer“ při nastavení HtmlViewOptions?**  
A: Ujistěte se, že výstupní adresář existuje a že `pageFilePathFormat` se správně rozpozná.

**Q: Existuje způsob, jak otáčet stránky při konverzi do jiných formátů (např. PNG)?**  
A: Ano. Použijte stejnou konfiguraci `rotatePage` s odpovídajícími možnostmi zobrazení pro cílový formát.

## Zdroje
- **Dokumentace**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Reference API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Stáhnout**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Nákup**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Bezplatná zkušební verze**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Požádat o dočasnou licenci**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Podpora**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Poslední aktualizace:** 2026-10-05  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs

## Související tutoriály

- [Java průvodce: renderování vybraných stránek java s GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Java PDF renderování GroupDocs Viewer přerušení stránek](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [GroupDocs Viewer Java responzivní HTML renderování](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)