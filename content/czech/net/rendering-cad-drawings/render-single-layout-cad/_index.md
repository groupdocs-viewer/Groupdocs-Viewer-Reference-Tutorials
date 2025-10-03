---
"description": "Naučte se, jak vykreslit jednotlivé rozvržení ve výkresech CAD pomocí GroupDocs.Viewer pro .NET. Snadné kroky pro bezproblémovou integraci do vašich .NET aplikací."
"linktitle": "Vykreslení jednoho rozvržení ve výkresech CAD"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení jednoho rozvržení ve výkresech CAD"
"url": "/cs/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# Vykreslení jednoho rozvržení ve výkresech CAD

## Zavedení
V oblasti vývoje v .NET je práce s CAD výkresy a jejich prohlížení běžným požadavkem. GroupDocs.Viewer pro .NET tento úkol zjednodušuje tím, že poskytuje komplexní řešení pro vykreslování CAD výkresů v .NET aplikacích. V tomto tutoriálu se ponoříme do vykreslování jednoho rozvržení ve CAD výkresech pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka C# a frameworku .NET.
- Visual Studio nainstalované ve vašem systému.
- Knihovna GroupDocs.Viewer pro .NET byla stažena a tutoriály jsou součástí vašeho projektu. Můžete si ji stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
- Znalost formátů CAD souborů a jejich struktur.

## Importovat jmenné prostory
Nejprve importujte potřebné jmenné prostory do kódu C# pro přístup k funkcím GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Definování výstupního adresáře
Zadejte adresář, kam chcete uložit vykreslený výstup.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru stránky
Definujte formát cesty k souboru každé vykreslené stránky.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Vytvoření instance objektu Viewer
Vytvořte instanci třídy Viewer poskytované třídou GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Krok 4: Konfigurace možností zobrazení HTML
Nakonfigurujte možnosti pro vykreslování HTML výstupu s vloženými zdroji.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Zadejte název rozvržení CAD
Zadejte název rozvržení CAD, které chcete vykreslit.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Krok 6: Vykreslení výkresu CAD
Volejte metodu View objektu Viewer se zadanými možnostmi.
```csharp
viewer.View(options);
```
## Krok 7: Zobrazení zprávy o úspěchu
Informujte uživatele o úspěšném vykreslení zdrojového dokumentu.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Vykreslování CAD výkresů, zejména při práci s rozvrženími, může být náročný úkol. S GroupDocs.Viewer pro .NET se však proces stává bezproblémovým a efektivním. Dodržováním kroků popsaných v tomto tutoriálu můžete bez námahy vykreslit jedno rozvržení ve výkresech CAD v rámci vašich .NET aplikací.
## Často kladené otázky
### Mohu pomocí GroupDocs.Viewer pro .NET vykreslit více rozvržení současně?
Ano, GroupDocs.Viewer pro .NET podporuje vykreslování více rozvržení z CAD výkresů.
### Je GroupDocs.Viewer kompatibilní s různými formáty CAD souborů?
Rozhodně, GroupDocs.Viewer podporuje širokou škálu formátů CAD souborů, včetně DWG, DXF, DGN a dalších.
### Mohu si přizpůsobit možnosti vykreslování pro výkresy CAD?
Ano, GroupDocs.Viewer nabízí rozsáhlé možnosti pro přizpůsobení nastavení vykreslování podle vašich požadavků.
### Je k dispozici bezplatná zkušební verze GroupDocs.Viewer pro .NET?
Ano, můžete si vyzkoušet funkce GroupDocs.Viewer s bezplatnou zkušební verzí. [zde](https://releases.groupdocs.com/).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
V případě jakýchkoli dotazů nebo potřeby pomoci můžete navštívit fórum GroupDocs.Viewer. [zde](https://forum.groupdocs.com/c/viewer/9).