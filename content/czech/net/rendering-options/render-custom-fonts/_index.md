---
title: Vykreslování pomocí vlastních písem
linktitle: Vykreslování pomocí vlastních písem
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat dokumenty pomocí vlastních písem pomocí GroupDocs.Viewer for .NET. Vylepšete vizuální prezentace bez námahy.
weight: 18
url: /cs/net/rendering-options/render-custom-fonts/
---

# Vykreslování pomocí vlastních písem

## Úvod
oblasti vývoje .NET nabízí GroupDocs.Viewer výkonné řešení pro vykreslování dokumentů různých formátů. Mezi mnoha funkcemi GroupDocs.Viewer umožňuje vykreslování dokumentů pomocí vlastních písem a přidává vašim aplikacím vrstvu personalizace a flexibility.
## Předpoklady
Než se ponoříte do vykreslování dokumentů pomocí vlastních písem pomocí GroupDocs.Viewer for .NET, ujistěte se, že máte splněny následující předpoklady:
### 1. Nainstalujte GroupDocs.Viewer pro .NET
Chcete-li používat GroupDocs.Viewer pro .NET, musíte jej mít nainstalovaný ve svém vývojovém prostředí. Potřebný balíček si můžete stáhnout z uvedeného odkazu:
[Stáhněte si GroupDocs.Viewer pro .NET](https://releases.groupdocs.com/viewer/net/)
### 2. Získejte písma
Připravte si vlastní písma, která chcete použít pro vykreslování dokumentů. Zajistěte, aby tato písma byla dostupná v prostředí vaší aplikace.
### 3. Nastavte vývojové prostředí
Nechte si na svém systému nastavit funkční vývojové prostředí .NET. Ujistěte se, že máte nainstalované potřebné nástroje a frameworky.
### 4. Základní porozumění C# a .NET
Seznamte se s programovacím jazykem C# a základy .NET frameworku, abyste mohli efektivně sledovat tutoriál.

## Importovat jmenné prostory
Abyste mohli vykreslit dokumenty s vlastními fonty pomocí GroupDocs.Viewer for .NET, musíte do svého projektu importovat požadované jmenné prostory.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Fonts;
using GroupDocs.Viewer.Options;
```

## Krok 1: Nastavte zdroje písem
Nejprve definujte zdroje písem, které se mají použít pro vykreslování dokumentů. Tento krok zajistí, že GroupDocs.Viewer bude mít přístup k vlastním fontům.
```csharp
FontSettings.SetFontSources(
    new FolderFontSource(Utils.FontsPath, Fonts.SearchOption.TopFolderOnly));
```
## Krok 2: Definujte výstupní adresář
Zadejte adresář, kam chcete ukládat vykreslené dokumenty.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 3: Definujte formát cesty k souboru stránky
Nastavte formát pro pojmenování výstupních souborů HTML obsahujících vykreslené stránky dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 4: Vykreslení dokumentu pomocí vlastních písem
 K vykreslení dokumentu pomocí vlastních písem použijte rozhraní GroupDocs.Viewer API. Nahradit`TestFiles.MISSING_FONT_ODG` s cestou k vašemu dokumentu.
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_ODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 5: Zobrazte výstupní adresář
Informujte uživatele o umístění, kde se ukládají vykreslené stránky dokumentu.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
tomto tutoriálu jsme prozkoumali, jak vykreslit dokumenty pomocí vlastních písem pomocí GroupDocs.Viewer pro .NET. Dodržováním podrobného průvodce a využitím poskytnutého příkladu můžete zlepšit vizuální prezentaci dokumentů ve vašich aplikacích .NET.
## Nejčastější dotazy
### Otázka: Mohu vykreslovat dokumenty pomocí vlastních písem pomocí GroupDocs.Viewer for .NET ve webových aplikacích?
Ano, GroupDocs.Viewer for .NET lze integrovat do desktopových i webových aplikací pro vykreslování dokumentů pomocí vlastních písem.
### Otázka: Je GroupDocs.Viewer for .NET kompatibilní s různými formáty dokumentů?
Absolutně! GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, souborů Microsoft Office, obrázků a dalších.
### Otázka: Existují nějaká omezení ohledně typů vlastních písem, která lze použít?
Pokud jsou vlastní písma dostupná v prostředí aplikace, může GroupDocs.Viewer for .NET vykreslovat dokumenty s těmito písmy bez jakýchkoli omezení.
### Otázka: Mohu přizpůsobit výstupní formát vykreslených dokumentů?
Ano, GroupDocs.Viewer for .NET poskytuje možnosti přizpůsobení výstupního formátu, včetně HTML, obrazových formátů a PDF.
### Otázka: Nabízí GroupDocs.Viewer for .NET podporu a dokumentaci pro vývojáře?
Rozhodně! GroupDocs poskytuje komplexní dokumentaci, fóra pro podporu a zdroje, které pomáhají vývojářům efektivně využívat GroupDocs.Viewer.