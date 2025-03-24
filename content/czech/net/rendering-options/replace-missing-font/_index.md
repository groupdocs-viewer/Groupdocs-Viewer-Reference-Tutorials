---
title: Nahradit chybějící písmo
linktitle: Nahradit chybějící písmo
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak nahradit chybějící písma v dokumentech .NET bez námahy pomocí GroupDocs.Viewer. Zajistěte přesné vykreslování pomocí jednoduchých kroků.
weight: 20
url: /cs/net/rendering-options/replace-missing-font/
---
## Úvod
Ve světě vývoje .NET je efektivní manipulace s dokumenty zásadní. GroupDocs.Viewer for .NET poskytuje výkonné řešení pro prohlížení různých formátů dokumentů v rámci vašich aplikací .NET. V tomto tutoriálu prozkoumáme, jak používat GroupDocs.Viewer pro .NET k nahrazení chybějících písem v dokumentech. Ať už pracujete s PDF, PowerPoint prezentacemi nebo dokumenty Wordu, GroupDocs.Viewer zjednodušuje proces a zajišťuje, že vaše dokumenty budou vykresleny přesně, i když chybí písma.
## Předpoklady
Než se pustíte do tohoto návodu, ujistěte se, že máte následující:
1. GroupDocs.Viewer for .NET: Stáhněte si a nainstalujte knihovnu GroupDocs.Viewer z webu](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Nastavte vývojové prostředí .NET, jako je Visual Studio.
3. Základní znalost C#: Znalost programovacího jazyka C# a .NET frameworku.

## Importovat jmenné prostory
Do kódu C# importujte potřebné jmenné prostory pro přístup k funkcím GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si projdeme proces nahrazení chybějících písem v dokumentech pomocí GroupDocs.Viewer pro .NET.
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Nastavte adresář, kam se budou ukládat vykreslené stránky dokumentu.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Zadejte formát pro pojmenování výstupních souborů HTML. V tomto příkladu bude každá stránka uložena jako soubor HTML s konvencí pojmenování "page_{page_number}.html".
## Krok 3: Inicializujte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inicializujte novou instanci třídy Viewer a jako parametr předejte cestu k souboru dokumentu (v tomto případě prezentaci PowerPoint s chybějícími fonty).
## Krok 4: Nastavte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Vytvořte instanci HtmlViewOptions a nakonfigurujte ji pro vkládání prostředků do výstupu HTML. Zadejte výchozí název písma, který se má použít jako náhrada za chybějící písma.
## Krok 5: Vykreslení dokumentu
```csharp
viewer.View(options);
```
Vyvolejte metodu View objektu Viewer a předejte možnosti zobrazení HTML. Tím se vykreslí stránky dokumentu pomocí zadaných možností.
## Krok 6: Zobrazte výstupní cestu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Vytiskněte zprávu o úspěšném vykreslení dokumentu a uveďte cestu, kam jsou uloženy výstupní soubory HTML.

## Závěr
V tomto tutoriálu jsme se naučili, jak používat GroupDocs.Viewer pro .NET k nahrazení chybějících písem v dokumentech. Pomocí těchto kroků můžete zajistit, že vaše dokumenty budou přesně vykresleny, i když některá písma nejsou k dispozici. GroupDocs.Viewer zjednodušuje proces a umožňuje vám soustředit se na vytváření robustních aplikací .NET bez obav z problémů s kompatibilitou písem.
## FAQ
### Dokáže GroupDocs.Viewer zvládnout jiné typy problémů souvisejících s písmy?
Ano, GroupDocs.Viewer poskytuje různé funkce související s písmy, včetně nahrazování písem a detekce písem.
### Je GroupDocs.Viewer kompatibilní se všemi .NET frameworky?
GroupDocs.Viewer podporuje širokou škálu .NET frameworků, včetně .NET Core a .NET Standard.
### Mohu upravit výchozí nahrazení písma v GroupDocs.Viewer?
Jako výchozí náhradu za chybějící písma můžete určit libovolné písmo podle svého výběru.
### Podporuje GroupDocs.Viewer dávkové zpracování dokumentů?
Ano, GroupDocs.Viewer umožňuje zpracovávat více dokumentů současně, takže je ideální pro scénáře dávkového zpracování.
### Kde najdu další pomoc nebo podporu pro GroupDocs.Viewer?
 Můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9) pro jakoukoli pomoc nebo dotazy na podporu.