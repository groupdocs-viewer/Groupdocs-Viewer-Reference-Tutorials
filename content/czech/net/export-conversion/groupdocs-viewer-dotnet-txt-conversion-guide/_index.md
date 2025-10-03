---
"date": "2025-04-25"
"description": "Naučte se, jak převádět soubory TXT do různých formátů, jako jsou HTML, JPG, PNG a PDF, pomocí GroupDocs.Viewer pro .NET v tomto komplexním průvodci."
"title": "Převod TXT do HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer .NET – kompletní průvodce"
"url": "/cs/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# Převod TXT do více formátů pomocí GroupDocs.Viewer .NET

## Zavedení

Chcete bez námahy převést textové dokumenty do různých formátů, jako je HTML, JPG, PNG nebo PDF? Správa konverzí dokumentů může být náročná, zejména při práci s více stránkami nebo specifickými požadavky na formát. **GroupDocs.Viewer pro .NET** Zjednodušuje proces vykreslování souborů TXT do různých výstupních formátů a zajišťuje tak přístupnost a vizuální přitažlivost vašich dat.

![Převod TXT do HTML, JPG, PNG, PDF pomocí GroupDocs.Viewer pro .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

V této příručce se podíváme na to, jak pomocí nástroje GroupDocs.Viewer pro .NET transformovat dokumenty TXT do vícestránkového HTML, jednostránkového HTML, JPG, PNG a PDF. Na konci se naučíte:
- Konverze TXT souborů pomocí C# s GroupDocs.Viewer
- Implementace různých možností vykreslování pro vaše potřeby
- Optimalizace výkonu během konverzí

Pojďme se pustit do řešení vašich problémů s konverzí dokumentů.

## Předpoklady

Než začneme, ujistěte se, že máte připravené následující:
- **Vývojové prostředí**Visual Studio 2019 nebo novější.
- **.NET Framework**Verze 4.6.1 nebo vyšší.
- **Knihovna GroupDocs.Viewer pro .NET**:
  - Prostřednictvím konzole Správce balíčků NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Použití .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Pro snadné pochopení se doporučuje znalost programování v C# a základních operací se soubory v .NET.

## Nastavení GroupDocs.Viewer pro .NET

### Instalace

Chcete-li začít, nainstalujte **Prohlížeč skupinových dokumentů** knihovna s použitím preferovaného správce balíčků:

#### Konzola Správce balíčků NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### Rozhraní příkazového řádku .NET
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Licencování

Můžete začít s **bezplatná zkušební verze** nebo získat **dočasná licence** prozkoumat všechny možnosti GroupDocs.Viewer pro .NET bez omezení vyhodnocování:
- Bezplatná zkušební verze: [Stáhnout zde](https://releases.groupdocs.com/viewer/net/)
- Dočasná licence: [Žádost zde](https://purchase.groupdocs.com/temporary-license/)

Pro trvalé používání zvažte zakoupení licence přímo od [GroupDocs](https://purchase.groupdocs.com/buy).

### Základní inicializace

Nastavení GroupDocs.Viewer ve vašem projektu:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Inicializujte objekt Viewer cestou k souboru TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Váš vykreslovací kód bude zde.
}
```

## Průvodce implementací

Nyní se pojďme ponořit do jednotlivých funkcí a zjistit, jak je můžete implementovat.

### Vykreslení dokumentu TXT do vícestránkového HTML

#### Přehled
Tato funkce demonstruje převod dokumentu TXT do vícestránkového formátu HTML. Každá stránka textového souboru je vykreslena jako samostatný soubor HTML s vloženými zdroji.

#### Krok 1: Nastavení prohlížeče

Vytvořte `Viewer` objekt pro váš zdrojový TXT soubor:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Inicializujte prohlížeč vzorovým textovým souborem.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Pokračujte krokem 2...
```

#### Krok 2: Konfigurace možností zobrazení HTML

Nastavení `HtmlViewOptions` pro vykreslení každé stránky samostatně:

```csharp
// Nastavení možností zobrazení HTML pro vykreslování více stránek.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Vykreslete dokument jako vícestránkový HTML.
viewer.View(options);
}
```

**Vysvětlení**: Ten `ForEmbeddedResources()` Metoda zajišťuje, že zdroje, jako jsou obrázky a styly, jsou vloženy přímo do souboru HTML, což usnadňuje sdílení.

### Vykreslení dokumentu TXT do formátu HTML s jednou stránkou

#### Přehled
Převeďte dokument TXT na jednu stránku HTML, ideální pro dokumenty, které je třeba zobrazit jako jednu souvislou webovou stránku.

#### Krok 1: Nastavení prohlížeče

Inicializujte `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Inicializujte novou instanci prohlížeče pro jiný textový soubor.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Pokračujte krokem 2...
```

#### Krok 2: Konfigurace možností HTML pro jednu stránku

Konfigurovat `HtmlViewOptions` s povoleným nastavením jedné stránky:

```csharp
// Nastavte možnosti pro vykreslování do jedné HTML stránky.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Vykreslit jako jednu HTML stránku.
viewer.View(options);
}
```

**Vysvětlení**: Ten `RenderToSinglePage` Vlastnost zajišťuje, že se veškerý obsah zobrazí na jedné stránce.

### Vykreslení dokumentu TXT do formátu JPG

#### Přehled
Tato funkce umožňuje převést textový dokument do formátu JPEG, což je užitečné pro vizuální prezentace nebo archivační účely.

#### Krok 1: Nastavení prohlížeče

Připravte si `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Inicializujte prohlížeč ukázkovým souborem.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Pokračujte krokem 2...
```

#### Krok 2: Konfigurace možností zobrazení JPG

Nastavení `JpgViewOptions` pro vykreslování obrázků:

```csharp
// Nastavte možnosti pro vykreslování jako obrázek JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Vykreslete dokument jako soubor JPEG.
viewer.View(options);
}
```

**Vysvětlení**: Ten `JpgViewOptions` Třída určuje, jak vykreslit a uložit každou stránku dokumentu ve formátu JPEG.

### Vykreslení dokumentu TXT do formátu PNG

#### Přehled
Převeďte textový dokument do formátu PNG a nabídněte vysoce kvalitní obrazový výstup s podporou průhlednosti.

#### Krok 1: Nastavení prohlížeče

Inicializujte `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Vytvořte instanci prohlížeče pro váš TXT soubor.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Pokračujte krokem 2...
```

#### Krok 2: Konfigurace možností zobrazení PNG

Nastavení `PngViewOptions`:

```csharp
// Nastavení možností zobrazení pro vykreslování jako obrázku PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Vykreslete dokument ve formátu PNG.
viewer.View(options);
}
```

**Vysvětlení**: Ten `PngViewOptions` Třída umožňuje vykreslení každé stránky s průhledností, což ji činí vhodnou pro vrstvenou grafiku.

### Vykreslení dokumentu TXT do PDF

#### Přehled
Tato funkce je ideální pro převod textových dokumentů do univerzálně dostupného formátu PDF.

#### Krok 1: Nastavení prohlížeče

Připravte si `Viewer` objekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Inicializujte instanci prohlížeče pro váš vzorový textový soubor.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Pokračujte krokem 2...
```

#### Krok 2: Konfigurace možností zobrazení PDF

Nastavení `PdfViewOptions`:

```csharp
// Nastavení možností zobrazení pro vykreslení jako dokumentu PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Vykreslete dokument do souboru PDF.
viewer.View(options);
}
```

**Vysvětlení**: Ten `PdfViewOptions` Třída určuje, jak převést a uložit soubory TXT jako dokumenty PDF.

## Závěr

S nástrojem GroupDocs.Viewer pro .NET je převod textových dokumentů do různých formátů snadný. Tato příručka se zabývá transformací souborů TXT do vícestránkového HTML, jednostránkového HTML, JPG, PNG a PDF pomocí jazyka C#. Ať už chcete zlepšit přístupnost dokumentů nebo jejich kompatibilitu, tyto metody poskytují robustní řešení.

Další pomoc nebo pokročilejší funkce naleznete v [oficiální dokumentace k GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/)Šťastné programování!