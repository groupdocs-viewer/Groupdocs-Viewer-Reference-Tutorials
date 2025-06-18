---
"description": "Naučte se, jak snadno nahradit chybějící písma v dokumentech .NET pomocí GroupDocs.Viewer. Zajistěte přesné vykreslování pomocí jednoduchých kroků."
"linktitle": "Nahradit chybějící písmo"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Nahradit chybějící písmo"
"url": "/cs/net/rendering-options/replace-missing-font/"
"weight": 20
---

# Nahradit chybějící písmo

## Zavedení
Ve světě vývoje v .NET je efektivní práce s dokumenty klíčová. GroupDocs.Viewer pro .NET poskytuje výkonné řešení pro prohlížení různých formátů dokumentů ve vašich .NET aplikacích. V tomto tutoriálu se podíváme na to, jak pomocí GroupDocs.Viewer pro .NET nahradit chybějící písma v dokumentech. Ať už pracujete s PDF, prezentacemi v PowerPointu nebo dokumenty Wordu, GroupDocs.Viewer zjednodušuje proces a zajišťuje, že vaše dokumenty budou vykresleny přesně, i když chybí písma.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující:
1. GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte knihovnu GroupDocs.Viewer z webových stránek](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Nastavte vývojové prostředí .NET, například Visual Studio.
3. Základní znalost C#: Znalost programovacího jazyka C# a frameworku .NET.

## Importovat jmenné prostory
kódu C# importujte potřebné jmenné prostory pro přístup k funkcím GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si projdeme proces nahrazení chybějících písem v dokumentech pomocí GroupDocs.Viewer pro .NET.
## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Nastavte adresář, kam budou uloženy vykreslené stránky dokumentu.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Zadejte formát pro pojmenování výstupních souborů HTML. V tomto příkladu bude každá stránka uložena jako soubor HTML s konvencí pojmenování „page_{page_number}.html“.
## Krok 3: Inicializace objektu prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inicializujte novou instanci třídy Viewer a jako parametr jí předejte cestu k souboru dokumentu (v tomto případě prezentaci PowerPoint s chybějícími fonty).
## Krok 4: Nastavení možností zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Vytvořte instanci HtmlViewOptions a nakonfigurujte ji tak, aby vkládala zdroje do HTML výstupu. Zadejte výchozí název písma, který se má použít jako náhrada za chybějící písma.
## Krok 5: Vykreslení dokumentu
```csharp
viewer.View(options);
```
Volejte metodu View objektu Viewer a předejte jí možnosti zobrazení HTML. Tím se stránky dokumentu vykreslí s použitím zadaných možností.
## Krok 6: Zobrazení výstupní cesty
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Vytiskněte zprávu oznamující úspěšné vykreslení dokumentu a zadejte cestu, kam jsou uloženy výstupní soubory HTML.

## Závěr
V tomto tutoriálu jsme se naučili, jak pomocí nástroje GroupDocs.Viewer pro .NET nahradit chybějící písma v dokumentech. Dodržením těchto kroků zajistíte, že se vaše dokumenty budou vykreslovat přesně, i když některá písma nejsou k dispozici. GroupDocs.Viewer tento proces zjednodušuje a umožňuje vám soustředit se na vytváření robustních aplikací pro .NET, aniž byste se museli starat o problémy s kompatibilitou písem.
## Často kladené otázky
### Dokáže GroupDocs.Viewer zvládnout i jiné typy problémů souvisejících s písmy?
Ano, GroupDocs.Viewer nabízí různé funkce související s písmy, včetně nahrazování písem a detekce písem.
### Je GroupDocs.Viewer kompatibilní se všemi .NET frameworky?
GroupDocs.Viewer podporuje širokou škálu frameworků .NET, včetně .NET Core a .NET Standard.
### Mohu si přizpůsobit výchozí nahrazení písma v GroupDocs.Viewer?
Samozřejmě můžete jako výchozí náhradu za chybějící písma zadat libovolné písmo.
### Podporuje GroupDocs.Viewer dávkové zpracování dokumentů?
Ano, GroupDocs.Viewer umožňuje zpracovávat více dokumentů současně, což je ideální pro dávkové zpracování.
### Kde mohu najít další pomoc nebo podporu pro GroupDocs.Viewer?
Můžete navštívit fórum GroupDocs.Viewer [zde](https://forum.groupdocs.com/c/viewer/9) pro jakékoli dotazy ohledně pomoci nebo podpory.