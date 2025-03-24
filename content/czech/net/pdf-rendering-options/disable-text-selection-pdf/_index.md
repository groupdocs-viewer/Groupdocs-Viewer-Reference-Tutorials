---
title: Zakázat výběr textu v PDF
linktitle: Zakázat výběr textu v PDF
second_title: GroupDocs.Viewer .NET API
description: Přečtěte si, jak zakázat výběr textu v PDF pomocí GroupDocs.Viewer pro .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
weight: 13
url: /cs/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Úvod
GroupDocs.Viewer for .NET je výkonné rozhraní API pro vykreslování dokumentů, které umožňuje vývojářům bez námahy integrovat možnosti prohlížení dokumentů do jejich aplikací .NET. Jednou z klíčových funkcí, které GroupDocs.Viewer poskytuje, je možnost zakázat výběr textu v dokumentech PDF. Tato funkce je užitečná zejména ve scénářích, kdy potřebujete zabránit uživatelům v kopírování textu z citlivých dokumentů, a zajistit tak bezpečnost a integritu dokumentu.
## Předpoklady
Než se ponoříme do podrobného průvodce, jak zakázat výběr textu v PDF pomocí GroupDocs.Viewer pro .NET, ujistěte se, že máte splněny následující předpoklady:
1.  Instalace GroupDocs.Viewer for .NET: Ujistěte se, že jste si stáhli a nainstalovali GroupDocs.Viewer for .NET z webu[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
2. Adresář dokumentů: Připravte si adresář, kde budou uloženy vaše dokumenty. Chcete-li vykreslit dokument PDF, budete muset ve fragmentu kódu zadat tento adresář.

## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory pro přístup k funkcím poskytovaným GroupDocs.Viewer pro .NET. Můžete to udělat takto:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si proces deaktivace výběru textu v dokumentu PDF pomocí GroupDocs.Viewer for .NET rozdělíme do několika kroků:
## Krok 1: Zadejte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
 V tomto kroku vyměňte`"Your Document Directory"` s cestou k adresáři, kde se nachází váš dokument PDF.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tento krok definuje formát cest k souborům vykreslených stránek HTML. Každá stránka dokumentu PDF bude převedena na soubor HTML s pořadovým číslem stránky.
## Krok 3: Vykreslení dokumentu PDF s deaktivovaným výběrem textu
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Nahradit`"Path to Your PDF Document"` se skutečnou cestou k vašemu souboru PDF. Tento fragment kódu inicializuje a`Viewer` objekt, konfiguruje možnosti zobrazení HTML pro vkládání zdrojů a zakazuje výběr textu nastavením`RenderTextAsImage` majetek do`true`.
## Krok 4: Zobrazte zprávu o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po vykreslení dokumentu PDF se v tomto kroku zobrazí zpráva o úspěchu spolu s adresářem, kde jsou uloženy vykreslené stránky HTML.

## Závěr
V tomto tutoriálu jsme se naučili, jak zakázat výběr textu v dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Pokud budete postupovat podle podrobného průvodce, můžete tuto funkci bez problémů integrovat do svých aplikací .NET, čímž zajistíte zabezpečení dokumentů a vylepšíte uživatelský komfort.
## FAQ
### Mohu přizpůsobit výstupní adresář pro vykreslené HTML stránky?
Ano, můžete zadat libovolnou cestu k adresáři, kam chcete ukládat vykreslené HTML stránky.
### Je GroupDocs.Viewer for .NET kompatibilní s různými verzemi .NET frameworku?
Ano, GroupDocs.Viewer for .NET je kompatibilní s různými verzemi rozhraní .NET, včetně .NET Core a .NET Framework.
### Má zakázání výběru textu vliv na další funkce dokumentu PDF?
Ne, zakázání výběru textu pouze zabrání uživatelům ve výběru a kopírování textu z dokumentu. Ostatní funkce zůstávají nedotčeny.
### Mohu po vykreslení dokumentu znovu povolit výběr textu?
 Ano, výběr textu můžete povolit jednoduchým nastavením`RenderTextAsImage` majetek do`false` v možnostech zobrazení HTML.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, máte přístup k bezplatné zkušební verzi GroupDocs.Viewer for .NET z webu[webová stránka](https://releases.groupdocs.com/).