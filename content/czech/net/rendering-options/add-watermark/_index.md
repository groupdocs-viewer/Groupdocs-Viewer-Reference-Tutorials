---
"description": "Naučte se, jak bez problémů přidávat vodoznaky do dokumentů pomocí GroupDocs.Viewer pro .NET. Vylepšete zabezpečení dokumentů a budování značky pomocí tohoto snadno srozumitelného tutoriálu."
"linktitle": "Přidat vodoznak do dokumentu"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Přidat vodoznak do dokumentu"
"url": "/cs/net/rendering-options/add-watermark/"
"weight": 10
type: docs
---
# Přidat vodoznak do dokumentu

## Zavedení
V dnešní digitální době je bezproblémová správa a prohlížení dokumentů různých formátů nezbytností pro mnoho firem i jednotlivců. Naštěstí s nástroji, jako je GroupDocs.Viewer pro .NET, se práce s dokumenty stává hračkou. Tato výkonná knihovna .NET umožňuje vývojářům snadno integrovat funkce prohlížení dokumentů do svých aplikací, což uživatelům umožňuje prohlížet dokumenty bez nutnosti původního softwaru, ve kterém byly vytvořeny.
## Předpoklady
Než se pustíte do používání GroupDocs.Viewer pro .NET k přidávání vodoznaků do dokumentů, ujistěte se, že máte následující:
1. Nastavení prostředí: Mějte nastavené vývojové prostředí s nainstalovaným .NET Framework nebo .NET Core.
2. GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte knihovnu GroupDocs.Viewer pro .NET z [stránka ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Soubory dokumentů: Připravte si soubory dokumentů, se kterými chcete pracovat, například DOCX, PDF nebo jiné.
4. Základní znalost jazyka C#: Pro implementaci příkladů kódu je nezbytná znalost programovacího jazyka C#.

## Importovat jmenné prostory
Než začnete přidávat vodoznaky do dokumentů pomocí GroupDocs.Viewer pro .NET, nezapomeňte importovat požadované jmenné prostory do kódu C#. Tento krok vám umožní bezproblémový přístup ke třídám a metodám poskytovaným knihovnou.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si projdeme proces přidání vodoznaku do dokumentu pomocí GroupDocs.Viewer pro .NET. Postupujte podle těchto kroků pro bezproblémovou integraci funkce vodoznaku do vaší aplikace.
## Krok 1: Nastavení výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Zadejte adresář, kam chcete uložit výstupní soubory po použití vodoznaku.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Nastavte formát cest k souborům vykreslených stránek. V tomto příkladu budou vygenerovány soubory HTML s čísly stránek.
## Krok 3: Vytvoření instance objektu Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kód pokračuje v dalším kroku...
}
```
Vytvořte instanci třídy Viewer a jako parametr předejte cestu k souboru dokumentu. V tomto příkladu používáme vzorový soubor DOCX.
## Krok 4: Konfigurace možností zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Nakonfigurujte možnosti zobrazení HTML, včetně textu vodoznaku, který chcete do dokumentu přidat.
## Krok 5: Zobrazení dokumentu s vodoznakem
```csharp
viewer.View(options);
```
Volejte metodu View objektu Viewer a předejte jí nakonfigurované možnosti. Tím se dokument vykreslí se zadaným vodoznakem.
## Krok 6: Zobrazení cesty k výstupnímu adresáři
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informujte uživatele o úspěšném vykreslení dokumentu a uveďte adresář, kam jsou uloženy výstupní soubory.

## Závěr
GroupDocs.Viewer pro .NET nabízí pohodlný způsob programově přidávat vodoznaky do dokumentů. Dodržováním kroků popsaných v tomto tutoriálu můžete bezproblémově integrovat funkci vodoznaků do svých aplikací .NET, a tím zvýšit zabezpečení dokumentů a budování značky.
## Často kladené otázky
### Mohu si přizpůsobit vzhled vodoznaku?
Ano, můžete si přizpůsobit různé vlastnosti vodoznaku, jako je text, písmo, barva, velikost a umístění.
### Podporuje GroupDocs.Viewer prohlížení dokumentů ze vzdálených zdrojů?
Ano, GroupDocs.Viewer podporuje prohlížení dokumentů z lokálního úložiště i ze vzdálených URL adres.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.groupdocs.com/).
### Mohu přidat vodoznaky na více stránek dokumentu?
GroupDocs.Viewer samozřejmě umožňuje přidávat vodoznaky na jednotlivé stránky nebo na všechny stránky dokumentu.
### Jak mohu získat podporu nebo pomoc, pokud narazím na nějaké problémy?
Pomoc a podporu můžete vyhledat na komunitních fórech GroupDocs. [zde](https://forum.groupdocs.com/c/viewer/9).