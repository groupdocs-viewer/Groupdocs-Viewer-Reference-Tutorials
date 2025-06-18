---
"description": "Naučte se, jak vykreslit všechna rozvržení ve výkresech CAD pomocí GroupDocs.Viewer pro .NET. Pro bezproblémovou integraci postupujte podle našeho komplexního tutoriálu."
"linktitle": "Vykreslení všech rozvržení ve výkresech CAD"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení všech rozvržení ve výkresech CAD"
"url": "/cs/net/rendering-cad-drawings/render-all-layouts-cad/"
"weight": 11
---

# Vykreslení všech rozvržení ve výkresech CAD

## Zavedení
V oblasti správy a vizualizace dokumentů se GroupDocs.Viewer pro .NET pyšní jako všestranné řešení, které vývojářům umožňuje bez námahy vykreslovat různé typy dokumentů v rámci jejich .NET aplikací. Mezi jeho nesčetné funkce patří i efektivní vykreslování CAD výkresů, včetně složitých rozvržení, která s sebou nesou. V tomto tutoriálu se ponoříme do procesu využití GroupDocs.Viewer pro .NET k vykreslování všech rozvržení přítomných ve CAD výkresech. 
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1. Základní znalost vývoje v .NET: Znalost základů vývoje v .NET bude přínosem pro pochopení kroků implementace popsaných v tomto tutoriálu.
2. Instalace GroupDocs.Viewer pro .NET: Ujistěte se, že máte nainstalovanou knihovnu GroupDocs.Viewer pro .NET. Můžete si ji stáhnout z [webové stránky](https://releases.groupdocs.com/viewer/net/).
3. Soubory výkresů CAD: Získejte soubory výkresů CAD, které chcete vykreslit. Mohou zahrnovat soubory DWG s více rozvrženími.
4. Vývojové prostředí: Nastavte si preferované vývojové prostředí s potřebnými nástroji a závislostmi.

## Importovat jmenné prostory
Nejprve se ujistěte, že jste do svého projektu .NET importovali požadované jmenné prostory. Tyto jmenné prostory poskytují přístup k funkcím potřebným pro vykreslování CAD výkresů pomocí GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 2: Import jmenného prostoru System.IO
```csharp
using System.IO;
```
## Krok 1: Zadejte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Definujte adresář, kam chcete uložit vykreslený výstup.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Nastavte formát cest k souborům vykreslených stránek. V tomto případě budou stránky uloženy jako soubory HTML.
## Krok 3: Vytvoření instance objektu Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Vytvořte instanci třídy Viewer a jako parametr předejte cestu k souboru výkresu CAD.
## Krok 4: Konfigurace možností zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Nakonfigurujte možnosti zobrazení HTML a určete, že se mají pro výkresy CAD vykreslovat rozvržení.
## Krok 5: Vykreslení výkresu CAD
```csharp
viewer.View(options);
```
Vyvolejte metodu View objektu Viewer a předejte nakonfigurované možnosti pro vykreslení výkresu CAD.
## Krok 6: Zobrazení výstupního adresáře
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informujte uživatele o úspěšném vykreslení a umístění výstupního adresáře.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak využít GroupDocs.Viewer pro .NET k vykreslení všech rozvržení přítomných ve výkresech CAD. Dodržováním podrobného návodu a implementací poskytnutých úryvků kódu můžete tuto funkci bezproblémově integrovat do vašich aplikací .NET, a tím vylepšit možnosti vizualizace dokumentů.
## Často kladené otázky
### Je GroupDocs.Viewer kompatibilní s různými CAD formáty?
Ano, GroupDocs.Viewer podporuje vykreslování CAD výkresů ve formátech jako DWG a DXF.
### Mohu si přizpůsobit výstup vykreslování podle požadavků mé aplikace?
GroupDocs.Viewer rozhodně nabízí širokou škálu možností pro přizpůsobení výstupu vykreslování, včetně kvality obrazu, velikosti stránky a dalších.
### Vyžaduje GroupDocs.Viewer nějaké další licence pro komerční použití?
Ano, pro komerční použití může být nutné získat licenci. Můžete získat dočasné licence pro testovací účely nebo si zakoupit komerční licenci na webových stránkách.
### Mohu asynchronně vykreslovat CAD výkresy pomocí GroupDocs.Viewer?
Ano, GroupDocs.Viewer poskytuje asynchronní vykreslovací funkce, což umožňuje efektivní zpracování velkých CAD výkresů bez blokování hlavního vlákna.
### Nabízí GroupDocs.Viewer podporu pro řešení problémů a technickou pomoc?
Jistě můžete vyhledat podporu a pomoc na fóru komunity GroupDocs.Viewer, které je přístupné [zde](https://forum.groupdocs.com/c/viewer/9).