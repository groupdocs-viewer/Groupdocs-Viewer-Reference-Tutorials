---
title: Vykreslování konkrétních složek a filtrování zpráv (Outlook)
linktitle: Vykreslování konkrétních složek a filtrování zpráv (Outlook)
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat konkrétní složky a filtrovat zprávy v Outlooku pomocí GroupDocs.Viewer for .NET. Zjednodušte správu dokumentů v aplikacích .NET.
type: docs
weight: 11
url: /cs/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---
## Úvod
Ve světě vývoje .NET je efektivní správa a zobrazování dokumentů zásadní. GroupDocs.Viewer for .NET tento úkol zjednodušuje tím, že poskytuje výkonné funkce pro bezproblémové vykreslování různých formátů dokumentů. V tomto tutoriálu se ponoříme do toho, jak vykreslit konkrétní složky a filtrovat zprávy v aplikaci Outlook pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující:
1.  GroupDocs.Viewer for .NET: Ujistěte se, že jste nainstalovali GroupDocs.Viewer for .NET. Můžete si jej stáhnout z[webová stránka](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Na vašem počítači musíte mít nainstalovaný .NET Framework.
3. Základní znalost C#: Seznámení s programovacím jazykem C# bude užitečné sledovat spolu s výukovým programem.

## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory do našeho kódu C#:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` s cestou k adresáři, kam chcete ukládat vykreslené dokumenty.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Tento řádek definuje formát cest k souboru každé vykreslené stránky. V tomto příkladu vygeneruje soubory HTML s názvem`page_1.html`, `page_2.html`, a tak dále.
## Krok 3: Inicializujte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
 Zde inicializujeme a`Viewer` objekt s cestou k ukázkové složce aplikace Outlook.
## Krok 4: Definujte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
 Vytvoříme instanci`HtmlViewOptions` a určit formát pro vložené zdroje. Kromě toho jsme nastavili složku Outlook, aby se vykreslila jako`"Входящие"` (Přicházející).
## Krok 5: Vykreslení dokumentu
```csharp
viewer.View(options);
```
Tento řádek spouští proces vykreslování se zadanými možnostmi.
## Krok 6: Zobrazte zprávu o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po vykreslení se zobrazí tato zpráva oznamující úspěšné dokončení procesu vykreslování a přesměruje uživatele do výstupního adresáře.

## Závěr
tomto tutoriálu jsme prozkoumali, jak vykreslit konkrétní složky a filtrovat zprávy v aplikaci Outlook pomocí GroupDocs.Viewer pro .NET. Podle výše uvedených kroků můžete efektivně spravovat a zobrazovat dokumenty ve svých aplikacích .NET.
## FAQ
### Mohu pomocí GroupDocs.Viewer for .NET vykreslit jiné dokumenty než zprávy aplikace Outlook?
Ano, GroupDocs.Viewer for .NET podporuje širokou škálu formátů dokumentů včetně PDF, DOCX, XLSX a dalších.
### Je GroupDocs.Viewer for .NET kompatibilní s .NET Core?
Ano, GroupDocs.Viewer for .NET je kompatibilní s .NET Framework i .NET Core.
### Mohu přizpůsobit výstupní formát vykreslování?
GroupDocs.Viewer for .NET samozřejmě poskytuje různé možnosti přizpůsobení výstupu vykreslování včetně formátů HTML, obrázků a PDF.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[webová stránka](https://releases.groupdocs.com/).
### Kde mohu hledat pomoc nebo podporu pro GroupDocs.Viewer pro .NET?
 Můžete navštívit[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pro jakoukoli pomoc nebo dotazy.