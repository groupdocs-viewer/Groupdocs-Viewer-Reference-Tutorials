---
title: Vykreslit PDF s původní velikostí stránky
linktitle: Vykreslit PDF s původní velikostí stránky
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat soubory PDF s původními velikostmi stránek pomocí GroupDocs.Viewer pro .NET. Postupujte podle našeho podrobného průvodce a plynule integrujte tuto funkci.
type: docs
weight: 17
url: /cs/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Úvod
V oblasti vývoje .NET GroupDocs.Viewer vyniká jako výkonný nástroj pro vykreslování různých formátů dokumentů, včetně PDF. Jedním z běžných požadavků při manipulaci s dokumenty je vykreslovat soubory PDF při zachování jejich původní velikosti stránky. Bezproblémové dosažení tohoto úkolu vyžaduje komplexní pochopení GroupDocs.Viewer for .NET a jeho funkcí.
## Předpoklady
Než se pustíte do vykreslování souborů PDF s původními velikostmi stránek pomocí GroupDocs.Viewer for .NET, ujistěte se, že máte splněny následující předpoklady:
### 1. Nainstalujte GroupDocs.Viewer pro .NET
 Začněte stažením knihovny GroupDocs.Viewer z webu. Knihovnu můžete získat z poskytnutého[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/). Postupujte podle pokynů k instalaci uvedených v dokumentaci, abyste jej efektivně integrovali do svého projektu .NET.
### 2. Nastavte vývojové prostředí
Ujistěte se, že máte vývojové prostředí nastavené pro vývoj .NET. To zahrnuje mít nainstalované kompatibilní IDE, jako je Visual Studio, a základní znalosti programování v C#.
### 3. Získejte dokument PDF
K vykreslení pomocí GroupDocs.Viewer budete potřebovat vzorový dokument PDF. Pro účely testování můžete použít jakýkoli dokument PDF. Pokud jej nemáte, můžete si stáhnout ukázku PDF z různých online zdrojů.

## Importovat jmenné prostory
Než budete pokračovat s vykreslováním PDF, je nezbytné importovat potřebné jmenné prostory do vašeho projektu C#. Tento krok umožňuje přístup k požadovaným třídám a metodám z knihovny GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní, když máte připravené předpoklady a importované potřebné jmenné prostory, pojďme si rozdělit proces vykreslování PDF s původními velikostmi stránek pomocí GroupDocs.Viewer pro .NET do jednoduchých kroků:
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
 Ujistěte se, že jste určili adresář, kam chcete ukládat vykreslené stránky. Nahradit`"Your Document Directory"` s cestou k požadovanému adresáři.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Nastavte formát pro pojmenování souborů vykreslených stránek. V tomto příkladu budou stránky uloženy jako obrázky PNG s názvy souborů ve formátu`"page_1.png"`, `"page_2.png"`, a tak dále.
## Krok 3: Vykreslení PDF s původní velikostí stránky
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Instantovat a`Viewer` objekt s cestou k vašemu souboru PDF. Poté vytvořte`PngViewOptions` se zadaným formátem cesty k souboru stránky. Soubor`RenderOriginalPageSize` majetek do`true` pro zachování původní velikosti stránek při vykreslování.
## Krok 4: Zobrazte umístění vykresleného dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Vytiskněte zprávu o úspěšném vykreslení a uveďte adresář, kde jsou vykreslené stránky uloženy.

## Závěr
Vykreslování PDF s původními velikostmi stránek pomocí GroupDocs.Viewer for .NET je jednoduchý proces, pokud budete postupovat podle kroků uvedených v tomto kurzu. Importováním potřebných jmenných prostorů a dodržováním podrobného průvodce můžete tuto funkci bez problémů integrovat do svých aplikací .NET.
## FAQ
### Může GroupDocs.Viewer vykreslovat jiné formáty dokumentů kromě PDF?
Ano, GroupDocs.Viewer podporuje vykreslování různých formátů dokumentů, včetně Wordu, Excelu, PowerPointu a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer je kompatibilní s prostředím .NET Framework i .NET Core.
### Mohu přizpůsobit výstupní formát vykreslených stránek?
Ano, výstupní formát si můžete přizpůsobit úpravou možností, které poskytuje GroupDocs.Viewer, jako je nastavení různých formátů obrázků nebo zadání vlastních možností vykreslování.
### Nabízí GroupDocs.Viewer podporu pro cloudové vykreslování dokumentů?
Ano, GroupDocs.Viewer poskytuje rozhraní API pro cloudové vykreslování dokumentů, což vám umožňuje vykreslovat dokumenty přímo od poskytovatelů cloudového úložiště.
### Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer?
 Ano, můžete prozkoumat GroupDocs.Viewer s bezplatnou zkušební verzí, když navštívíte poskytnuté[odkaz](https://releases.groupdocs.com/).