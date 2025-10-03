---
"description": "Naučte se, jak vykreslovat konkrétní složky a filtrovat zprávy v Outlooku pomocí GroupDocs.Viewer pro .NET. Zjednodušte si správu dokumentů v aplikacích .NET."
"linktitle": "Vykreslení specifických složek a filtrování zpráv (Outlook)"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení specifických složek a filtrování zpráv (Outlook)"
"url": "/cs/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/"
"weight": 11
type: docs
---
# Vykreslení specifických složek a filtrování zpráv (Outlook)

## Zavedení
Ve světě vývoje v .NET je efektivní správa a zobrazování dokumentů klíčové. GroupDocs.Viewer pro .NET tento úkol zjednodušuje tím, že poskytuje výkonné funkce pro bezproblémové vykreslování různých formátů dokumentů. V tomto tutoriálu se ponoříme do toho, jak vykreslovat konkrétní složky a filtrovat zprávy v Outlooku pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující:
1. GroupDocs.Viewer pro .NET: Ujistěte se, že máte nainstalovaný GroupDocs.Viewer pro .NET. Můžete si ho stáhnout z [webové stránky](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Musíte mít na svém počítači nainstalovaný .NET Framework.
3. Základní znalost jazyka C#: Znalost programovacího jazyka C# bude přínosem pro sledování tohoto tutoriálu.

## Importovat jmenné prostory
Nejprve si importujme potřebné jmenné prostory do našeho kódu v C#:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Nahradit `"Your Document Directory"` cestou k adresáři, kam chcete ukládat vykreslené dokumenty.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tento řádek definuje formát cest k souborům každé vykreslené stránky. V tomto příkladu vygeneruje HTML soubory s názvem `page_1.html`, `page_2.html`, a tak dále.
## Krok 3: Inicializace objektu prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Zde inicializujeme `Viewer` objekt s cestou k ukázkové složce Outlooku.
## Krok 4: Definování možností zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
Vytvoříme instanci `HtmlViewOptions` a určete formát pro vložené zdroje. Dále jsme nastavili, aby se složka Outlooku vykreslovala jako `"Входящие"` (Přicházející).
## Krok 5: Vykreslení dokumentu
```csharp
viewer.View(options);
```
Tento řádek spustí proces vykreslování se zadanými možnostmi.
## Krok 6: Zobrazení zprávy o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po vykreslení se zobrazí tato zpráva, která informuje o úspěšném dokončení procesu vykreslení a přesměruje uživatele do výstupního adresáře.

## Závěr
tomto tutoriálu jsme se podívali na to, jak vykreslovat konkrétní složky a filtrovat zprávy v Outlooku pomocí nástroje GroupDocs.Viewer pro .NET. Dodržením výše uvedených kroků můžete efektivně spravovat a zobrazovat dokumenty ve vašich aplikacích .NET.
## Často kladené otázky
### Mohu pomocí GroupDocs.Viewer pro .NET vykreslovat i jiné dokumenty než zprávy Outlooku?
Ano, GroupDocs.Viewer pro .NET podporuje širokou škálu formátů dokumentů včetně PDF, DOCX, XLSX a dalších.
### Je GroupDocs.Viewer pro .NET kompatibilní s .NET Core?
Ano, GroupDocs.Viewer pro .NET je kompatibilní s .NET Framework i .NET Core.
### Mohu si přizpůsobit výstupní formát vykreslování?
GroupDocs.Viewer pro .NET rozhodně nabízí různé možnosti pro přizpůsobení výstupu vykreslování, včetně formátů HTML, obrázků a PDF.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [webové stránky](https://releases.groupdocs.com/).
### Kde mohu hledat pomoc nebo podporu pro GroupDocs.Viewer pro .NET?
Můžete navštívit [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pro jakoukoli pomoc nebo dotazy.