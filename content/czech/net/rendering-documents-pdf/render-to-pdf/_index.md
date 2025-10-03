---
"description": "Naučte se, jak vykreslit dokumenty do PDF pomocí GroupDocs.Viewer pro .NET. Podrobný návod s předpoklady a častými dotazy."
"linktitle": "Vykreslení dokumentu do PDF"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení dokumentu do PDF"
"url": "/cs/net/rendering-documents-pdf/render-to-pdf/"
"weight": 10
type: docs
---
# Vykreslení dokumentu do PDF

## Zavedení
GroupDocs.Viewer pro .NET je výkonný nástroj pro převod různých formátů dokumentů do PDF. V tomto tutoriálu vás krok za krokem provedeme celým procesem.
## Předpoklady

Než začneme, ujistěte se, že máte následující:
1. Knihovna GroupDocs.Viewer pro .NET: Knihovnu si můžete stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Ujistěte se, že máte v počítači nainstalovanou správnou verzi .NET Frameworku.
3. Soubory dokumentů: Připravte si soubory dokumentů, které chcete vykreslit. Mezi podporované formáty patří DOCX, PDF, PPTX, XLSX a další.

## Import jmenných prostorů:
Než se ponoříte do kódu, ujistěte se, že jste importovali potřebné jmenné prostory:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme proces renderování do několika kroků:
## Krok 1: Definování výstupního adresáře a cesty k souboru
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
Ujistěte se, že vyměníte `"Your Document Directory"` s adresářem, kam chcete uložit vykreslený soubor PDF.
## Krok 2: Vytvoření instance objektu Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Váš kód zde
}
```
Nahradit `TestFiles.SAMPLE_DOCX` s cestou k souboru dokumentu.
## Krok 3: Nastavení možností zobrazení PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Krok 4: Vykreslení dokumentu do PDF
```csharp
viewer.View(options);
```
## Krok 5: Zobrazení zprávy o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po provedení těchto kroků budete mít dokument úspěšně vykreslený do PDF pomocí GroupDocs.Viewer pro .NET.

## Závěr
Vykreslování dokumentů do PDF je běžným požadavkem v různých aplikacích. S GroupDocs.Viewer pro .NET se tento proces stává bezproblémovým a efektivním, což vám umožňuje snadno zpracovávat širokou škálu formátů dokumentů.
## Často kladené otázky
### Mohu převést dokumenty z jiného formátu než DOCX do PDF?
Ano, GroupDocs.Viewer pro .NET podporuje různé formáty, jako například PDF, PPTX, XLSX a další.
### Je k dispozici zkušební verze?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.groupdocs.com/).
### Jak mohu získat podporu, pokud narazím na nějaké problémy?
Můžete navštívit fórum GroupDocs.Viewer [zde](https://forum.groupdocs.com/c/viewer/9) o pomoc.
### Potřebuji pro účely testování dočasnou licenci?
Ano, můžete získat dočasnou licenci od [zde](https://purchase.groupdocs.com/temporary-license/).
### Kde si mohu koupit plnou licenci?
Licenci si můžete zakoupit od [zde](https://purchase.groupdocs.com/buy).