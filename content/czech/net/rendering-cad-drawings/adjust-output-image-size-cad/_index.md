---
"description": "Naučte se, jak upravit velikost výstupního obrázku pro CAD výkresy pomocí GroupDocs.Viewer pro .NET. Bez námahy vylepšete viditelnost a použitelnost."
"linktitle": "Úprava velikosti výstupního obrázku pro výkresy CAD"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Úprava velikosti výstupního obrázku pro výkresy CAD"
"url": "/cs/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Úprava velikosti výstupního obrázku pro výkresy CAD

## Zavedení
Výkresy CAD často vyžadují specifické úpravy pro optimální zobrazení a prezentaci. GroupDocs.Viewer pro .NET poskytuje výkonnou sadu nástrojů pro správu a přizpůsobení výstupu výkresů CAD. V tomto tutoriálu vás krok za krokem provedeme procesem úpravy velikosti výstupního obrazu pro výkresy CAD.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z [zde](https://releases.groupdocs.com/viewer/net/).
2. Adresář dokumentů: Připravte adresář, ve kterém se váš dokument nachází.
3. Základní znalosti: Seznamte se se základními koncepty programování v .NET.

## Importovat jmenné prostory
Nejprve se ujistěte, že jste importovali potřebné jmenné prostory pro přístup k funkcím GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavení výstupního adresáře
Definujte adresář, kam chcete ukládat výstupní obrázky výkresů CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru stránky
Nastavte formát cest k souborům stránek. Tento formát bude použit k pojmenování a uložení jednotlivých stránek jako souborů HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Úprava velikosti obrázku
Uvnitř bloku using pro objekt Viewer upravte velikost obrázku pro výkresy CAD nastavením příslušných možností:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Krok 4: Zobrazení výstupního adresáře
Po vykreslení dokumentu zobrazte zprávu o úspěšném vykreslení a uveďte umístění výstupního adresáře:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Úprava velikosti výstupního obrázku pro CAD výkresy je klíčová pro zlepšení jejich viditelnosti a použitelnosti. S GroupDocs.Viewer pro .NET se tento proces zjednodušuje a zefektivňuje, což vám umožňuje přizpůsobit výstup vašim specifickým požadavkům.
## Často kladené otázky
### Mohu upravit velikost výstupního obrázku i pro jiné typy dokumentů než výkresy CAD?
Ano, GroupDocs.Viewer pro .NET podporuje různé typy dokumentů a pro většinu formátů dokumentů můžete upravit velikost výstupního obrázku.
### Je GroupDocs.Viewer pro .NET kompatibilní s různými verzemi frameworku .NET?
Ano, GroupDocs.Viewer pro .NET je kompatibilní s více verzemi frameworku .NET, což zajišťuje flexibilitu a použitelnost v různých prostředích.
### Existují nějaké možnosti licencování pro GroupDocs.Viewer pro .NET?
Ano, můžete si prohlédnout různé možnosti licencování, včetně dočasných licencí a komerčních licencí, které budou vyhovovat vašim potřebám.
### Mohu si přizpůsobit výstupní formát vykreslených dokumentů?
GroupDocs.Viewer pro .NET rozhodně nabízí různé možnosti přizpůsobení, které vám umožňují přizpůsobit výstupní formát vašim požadavkům.
### Kde najdu další podporu nebo pomoc s GroupDocs.Viewer pro .NET?
Můžete navštívit fórum GroupDocs.Viewer [zde](https://forum.groupdocs.com/c/viewer/9) získat podporu, klást otázky a zapojit se do komunity.