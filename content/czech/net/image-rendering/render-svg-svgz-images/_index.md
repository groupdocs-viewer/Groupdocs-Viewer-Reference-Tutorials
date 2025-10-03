---
"description": "Naučte se, jak vykreslovat obrázky SVG a SVGZ pomocí GroupDocs.Viewer pro .NET. Bez námahy převádějte vektorovou grafiku do formátů HTML, JPG, PNG a PDF."
"linktitle": "Renderování obrázků SVG a SVGZ"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Renderování obrázků SVG a SVGZ"
"url": "/cs/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# Renderování obrázků SVG a SVGZ

## Zavedení
tomto tutoriálu vás provedeme procesem vykreslování obrázků SVG a SVGZ pomocí nástroje GroupDocs.Viewer pro .NET. GroupDocs.Viewer pro .NET je výkonné API pro vykreslování dokumentů, které umožňuje vývojářům vykreslovat různé formáty dokumentů v jejich .NET aplikacích. SVG a SVGZ jsou oblíbené obrazové formáty používané pro vektorovou grafiku a pomocí nástroje GroupDocs.Viewer pro .NET je můžete snadno vykreslit do různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF.

![Renderování obrázků SVG a SVGZ pomocí GroupDocs.Viewer pro .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Předpoklady
Než začneme, ujistěte se, že máte nainstalované a nastavené následující předpoklady:
1. GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z [zde](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Ujistěte se, že máte funkční vývojové prostředí pro vývoj v .NET, například Visual Studio.
3. Ukázkový soubor SVGZ: Mějte připravený ukázkový soubor SVGZ pro testování.

## Importovat jmenné prostory
Než se ponoříme do kódu, importujme potřebné jmenné prostory:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Vykreslení SVGZ do HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Krok 2: Vykreslení SVGZ do JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Krok 3: Vykreslení SVGZ do PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Krok 4: Vykreslení SVGZ do PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vykreslovat obrázky SVG a SVGZ pomocí GroupDocs.Viewer pro .NET. Pomocí několika jednoduchých kroků můžete převést obrázky SVGZ do různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF, a zpřístupnit je tak a zobrazitelné v různých prostředích.
## Často kladené otázky
### Může GroupDocs.Viewer vykreslit i jiné formáty obrázků?
Ano, GroupDocs.Viewer podporuje vykreslování různých obrazových formátů včetně PNG, JPEG, BMP, TIFF, GIF a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer je kompatibilní s .NET Framework i .NET Core.
### Mohu si přizpůsobit možnosti vykreslování?
Ano, GroupDocs.Viewer nabízí rozsáhlé možnosti vykreslování, které vám umožňují přizpůsobit výstup vašim požadavkům.
### Vyžaduje GroupDocs.Viewer nějaké závislosti třetích stran?
Ne, GroupDocs.Viewer je samostatné API a pro vykreslování dokumentů nevyžaduje žádné závislosti třetích stran.
### Je k dispozici zkušební verze pro testování?
Ano, můžete si stáhnout bezplatnou zkušební verzi GroupDocs.Viewer z [zde](https://releases.groupdocs.com/) aby si před nákupem ohodnotil jeho vlastnosti.