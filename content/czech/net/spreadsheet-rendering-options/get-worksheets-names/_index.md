---
"description": "Objevte kouzlo GroupDocs.Viewer pro .NET – bezproblémově integrujte prohlížení dokumentů do svých aplikací. Vyzkoušejte si bezplatnou zkušební verzi hned teď!"
"linktitle": "Získat názvy pracovních listů"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Získat názvy pracovních listů"
"url": "/cs/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# Získat názvy pracovních listů

## Zavedení
Vítejte ve fascinujícím světě GroupDocs.Viewer pro .NET! Pokud jste vývojář nebo nadšenec, který touží prozkoumat výkonné funkce prohlížení dokumentů ve vašich .NET aplikacích, čeká vás lahůdka. V této komplexní příručce se ponoříme do složitostí načítání názvů pracovních listů pomocí GroupDocs.Viewer. Takže si zapněte pásy a pojďme se vydat na tuto vzrušující cestu!
## Předpoklady
Než se ponoříme do programátorské magie, ujistěme se, že máte vše nastavené:
1. Nainstalujte GroupDocs.Viewer pro .NET: Přejděte na [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/) Stáhněte si nejnovější verzi GroupDocs.Viewer pro .NET. Postupujte podle pokynů k instalaci a bezproblémově jej integrujte do svého vývojového prostředí.
2. Připravte si dokument: Ujistěte se, že máte v určeném adresáři dokumentů cílový dokument, například soubor aplikace Excel s názvem „file.xlsx“.
## Importovat jmenné prostory
Nyní, když máte splněny předpoklady, začněme importem potřebných jmenných prostorů. Tím zajistíte, že vaše aplikace rozpozná a bude moci využívat funkce poskytované GroupDocs.Viewer pro .NET.
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
Nahraďte „Adresář dokumentů“ cestou k adresáři, kde se nachází cílový dokument.
## 2. Inicializace prohlížeče
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
V tomto kroku vytvoříme instanci třídy Viewer, která poskytne cestu k vašemu souboru aplikace Excel.
## 3. Konfigurace možností zobrazení informací
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Zde nakonfigurujeme ViewInfoOptions pro generování HTML zobrazení a nastavíme další možnosti pro vykreslování tabulek.
## 4. Získání informací o zobrazení
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Použijte instanci prohlížeče k načtení informací o zobrazení na základě nakonfigurovaných možností.
## 5. Zobrazení názvů pracovních listů
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Projděte načtené stránky a vypište název každého listu do konzole.
## Závěr
Gratulujeme! Úspěšně jste zvládli proces načítání názvů pracovních listů pomocí nástroje GroupDocs.Viewer pro .NET. To otevírá nepřeberné množství možností pro vylepšení funkcí prohlížení dokumentů ve vašich aplikacích.
## Často kladené otázky
### Mohu používat GroupDocs.Viewer pro .NET s jinými formáty dokumentů?
Rozhodně! GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office a dalších.
### Je k dispozici bezplatná zkušební verze?
Ano, můžete si prohlédnout GroupDocs.Viewer pro .NET s naším [bezplatná zkušební verze](https://releases.groupdocs.com/).
### Kde mohu najít další podporu?
Vydejte se do [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pro podporu komunity a diskuse.
### Mohu získat dočasnou licenci?
Jistě! Navštivte [tento odkaz](https://purchase.groupdocs.com/temporary-license/) abyste získali dočasný řidičský průkaz.
### Jsou k dispozici podrobné dokumentační zdroje?
Rozhodně! Podívejte se na [oficiální dokumentace](https://tutorials.groupdocs.com/viewer/net/) pro podrobné informace a návody.