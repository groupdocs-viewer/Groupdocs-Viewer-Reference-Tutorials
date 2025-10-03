---
"description": "Naučte se, jak zakázat výběr textu v PDF pomocí GroupDocs.Viewer pro .NET. Pro bezproblémovou integraci postupujte podle našeho podrobného návodu."
"linktitle": "Zakázat výběr textu v PDF"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Zakázat výběr textu v PDF"
"url": "/cs/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# Zakázat výběr textu v PDF

## Zavedení
GroupDocs.Viewer pro .NET je výkonné API pro vykreslování dokumentů, které vývojářům umožňuje snadno integrovat funkce prohlížení dokumentů do jejich .NET aplikací. Jednou z klíčových funkcí, které GroupDocs.Viewer nabízí, je možnost zakázat výběr textu v dokumentech PDF. Tato funkce je obzvláště užitečná v situacích, kdy potřebujete zabránit uživatelům v kopírování textu z citlivých dokumentů a zajistit tak bezpečnost a integritu dokumentů.

![Zakázat výběr textu v PDF pomocí GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Předpoklady
Než se ponoříme do podrobného návodu, jak zakázat výběr textu v PDF pomocí GroupDocs.Viewer pro .NET, ujistěte se, že máte splněny následující předpoklady:
1. Instalace GroupDocs.Viewer pro .NET: Ujistěte se, že jste si stáhli a nainstalovali GroupDocs.Viewer pro .NET z [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
2. Adresář dokumentů: Připravte si adresář, kam budou vaše dokumenty uloženy. Tento adresář budete muset zadat v úryvku kódu pro vykreslení dokumentu PDF.

## Importovat jmenné prostory
Nejprve je třeba importovat potřebné jmenné prostory pro přístup k funkcím poskytovaným GroupDocs.Viewer pro .NET. Zde je návod, jak to udělat:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme proces zakázání výběru textu v dokumentu PDF pomocí GroupDocs.Viewer pro .NET do několika kroků:
## Krok 1: Zadejte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
V tomto kroku nahraďte `"Your Document Directory"` s cestou k adresáři, kde se nachází váš dokument PDF.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tento krok definuje formát cest k souborům vykreslených stránek HTML. Každá stránka dokumentu PDF bude převedena do souboru HTML s pořadovým číslem stránky.
## Krok 3: Vykreslení PDF dokumentu s vypnutým výběrem textu
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Nahradit `"Path to Your PDF Document"` se skutečnou cestou k vašemu PDF souboru. Tento úryvek kódu inicializuje `Viewer` objekt, konfiguruje možnosti zobrazení HTML pro vkládání zdrojů a zakazuje výběr textu nastavením `RenderTextAsImage` majetek `true`.
## Krok 4: Zobrazení zprávy o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po vykreslení dokumentu PDF se v tomto kroku zobrazí zpráva o úspěšném dokončení spolu s adresářem, kde jsou uloženy vykreslené stránky HTML.

## Závěr
V tomto tutoriálu jsme se naučili, jak zakázat výběr textu v dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Dodržováním podrobného návodu můžete tuto funkci bezproblémově integrovat do svých aplikací .NET, čímž zajistíte zabezpečení dokumentů a vylepšíte uživatelský komfort.
## Často kladené otázky
### Mohu si přizpůsobit výstupní adresář pro vykreslené HTML stránky?
Ano, můžete zadat libovolnou cestu k adresáři, kam chcete ukládat vykreslené HTML stránky.
### Je GroupDocs.Viewer pro .NET kompatibilní s různými verzemi frameworku .NET?
Ano, GroupDocs.Viewer pro .NET je kompatibilní s různými verzemi frameworku .NET, včetně .NET Core a .NET Framework.
### Ovlivňuje zakázání výběru textu další funkce dokumentu PDF?
Ne, zakázání výběru textu pouze zabrání uživatelům ve výběru a kopírování textu z dokumentu. Ostatní funkce zůstávají zachovány.
### Mohu po vykreslení dokumentu znovu povolit výběr textu?
Ano, výběr textu můžete povolit jednoduše nastavením `RenderTextAsImage` majetek `false` v možnostech zobrazení HTML.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete si zdarma stáhnout zkušební verzi GroupDocs.Viewer pro .NET z [webové stránky](https://releases.groupdocs.com/).