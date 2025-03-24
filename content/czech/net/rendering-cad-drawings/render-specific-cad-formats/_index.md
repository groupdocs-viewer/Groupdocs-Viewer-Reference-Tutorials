---
title: Vykreslování specifických CAD formátů (CF2)
linktitle: Vykreslování specifických CAD formátů (CF2)
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat konkrétní formáty CAD, jako je CF2, do HTML, JPG, PNG a PDF pomocí Groupdocs.Viewer pro .NET.
weight: 12
url: /cs/net/rendering-cad-drawings/render-specific-cad-formats/
---

# Vykreslování specifických CAD formátů (CF2)

## Úvod
V tomto tutoriálu prozkoumáme, jak vykreslit konkrétní formáty CAD pomocí Groupdocs.Viewer pro .NET. Groupdocs.Viewer je výkonné rozhraní API pro prohlížeč dokumentů, které umožňuje vývojářům zobrazovat více než 170 typů dokumentů ve svých aplikacích, aniž by vyžadovali instalaci externího softwaru. Konkrétně se zaměříme na vykreslování CAD formátů, jako je CF2, do různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
- Visual Studio nainstalované ve vašem systému.
-  Groupdocs.Viewer pro .NET SDK. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
- Základní znalost programovacího jazyka C#.
## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory potřebné pro vykreslování CAD formátů.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nyní si každý příklad rozdělíme do několika kroků:
## Vykreslení CF2 do HTML
### Krok 1: Definujte výstupní adresář, do kterého bude vykreslený HTML uložen.
```csharp
string outputDirectory = "Your Document Directory";
```
### Krok 2: Definujte formát cesty k souboru pro výstup HTML.
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
## Vykreslit CF2 do JPG
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
## Vykreslit CF2 do PNG

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
## Vykreslit CF2 do PDF
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
tomto tutoriálu jsme se naučili vykreslovat konkrétní formáty CAD, jako je CF2, pomocí Groupdocs.Viewer pro .NET. Podle podrobného průvodce můžete snadno integrovat možnosti vykreslování dokumentů do aplikací .NET.
## FAQ
### Dokáže Groupdocs.Viewer vykreslit jiné formáty CAD kromě CF2?
Ano, Groupdocs.Viewer podporuje širokou škálu CAD formátů, včetně DWG, DXF, DGN a dalších.
### Je Groupdocs.Viewer vhodný pro vykreslování dokumentů ve webových aplikacích?
Groupdocs.Viewer lze bez problémů integrovat do webových aplikací pro vykreslování dokumentů přímo v prohlížeči.
### Vyžaduje Groupdocs.Viewer nějaké externí závislosti pro vykreslování?
Ne, Groupdocs.Viewer je samostatné API a nevyžaduje žádné externí závislosti ani instalace softwaru.
### Mohu upravit možnosti vykreslování podle svých požadavků?
Ano, Groupdocs.Viewer poskytuje různé možnosti vykreslování, které lze upravit tak, aby vyhovovaly vašim specifickým potřebám.
### Je k dispozici zkušební verze pro Groupdocs.Viewer?
 Ano, můžete získat bezplatnou zkušební verzi Groupdocs.Viewer od[tady](https://releases.groupdocs.com/).