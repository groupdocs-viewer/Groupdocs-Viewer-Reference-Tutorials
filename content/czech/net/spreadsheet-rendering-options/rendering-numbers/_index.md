---
title: Vykreslování čísel
linktitle: Vykreslování čísel
second_title: GroupDocs.Viewer .NET API
description: Prozkoumejte sílu Groupdocs.Viewer pro .NET při bezproblémovém vykreslování souborů Numbers. Převeďte do HTML, JPG, PNG a PDF bez námahy.
weight: 15
url: /cs/net/spreadsheet-rendering-options/rendering-numbers/
---
## Úvod
Vítejte v tomto podrobném návodu k vykreslování souborů Numbers pomocí Groupdocs.Viewer pro .NET. Ať už jste zkušený vývojář nebo začátečník, tato příručka vás provede procesem převodu dokumentů Numbers do různých formátů. Groupdocs.Viewer for .NET je výkonný nástroj, který vám umožňuje bezproblémově integrovat možnosti prohlížení dokumentů do vašich aplikací .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost vývoje C# a .NET.
-  Nainstalovaná knihovna Groupdocs.Viewer for .NET. Můžete si jej stáhnout[tady](https://releases.groupdocs.com/viewer/net/).
- Cesta k adresáři vašeho dokumentu, kam budou uloženy výstupní soubory.
## Importovat jmenné prostory
Ujistěte se, že ve svém projektu C# importujete potřebné jmenné prostory pro použití knihovny Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavte výstupní adresář
Než začnete vykreslovat, definujte výstupní adresář, kam se budou ukládat převedené soubory. Nahraďte „Adresář vašich dokumentů“ skutečnou cestou:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Vykreslení do vícestránkového HTML
K převodu souboru Numbers na vícestránkový HTML použijte následující kód:
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
Gratulujeme! Pomocí Groupdocs.Viewer for .NET jste úspěšně vykreslili soubory Numbers do různých formátů.
## Závěr
V tomto tutoriálu jsme probrali základy vykreslování souborů Numbers pomocí Groupdocs.Viewer pro .NET. Tato výkonná knihovna poskytuje bezproblémovou integraci pro prohlížení a konverzi dokumentů ve vašich aplikacích .NET.
## Nejčastější dotazy
### Mohu použít Groupdocs.Viewer pro .NET s jinými typy dokumentů?
Ano, Groupdocs.Viewer podporuje širokou škálu formátů dokumentů, včetně Wordu, Excelu, PDF a dalších.
### Je k dispozici dočasná licence pro účely testování?
 Ano, můžete získat dočasnou licenci[tady](https://purchase.groupdocs.com/temporary-license/) pro testování.
### Kde najdu podporu pro Groupdocs.Viewer pro .NET?
 Navštivte[Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za pomoc a diskuze.
### Jak si koupím plnou verzi Groupdocs.Viewer pro .NET?
 Můžete si zakoupit plnou verzi[tady](https://purchase.groupdocs.com/buy).
### Je k dispozici bezplatná zkušební verze?
 Ano, můžete prozkoumat bezplatnou zkušební verzi[tady](https://releases.groupdocs.com/).