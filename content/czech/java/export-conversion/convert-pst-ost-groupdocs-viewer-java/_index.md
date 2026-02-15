---
date: '2026-02-15'
description: Naučte se, jak převést PST na HTML a další formáty jako JPG, PNG, PDF
  pomocí GroupDocs.Viewer pro Javu. Tento průvodce pokrývá všechny potřebné kroky
  a konfigurace.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Převod PST na HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer pro Java
type: docs
url: /cs/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Převod PST na HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer pro Java

Hledáte **convert pst to html** nebo jiné formáty jako JPG, PNG či PDF? S výkonnou knihovnou GroupDocs.Viewer pro Java je tento úkol jednoduchý a efektivní. V tomto tutoriálu se naučíte, jak renderovat soubory Outlook PST/OST do web‑přátelského HTML, obrazových souborů nebo jediného PDF, což usnadní sdílení a archivaci vašich e‑mailových archivů.

![Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Co se naučíte**
- Jak nastavit GroupDocs.Viewer pro Java v Maven projektu.  
- Krok‑za‑krokem instrukce pro **java convert pst** soubory do HTML, JPG, PNG a PDF.  
- Tipy na konfiguraci pro optimální výkon a běžné úskalí.

## Rychlé odpovědi
- **Jaká knihovna provádí konverzi PST?** GroupDocs.Viewer pro Java.  
- **Mohu převést PST přímo na PDF?** Ano, pomocí `PdfViewOptions`.  
- **Je licence vyžadována pro produkci?** Ano, je potřeba platná licence GroupDocs.  
- **Jaká verze Javy je podporována?** JDK 8 nebo vyšší.  
- **Musím ručně extrahovat přílohy?** Ne, prohlížeč je renderuje automaticky.

## Jak převést pst na html pomocí GroupDocs.Viewer pro Java
Níže najdete stručný přehled procesu konverze před tím, než se ponoříte do podrobných ukázek kódu.

### Proč zvolit GroupDocs.Viewer?
- **Vysoká věrnost** renderování těla e‑mailu, příloh a formátování.  
- **Více výstupních formátů** (HTML, JPG, PNG, PDF) z jediné API.  
- **Žádné externí závislosti** – vše běží uvnitř vaší Java aplikace.

## Požadavky

- **GroupDocs.Viewer pro Java** – verze 25.2 nebo novější.  
- **Java Development Kit (JDK)** – 8 nebo novější.  
- Maven pro správu závislostí.  
- Základní znalosti Javy a Maven.

## Nastavení GroupDocs.Viewer pro Java

Přidejte repozitář GroupDocs a závislost do vašeho `pom.xml`:

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
- **Bezplatná zkušební verze** – vyzkoušejte všechny funkce bez nákladů.  
- **Dočasná licence** – prodlužte evaluační dobu podle potřeby.  
- **Plná licence** – vyžadována pro nasazení do produkce.

### Základní inicializace

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Průvodce implementací

Následující sekce vás provedou renderováním souborů PST/OST do každého podporovaného formátu.

### Renderování dokumentů PST/OST do HTML

#### Krok 1: Nastavte výstupní adresář

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Krok 2: Konfigurace Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Krok 3: Inicializace Viewer a renderování HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderování dokumentů PST/OST do JPG

#### Krok 1: Nastavte výstupní adresář

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Krok 2: Konfigurace Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Krok 3: Inicializace Viewer a renderování JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderování dokumentů PST/OST do PNG

#### Krok 1: Nastavte výstupní adresář

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Krok 2: Konfigurace Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Krok 3: Inicializace Viewer a renderování PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderování dokumentů PST/OST do PDF

#### Krok 1: Nastavte výstupní adresář

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Krok 2: Konfigurace Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Krok 3: Inicializace Viewer a renderování PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Praktické aplikace

- **Archivace e‑mailů:** Převod velkých PST archivů na prohledávatelné HTML nebo PDF pro soulad s předpisy.  
- **Systémy správy dokumentů:** Ukládejte konvertované soubory v systémech, které přijímají jen PDF, PNG nebo JPG.  
- **Kolaborační platformy:** Sdílejte převedené e‑maily jako obrázky ve Slacku nebo Teams.  
- **Právní revize:** Poskytněte soudům PDF verze e‑mailových důkazů.  
- **Zálohovací strategie:** Uchovávejte lehké PNG nebo JPG snímky kritických zpráv.

## Úvahy o výkonu

- **Správa zdrojů:** Znovu používejte instance `Viewer` při zpracování více souborů, abyste snížili režii.  
- **Ladění paměti:** Upravit `loadOptions.setResourceLoadingTimeout` podle kapacity serveru.  
- **Asynchronní zpracování:** Přesuňte konverzi do background vláken pro responzivní UI.  

## Často kladené otázky

**Q: Jak **convert pst to pdf** pomocí stejné základny kódu?**  
A: Použijte `PdfViewOptions` podle ukázky v sekci renderování PDF; zbytek kódu zůstane stejný.

**Q: Dokáže GroupDocs.Viewer zpracovat šifrované PST soubory?**  
A: Ano, před renderováním nastavte heslo pomocí `LoadOptions.setPassword("yourPassword")`.

**Q: Jaký je rozdíl mezi **java convert pst** na PNG a JPG?**  
A: PNG zachovává bezztrátovou kvalitu, ideální pro screenshoty, zatímco JPG nabízí menší velikost souboru pro náhledy e‑mailů.

**Q: Existuje způsob, jak **how to convert pst** soubory hromadně?**  
A: Zabalte logiku renderování do smyčky, která iteruje přes adresář PST souborů; pro každý soubor znovu použijte stejnou konfiguraci `Viewer`.

## Závěr

Nyní máte kompletní, připravený průvodce pro **convert pst to html**, JPG, PNG a PDF pomocí GroupDocs.Viewer pro Java. Dodržením výše uvedených kroků můžete integrovat konverzi e‑mailů do libovolného Java‑založeného workflow, zlepšit přístupnost a splnit požadavky na soulad.

---

**Poslední aktualizace:** 2026-02-15  
**Testováno s:** GroupDocs.Viewer pro Java 25.2  
**Autor:** GroupDocs