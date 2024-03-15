---
title: Render Single Layout ve výkresech CAD
linktitle: Render Single Layout ve výkresech CAD
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat jednotlivé rozvržení ve výkresech CAD pomocí GroupDocs.Viewer pro .NET. Snadné kroky pro bezproblémovou integraci do vašich aplikací .NET.
type: docs
weight: 14
url: /cs/net/rendering-cad-drawings/render-single-layout-cad/
---
## Úvod
oblasti vývoje .NET je manipulace a prohlížení CAD výkresů běžným požadavkem. GroupDocs.Viewer for .NET tento úkol zjednodušuje tím, že poskytuje komplexní řešení pro vykreslování CAD výkresů v aplikacích .NET. V tomto tutoriálu se ponoříme do vykreslování jediného rozvržení ve výkresech CAD pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka C# a .NET frameworku.
- Visual Studio nainstalované ve vašem systému.
-  Knihovna GroupDocs.Viewer for .NET stažená a odkazovaná ve vašem projektu. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
- Seznámení s formáty souborů CAD a jejich strukturami.

## Importovat jmenné prostory
Nejprve importujte potřebné jmenné prostory do svého kódu C#, abyste získali přístup k funkcím GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Definujte výstupní adresář
Zadejte adresář, kam chcete uložit vykreslený výstup.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
Definujte formát pro cestu k souboru každé vykreslené stránky.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Vytvořte objekt prohlížeče
Vytvořte instanci třídy Viewer poskytované GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
Nakonfigurujte možnosti pro vykreslování výstupu HTML s vloženými prostředky.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Zadejte název rozvržení CAD
Zadejte název rozvržení CAD, které chcete vykreslit.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Krok 6: Vykreslení výkresu CAD
Vyvolejte metodu View objektu Viewer se zadanými možnostmi.
```csharp
viewer.View(options);
```
## Krok 7: Zobrazte zprávu o úspěchu
Informujte uživatele o úspěšném vykreslení zdrojového dokumentu.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Vykreslování výkresů CAD, zejména při práci s rozvržením, může být skličující úkol. S GroupDocs.Viewer for .NET se však proces stává bezproblémovým a efektivním. Podle kroků uvedených v tomto kurzu můžete bez námahy vykreslit jedno rozvržení ve výkresech CAD ve vašich aplikacích .NET.
## FAQ
### Mohu pomocí GroupDocs.Viewer for .NET vykreslit více rozložení současně?
Ano, GroupDocs.Viewer for .NET podporuje vykreslování více rozvržení z výkresů CAD.
### Je GroupDocs.Viewer kompatibilní s různými formáty souborů CAD?
GroupDocs.Viewer rozhodně podporuje širokou škálu formátů souborů CAD, včetně DWG, DXF, DGN a dalších.
### Mohu přizpůsobit možnosti vykreslování pro výkresy CAD?
Ano, GroupDocs.Viewer poskytuje rozsáhlé možnosti přizpůsobení nastavení vykreslování podle vašich požadavků.
### Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, funkce GroupDocs.Viewer můžete prozkoumat pomocí bezplatné zkušební verze[tady](https://releases.groupdocs.com/).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
 Máte-li jakékoli dotazy nebo pomoc, můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9).