---
title: Získejte názvy pracovních listů
linktitle: Získejte názvy pracovních listů
second_title: GroupDocs.Viewer .NET API
description: Prozkoumejte kouzlo GroupDocs.Viewer pro .NET – bezproblémově integrujte zobrazování dokumentů do svých aplikací. Vyzkoušejte bezplatnou zkušební verzi nyní!
type: docs
weight: 11
url: /cs/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Úvod
Vítejte ve fascinujícím světě GroupDocs.Viewer pro .NET! Pokud jste vývojář nebo nadšenec, který má zájem prozkoumávat výkonné možnosti prohlížení dokumentů ve svých aplikacích .NET, máte se na co těšit. V tomto komplexním průvodci se ponoříme do složitosti získávání názvů listů pomocí GroupDocs.Viewer. Zapněte si bezpečnostní pás a vydejte se na tuto vzrušující cestu!
## Předpoklady
Než se ponoříme do kouzla kódování, ujistěte se, že máte vše nastaveno:
1.  Nainstalujte GroupDocs.Viewer pro .NET: Přejděte na[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/)získat nejnovější verzi GroupDocs.Viewer pro .NET. Postupujte podle pokynů k instalaci a bezproblémově jej integrujte do svého vývojového prostředí.
2. Připravte si dokument: Ujistěte se, že máte v určeném adresáři dokumentů cílový dokument, řekněme soubor aplikace Excel s názvem „file.xlsx“.
## Importovat jmenné prostory
Nyní, když máte připravené předpoklady, začněme tím, že naimportujeme potřebné jmenné prostory. To zajistí, že vaše aplikace rozpozná a bude moci využívat funkce poskytované GroupDocs.Viewer pro .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Nastavení adresáře dokumentů
```csharp
string outputDirectory = "Your Document Directory";
```
Nahraďte "Your Document Directory" cestou k adresáři, kde je umístěn váš cílový dokument.
## 2. Inicializace prohlížeče
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
V tomto kroku vytvoříme instanci třídy Viewer, která poskytne cestu k vašemu souboru Excel.
## 3. Konfigurace možností zobrazení informací
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Zde nakonfigurujeme ViewInfoOptions pro generování zobrazení HTML a nastavíme další možnosti pro vykreslování tabulek.
## 4. Získání informací o zobrazení
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Použijte instanci Viewer k načtení informací o zobrazení na základě nakonfigurovaných možností.
## 5. Zobrazení názvů pracovních listů
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Procházejte načtené stránky a vytiskněte název každého listu na konzole.
## Závěr
Gratulujeme! Úspěšně jste prošli procesem načítání názvů listů pomocí GroupDocs.Viewer pro .NET. To otevírá nespočet možností pro vylepšení funkcí prohlížení dokumentů ve vašich aplikacích.
## Nejčastější dotazy
### Mohu použít GroupDocs.Viewer pro .NET s jinými formáty dokumentů?
Absolutně! GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office a dalších.
### Je k dispozici bezplatná zkušební verze?
 Ano, GroupDocs.Viewer pro .NET můžete prozkoumat s naším[zkušební verze zdarma](https://releases.groupdocs.com/).
### Kde najdu další podporu?
 Zamiřte do[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za podporu komunity a diskuze.
### Mohu získat dočasnou licenci?
 Rozhodně! Návštěva[tento odkaz](https://purchase.groupdocs.com/temporary-license/) získat dočasnou licenci.
### Jsou k dispozici podrobné zdroje dokumentace?
 Absolutně! Podívejte se na[oficiální dokumentace](https://reference.groupdocs.com/viewer/net/) pro podrobné informace a průvodce.