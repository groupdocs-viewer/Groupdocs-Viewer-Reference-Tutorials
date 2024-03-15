---
title: Povolit vrstvené vykreslování v PDF
linktitle: Povolit vrstvené vykreslování v PDF
second_title: GroupDocs.Viewer .NET API
description: Přečtěte si, jak povolit vrstvené vykreslování v dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Vylepšete zážitek ze sledování dokumentů bez námahy.
type: docs
weight: 15
url: /cs/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Úvod
V tomto tutoriálu se ponoříme do procesu povolení vrstveného vykreslování v dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Vrstvené vykreslování umožňuje vylepšené zobrazení dokumentů a manipulaci s nimi, což uživatelům poskytuje interaktivnější zážitek ze sledování.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer for .NET: Ujistěte se, že jste nainstalovali potřebný balíček nebo knihovnu pro použití GroupDocs.Viewer for .NET ve vašem projektu.
2. Visual Studio: Pro kódování a spouštění poskytnutých příkladů byste měli mít na svém systému nainstalované Visual Studio.
3. Základní porozumění C#: Tento tutoriál předpokládá znalost syntaxe a konceptů programovacího jazyka C#.

## Importovat jmenné prostory
Začněte importováním požadovaných jmenných prostorů do vašeho projektu:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Ujistěte se, že jste zadali cestu k adresáři, kam chcete uložit vykreslený výstup.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Tento krok nastavuje formát cest k souborům jednotlivých stránek ve vykresleném výstupu.`{0}` je zástupný symbol pro číslo stránky.
## Krok 3: Povolte vrstvené vykreslování
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Zde vytvoříme a`Viewer` objekt a zadejte dokument PDF, který má být zpracován. Poté konfigurujeme`HtmlViewOptions` s definovaným formátem cesty k souboru stránky. Nastavením`EnableLayeredRendering` majetek do`true` v`PdfOptions`, umožňujeme vrstvené vykreslování pro dokument PDF.
## Krok 4: Zobrazte výstupní adresář
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nakonec vytiskneme zprávu o úspěšném vykreslení zdrojového dokumentu a vyzveme uživatele, aby zkontroloval výstup v zadaném adresáři.

## Závěr
Povolení vrstveného vykreslování v dokumentech PDF pomocí GroupDocs.Viewer for .NET zlepšuje možnosti prohlížení dokumentů a poskytuje uživatelům bohatší a interaktivnější zážitek. Podle kroků uvedených v tomto kurzu můžete tuto funkci bez problémů integrovat do svých aplikací .NET.
## FAQ
### Co je vrstvené vykreslování v dokumentech PDF?
Vrstvené vykreslování umožňuje oddělení a manipulaci s různými součástmi v dokumentu PDF, což umožňuje interaktivní prohlížení a lepší uživatelský zážitek.
### Mohu přizpůsobit výstupní adresář pro renderované dokumenty?
Ano, můžete zadat libovolnou cestu k adresáři pro výstup podle vašich požadavků.
### Podporuje GroupDocs.Viewer jiné formáty souborů kromě PDF?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů včetně Wordu, Excelu, PowerPointu a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer je kompatibilní s prostředím .NET Framework i .NET Core.
### Kde najdu další podporu nebo pomoc?
Můžete navštívit fórum GroupDocs.Viewer, kde najdete jakékoli dotazy nebo pomoc týkající se knihovny prohlížeče.