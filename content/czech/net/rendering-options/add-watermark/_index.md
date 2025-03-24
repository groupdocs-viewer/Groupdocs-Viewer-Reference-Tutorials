---
title: Přidat vodoznak do dokumentu
linktitle: Přidat vodoznak do dokumentu
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak plynule přidávat vodoznaky do dokumentů pomocí GroupDocs.Viewer pro .NET. Vylepšete zabezpečení dokumentů a branding pomocí tohoto snadno srozumitelného návodu.
weight: 10
url: /cs/net/rendering-options/add-watermark/
---
## Úvod
V dnešní digitální době je bezproblémová správa a prohlížení různých formátů dokumentů nutností pro mnoho firem i jednotlivců. Naštěstí s nástroji jako GroupDocs.Viewer pro .NET se manipulace s dokumenty stává hračkou. Tato výkonná knihovna .NET umožňuje vývojářům bez námahy integrovat funkci prohlížení dokumentů do svých aplikací, což uživatelům umožňuje prohlížet dokumenty, aniž by potřebovali původní software, který je vytvořil.
## Předpoklady
Než se pustíte do používání GroupDocs.Viewer for .NET k přidávání vodoznaků do dokumentů, ujistěte se, že máte následující:
1. Nastavení prostředí: Nechte si nastavit vývojové prostředí s nainstalovaným rozhraním .NET Framework nebo .NET Core.
2.  GroupDocs.Viewer for .NET: Stáhněte si a nainstalujte knihovnu GroupDocs.Viewer for .NET z[stránka ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Soubory dokumentů: Připravte si soubory dokumentů, se kterými chcete pracovat, jako jsou DOCX, PDF nebo jiné.
4. Základní znalost C#: Pro implementaci příkladů kódu je nutná znalost programovacího jazyka C#.

## Importovat jmenné prostory
Než začnete přidávat vodoznaky do dokumentů pomocí GroupDocs.Viewer for .NET, ujistěte se, že jste do kódu C# importovali požadované jmenné prostory. Tento krok vám umožní bezproblémový přístup ke třídám a metodám poskytovaným knihovnou.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si projdeme proces přidání vodoznaku do dokumentu pomocí GroupDocs.Viewer for .NET. Pro bezproblémovou integraci funkcí vodoznaku do vaší aplikace postupujte podle těchto kroků.
## Krok 1: Nastavte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Zadejte adresář, kam chcete uložit výstupní soubory po použití vodoznaku.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Nastavte formát cest k souborům vykreslených stránek. V tomto příkladu budou vygenerovány soubory HTML s čísly stránek.
## Krok 3: Vytvořte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kód pokračuje v dalším kroku...
}
```
Vytvořte instanci třídy Viewer a jako parametr předejte cestu k souboru dokumentu. V tomto příkladu používáme ukázkový soubor DOCX.
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Nakonfigurujte možnosti zobrazení HTML, včetně textu vodoznaku, který chcete přidat do dokumentu.
## Krok 5: Zobrazte dokument s vodoznakem
```csharp
viewer.View(options);
```
Vyvolejte metodu View objektu Viewer a předejte nakonfigurované možnosti. Tím se vykreslí dokument se zadaným vodoznakem.
## Krok 6: Zobrazte cestu výstupního adresáře
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informujte uživatele o úspěšném vykreslení dokumentu a uveďte adresář, kde jsou uloženy výstupní soubory.

## Závěr
GroupDocs.Viewer pro .NET poskytuje pohodlný způsob programového přidávání vodoznaků do dokumentů. Dodržováním kroků popsaných v tomto tutoriálu můžete bezproblémově integrovat funkci vodoznaku do vašich aplikací .NET a zlepšit tak zabezpečení dokumentů a branding.
## FAQ
### Mohu upravit vzhled vodoznaku?
Ano, můžete přizpůsobit různé vlastnosti vodoznaku, jako je text, písmo, barva, velikost a poloha.
### Podporuje GroupDocs.Viewer prohlížení dokumentů ze vzdálených zdrojů?
Ano, GroupDocs.Viewer podporuje prohlížení dokumentů z místního úložiště i ze vzdálených URL.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.groupdocs.com/).
### Mohu přidat vodoznak na více stránek dokumentu?
GroupDocs.Viewer rozhodně umožňuje přidávání vodoznaků na jednotlivé stránky nebo všechny stránky dokumentu.
### Jak mohu získat podporu nebo pomoc, pokud narazím na nějaké problémy?
 Pomoc a podporu můžete hledat na fórech komunity GroupDocs[tady](https://forum.groupdocs.com/c/viewer/9).