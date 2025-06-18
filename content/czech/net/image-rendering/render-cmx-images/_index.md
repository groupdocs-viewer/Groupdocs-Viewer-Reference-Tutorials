---
"description": "Naučte se, jak snadno vykreslovat obrázky CMX do různých formátů pomocí GroupDocs.Viewer pro .NET. Vylepšete si správu dokumentů."
"linktitle": "Renderování obrázků CMX"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Renderování obrázků CMX"
"url": "/cs/net/image-rendering/render-cmx-images/"
"weight": 13
---

# Renderování obrázků CMX

## Zavedení
V oblasti správy a manipulace s dokumenty je vykreslování obrázků z různých formátů klíčovým úkolem. GroupDocs.Viewer pro .NET tento proces zjednodušuje tím, že poskytuje komplexní funkce pro vykreslování obrázků CMX do různých formátů, jako jsou HTML, JPG, PNG a PDF. Tento tutoriál vás provede krok za krokem procesem vykreslování obrázků CMX pomocí GroupDocs.Viewer pro .NET.

![Vykreslování obrázků CMX pomocí GroupDocs.Viewer pro .NET](/viewer/image-rendering/render-cmx-images.png)

## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
1. Knihovna GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte knihovnu GroupDocs.Viewer pro .NET z [zde](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Mějte nastavené funkční vývojové prostředí s .NET frameworkem.
3. Soubor s obrázkem CMX: Získejte soubor s obrázkem CMX, který chcete vykreslit.

## Import jmenných prostorů
Než budete pokračovat, nezapomeňte importovat potřebné jmenné prostory pro přístup k funkcím GroupDocs.Viewer ve vaší .NET aplikaci:
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
- Definovat výstupní adresář: Nastavte adresář, kam chcete ukládat vykreslené soubory HTML.
- Zadat formát cesty k souboru: Definujte formát výstupních souborů HTML.
- Vytvoření instance objektu Viewer: Vytvoření instance třídy Viewer se souborem obrazu CMX.
- Možnosti vykreslování HTML: Nakonfigurujte možnosti vykreslování HTML, například vkládání zdrojů.
- Vykreslení CMX do HTML: Vyvoláním metody View objektu prohlížeče vykreslíte obrázek CMX do HTML.
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
- Zadat formát cesty k souboru: Definujte formát výstupních souborů JPG.
- Vytvoření instance objektu Viewer: Vytvoření instance třídy Viewer se souborem obrazu CMX.
- Možnosti vykreslování JPG: Konfigurace možností vykreslování JPG.
- Vykreslení CMX do JPG: Vyvoláním metody View objektu prohlížeče vykreslíte obrázek CMX do JPG.
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
- Zadat formát cesty k souboru: Definuje formát pro výstupní soubory PNG.
- Vytvoření instance objektu Viewer: Vytvoření instance třídy Viewer se souborem obrazu CMX.
- Možnosti vykreslování PNG: Konfigurace možností vykreslování PNG.
- Vykreslení CMX do PNG: Vyvoláním metody View objektu prohlížeče vykreslíte obrázek CMX do PNG.
## Vykreslování do PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definovat výstupní adresář: Nastavte adresář pro uložení vykresleného PDF souboru.
- Zadat formát cesty k souboru: Definujte formát výstupního souboru PDF.
- Vytvoření instance objektu Viewer: Vytvoření instance třídy Viewer se souborem obrazu CMX.
- Možnosti vykreslování PDF: Nakonfigurujte možnosti vykreslování PDF.
- Vykreslení CMX do PDF: Vyvoláním metody View objektu prohlížeče vykreslíte obrázek CMX do PDF.

## Závěr
Závěrem lze říci, že GroupDocs.Viewer pro .NET nabízí robustní řešení pro bezproblémové vykreslování obrázků CMX do různých formátů. Dodržováním kroků popsaných v tomto tutoriálu můžete snadno integrovat funkce vykreslování obrázků CMX do svých aplikací .NET a zvýšit tak efektivitu správy dokumentů.
## Často kladené otázky
### Mohu vykreslit konkrétní stránky obrazu CMX?
Ano, konkrétní stránky můžete vykreslit zadáním čísla stránky v možnostech vykreslování.
### Je GroupDocs.Viewer pro .NET kompatibilní se všemi .NET frameworky?
Ano, GroupDocs.Viewer pro .NET je kompatibilní s více frameworky .NET, včetně .NET Core a .NET Framework.
### Podporuje GroupDocs.Viewer vykreslování šifrovaných obrázků CMX?
Ano, GroupDocs.Viewer podporuje vykreslování šifrovaných obrázků CMX s příslušnými dešifrovacími klíči.
### Mohu si přizpůsobit možnosti vykreslování pro různé výstupní formáty?
Rozhodně, GroupDocs.Viewer nabízí rozsáhlé možnosti pro přizpůsobení parametrů vykreslování na základě vašich požadavků.
### Existuje nějaké komunitní fórum pro podporu GroupDocs.Viewer?
Ano, můžete vyhledat pomoc a spojit se s komunitou GroupDocs.Viewer na fóru podpory. [zde](https://forum.groupdocs.com/c/viewer/9).