---
title: Upravte kvalitu obrázku JPG ve vykresleném PDF
linktitle: Upravte kvalitu obrázku JPG ve vykresleném PDF
second_title: GroupDocs.Viewer .NET API
description: Zjistěte, jak upravit kvalitu obrazu JPG ve vykreslených dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Vylepšete si zážitek ze sledování dokumentů.
weight: 11
url: /cs/net/rendering-documents-pdf/adjust-jpg-quality-pdf/
---

# Upravte kvalitu obrázku JPG ve vykresleném PDF

## Úvod
tomto tutoriálu se naučíme, jak upravit kvalitu obrázků JPG při vykreslování PDF pomocí GroupDocs.Viewer for .NET. Tato výkonná knihovna vám umožňuje bezproblémově prohlížet a manipulovat s různými formáty dokumentů ve vašich aplikacích .NET.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1.  Knihovna GroupDocs.Viewer for .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu GroupDocs.Viewer for .NET. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Mějte nastavené pracovní vývojové prostředí s nainstalovaným .NET frameworkem.

## Importovat jmenné prostory
Nejprve musíte do kódu C# importovat potřebné jmenné prostory. To umožňuje vaší aplikaci přístup k funkcím, které poskytuje GroupDocs.Viewer pro .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Definujte výstupní adresář a cestu k souboru
Nastavte výstupní adresář, kam bude vykreslený PDF uložen, a definujte cestu k výstupnímu souboru PDF.
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 2: Vykreslení PDF s upravenou kvalitou obrazu JPG
Vytvořte instanci třídy Viewer a předejte cestu k dokumentu obsahujícímu obrázky JPG. Poté nakonfigurujte možnosti vykreslování PDF a upravte kvalitu obrázku JPG.
```csharp
using (Viewer viewer = new Viewer(TestFiles.JPG_IMAGE_PPTX))
{               
    PdfViewOptions options = new PdfViewOptions(filePath);
    viewer.View(options);
}
```
## Krok 3: Zobrazte zprávu o úspěchu
Po úspěšném vykreslení PDF zobrazte zprávu, která uživatele upozorní na dokončení a umístění výstupního souboru.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
V tomto tutoriálu jsme prozkoumali, jak upravit kvalitu obrázku JPG při vykreslování PDF pomocí GroupDocs.Viewer pro .NET. Dodržením těchto kroků můžete efektivně řídit kvalitu obrázků ve vašich vykreslených dokumentech PDF a zajistit tak optimální vizuální reprezentaci.
## FAQ
### Mohu upravit kvalitu obrazu pro jiné formáty kromě JPG?
Ano, GroupDocs.Viewer for .NET podporuje různé formáty obrázků a kvalitu můžete upravit také pro formáty PNG, TIFF a další.
### Je GroupDocs.Viewer for .NET kompatibilní se všemi verzemi .NET frameworku?
GroupDocs.Viewer for .NET je kompatibilní s více verzemi rozhraní .NET, včetně .NET Core a .NET Standard.
### Mohu vykreslovat dokumenty asynchronně pomocí GroupDocs.Viewer pro .NET?
Ano, GroupDocs.Viewer for .NET poskytuje možnosti asynchronního vykreslování, což vám umožní zvýšit výkon vašich aplikací.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, máte přístup k bezplatné zkušební verzi GroupDocs.Viewer for .NET z[tady](https://releases.groupdocs.com/).
### Jak mohu získat podporu nebo pomoc s GroupDocs.Viewer pro .NET?
 Můžete navštívit fórum GroupDocs.Viewer for .NET[tady](https://forum.groupdocs.com/c/viewer/9) získat pomoc, klást otázky a komunikovat s ostatními uživateli a vývojáři.