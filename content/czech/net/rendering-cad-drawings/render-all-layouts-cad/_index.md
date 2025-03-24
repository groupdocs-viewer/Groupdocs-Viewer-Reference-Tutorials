---
title: Vykreslit všechna rozvržení ve výkresech CAD
linktitle: Vykreslit všechna rozvržení ve výkresech CAD
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat všechna rozvržení ve výkresech CAD pomocí GroupDocs.Viewer pro .NET. Postupujte podle našeho komplexního návodu pro bezproblémovou integraci.
weight: 11
url: /cs/net/rendering-cad-drawings/render-all-layouts-cad/
---
## Úvod
oblasti správy a vizualizace dokumentů je GroupDocs.Viewer pro .NET všestranným řešením, které umožňuje vývojářům bez námahy vykreslovat různé typy dokumentů v rámci jejich aplikací .NET. Mezi jeho nesčetné schopnosti patří schopnost efektivně vykreslovat CAD výkresy, včetně složitých rozvržení, které s sebou nesou. V tomto tutoriálu se ponoříme do procesu využití GroupDocs.Viewer pro .NET k vykreslení všech rozvržení přítomných ve výkresech CAD. 
## Předpoklady
Než se pustíte do tohoto kurzu, ujistěte se, že máte následující předpoklady:
1. Základní pochopení vývoje .NET: Znalost základů vývoje .NET bude přínosem pro pochopení kroků implementace uvedených v tomto kurzu.
2.  Instalace GroupDocs.Viewer pro .NET: Ujistěte se, že jste nainstalovali knihovnu GroupDocs.Viewer pro .NET. Můžete si jej stáhnout z[webová stránka](https://releases.groupdocs.com/viewer/net/).
3. Výkresové soubory CAD: Získejte výkresové soubory CAD, které chcete vykreslit. Ty mohou zahrnovat soubory DWG s více rozvrženími.
4. Vývojové prostředí: Nastavte si preferované vývojové prostředí s nezbytnými nástroji a závislostmi.

## Importovat jmenné prostory
Nejprve se ujistěte, že do svého projektu .NET importujete požadované jmenné prostory. Tyto jmenné prostory poskytují přístup k funkcím potřebným pro vykreslování CAD výkresů pomocí GroupDocs.Viewer.

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
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Nastavte formát cest k souborům vykreslených stránek. V tomto případě budou stránky uloženy jako soubory HTML.
## Krok 3: Vytvořte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Vytvořte instanci třídy Viewer a předejte cestu k souboru výkresu CAD jako parametr.
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Nakonfigurujte možnosti zobrazení HTML a určete, že se mají rozvržení vykreslovat pro výkresy CAD.
## Krok 5: Vykreslení výkresu CAD
```csharp
viewer.View(options);
```
Vyvolejte metodu View objektu Viewer a předejte nakonfigurované možnosti pro vykreslení výkresu CAD.
## Krok 6: Zobrazte výstupní adresář
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informujte uživatele o úspěšném vykreslení a umístění výstupního adresáře.

## Závěr
tomto tutoriálu jsme prozkoumali, jak využít GroupDocs.Viewer pro .NET k vykreslení všech rozvržení přítomných ve výkresech CAD. Budete-li se řídit podrobným průvodcem a implementací poskytnutých úryvků kódu, můžete tuto funkci hladce integrovat do svých aplikací .NET, a tím vylepšit možnosti vizualizace dokumentů.
## FAQ
### Je GroupDocs.Viewer kompatibilní s různými formáty CAD?
Ano, GroupDocs.Viewer podporuje vykreslování CAD výkresů ve formátech jako DWG a DXF.
### Mohu přizpůsobit výstup vykreslování podle požadavků mé aplikace?
GroupDocs.Viewer rozhodně nabízí širokou škálu možností pro přizpůsobení výstupu vykreslování, včetně kvality obrazu, velikosti stránky a dalších.
### Vyžaduje GroupDocs.Viewer nějaké další licence pro komerční použití?
Ano, pro komerční použití možná budete muset získat licenci. Z webové stránky můžete získat dočasné licence pro testovací účely nebo zakoupit komerční licenci.
### Mohu vykreslovat výkresy CAD asynchronně s GroupDocs.Viewer?
Ano, GroupDocs.Viewer poskytuje možnosti asynchronního vykreslování, což umožňuje efektivní manipulaci s velkými CAD výkresy bez blokování hlavního vlákna.
### Nabízí GroupDocs.Viewer podporu pro odstraňování problémů a technickou pomoc?
 Jistě můžete vyhledat podporu a pomoc na fóru komunity GroupDocs.Viewer, které je dostupné[tady](https://forum.groupdocs.com/c/viewer/9).