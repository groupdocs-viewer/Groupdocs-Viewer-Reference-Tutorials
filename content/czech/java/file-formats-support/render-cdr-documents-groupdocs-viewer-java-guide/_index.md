---
date: '2026-02-28'
description: Naučte se, jak převádět soubory CDR do HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer
  pro Javu. Obsahuje nastavení, ukázky kódu a tipy na výkon.
keywords:
- render CDR files
- GroupDocs.Viewer Java
- HTML conversion
title: Převést CDR na HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer Java
type: docs
url: /cs/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# převod cdr na html, jpg, png, pdf s GroupDocs.Viewer pro Java

Pokud potřebujete **převést CDR na HTML** (nebo na JPG, PNG a PDF) rychle a spolehlivě, jste na správném tutoriálu. V tomto průvodci projdeme vše, co potřebujete – od instalace GroupDocs.Viewer pro Java až po vykreslení souborů CorelDRAW (CDR) do web‑přátelských HTML stránek, vysoce kvalitních obrázků a univerzálně čitelných PDF. Na konci budete schopni integrovat tyto převody do jakékoli Java aplikace pomocí několika řádků kódu.

![Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

## Rychlé odpovědi
- **Jaká knihovna převádí CDR na HTML?** GroupDocs.Viewer pro Java.  
- **Mohu také převést CDR na JPG, PNG a PDF?** Ano – stejná Viewer API s různými možnostmi zobrazení.  
- **Potřebuji licenci?** Pro testování stačí bezplatná zkušební verze nebo dočasná licence; pro produkci je vyžadována plná licence.  
- **Jaká verze Javy je požadována?** JDK 8 nebo novější.  
- **Je podporován hromadný převod?** Rozhodně – stačí iterovat soubory se stejnou instancí Vieweru.

## Co znamená „převod CDR na HTML“?
Převod CDR na HTML znamená transformaci vektorového souboru CorelDRAW do standardního HTML markup, případně s vloženými obrázky a styly, aby design mohl být zobrazen přímo v webovém prohlížeči bez nutnosti původního designového softwaru.

## Proč převádět CDR na HTML, JPG, PNG nebo PDF?
- **HTML** vám umožní vložit grafiku do webových portálů a okamžitě ji sdílet.  
- **JPG** a **PNG** poskytují rastrové obrázky pro galerie, náhledy nebo e‑mailové přílohy.  
- **PDF** nabízí tisknutelnou, platformně nezávislou verzi pro archivaci nebo systémy pro sdílení dokumentů.  

Mít všechny čtyři formáty po ruce znamená, že můžete doručit správný typ souboru správnému publiku, zlepšit výkon a zajistit budoucí použitelnost vašich aktiv.

## Předpoklady

Než začneme, ujistěte se, že máte:

1. **Knihovny a závislosti** – GroupDocs.Viewer přidaný do vašeho Maven projektu.  
2. **Java Development Kit (JDK)** – verze 8 nebo novější nainstalovaná.  
3. **Základní znalosti Javy** – pro pochopení ukázek kódu.

### Požadované knihovny, verze a závislosti

Do souboru `pom.xml` přidejte následující Maven konfiguraci (zůstává beze změny oproti originálnímu tutoriálu):

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

### Kroky k získání licence

GroupDocs.Viewer nabízí bezplatnou zkušební verzi, dočasné licence pro testování nebo plné zakoupení:

- **Bezplatná zkuška** – Stáhněte ze [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/).  
- **Dočasná licence** – Požádejte o ni na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Nákup** – Získejte trvalou licenci prostřednictvím [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Nastavení GroupDocs.Viewer pro Java

### Instalace pomocí Maven
Výše uvedený Maven úryvek automaticky stáhne všechny potřebné JAR soubory. Stačí spustit `mvn clean install` po uložení souboru.

### Inicializace licence
Inicializujte licenci před vykreslením jakýchkoli dokumentů:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Průvodce implementací

Níže najdete krok‑za‑krokem příklady pro každý výstupní formát. Kódové bloky jsou identické s originálním tutoriálem; přidali jsme pouze vysvětlující text kolem nich.

### Jak převést CDR na HTML pomocí GroupDocs.Viewer

#### Vykreslení CDR dokumentu do HTML
**Přehled:** Převod vašich CDR souborů do web‑přátelského HTML pro snadné sdílení.

**Krok 1 – Nastavení cest k souborům**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Krok 2 – Inicializace Vieweru a vykreslení**

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### Jak převést CDR na JPG pomocí GroupDocs.Viewer

#### Vykreslení CDR dokumentu do JPG
**Přehled:** Vytvoření vysoce kvalitních JPEG obrázků z vašeho CDR zdroje.

**Krok 1 – Nastavení cest k souborům**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Krok 2 – Inicializace Vieweru a vykreslení**

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### Jak převést CDR na PNG pomocí GroupDocs.Viewer

#### Vykreslení CDR dokumentu do PNG
**Přehled:** Generování bezztrátových PNG obrázků pro archivaci nebo designové účely.

**Krok 1 – Nastavení cest k souborům**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Krok 2 – Inicializace Vieweru a vykreslení**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### Jak převést CDR na PDF pomocí GroupDocs.Viewer

#### Vykreslení CDR dokumentu do PDF
**Přehled:** Přeměna vašich CDR souborů na univerzálně čitelné PDF.

**Krok 1 – Nastavení cest k souborům**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Krok 2 – Inicializace Vieweru a vykreslení**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Praktické aplikace

- **Webové portály:** Použijte HTML převod k vložení CDR designů přímo na vašem webu.  
- **Obrázkové galerie:** Nasazujte JPG/PNG výstupy pro rychle načítající se galerie.  
- **Sdílení dokumentů:** Poskytněte PDF klientům, kteří potřebují tisknutelnou, pouze‑ke‑čtení verzi.  
- **Archivace:** Ukládejte více formátů pro zajištění budoucí přístupnosti.  
- **Cross‑platform integrace:** Vkládejte vygenerované soubory do dalších služeb (např. OCR, analytika).

## Úvahy o výkonu

- **Okamžitě uvolňujte instance Vieweru** (jak je ukázáno pomocí try‑with‑resources), aby se uvolnila paměť.  
- **Hromadné zpracování:** Procházejte kolekci CDR souborů se stejnou konfigurací Vieweru, čímž snížíte režii.  
- **Alokace zdrojů:** Přidělte dostatečné CPU/RAM pro velké nebo složité CDR soubory; monitorovací nástroje vám pomohou doladit nastavení.

## Závěr

Ukázali jsme vám, jak **převést CDR na HTML**, stejně jako na JPG, PNG a PDF, pomocí GroupDocs.Viewer pro Java. Dodržením stručných ukázek kódu a tipů pro nejlepší praxi můžete tyto převody začlenit do jakéhokoli Java‑založeného workflow a poskytovat uživatelům flexibilní, vysoce kvalitní výstupy.

### Další kroky
- Experimentujte s pokročilými možnostmi vykreslování, jako jsou vlastní velikosti stránek nebo vodoznaky.  
- Propojte převodní pipeline s REST API a nabídněte transformaci souborů na vyžádání.  
- Připojte se ke komunitě a ptejte se na otázky ve [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## Často kladené otázky

**Q: Mohu převést CDR soubory chráněné heslem?**  
A: Ano. Načtěte soubor pomocí instance `Viewer`, která přijímá parametr hesla (viz dokumentace API).

**Q: Existuje limit na počet stránek, které lze převést najednou?**  
A: Žádný pevný limit, ale velmi velké soubory mohou vyžadovat více paměti; zvažte zpracování po jednotlivých stránkách.

**Q: Obsahuje HTML výstup vložená písma?**  
A: Při použití `HtmlViewOptions.forEmbeddedResources` jsou písma vložena jako Base64, což zajišťuje konzistentní vykreslení.

**Q: Jak mohu nastavit kvalitu JPEG?**  
A: `JpgViewOptions` poskytuje metodu `setQuality(int)`, kde můžete zadat hodnotu od 1‑100.

**Q: Mohu převádět CDR soubory na Linux serveru?**  
A: Rozhodně – GroupDocs.Viewer je platformně nezávislý, pokud je nainstalována JDK.

---

**Poslední aktualizace:** 2026-02-28  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs