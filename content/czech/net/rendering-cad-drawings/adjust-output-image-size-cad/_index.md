---
title: Upravte velikost výstupního obrázku pro výkresy CAD
linktitle: Upravte velikost výstupního obrázku pro výkresy CAD
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak upravit velikost výstupního obrázku pro výkresy CAD pomocí GroupDocs.Viewer pro .NET. Zvyšte viditelnost a použitelnost bez námahy.
weight: 15
url: /cs/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# Upravte velikost výstupního obrázku pro výkresy CAD

## Úvod
CAD výkresy často vyžadují specifické úpravy pro optimální zobrazení a prezentaci. GroupDocs.Viewer for .NET poskytuje výkonnou sadu nástrojů pro správu a přizpůsobení výstupu výkresů CAD. V tomto tutoriálu vás krok za krokem provedeme procesem úpravy velikosti výstupního obrázku pro výkresy CAD.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
1.  GroupDocs.Viewer for .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z[tady](https://releases.groupdocs.com/viewer/net/).
2. Adresář dokumentů: Připravte adresář, kde je umístěn váš dokument.
3. Základní porozumění: Seznamte se se základními pojmy programování .NET.

## Importovat jmenné prostory
Nejprve se ujistěte, že jste importovali potřebné jmenné prostory pro přístup k funkcím GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavte výstupní adresář
Definujte adresář, kam chcete uložit výstupní obrázky výkresů CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
Nastavte formát cest k souboru stránky. Tento formát bude použit k pojmenování a uložení jednotlivých stránek jako HTML souborů:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Upravte velikost obrázku
Uvnitř bloku using pro objekt Viewer upravte velikost obrázku pro výkresy CAD nastavením příslušných možností:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Krok 4: Zobrazte výstupní adresář
Po vykreslení dokumentu zobrazte zprávu o úspěšném vykreslení a uveďte umístění výstupního adresáře:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Úprava velikosti výstupního obrazu pro výkresy CAD je zásadní pro zlepšení jejich viditelnosti a použitelnosti. S GroupDocs.Viewer for .NET se tento proces zjednoduší a zefektivní, což vám umožní přizpůsobit výstup podle vašich specifických požadavků.
## FAQ
### Mohu upravit velikost výstupního obrázku pro jiné typy dokumentů kromě výkresů CAD?
Ano, GroupDocs.Viewer for .NET podporuje různé typy dokumentů a můžete upravit velikost výstupního obrázku pro většinu formátů dokumentů.
### Je GroupDocs.Viewer for .NET kompatibilní s různými verzemi rozhraní .NET?
Ano, GroupDocs.Viewer for .NET je kompatibilní s více verzemi frameworku .NET, což zajišťuje flexibilitu a použitelnost v různých prostředích.
### Jsou pro GroupDocs.Viewer pro .NET k dispozici nějaké možnosti licencování?
Ano, můžete prozkoumat různé možnosti licencování, včetně dočasných licencí a komerčních licencí, aby vyhovovaly vašim potřebám.
### Mohu přizpůsobit výstupní formát vykreslených dokumentů?
Rozhodně, GroupDocs.Viewer for .NET nabízí různé možnosti přizpůsobení, které vám umožní přizpůsobit výstupní formát podle vašich preferencí.
### Kde najdu další podporu nebo pomoc s GroupDocs.Viewer pro .NET?
 Můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9) získat podporu, klást otázky a zapojit se do komunity.