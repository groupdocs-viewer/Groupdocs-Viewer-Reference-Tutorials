---
"description": "Naučte se, jak vykreslovat obrázky ve Visiu pomocí GroupDocs.Viewer pro .NET v tomto komplexním návodu. Vylepšete možnosti prohlížení dokumentů ve vašich .NET aplikacích."
"linktitle": "Vykreslení obrázků z aplikace Visio"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení obrázků z aplikace Visio"
"url": "/cs/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
---

# Vykreslení obrázků z aplikace Visio

## Zavedení
dnešní digitální době hraje vykreslování dokumentů klíčovou roli v různých aplikacích. Ať už se jedná o zobrazování dokumentů na webových stránkách nebo jejich převod do různých formátů, efektivní vykreslování je nezbytné. GroupDocs.Viewer pro .NET poskytuje robustní řešení pro prohlížení a manipulaci s dokumenty v aplikacích .NET. V tomto tutoriálu se ponoříme do vykreslování obrázků ve Visiu pomocí GroupDocs.Viewer pro .NET a rozdělíme proces do jednoduchých kroků.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:
1. Nastavení prostředí: Ujistěte se, že máte pracovní prostředí pro vývoj v .NET.
2. GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Základní znalost jazyka C#: Seznamte se se základy programovacího jazyka C#.
4. Ukázkový dokument aplikace Visio: Mějte připravený ukázkový dokument aplikace Visio k vykreslení.

## Importovat jmenné prostory
Ve vašem projektu C# začněte importem potřebných jmenných prostorů:
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
- Výstupní adresář: Definujte adresář, kam bude uložen vykreslený HTML kód.
- Formát cesty k souboru stránky: Zadejte formát cesty pro stránku HTML.
- Inicializace prohlížeče: Inicializujte objekt prohlížeče cestou k dokumentu aplikace Visio.
- Možnosti zobrazení HTML: Konfigurace možností pro vykreslování HTML.
- Možnosti vykreslování ve Visiu: Nastavte možnosti specifické pro vykreslování ve Visiu, například vykreslování pouze obrázků a šířky obrázků.
## 2. Vykreslení do JPG
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
- Podobně jako u vykreslování do HTML nakonfigurujte možnosti pro vykreslování do formátu JPG.
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
- Pro vykreslování do PDF nakonfigurujte možnosti specifické pro formát PDF.

## Závěr
tomto tutoriálu jsme prozkoumali, jak vykreslovat obrázky ve Visiu pomocí GroupDocs.Viewer pro .NET. Dodržováním podrobných pokynů můžete bezproblémově integrovat funkce vykreslování dokumentů do svých aplikací .NET, a tím zlepšit uživatelský komfort a produktivitu.
## Často kladené otázky
### Mohu si přizpůsobit možnosti vykreslování obrázků ve Visiu?
Ano, GroupDocs.Viewer pro .NET nabízí rozsáhlé možnosti pro přizpůsobení vykreslování, včetně šířky obrázků, vykreslování pouze obrázků a dalších.
### Je GroupDocs.Viewer pro .NET vhodný pro vykreslování dokumentů ve velkém měřítku?
Rozhodně je GroupDocs.Viewer pro .NET optimalizován pro efektivní zpracování rozsáhlých dokumentů.
### Podporuje GroupDocs.Viewer i jiné formáty dokumentů než Visio?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office, AutoCADu a dalších.
### Mohu integrovat GroupDocs.Viewer do webových aplikací?
Ano, GroupDocs.Viewer lze bez problémů integrovat do webových aplikací pro prohlížení a manipulaci s dokumenty.
### Je k dispozici zkušební verze pro vyzkoušení před zakoupením?
Ano, můžete využít bezplatnou zkušební verzi od [webové stránky](https://releases.groupdocs.com/) otestovat možnosti GroupDocs.Viewer pro .NET.