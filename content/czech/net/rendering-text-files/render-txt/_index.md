---
"description": "Prozkoumejte bezproblémovou konverzi textových souborů do různých formátů pomocí GroupDocs.Viewer pro .NET. Vylepšete své možnosti správy dokumentů bez námahy."
"linktitle": "Vykreslení textových souborů (.txt)"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení textových souborů (.txt)"
"url": "/cs/net/rendering-text-files/render-txt/"
"weight": 10
type: docs
---
# Vykreslení textových souborů (.txt)

## Zavedení
V oblasti správy a manipulace s dokumenty se GroupDocs.Viewer pro .NET jeví jako výkonný nástroj, který nabízí nepřeberné množství funkcí pro efektivní vykreslování dokumentů v různých formátech. Tento článek se ponoří do složitostí využití GroupDocs.Viewer pro .NET k vykreslování textových souborů (.txt) do různých formátů. Ať už chcete převést textové soubory do formátu HTML, JPG, PNG nebo PDF, GroupDocs.Viewer vám poskytne potřebné nástroje k bezproblémovému splnění těchto úkolů.
## Předpoklady
Než se ponoříte do procesu konverze, ujistěte se, že máte splněny následující předpoklady:
### 1. Instalace GroupDocs.Viewer pro .NET
Ujistěte se, že máte ve svém vývojovém prostředí nainstalovaný nástroj GroupDocs.Viewer pro .NET. Potřebné soubory si můžete stáhnout z [webové stránky](https://releases.groupdocs.com/viewer/net/).
### 2. Základní znalost .NET Frameworku
Seznamte se se základy frameworku .NET, včetně toho, jak nastavit projekt a využívat knihovny v rámci vaší kódové základny.
### 3. Ukázkové textové soubory
Připravte si vzorové textové soubory (.txt), které chcete převést. Tyto soubory budou sloužit jako vstup pro proces převodu.

## Importovat jmenné prostory
Než se pustíte do procesu konverze, nezapomeňte do projektu importovat potřebné jmenné prostory. To vám umožní bezproblémový přístup k funkcím poskytovaným GroupDocs.Viewer pro .NET.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Rozdělme si každý příklad do několika kroků, abychom vás efektivně provedli procesem konverze:

## Krok 1: Definování výstupní cesty HTML
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
Vytvořte instanci `Viewer` objekt s cestou k textovému souboru. Konfigurace `HtmlViewOptions` pro vložené zdroje a vykreslení textového souboru do vícestránkového HTML.
## Krok 3: Definování výstupní cesty HTML pro jednu stránku
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Zadejte úplnou cestu k výstupnímu souboru HTML s jednou stránkou.
## Krok 4: Vykreslení textových souborů do jednostránkového HTML kódu
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
Vytvořte instanci `Viewer` objekt s cestou k textovému souboru. Konfigurace `HtmlViewOptions` pro vložené zdroje a sadu `RenderToSinglePage` na hodnotu true. Vykreslete textový soubor do jednostránkového HTML kódu.
## Krok 5: Definování výstupní cesty JPG
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
Vytvořte instanci `Viewer` objekt s cestou k textovému souboru. Konfigurace `JpgViewOptions` pro výstupní cestu a vykreslení textového souboru do formátu JPG.
## Krok 7: Definování výstupní cesty PNG
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
Vytvořte instanci `Viewer` objekt s cestou k textovému souboru. Konfigurace `PngViewOptions` pro výstupní cestu a vykreslení textového souboru do formátu PNG.
## Krok 9: Definování výstupní cesty PDF
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
Vytvořte instanci `Viewer` objekt s cestou k textovému souboru. Konfigurace `PdfViewOptions` pro výstupní cestu a vykreslení textového souboru do formátu PDF.

## Závěr
Závěrem lze říci, že GroupDocs.Viewer pro .NET umožňuje vývojářům snadno vykreslovat textové soubory do různých formátů, včetně HTML, JPG, PNG a PDF. Dodržováním podrobných pokynů uvedených v tomto článku můžete bezproblémově integrovat GroupDocs.Viewer do svých .NET aplikací a vylepšit tak možnosti správy dokumentů.
## Často kladené otázky
### Otázka: Je GroupDocs.Viewer pro .NET kompatibilní se všemi verzemi frameworku .NET?
Ano, GroupDocs.Viewer pro .NET je navržen tak, aby byl kompatibilní s širokou škálou verzí frameworku .NET, což zajišťuje všestrannost a flexibilitu při vývoji.
### Otázka: Mohu si přizpůsobit vzhled výstupu vykreslených dokumentů?
Rozhodně! GroupDocs.Viewer nabízí rozsáhlé možnosti přizpůsobení, které vývojářům umožňují přizpůsobit vzhled vykreslených dokumentů podle jejich požadavků a návodů.
### Otázka: Je k dispozici zkušební verze GroupDocs.Viewer pro .NET?
Ano, funkce GroupDocs.Viewer pro .NET si můžete prohlédnout s bezplatnou zkušební verzí dostupnou na [webové stránky]( https://releases.groupdocs.com/).
### Otázka: Jak mohu získat podporu nebo pomoc s GroupDocs.Viewer pro .NET?
S jakýmikoli dotazy, podporou nebo asistencí týkající se GroupDocs.Viewer pro .NET můžete navštívit specializované fórum podpory, které je k dispozici [zde](https://forum.groupdocs.com/c/viewer/9).
### Otázka: Mohu si zakoupit dočasnou licenci pro GroupDocs.Viewer pro .NET?
Ano, k dispozici jsou dočasné licence, které uživatelům poskytují flexibilitu a pohodlí při používání GroupDocs.Viewer pro .NET po určitou dobu.