---
title: Vykreslení obrázků aplikace Visio
linktitle: Vykreslení obrázků aplikace Visio
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat obrázky aplikace Visio pomocí GroupDocs.Viewer for .NET s tímto komplexním. Vylepšete možnosti prohlížení dokumentů ve svých aplikacích .NET.
weight: 10
url: /cs/net/rendering-visio-documents/render-visio-figures/
---

# Vykreslení obrázků aplikace Visio

## Úvod
V dnešní digitální době hraje vykreslování dokumentů zásadní roli v různých aplikacích. Ať už se jedná o zobrazování dokumentů na webových stránkách nebo jejich převod do různých formátů, efektivní vykreslování je zásadní. GroupDocs.Viewer for .NET poskytuje robustní řešení pro prohlížení a manipulaci s dokumenty v aplikacích .NET. V tomto kurzu se ponoříme do vykreslování obrázků Visio pomocí GroupDocs.Viewer pro .NET a rozdělíme proces do jednoduchých kroků.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1. Nastavení prostředí: Ujistěte se, že máte pracovní prostředí pro vývoj .NET.
2.  GroupDocs.Viewer for .NET: Stáhněte si a nainstalujte GroupDocs.Viewer pro .NET z webu[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Základní porozumění C#: Seznamte se se základy programovacího jazyka C#.
4. Ukázkový dokument Visio: Připravte si ukázkový dokument Visia k vykreslení.

## Importovat jmenné prostory
Ve svém projektu C# začněte importováním potřebných jmenných prostorů:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Vykreslování do HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Output Directory (Výstupní adresář): Definujte adresář, do kterého bude uložen vykreslený HTML.
- Formát cesty souboru stránky: Zadejte formát cesty pro stránku HTML.
- Inicializace prohlížeče: Inicializujte objekt Viewer s cestou k dokumentu aplikace Visio.
- Možnosti zobrazení HTML: Konfigurace možností pro vykreslování HTML.
- Možnosti vykreslování Visio: Nastavte možnosti specifické pro vykreslování Visia, jako je vykreslování pouze obrázků a šířka obrázku.
## 2. Vykreslování do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Podobně jako při vykreslování do HTML nakonfigurujte možnosti vykreslování do formátu JPG.
## 3. Vykreslování do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Konfigurace pro vykreslování do formátu PNG se řídí podobným vzorem jako vykreslování JPG.
## 4. Vykreslování do PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Pro vykreslování do PDF nakonfigurujte volby specifické pro formát PDF.

## Závěr
V tomto kurzu jsme prozkoumali, jak vykreslit obrázky Visia pomocí GroupDocs.Viewer pro .NET. Dodržováním tohoto podrobného průvodce můžete bezproblémově integrovat funkce vykreslování dokumentů do vašich aplikací .NET, čímž zvýšíte uživatelský komfort a produktivitu.
## FAQ
### Mohu přizpůsobit možnosti vykreslování obrázků aplikace Visio?
Ano, GroupDocs.Viewer for .NET poskytuje rozsáhlé možnosti přizpůsobení vykreslování, včetně šířky obrázku, vykreslování pouze obrázků a dalších.
### Je GroupDocs.Viewer for .NET vhodný pro vykreslování dokumentů ve velkém měřítku?
GroupDocs.Viewer for .NET je rozhodně optimalizován pro efektivní zpracování rozsáhlých dokumentů.
### Podporuje GroupDocs.Viewer jiné formáty dokumentů kromě aplikace Visio?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office, AutoCAD a dalších.
### Mohu integrovat GroupDocs.Viewer do webových aplikací?
Ano, GroupDocs.Viewer lze bez problémů integrovat do webových aplikací pro prohlížení dokumentů a manipulaci s nimi.
### Je k dispozici zkušební verze pro testování před zakoupením?
Ano, můžete využít bezplatnou zkušební verzi z[webová stránka](https://releases.groupdocs.com/) k otestování schopností GroupDocs.Viewer pro .NET.