---
date: '2026-02-23'
description: Naučte se, jak převést IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer
  pro Javu. Postupujte podle tohoto krok‑za‑krokem průvodce s připravenými spustitelnými
  ukázkami kódu.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Převod IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer Java
type: docs
url: /cs/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

Translate bullet points.

Make sure to keep bold formatting.

Proceed.

Table: translate headers and cells.

FAQ: translate Q and A.

Make sure code block placeholders remain.

Let's produce final content.

# Převod IGS na PDF, HTML, JPG a PNG pomocí GroupDocs.Viewer Java

Pokud potřebujete **převést IGS na PDF** (nebo na HTML, JPG, PNG) přímo z Java aplikace, jste na správném místě. V tomto tutoriálu projdeme vše, co potřebujete – od nastavení knihovny až po vykreslení 3‑D modelu ve formátu, který vyhovuje vašemu projektu. Ukážeme vám, proč je GroupDocs.Viewer solidní volbou pro rychlé a spolehlivé konverze, a poskytneme praktický kód, který můžete vložit do svého řešení.

![Převod souborů IGS na HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer pro Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Rychlé odpovědi
- **Mohu převést IGS na PDF pomocí Javy?** Ano, pomocí `PdfViewOptions` z GroupDocs.Viewer.
- **Jaké výstupní formáty jsou podporovány?** HTML, JPG, PNG a PDF.
- **Potřebuji licenci pro produkci?** Komerční licence je vyžadována; k testování je k dispozici bezplatná zkušební verze.
- **Jaká verze Javy je potřeba?** JDK 8 nebo vyšší.
- **Je Maven jediný způsob, jak přidat knihovnu?** Ne, můžete také použít Gradle nebo ruční zahrnutí JAR souboru.

## Co znamená „převod IGS na PDF“?
Převod IGS (neutrálního souborového formátu pro 3‑D CAD data) na PDF znamená změnu komplexního 3‑D modelu na statický, široce zobrazitelný dokument. To je užitečné pro sdílení návrhů se zainteresovanými stranami, které nemají CAD nástroje.

## Proč použít GroupDocs.Viewer pro konverze IGS?
- **Zero‑code CAD rendering** – knihovna se postará o těžkou práci s parsováním formátu IGS.
- **Více výstupních možností** – jedním voláním API můžete získat HTML, JPG, PNG nebo PDF.
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu.
- **Performance‑focused** – rychlé vykreslování i pro velké sestavy.

## Požadavky
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** nainstalovaný a nakonfigurovaný ve vašem IDE (IntelliJ IDEA, Eclipse, NetBeans, atd.)  
- Základní znalost Maven (volitelné, ale doporučené)  

## Nastavení GroupDocs.Viewer pro Java

### Maven Dependency
Přidejte repozitář GroupDocs a závislost Viewer do souboru `pom.xml`:

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
GroupDocs.Viewer nabízí:
- **Free trial** – omezené využití, ideální pro rychlé testy.  
- **Temporary license** – plná funkčnost po omezenou zkušební dobu.  
- **Commercial license** – neomezené používání v produkci.

### Základní inicializace Vieweru
Níže uvedený úryvek ukazuje, jak vytvořit instanci `Viewer`, která ukazuje na váš IGS soubor:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Vykreslení IGS do HTML

### Jak převést IGS na HTML?
HTML výstup vám poskytne interaktivní, prohlížečem přátelský pohled na 3‑D model.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Klíčový bod:** `HtmlViewOptions.forEmbeddedResources()` vloží všechny potřebné assety (CSS, obrázky) přímo do HTML souboru, což jej činí přenosným.

## Vykreslení IGS do JPG

### Jak převést IGS na JPG?
JPG obrázky jsou ideální pro miniatury nebo rychlé náhledy.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Můžete upravit `JpgViewOptions` pro nastavení rozlišení a kvality komprese.

## Vykreslení IGS do PNG

### Jak převést IGS na PNG?
PNG podporuje průhlednost, což se hodí při překrývání modelu na různých pozadích.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Experimentujte s `PngViewOptions`, abyste dosáhli nejlepšího poměru mezi velikostí souboru a vizuální věrností.

## Vykreslení IGS do PDF

### Jak převést IGS na PDF?
PDF je standardní formát pro sdílení podrobné dokumentace návrhů. Tato sekce přímo řeší hlavní klíčové slovo **convert IGS to PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` vám umožní nastavit rozvržení stránky, kvalitu obrázku a zda vložit písma.

## Praktické aplikace

- **Webové portály** – vložte HTML‑vykreslené modely přímo do produktových konfigurátorů.  
- **Marketingové materiály** – generujte vysoce kvalitní JPG/PNG obrázky pro brožury.  
- **Technická dokumentace** – zahrňte PDF vykreslení CAD modelů do uživatelských příruček.  
- **Kontrola kvality** – automatizujte generování miniatur pro velké dávky IGS souborů.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Výstupní složka nebyla nalezena** | Ověřte cestu předanou do `Path outputDirectory` a zajistěte, aby Java proces měl práva zápisu. |
| **Prázdné stránky v PDF** | Ujistěte se, že IGS soubor není poškozený; zkuste jej nejprve otevřít v CAD prohlížeči. |
| **Pomalé vykreslování velkých sestav** | Zvyšte heap JVM (`-Xmx2g` nebo více) a zvažte vykreslování po stránkách pomocí `viewer.getPageCount()`, pokud je to potřeba. |
| **Chybějící písma v PDF** | Použijte `PdfViewOptions` k vložení požadovaných písem nebo nainstalujte chybějící písma na server. |

## Často kladené otázky

**Q: Mohu převést více IGS souborů v jednom běhu?**  
A: Ano. Procházejte seznam cest k souborům a pro každý zavolejte příslušnou metodu `view`.

**Q: Je možné přizpůsobit velikost stránky PDF?**  
A: Rozhodně. `PdfViewOptions` poskytuje metodu `setPageSize(PageSize.A4)` a podobné možnosti.

**Q: Potřebuji samostatnou licenci pro každý výstupní formát?**  
A: Ne. Jedna licence GroupDocs.Viewer pokrývá všechny podporované formáty.

**Q: Jak velký může být IGS soubor, než dojde k poklesu výkonu?**  
A: Knihovna zvládne soubory až na několik stovek megabajtů, ale pro velmi velké modely může být nutné přidělit více paměti JVM.

**Q: Mohu vykreslit jen konkrétní pohled nebo orientaci?**  
A: GroupDocs.Viewer vykresluje výchozí pohled. Pro vlastní orientace je potřeba před konverzí předzpracovat IGS soubor v CAD nástroji.

---

**Poslední aktualizace:** 2026-02-23  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs