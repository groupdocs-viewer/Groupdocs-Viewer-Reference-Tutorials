---
title: Vykreslování obrázků FODG a ODG
linktitle: Vykreslování obrázků FODG a ODG
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat obrázky FODG a ODG do HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer pro .NET. Vylepšete práci s dokumenty.
weight: 15
url: /cs/net/image-rendering/render-fodg-odg-images/
---
## Úvod
Ve světě vývoje softwaru je prvořadá efektivní manipulace s formáty dokumentů. GroupDocs.Viewer for .NET je výkonný nástroj navržený pro zjednodušení procesu vykreslování obrázků FODG a ODG v aplikacích .NET. Tento tutoriál vás provede kroky potřebnými k vykreslení těchto obrázků do různých formátů, jako jsou HTML, JPG, PNG a PDF, pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1.  GroupDocs.Viewer for .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z[tady](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Ujistěte se, že máte v systému nainstalované rozhraní .NET Framework.
3. Základní znalost C#: Užitečná bude znalost programovacího jazyka C#.

## Importovat jmenné prostory
Než začnete s implementací, importujte potřebné jmenné prostory:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Nastavte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` cestou k adresáři, kam chcete uložit vykreslené obrázky.
## Krok 2: Vykreslení do HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Tento krok vykreslí obrázek FODG do formátu HTML.
## Krok 3: Vykreslení do JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Zde je obrázek FODG vykreslen do formátu JPG.
## Krok 4: Vykreslení do PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Tento krok převede obrázek FODG do formátu PNG.
## Krok 5: Vykreslení do PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Nakonec je obrázek FODG vykreslen do formátu PDF.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak vykreslit obrázky FODG a ODG do různých formátů pomocí GroupDocs.Viewer pro .NET. Pomocí těchto kroků můžete bezproblémově integrovat možnosti vykreslování dokumentů do aplikací .NET.
## FAQ
### Je GroupDocs.Viewer for .NET kompatibilní se všemi verzemi .NET Framework?
GroupDocs.Viewer for .NET je kompatibilní s celou řadou verzí .NET Framework, včetně těch nejnovějších.
### Mohu vykreslovat dokumenty asynchronně s GroupDocs.Viewer pro .NET?
Ano, GroupDocs.Viewer for .NET poskytuje možnosti asynchronního vykreslování pro lepší výkon.
### Podporuje GroupDocs.Viewer for .NET vykreslování zašifrovaných dokumentů?
Ano, GroupDocs.Viewer for .NET podporuje vykreslování zašifrovaných dokumentů s příslušnými dešifrovacími klíči.
### Je možné upravit výstup vykreslování pomocí GroupDocs.Viewer pro .NET?
Rozhodně, GroupDocs.Viewer for .NET nabízí různé možnosti přizpůsobení pro přizpůsobení výstupu vykreslování podle vašich požadavků.
### Mohu renderovat dokumenty ze vzdálených úložišť pomocí GroupDocs.Viewer for .NET?
Ano, GroupDocs.Viewer for .NET podporuje vykreslování dokumentů z lokálního i vzdáleného úložiště.