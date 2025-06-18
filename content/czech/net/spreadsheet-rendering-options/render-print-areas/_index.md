---
"description": "Prozkoumejte GroupDocs.Viewer pro .NET a bez námahy vykreslujte oblasti tisku v různých formátech dokumentů. Vyzkoušejte si bezplatnou zkušební verzi hned teď!"
"linktitle": "Vykreslení oblastí tisku"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení tiskových oblastí pomocí GroupDocs.Viewer pro .NET"
"url": "/cs/net/spreadsheet-rendering-options/render-print-areas/"
"weight": 17
---

# Vykreslení tiskových oblastí pomocí GroupDocs.Viewer pro .NET

## Zavedení
Vítejte v tomto komplexním průvodci o využití GroupDocs.Viewer pro .NET k vykreslování tiskových oblastí ve vašich dokumentech. Pokud jste vývojář v .NET a hledáte robustní řešení pro vykreslování dokumentů, jste na správném místě. V tomto tutoriálu vás provedeme procesem vykreslování tiskových oblastí pomocí GroupDocs.Viewer, což zajistí bezproblémový provoz vašich aplikací.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Praktická znalost vývoje v C# a .NET.
- Nainstalován je GroupDocs.Viewer pro .NET. Můžete si ho stáhnout. [zde](https://releases.groupdocs.com/viewer/net/).
- Ukázkový dokument (např. „SAMPLE.XLSX“) ve vámi zadaném adresáři dokumentů.
## Importovat jmenné prostory
Pro správnou implementaci nezapomeňte do kódu C# importovat potřebné jmenné prostory:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavení adresáře dokumentů
Začněte zadáním výstupního adresáře pro vykreslené HTML stránky:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru stránky
Vytvořte formát pro cesty k stránkovacímu souboru, který kombinuje výstupní adresář a zástupný symbol pro číslo stránky:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Inicializace souboru GroupDocs.Viewer
Vytvořte instanci třídy Viewer s cestou k vašemu vzorovému dokumentu:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Krok 4: Konfigurace možností zobrazení HTML
Nakonfigurujte možnosti zobrazení HTML, zadejte formát cesty k souboru stránky a povolte možnosti pro vykreslování oblastí tisku:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Krok 5: Vykreslení dokumentu
Vyvolat `View` metoda pro vykreslení dokumentu se zadanými možnostmi:
```csharp
viewer.View(options);
```
## Krok 6: Zobrazení zprávy o úspěchu
Vytiskněte zprávu o úspěchu, která indikuje, že zdrojový dokument byl úspěšně vykreslen:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak používat GroupDocs.Viewer pro .NET k vykreslování tiskových oblastí ve vašich dokumentech. Tento výkonný nástroj otevírá nové možnosti vykreslování dokumentů ve vašich .NET aplikacích.
## Často kladené otázky
### Je GroupDocs.Viewer kompatibilní s různými formáty dokumentů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, DOCX, XLSX a dalších. Viz [dokumentace](https://tutorials.groupdocs.com/viewer/net/) pro kompletní seznam.
### Mohu si před nákupem vyzkoušet GroupDocs.Viewer?
Rozhodně! Nástroj si můžete vyzkoušet s bezplatnou zkušební verzí. [zde](https://releases.groupdocs.com/).
### Kde mohu najít podporu nebo vyhledat pomoc s jakýmikoli problémy?
Navštivte [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) spojit se s komunitou a získat pomoc.
### Existuje možnost dočasné licence?
Ano, můžete získat dočasnou licenci [zde](https://purchase.groupdocs.com/temporary-license/).
### Kde mohu zakoupit GroupDocs.Viewer pro .NET?
Můžete provést nákup [zde](https://purchase.groupdocs.com/buy).