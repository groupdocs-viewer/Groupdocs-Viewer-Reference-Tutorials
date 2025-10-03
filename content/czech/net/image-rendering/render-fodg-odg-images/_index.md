---
"description": "Naučte se, jak vykreslovat obrázky FODG a ODG do formátu HTML, JPG, PNG a PDF pomocí nástroje GroupDocs.Viewer pro .NET. Vylepšete si práci s dokumenty."
"linktitle": "Vykreslení obrázků FODG a ODG"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení obrázků FODG a ODG"
"url": "/cs/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# Vykreslení obrázků FODG a ODG

## Zavedení
Ve světě vývoje softwaru je efektivní práce s formáty dokumentů prvořadá. GroupDocs.Viewer pro .NET je výkonný nástroj určený ke zjednodušení procesu vykreslování obrázků FODG a ODG v aplikacích .NET. Tento tutoriál vás provede kroky potřebnými k vykreslení těchto obrázků do různých formátů, jako je HTML, JPG, PNG a PDF, pomocí GroupDocs.Viewer pro .NET.

![Vykreslení obrázků FODG a ODG pomocí GroupDocs.Viewer pro .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z [zde](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Ujistěte se, že máte v systému nainstalovaný .NET Framework.
3. Základní znalost C#: Znalost programovacího jazyka C# bude užitečná.

## Importovat jmenné prostory
Než začnete s implementací, importujte potřebné jmenné prostory:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Nastavení výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Nahradit `"Your Document Directory"` s cestou k adresáři, kam chcete uložit vykreslené obrázky.
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
tomto tutoriálu jsme prozkoumali, jak vykreslovat obrázky FODG a ODG do různých formátů pomocí GroupDocs.Viewer pro .NET. Dodržením těchto kroků můžete bezproblémově integrovat funkce vykreslování dokumentů do vašich aplikací .NET.
## Často kladené otázky
### Je GroupDocs.Viewer pro .NET kompatibilní se všemi verzemi .NET Frameworku?
GroupDocs.Viewer pro .NET je kompatibilní s širokou škálou verzí .NET Frameworku, včetně těch nejnovějších.
### Mohu vykreslovat dokumenty asynchronně pomocí GroupDocs.Viewer pro .NET?
Ano, GroupDocs.Viewer pro .NET poskytuje asynchronní vykreslování pro lepší výkon.
### Podporuje GroupDocs.Viewer pro .NET vykreslování šifrovaných dokumentů?
Ano, GroupDocs.Viewer pro .NET podporuje vykreslování šifrovaných dokumentů s příslušnými dešifrovacími klíči.
### Je možné přizpůsobit výstup vykreslování pomocí GroupDocs.Viewer pro .NET?
Rozhodně, GroupDocs.Viewer pro .NET nabízí různé možnosti přizpůsobení, aby se výstup vykreslování přizpůsobil vašim požadavkům.
### Mohu vykreslovat dokumenty ze vzdálených úložišť pomocí GroupDocs.Viewer pro .NET?
Ano, GroupDocs.Viewer pro .NET podporuje vykreslování dokumentů z lokálních i vzdálených úložišť.