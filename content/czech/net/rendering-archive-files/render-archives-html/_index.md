---
title: Vykreslit archivy na jednu nebo více stránek HTML
linktitle: Vykreslit archivy na jednu nebo více stránek HTML
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat archivy na stránky HTML pomocí GroupDocs.Viewer for .NET. Bez námahy integrujte možnosti prohlížení dokumentů do svých aplikací .NET.
weight: 12
url: /cs/net/rendering-archive-files/render-archives-html/
---

# Vykreslit archivy na jednu nebo více stránek HTML

## Úvod
GroupDocs.Viewer for .NET je výkonná knihovna pro vykreslování dokumentů, která umožňuje vývojářům bez námahy integrovat možnosti prohlížení dokumentů do jejich aplikací .NET. Ať už potřebujete vykreslit archivy na jednu nebo více stránek HTML, tento tutoriál vás provede procesem krok za krokem.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1.  GroupDocs.Viewer for .NET: Ujistěte se, že máte knihovnu nainstalovanou ve svém projektu. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Mějte pracovní vývojové prostředí nastavené pro vývoj .NET.
3. Adresář dokumentů: Připravte si adresář, kde jsou uloženy vaše dokumenty.
4. Základní porozumění C#: Seznamte se se základy programovacího jazyka C#.

## Importovat jmenné prostory
V kódu C# nezapomeňte importovat potřebné jmenné prostory:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Chcete-li vykreslit archivy na jednu nebo více stránek HTML pomocí GroupDocs.Viewer pro .NET, postupujte takto:
## Krok 1: Nastavte výstupní adresář
Definujte adresář, kam chcete ukládat vykreslené HTML stránky:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru
Zadejte formát cesty k souboru pro stránky HTML. Pro vykreslování jedné stránky:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Pro vícestránkové vykreslování:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Krok 3: Vykreslení na jednu stránku HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Krok 4: Vykreslení HTML na více stránek
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Nastavte položky na stránku
    viewer.View(options);
}
```
## Krok 5: Zkontrolujte výstup
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Vykreslování archivů na stránky HTML pomocí GroupDocs.Viewer for .NET je jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete bezproblémově integrovat možnosti prohlížení dokumentů do vašich aplikací .NET.
## FAQ
### Mohu vykreslit jiné formáty dokumentů kromě archivů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů včetně PDF, DOCX, XLSX, PPTX a dalších.
### Je GroupDocs.Viewer vhodný pro desktopové i webové aplikace?
GroupDocs.Viewer lze bez problémů používat v desktopových i webových aplikacích.
### Nabízí GroupDocs.Viewer možnosti přizpůsobení rozhraní prohlížeče?
Ano, rozhraní prohlížeče si můžete přizpůsobit podle svých požadavků.
### Mohu vykreslovat dokumenty asynchronně s GroupDocs.Viewer?
Ano, GroupDocs.Viewer poskytuje možnosti asynchronního vykreslování pro lepší výkon.
### Podporuje GroupDocs.Viewer anotace dokumentů?
Ano, GroupDocs.Viewer umožňuje uživatelům efektivně prohlížet a spravovat anotace dokumentů.