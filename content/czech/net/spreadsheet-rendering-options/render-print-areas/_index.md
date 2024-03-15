---
title: Vykreslování tiskových oblastí pomocí GroupDocs.Viewer pro .NET
linktitle: Vykreslit oblasti tisku
second_title: GroupDocs.Viewer .NET API
description: Prozkoumejte GroupDocs.Viewer pro .NET a bez námahy vykreslujte oblasti tisku v různých formátech dokumentů. Vyzkoušejte bezplatnou zkušební verzi nyní! #GroupDocs.Viewer
type: docs
weight: 17
url: /cs/net/spreadsheet-rendering-options/render-print-areas/
---
## Úvod
Vítejte v tomto komplexním průvodci o využití GroupDocs.Viewer pro .NET k vykreslení oblastí tisku ve vašich dokumentech. Pokud jste vývojář .NET, který hledá robustní řešení pro vykreslování dokumentů, jste na správném místě. V tomto tutoriálu vás provedeme procesem vykreslování tiskových oblastí pomocí GroupDocs.Viewer, což zajistí bezproblémové používání vašich aplikací.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost vývoje C# a .NET.
-  GroupDocs.Viewer pro .NET nainstalován. Můžete si jej stáhnout[tady](https://releases.groupdocs.com/viewer/net/).
- Ukázkový dokument (např. "SAMPLE.XLSX") ve vámi zadaném adresáři dokumentů.
## Importovat jmenné prostory
Ujistěte se, že jste do kódu C# importovali potřebné jmenné prostory pro správnou implementaci:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavte adresář dokumentů
Začněte zadáním výstupního adresáře pro vykreslené HTML stránky:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
Vytvořte formát pro cesty k souboru stránky zkombinováním výstupního adresáře a zástupného symbolu pro číslo stránky:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Inicializujte GroupDocs.Viewer
Vytvořte instanci třídy Viewer s cestou k vašemu vzorovému dokumentu:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
Nakonfigurujte možnosti zobrazení HTML, určete formát cesty k souboru stránky a povolte volby pro vykreslení oblastí tisku:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Krok 5: Vykreslení dokumentu
 Vyvolat`View` metoda vykreslení dokumentu se zadanými možnostmi:
```csharp
viewer.View(options);
```
## Krok 6: Zobrazte zprávu o úspěchu
Vytiskněte zprávu o úspěchu, která označuje, že zdrojový dokument byl úspěšně vykreslen:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak používat GroupDocs.Viewer pro .NET k vykreslení oblastí tisku ve vašich dokumentech. Tento výkonný nástroj otevírá nové možnosti pro vykreslování dokumentů ve vašich aplikacích .NET.
## Nejčastější dotazy
### Je GroupDocs.Viewer kompatibilní s různými formáty dokumentů?
 Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, DOCX, XLSX a dalších. Odkazovat na[dokumentace](https://reference.groupdocs.com/viewer/net/) pro úplný seznam.
### Mohu GroupDocs.Viewer před nákupem vyzkoušet?
 Absolutně! Nástroj můžete prozkoumat pomocí bezplatné zkušební verze[tady](https://releases.groupdocs.com/).
### Kde mohu najít podporu nebo vyhledat pomoc v případě jakýchkoli problémů?
 Navštivte[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)spojit se s komunitou a získat pomoc.
### Je k dispozici možnost dočasné licence?
 Ano, můžete získat dočasnou licenci[tady](https://purchase.groupdocs.com/temporary-license/).
### Kde si mohu zakoupit GroupDocs.Viewer pro .NET?
 Můžete provést nákup[tady](https://purchase.groupdocs.com/buy).