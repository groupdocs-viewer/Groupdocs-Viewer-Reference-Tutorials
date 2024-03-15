---
title: Vykreslování CMX obrázků
linktitle: Vykreslování CMX obrázků
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak bez námahy vykreslovat obrázky CMX do různých formátů pomocí GroupDocs.Viewer pro .NET. Vylepšete svou správu dokumentů.
type: docs
weight: 13
url: /cs/net/image-rendering/render-cmx-images/
---
## Úvod
V oblasti správy a manipulace s dokumenty je klíčovým úkolem vykreslování obrázků z různých formátů. GroupDocs.Viewer for .NET zjednodušuje tento proces tím, že poskytuje komplexní funkce pro vykreslování CMX obrázků do různých formátů, jako jsou HTML, JPG, PNG a PDF. Tento tutoriál vás provede procesem vykreslování obrázků CMX krok za krokem pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Knihovna GroupDocs.Viewer for .NET: Stáhněte a nainstalujte knihovnu GroupDocs.Viewer for .NET z[tady](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Mějte pracovní vývojové prostředí nastavené s .NET frameworkem.
3. Soubor obrázku CMX: Získejte soubor obrázku CMX, který chcete vykreslit.

## Import jmenných prostorů
Než budete pokračovat, ujistěte se, že jste importovali potřebné jmenné prostory pro přístup k funkcím GroupDocs.Viewer ve vaší aplikaci .NET:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Vykreslování do HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Definovat výstupní adresář: Nastavte adresář, do kterého chcete ukládat vykreslené soubory HTML.
- Specify File Path Format: Definujte formát pro výstupní soubory HTML.
- Objekt Instantiate Viewer: Vytvořte instanci třídy Viewer s obrazovým souborem CMX.
- Možnosti vykreslování HTML: Nakonfigurujte možnosti vykreslování HTML, jako je vkládání zdrojů.
- Vykreslit CMX do HTML: Vyvoláním metody View objektu prohlížeče vykreslíte obrázek CMX do HTML.
## Vykreslování do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definovat výstupní adresář: Nastavte adresář pro ukládání vykreslených souborů JPG.
- Specify File Path Format: Definujte formát pro výstupní soubory JPG.
- Objekt Instantiate Viewer: Vytvořte instanci třídy Viewer s obrazovým souborem CMX.
- Možnosti vykreslování JPG: Konfigurace možností vykreslování JPG.
- Vykreslit CMX do JPG: Vyvolejte metodu View objektu prohlížeče pro vykreslení obrázku CMX do JPG.
## Vykreslování do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definovat výstupní adresář: Nastavte adresář pro ukládání vykreslených souborů PNG.
- Specify File Path Format: Definujte formát pro výstupní soubory PNG.
- Objekt Instantiate Viewer: Vytvořte instanci třídy Viewer s obrazovým souborem CMX.
- Možnosti vykreslování PNG: Konfigurace možností vykreslování PNG.
- Vykreslit CMX do PNG: Vyvoláním metody View objektu prohlížeče vykreslíte obrázek CMX do PNG.
## Vykreslování do PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definovat výstupní adresář: Nastavte adresář pro uložení vykresleného souboru PDF.
- Specify File Path Format: Definujte formát pro výstupní soubor PDF.
- Objekt Instantiate Viewer: Vytvořte instanci třídy Viewer s obrazovým souborem CMX.
- Možnosti vykreslování PDF: Konfigurace možností vykreslování PDF.
- Render CMX to PDF: Vyvolejte metodu View objektu prohlížeče pro vykreslení obrazu CMX do PDF.

## Závěr
Na závěr, GroupDocs.Viewer for .NET nabízí robustní řešení pro bezproblémové vykreslování CMX obrázků do různých formátů. Podle kroků popsaných v tomto tutoriálu můžete bez námahy integrovat možnosti vykreslování obrázků CMX do aplikací .NET a zvýšit tak efektivitu správy dokumentů.
## FAQ
### Mohu vykreslit konkrétní stránky obrázku CMX?
Ano, konkrétní stránky můžete vykreslit zadáním čísla stránky v možnostech vykreslení.
### Je GroupDocs.Viewer for .NET kompatibilní se všemi frameworky .NET?
Ano, GroupDocs.Viewer for .NET je kompatibilní s více frameworky .NET, včetně .NET Core a .NET Framework.
### Podporuje GroupDocs.Viewer vykreslování šifrovaných obrázků CMX?
Ano, GroupDocs.Viewer podporuje vykreslování zašifrovaných obrázků CMX s příslušnými dešifrovacími klíči.
### Mohu přizpůsobit možnosti vykreslování pro různé výstupní formáty?
Rozhodně, GroupDocs.Viewer poskytuje rozsáhlé možnosti pro přizpůsobení parametrů vykreslování na základě vašich požadavků.
### Existuje komunitní fórum pro podporu GroupDocs.Viewer?
 Ano, můžete vyhledat pomoc a zapojit se do komunity GroupDocs.Viewer na fóru podpory[tady](https://forum.groupdocs.com/c/viewer/9).