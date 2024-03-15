---
title: Renderujte obrázky SVG a SVGZ
linktitle: Renderujte obrázky SVG a SVGZ
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat obrázky SVG a SVGZ pomocí GroupDocs.Viewer pro .NET. Převeďte vektorovou grafiku do HTML, JPG, PNG a PDF bez námahy.
type: docs
weight: 16
url: /cs/net/image-rendering/render-svg-svgz-images/
---
## Úvod
tomto tutoriálu vás provedeme procesem vykreslování obrázků SVG a SVGZ pomocí GroupDocs.Viewer pro .NET. GroupDocs.Viewer for .NET je výkonné rozhraní API pro vykreslování dokumentů, které umožňuje vývojářům vykreslovat různé formáty dokumentů v jejich aplikacích .NET. SVG a SVGZ jsou oblíbené obrazové formáty používané pro vektorovou grafiku a pomocí GroupDocs.Viewer pro .NET je můžete snadno vykreslit do různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF.
## Předpoklady
Než začneme, ujistěte se, že máte nainstalované a nastavené následující předpoklady:
1.  GroupDocs.Viewer for .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z[tady](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Ujistěte se, že máte funkční vývojové prostředí pro vývoj .NET, jako je Visual Studio.
3. Vzorový soubor SVGZ: Připravte si vzorový soubor SVGZ k testování.

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

## Krok 2: Vykreslete SVGZ do JPG
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
tomto tutoriálu jsme se naučili vykreslovat obrázky SVG a SVGZ pomocí GroupDocs.Viewer pro .NET. Pomocí několika jednoduchých kroků můžete převést obrázky SVGZ do různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF, a učinit je tak přístupnými a zobrazitelnými v různých prostředích.
## FAQ
### Dokáže GroupDocs.Viewer vykreslit jiné formáty obrázků?
Ano, GroupDocs.Viewer podporuje vykreslování různých obrazových formátů včetně PNG, JPEG, BMP, TIFF, GIF a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer je kompatibilní s .NET Framework i .NET Core.
### Mohu upravit možnosti vykreslování?
Ano, GroupDocs.Viewer poskytuje rozsáhlé možnosti vykreslování, které vám umožní přizpůsobit výstup podle vašich požadavků.
### Vyžaduje GroupDocs.Viewer nějaké závislosti třetích stran?
Ne, GroupDocs.Viewer je samostatné API a pro vykreslování dokumentů nevyžaduje žádné závislosti třetích stran.
### Je k dispozici zkušební verze pro testování?
Ano, můžete si stáhnout bezplatnou zkušební verzi GroupDocs.Viewer z[tady](https://releases.groupdocs.com/) před nákupem vyhodnotit jeho vlastnosti.