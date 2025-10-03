---
"description": "Naučte se, jak vykreslit specifické CAD formáty, jako je CF2, do HTML, JPG, PNG a PDF pomocí Groupdocs.Viewer pro .NET."
"linktitle": "Formáty CAD specifické pro renderování (CF2)"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Formáty CAD specifické pro renderování (CF2)"
"url": "/cs/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
type: docs
---
# Formáty CAD specifické pro renderování (CF2)

## Zavedení
V tomto tutoriálu se podíváme na to, jak vykreslovat specifické formáty CAD pomocí Groupdocs.Viewer pro .NET. Groupdocs.Viewer je výkonné API pro prohlížeč dokumentů, které umožňuje vývojářům zobrazovat v jejich aplikacích více než 170 typů dokumentů bez nutnosti instalace externího softwaru. Konkrétně se zaměříme na vykreslování formátů CAD, jako je CF2, do různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF.
## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte následující předpoklady:
- Visual Studio nainstalované ve vašem systému.
- Groupdocs.Viewer pro .NET SDK. Můžete si ho stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
- Základní znalost programovacího jazyka C#.
## Importovat jmenné prostory
Nejprve si importujme potřebné jmenné prostory pro vykreslování CAD formátů.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nyní si každý příklad rozdělme do několika kroků:
## Vykreslení CF2 do HTML
### Krok 1: Definujte výstupní adresář, kam bude uložen vykreslený HTML kód.
```csharp
string outputDirectory = "Your Document Directory";
```
### Krok 2: Definujte formát cesty k souboru pro HTML výstup.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Krok 3: Inicializujte objekt Viewer a zadejte vstupní soubor CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // V případě potřeby nastavte další možnosti vykreslování
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderování CF2 do JPG
### Krok 1: Definujte formát cesty k souboru pro výstup JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Krok 2: Inicializujte objekt Viewer a zadejte vstupní soubor CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // V případě potřeby nastavte další možnosti vykreslování
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderování CF2 do PNG

### Krok 1: Definujte formát cesty k souboru pro výstup PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Krok 2: Inicializujte objekt Viewer a zadejte vstupní soubor CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // V případě potřeby nastavte další možnosti vykreslování
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderování CF2 do PDF
### Krok 1: Definujte formát cesty k souboru pro výstup PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Krok 2: Inicializujte objekt Viewer a zadejte vstupní soubor CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // V případě potřeby nastavte další možnosti vykreslování
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vykreslovat specifické CAD formáty, jako například CF2, pomocí Groupdocs.Viewer pro .NET. Dodržováním podrobného návodu můžete snadno integrovat funkce vykreslování dokumentů do svých .NET aplikací.
## Často kladené otázky
### Může Groupdocs.Viewer vykreslovat i jiné CAD formáty kromě CF2?
Ano, Groupdocs.Viewer podporuje širokou škálu CAD formátů, včetně DWG, DXF, DGN a dalších.
### Je Groupdocs.Viewer vhodný pro vykreslování dokumentů ve webových aplikacích?
Rozhodně lze Groupdocs.Viewer bez problémů integrovat do webových aplikací pro vykreslování dokumentů přímo v prohlížeči.
### Vyžaduje Groupdocs.Viewer pro vykreslování nějaké externí závislosti?
Ne, Groupdocs.Viewer je samostatné API a nevyžaduje žádné externí závislosti ani instalaci softwaru.
### Mohu si přizpůsobit možnosti vykreslování podle svých požadavků?
Ano, Groupdocs.Viewer nabízí různé možnosti vykreslování, které lze přizpůsobit vašim specifickým potřebám.
### Je k dispozici zkušební verze pro Groupdocs.Viewer?
Ano, bezplatnou zkušební verzi Groupdocs.Viewer si můžete stáhnout z [zde](https://releases.groupdocs.com/).