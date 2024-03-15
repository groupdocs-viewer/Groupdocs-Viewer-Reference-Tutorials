---
title: Vykreslit textové soubory (.txt)
linktitle: Vykreslit textové soubory (.txt)
second_title: GroupDocs.Viewer .NET API
description: Prozkoumejte bezproblémový převod textových souborů do různých formátů pomocí GroupDocs.Viewer pro .NET. Vylepšete své možnosti správy dokumentů bez námahy.
type: docs
weight: 10
url: /cs/net/rendering-text-files/render-txt/
---
## Úvod
oblasti správy a manipulace s dokumenty se GroupDocs.Viewer for .NET ukazuje jako výkonný nástroj, který nabízí nepřeberné množství funkcí pro efektivní vykreslování různých formátů dokumentů. Tento článek se ponoří do složitosti využití GroupDocs.Viewer for .NET k vykreslení textových souborů (.txt) do různých formátů. Ať už chcete převést textové soubory do HTML, JPG, PNG nebo PDF, GroupDocs.Viewer vás vybaví nezbytnými nástroji k bezproblémovému plnění těchto úkolů.
## Předpoklady
Než se ponoříte do procesu převodu, ujistěte se, že máte splněny následující předpoklady:
### 1. Instalace GroupDocs.Viewer pro .NET
 Ujistěte se, že máte ve vývojovém prostředí nainstalovaný GroupDocs.Viewer for .NET. Potřebné soubory si můžete stáhnout z[webová stránka](https://releases.groupdocs.com/viewer/net/).
### 2. Základní seznámení s .NET Framework
Seznamte se se základy .NET frameworku, včetně toho, jak nastavit projekt a využívat knihovny ve vaší kódové základně.
### 3. Ukázkové textové soubory
Připravte si ukázkové textové soubory (.txt), které chcete převést. Tyto soubory budou sloužit jako vstup pro proces převodu.

## Importovat jmenné prostory
Než se ponoříte do procesu převodu, nezapomeňte do projektu importovat potřebné jmenné prostory. To vám umožní bezproblémový přístup k funkcím, které poskytuje GroupDocs.Viewer pro .NET.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Pojďme si každý příklad rozdělit do několika kroků, které vás efektivně provedou procesem převodu:

## Krok 1: Definujte výstupní cestu HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
Zadejte úplnou cestu k výstupnímu souboru HTML.
## Krok 2: Vykreslení textových souborů do vícestránkového HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 Instantovat a`Viewer` objekt s cestou k textovému souboru. Konfigurovat`HtmlViewOptions` pro vložené zdroje a vykreslí textový soubor do vícestránkového HTML.
## Krok 3: Definujte výstupní cestu HTML pro jednu stránku
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Zadejte úplnou cestu k jednostránkovému výstupnímu souboru HTML.
## Krok 4: Vykreslení textových souborů do jednostránkového HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 Instantovat a`Viewer` objekt s cestou k textovému souboru. Konfigurovat`HtmlViewOptions` pro vložené zdroje a sadu`RenderToSinglePage` na pravdu. Vykreslete textový soubor do jednostránkového HTML.
## Krok 5: Definujte výstupní cestu JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
Zadejte úplnou cestu k výstupnímu souboru JPG.
## Krok 6: Vykreslení textových souborů do formátu JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Instantovat a`Viewer` objekt s cestou k textovému souboru. Konfigurovat`JpgViewOptions` pro výstupní cestu a vykreslit textový soubor do formátu JPG.
## Krok 7: Definujte výstupní cestu PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
Zadejte úplnou cestu k výstupnímu souboru PNG.
## Krok 8: Vykreslení textových souborů do formátu PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Instantovat a`Viewer` objekt s cestou k textovému souboru. Konfigurovat`PngViewOptions` pro výstupní cestu a vykreslit textový soubor do formátu PNG.
## Krok 9: Definujte výstupní cestu PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Zadejte úplnou cestu k výstupnímu souboru PDF.
## Krok 10: Vykreslení textových souborů do PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Instantovat a`Viewer` objekt s cestou k textovému souboru. Konfigurovat`PdfViewOptions` pro výstupní cestu a vykreslit textový soubor do formátu PDF.

## Závěr
Na závěr, GroupDocs.Viewer for .NET umožňuje vývojářům bez námahy vykreslovat textové soubory do různých formátů, včetně HTML, JPG, PNG a PDF. Podle podrobného průvodce popsaného v tomto článku můžete bez problémů integrovat GroupDocs.Viewer do svých aplikací .NET a vylepšit tak možnosti správy dokumentů.
## FAQ
### Otázka: Je GroupDocs.Viewer for .NET kompatibilní se všemi verzemi rozhraní .NET?
Ano, GroupDocs.Viewer for .NET je navržen tak, aby byl kompatibilní s širokou škálou verzí .NET frameworku, což zajišťuje všestrannost a flexibilitu ve vývoji.
### Otázka: Mohu přizpůsobit výstupní vzhled vykreslených dokumentů?
Absolutně! GroupDocs.Viewer nabízí rozsáhlé možnosti přizpůsobení a umožňuje vývojářům přizpůsobit vzhled vykreslených dokumentů podle jejich preferencí a požadavků.
### Otázka: Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, můžete prozkoumat funkce GroupDocs.Viewer for .NET přístupem k bezplatné zkušební verzi dostupné na[webová stránka]( https://releases.groupdocs.com/).
### Otázka: Jak mohu získat podporu nebo vyhledat pomoc s GroupDocs.Viewer pro .NET?
 Máte-li jakékoli dotazy, podporu nebo pomoc týkající se GroupDocs.Viewer pro .NET, můžete navštívit vyhrazené dostupné fórum podpory[tady](https://forum.groupdocs.com/c/viewer/9).
### Otázka: Mohu si zakoupit dočasnou licenci pro GroupDocs.Viewer pro .NET?
Ano, dočasné licence jsou k dispozici ke koupi a poskytují uživatelům flexibilitu a pohodlí při používání GroupDocs.Viewer for .NET po určitou dobu.