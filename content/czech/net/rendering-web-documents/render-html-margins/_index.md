---
title: Vykreslování HTML s uživatelsky definovanými okraji
linktitle: Vykreslování HTML s uživatelsky definovanými okraji
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat HTML s vlastními okraji v .NET pomocí GroupDocs.Viewer. Vylepšete prezentaci dokumentů bez námahy.
type: docs
weight: 11
url: /cs/net/rendering-web-documents/render-html-margins/
---
## Úvod
oblasti vývoje .NET je vykreslování HTML s uživatelsky definovanými okraji zásadním aspektem vytváření vizuálně přitažlivých dokumentů. Ať už se jedná o úpravu okrajů pro web nebo konfiguraci rozvržení tisku, přesná kontrola nad okraji zlepšuje celkovou prezentaci obsahu. V tomto tutoriálu se ponoříme do využití GroupDocs.Viewer pro .NET k bezproblémovému dosažení této funkce.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1.  GroupDocs.Viewer for .NET: Nainstalujte knihovnu GroupDocs.Viewer pro .NET. Můžete si jej stáhnout z[webová stránka](https://releases.groupdocs.com/viewer/net/).
2. Prostředí .NET: Mít pracovní prostředí pro vývoj .NET.
3. Dokument HTML: Připravte dokument HTML, který chcete vykreslit s vlastními okraji.

## Importovat jmenné prostory
Než začnete, nezapomeňte importovat potřebné jmenné prostory:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Nastavte výstupní adresář
Definujte adresář, kam chcete ukládat vykreslené soubory:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
Nastavte formát cest k souborům vykreslených stránek:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "html_render_margins_page_{0}.jpg");
```
## Krok 3: Upravte okraje pro vykreslování JPG
Konfigurace okrajů pro vykreslování HTML do formátu JPG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## Krok 4: Upravte okraje pro vykreslování PNG
Podobně upravte okraje pro vykreslení HTML do formátu PNG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## Krok 5: Upravte okraje pro vykreslování PDF
Pro vykreslování PDF nastavte okraje podle toho:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```

## Závěr
Přizpůsobení okrajů při vykreslování dokumentů HTML v .NET pomocí GroupDocs.Viewer umožňuje vývojářům přesně přizpůsobit prezentaci obsahu. Podle tohoto návodu můžete bez námahy upravit okraje pro výstupní formáty JPG, PNG nebo PDF, čímž zvýšíte vizuální přitažlivost a čitelnost vašich dokumentů.
## FAQ
### Je GroupDocs.Viewer for .NET kompatibilní s různými formáty HTML?
GroupDocs.Viewer podporuje širokou škálu formátů HTML, což zajišťuje kompatibilitu s různými dokumenty HTML.
### Mohu upravit okraje dynamicky na základě obsahu dokumentu?
Ano, můžete programově upravit okraje na základě vlastností dokumentu nebo uživatelských preferencí.
### Existují nějaká omezení pro úpravy marží?
GroupDocs.Viewer nabízí flexibilitu v úpravách okrajů, což umožňuje přizpůsobení v rozumných mezích.
### Podporuje GroupDocs.Viewer jiné výstupní formáty kromě JPG, PNG a PDF?
Ano, GroupDocs.Viewer podporuje vykreslování do různých formátů, včetně TIFF, SVG a dalších.
### Jak mohu vyhledat další pomoc nebo nahlásit problémy související s GroupDocs.Viewer?
 Můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9) za podporu a diskuze.