---
title: Vykreslit dokument do PDF
linktitle: Vykreslit dokument do PDF
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat dokumenty do PDF pomocí GroupDocs.Viewer pro .NET. Podrobný průvodce s nezbytnými předpoklady a často kladenými dotazy.
type: docs
weight: 10
url: /cs/net/rendering-documents-pdf/render-to-pdf/
---
## Úvod
GroupDocs.Viewer for .NET je výkonný nástroj pro vykreslování různých formátů dokumentů do PDF. V tomto tutoriálu vás provedeme procesem krok za krokem.
## Předpoklady

Než začneme, ujistěte se, že máte následující:
1.  GroupDocs.Viewer for .NET Library: Knihovnu si můžete stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Ujistěte se, že máte na svém počítači nainstalovanou příslušnou verzi .NET Framework.
3. Soubory dokumentů: Připravte soubory dokumentů, které chcete vykreslit. Mezi podporované formáty patří DOCX, PDF, PPTX, XLSX a další.

## Import jmenných prostorů:
Než se ponoříte do kódu, ujistěte se, že jste importovali potřebné jmenné prostory:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme proces vykreslování do několika kroků:
## Krok 1: Definujte výstupní adresář a cestu k souboru
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
 Zajistěte výměnu`"Your Document Directory"` s adresářem, kam chcete uložit vykreslený soubor PDF.
## Krok 2: Vytvořte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Váš kód zde
}
```
 Nahradit`TestFiles.SAMPLE_DOCX` s cestou k souboru vašeho dokumentu.
## Krok 3: Nastavte možnosti zobrazení PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Krok 4: Vykreslení dokumentu do PDF
```csharp
viewer.View(options);
```
## Krok 5: Zobrazte zprávu o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po provedení těchto kroků úspěšně vykreslíte svůj dokument do PDF pomocí GroupDocs.Viewer for .NET.

## Závěr
Vykreslování dokumentů do PDF je běžným požadavkem v různých aplikacích. S GroupDocs.Viewer for .NET se tento proces stává bezproblémovým a efektivním a umožňuje vám snadno zpracovávat širokou škálu formátů dokumentů.
## FAQ
### Mohu vykreslit do PDF jiné dokumenty než DOCX?
Ano, GroupDocs.Viewer for .NET podporuje různé formáty jako PDF, PPTX, XLSX a další.
### Je k dispozici zkušební verze?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.groupdocs.com/).
### Jak mohu získat podporu, pokud narazím na nějaké problémy?
 Můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9) pro pomoc.
### Potřebuji dočasnou licenci pro testovací účely?
 Ano, můžete získat dočasnou licenci od[tady](https://purchase.groupdocs.com/temporary-license/).
### Kde si mohu zakoupit plnou licenci?
 Licenci si můžete zakoupit od[tady](https://purchase.groupdocs.com/buy).