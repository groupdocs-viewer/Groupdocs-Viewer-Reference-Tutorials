---
title: Vykreslit soubory CHM
linktitle: Vykreslit soubory CHM
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat soubory CHM v .NET pomocí GroupDocs.Viewer. Převeďte CHM do formátů HTML, JPG, PNG a PDF bez námahy.
weight: 10
url: /cs/net/rendering-web-documents/render-chm/
---
## Úvod
tomto tutoriálu prozkoumáme, jak vykreslit soubory CHM (Compiled HTML Help) pomocí GroupDocs.Viewer pro .NET. GroupDocs.Viewer for .NET je výkonné rozhraní API pro vykreslování dokumentů, které umožňuje vývojářům zobrazovat více než 170 typů dokumentů v rámci jejich aplikací .NET, aniž by vyžadovali instalaci externího softwaru.

## Předpoklady

Než se pustíme do vykreslování souborů CHM, ujistěte se, že máte následující předpoklady:

### Instalace GroupDocs.Viewer pro .NET

 Chcete-li začít, musíte nainstalovat GroupDocs.Viewer for .NET. Knihovnu si můžete stáhnout z[Web GroupDocs](https://releases.groupdocs.com/viewer/net/) nebo jej nainstalujte pomocí NuGet Package Manager spuštěním následujícího příkazu v konzole Package Manager:

```bash
Install-Package GroupDocs.Viewer
```

## Import jmenných prostorů

Ujistěte se, že jste do projektu importovali potřebné jmenné prostory:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme proces vykreslování do několika kroků:

## Krok 1: Definujte výstupní adresář

Definujte adresář, kam chcete ukládat vykreslené soubory:

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Vykreslení do HTML

Chcete-li vykreslit soubory CHM do HTML, použijte následující fragment kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Nastavením na hodnotu true převedete veškerý obsah CHM na jednu stránku

    viewer.View(options); //Převést všechny stránky
}
```

## Krok 3: Vykreslení do JPG

Chcete-li vykreslit soubory CHM na obrázky JPG, použijte následující fragment kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Převeďte pouze stránky 1, 2, 3
}
```

## Krok 4: Vykreslení do PNG

Chcete-li vykreslit soubory CHM do obrázků PNG, použijte následující fragment kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Převeďte pouze stránky 1, 2, 3
}
```

## Krok 5: Vykreslení do PDF

Chcete-li vykreslit soubory CHM do dokumentu PDF, použijte následující fragment kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Převést všechny stránky
}
```

## Krok 6: Zkontrolujte výstup

Po dokončení procesu vykreslování zkontrolujte zadaný výstupní adresář pro vykreslené soubory:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Vykreslování souborů CHM pomocí GroupDocs.Viewer for .NET je jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete efektivně převádět dokumenty CHM do různých formátů, jako jsou HTML, obrázky (JPG, PNG) a PDF v rámci vašich aplikací .NET.

## FAQ

### Q1: Může GroupDocs.Viewer vykreslit jiné formáty dokumentů kromě CHM?

Odpověď 1: Ano, GroupDocs.Viewer podporuje vykreslování více než 170 formátů dokumentů včetně PDF, DOCX, XLSX, PPTX a dalších.

### Q2: Je GroupDocs.Viewer kompatibilní s .NET Core?

Odpověď 2: Ano, GroupDocs.Viewer podporuje kromě tradičního rozhraní .NET Framework také .NET Core.

### Q3: Mohu přizpůsobit možnosti vykreslování pro různé výstupní formáty?

Odpověď 3: Ano, GroupDocs.Viewer poskytuje různé možnosti pro přizpůsobení procesu vykreslování, jako je zadání čísel stránek, nastavení kvality obrazu a konfigurace výstupních cest.

### Q4: Vyžaduje GroupDocs.Viewer nějaké externí závislosti pro vykreslování dokumentů?

Odpověď 4: Ne, GroupDocs.Viewer je samostatná knihovna a nevyžaduje žádné externí závislosti ani instalace softwaru třetích stran.

### Q5: Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer?

 A5: Ano, můžete využít bezplatnou zkušební verzi GroupDocs.Viewer návštěvou[webová stránka](https://releases.groupdocs.com/).