---
"description": "Naučte se, jak vykreslovat soubory CHM v .NET pomocí GroupDocs.Viewer. Převádějte CHM do formátů HTML, JPG, PNG a PDF bez námahy."
"linktitle": "Renderování souborů CHM"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Renderování souborů CHM"
"url": "/cs/net/rendering-web-documents/render-chm/"
"weight": 10
---

# Renderování souborů CHM

## Zavedení
V tomto tutoriálu se podíváme na to, jak vykreslovat soubory CHM (kompilovaná HTML nápověda) pomocí GroupDocs.Viewer for .NET. GroupDocs.Viewer for .NET je výkonné API pro vykreslování dokumentů, které umožňuje vývojářům zobrazovat více než 170 typů dokumentů v rámci jejich .NET aplikací bez nutnosti instalace externího softwaru.

## Předpoklady

Než se pustíme do vykreslování souborů CHM, ujistěte se, že máte následující předpoklady:

### Instalace GroupDocs.Viewer pro .NET

Pro začátek je potřeba nainstalovat GroupDocs.Viewer pro .NET. Knihovnu si můžete stáhnout z [Webové stránky GroupDocs](https://releases.groupdocs.com/viewer/net/) nebo jej nainstalujte pomocí Správce balíčků NuGet spuštěním následujícího příkazu v konzoli Správce balíčků:

```bash
Install-Package GroupDocs.Viewer
```

## Import jmenných prostorů

Nezapomeňte do projektu importovat potřebné jmenné prostory:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme proces renderování do několika kroků:

## Krok 1: Definování výstupního adresáře

Definujte adresář, kam chcete ukládat vykreslené soubory:

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Vykreslení do HTML

Pro vykreslení souborů CHM do HTML použijte následující úryvek kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Nastavením na hodnotu true převedete veškerý obsah CHM na jednu stránku.

    viewer.View(options); // Převést všechny stránky
}
```

## Krok 3: Vykreslení do JPG

Pro vykreslení souborů CHM do obrázků JPG použijte následující úryvek kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Převést pouze stránky 1, 2, 3
}
```

## Krok 4: Vykreslení do PNG

Pro vykreslení souborů CHM do obrázků PNG použijte následující úryvek kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Převést pouze stránky 1, 2, 3
}
```

## Krok 5: Vykreslení do PDF

Pro vykreslení souborů CHM do dokumentu PDF použijte následující úryvek kódu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Převést všechny stránky
}
```

## Krok 6: Zkontrolujte výstup

Jakmile je proces vykreslování dokončen, zkontrolujte zadaný výstupní adresář, zda se v něm nenacházejí vykreslené soubory:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Vykreslování souborů CHM pomocí GroupDocs.Viewer pro .NET je jednoduchý proces. Dodržováním kroků popsaných v tomto tutoriálu můžete efektivně převádět dokumenty CHM do různých formátů, jako je HTML, obrázky (JPG, PNG) a PDF ve vašich aplikacích .NET.

## Často kladené otázky

### Q1: Může GroupDocs.Viewer vykreslit i jiné formáty dokumentů než CHM?

A1: Ano, GroupDocs.Viewer podporuje vykreslování více než 170 formátů dokumentů včetně PDF, DOCX, XLSX, PPTX a dalších.

### Q2: Je GroupDocs.Viewer kompatibilní s .NET Core?

A2: Ano, GroupDocs.Viewer podporuje kromě tradičního .NET Frameworku i .NET Core.

### Q3: Mohu si přizpůsobit možnosti vykreslování pro různé výstupní formáty?

A3: Ano, GroupDocs.Viewer nabízí různé možnosti pro přizpůsobení procesu vykreslování, jako je například zadání čísel stránek, nastavení kvality obrazu a konfigurace výstupních cest.

### Q4: Vyžaduje GroupDocs.Viewer nějaké externí závislosti pro vykreslování dokumentů?

A4: Ne, GroupDocs.Viewer je samostatná knihovna a nevyžaduje žádné externí závislosti ani instalaci softwaru třetích stran.

### Q5: Je k dispozici bezplatná zkušební verze GroupDocs.Viewer?

A5: Ano, můžete využít bezplatnou zkušební verzi GroupDocs.Viewer na adrese [webové stránky](https://releases.groupdocs.com/).