---
"description": "Prozkoumejte sílu Groupdocs.Viewer pro .NET pro bezproblémové vykreslování souborů Numbers. Bez námahy převádějte do HTML, JPG, PNG a PDF."
"linktitle": "Vykreslování čísel"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslování čísel"
"url": "/cs/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# Vykreslování čísel

## Zavedení
Vítejte v tomto podrobném tutoriálu o vykreslování souborů Numbers pomocí Groupdocs.Viewer pro .NET. Ať už jste zkušený vývojář nebo začátečník, tento průvodce vás provede procesem převodu dokumentů Numbers do různých formátů. Groupdocs.Viewer pro .NET je výkonný nástroj, který vám umožňuje bezproblémově integrovat funkce prohlížení dokumentů do vašich .NET aplikací.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Praktická znalost vývoje v C# a .NET.
- Knihovna Groupdocs.Viewer pro .NET je nainstalována. Můžete si ji stáhnout. [zde](https://releases.groupdocs.com/viewer/net/).
- Cesta k adresáři dokumentů, kam budou uloženy výstupní soubory.
## Importovat jmenné prostory
Ve vašem projektu C# se ujistěte, že jste importovali potřebné jmenné prostory pro použití knihovny Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavení výstupního adresáře
Než začnete s vykreslováním, definujte výstupní adresář, kam budou převedené soubory uloženy. Nahraďte „Adresář dokumentů“ skutečnou cestou:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Vykreslení do vícestránkového HTML
Pomocí následujícího kódu převeďte soubor Numbers do vícestránkového HTML:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 3: Vykreslení do JPG
Převeďte soubor Numbers do formátu JPG pomocí následujícího kódu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 4: Vykreslení do PNG
Transformujte soubor Numbers do formátu PNG pomocí následujícího kódu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 5: Vykreslení do PDF
Nakonec převeďte soubor Numbers do formátu PDF pomocí následujícího kódu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Gratulujeme! Úspěšně jste vykreslili soubory Numbers do různých formátů pomocí Groupdocs.Viewer pro .NET.
## Závěr
tomto tutoriálu jsme se seznámili se základy vykreslování souborů Numbers pomocí Groupdocs.Viewer pro .NET. Tato výkonná knihovna poskytuje bezproblémovou integraci pro prohlížení a převod dokumentů ve vašich .NET aplikacích.
## Často kladené otázky
### Mohu použít Groupdocs.Viewer pro .NET s jinými typy dokumentů?
Ano, Groupdocs.Viewer podporuje širokou škálu formátů dokumentů, včetně Wordu, Excelu, PDF a dalších.
### Je k dispozici dočasná licence pro testovací účely?
Ano, můžete získat dočasnou licenci [zde](https://purchase.groupdocs.com/temporary-license/) pro testování.
### Kde najdu podporu pro Groupdocs.Viewer pro .NET?
Navštivte [Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za pomoc a diskuzi.
### Jak si mohu zakoupit plnou verzi Groupdocs.Viewer pro .NET?
Plnou verzi si můžete zakoupit [zde](https://purchase.groupdocs.com/buy).
### Je k dispozici bezplatná zkušební verze?
Ano, můžete si vyzkoušet bezplatnou zkušební verzi [zde](https://releases.groupdocs.com/).