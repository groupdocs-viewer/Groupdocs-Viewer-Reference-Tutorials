---
title: Vykreslení skrytých sloupců a řádků
linktitle: Vykreslení skrytých sloupců a řádků
second_title: GroupDocs.Viewer .NET API
description: Odemkněte skrytá data v tabulkách bez námahy pomocí GroupDocs.Viewer pro .NET. Postupujte podle našeho podrobného průvodce a odhalte skryté sloupce a řádky.
type: docs
weight: 13
url: /cs/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## Úvod
V oblasti vizualizace dokumentů je GroupDocs.Viewer for .NET robustní nástroj, který usnadňuje bezproblémové vykreslování různých formátů dokumentů. Jednou ze zajímavých funkcí je schopnost odhalit skryté sloupce a řádky v tabulkách. V tomto tutoriálu se ponoříme do kroků k odemknutí této funkce a uvolnění potenciálu vašich dat.
## Předpoklady
Než se vydáte na tuto cestu, ujistěte se, že máte splněny následující předpoklady:
- GroupDocs.Viewer for .NET: Ujistěte se, že máte nainstalovanou nejnovější verzi. Pokud ne, můžete si jej stáhnout z[oficiální webové stránky](https://releases.groupdocs.com/viewer/net/).
- Soubor dokumentu: Připravte si vzorový dokument ve formátu tabulky (např. SAMPLE.XLSX), abyste mohli experimentovat se skrytými sloupci a řádky.
- Vývojové prostředí: Nastavte pracovní prostředí, nejlépe pomocí Visual Studia nebo jiného vhodného IDE pro vývoj .NET.
## Importovat jmenné prostory
Ve svém projektu .NET importujte potřebné jmenné prostory, abyste mohli efektivně využívat funkce GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definujte výstupní adresář, kam se budou ukládat vykreslené HTML stránky. Upravte odpovídajícím způsobem formát cesty k souboru.
## Krok 2: Inicializujte prohlížeč a konfigurujte možnosti
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Vytvořte instanci prohlížeče zadáním cesty k dokumentu tabulky. Nakonfigurujte možnosti zobrazení HTML pro vložení zdrojů a povolení vykreslování skrytých sloupců a řádků.
## Krok 3: Spusťte proces vykreslování
```csharp
    viewer.View(options);
}
```
Vyvolejte metodu View na objektu prohlížeče a předejte nakonfigurované možnosti. Tím se spustí proces vykreslování.
## Krok 4: Zkontrolujte výstup
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ověřte úspěšné vykreslení zdrojového dokumentu a vyhledejte výstup v určeném adresáři.
## Závěr
Odemknutí skrytých sloupců a řádků ve vašich tabulkách se s GroupDocs.Viewer pro .NET stane hračkou. Tento výukový program vás vybavil základními kroky k odhalení skrytých dat a poskytuje komplexnější pohled na vaše dokumenty.
## Často kladené otázky
### Mohu vykreslit skryté sloupce a řádky v jiných formátech dokumentů kromě tabulek?
Ano, GroupDocs.Viewer podporuje kromě tabulek různé formáty dokumentů, včetně Wordu, PDF a PowerPointu.
### Existuje omezení počtu skrytých sloupců a řádků, které lze vykreslit?
GroupDocs.Viewer efektivně zpracovává vykreslování pro širokou škálu skrytých sloupců a řádků. Extrémní případy s velkým množstvím skrytých dat však mohou ovlivnit výkon.
### Mohu přizpůsobit výstupní formát vykreslených dat?
Absolutně! GroupDocs.Viewer poskytuje flexibilní možnosti přizpůsobení výstupu, což vám umožní přizpůsobit vykreslená data vašim konkrétním potřebám.
### Existují nějaké úvahy o licencování pro používání GroupDocs.Viewer?
 Ano, ujistěte se, že máte příslušnou licenci pro své použití. Prozkoumejte možnosti licencování na[Nákup GroupDocs](https://purchase.groupdocs.com/buy) nebo získat a[dočasná licence](https://purchase.groupdocs.com/temporary-license/) pro testování.
### Kde mohu vyhledat pomoc nebo se spojit s komunitou GroupDocs pro podporu?
 Navštivte[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za podporu, diskuse a interakci s komunitou.