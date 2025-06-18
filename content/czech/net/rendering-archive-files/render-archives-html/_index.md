---
"description": "Naučte se, jak vykreslovat archivy do HTML stránek pomocí GroupDocs.Viewer pro .NET. Snadno integrujte funkce prohlížení dokumentů do svých .NET aplikací."
"linktitle": "Vykreslení archivů na jednu nebo více HTML stránek"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení archivů na jednu nebo více HTML stránek"
"url": "/cs/net/rendering-archive-files/render-archives-html/"
"weight": 12
---

# Vykreslení archivů na jednu nebo více HTML stránek

## Zavedení
GroupDocs.Viewer pro .NET je výkonná knihovna pro vykreslování dokumentů, která vývojářům umožňuje snadno integrovat funkce prohlížení dokumentů do jejich .NET aplikací. Ať už potřebujete vykreslit archivy na jednu nebo více HTML stránek, tento tutoriál vás krok za krokem provede celým procesem.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer pro .NET: Ujistěte se, že máte knihovnu nainstalovanou ve svém projektu. Můžete si ji stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Mějte nastavené funkční vývojové prostředí pro vývoj v .NET.
3. Adresář dokumentů: Připravte si adresář, kde budou vaše dokumenty uloženy.
4. Základní znalost C#: Seznamte se se základy programovacího jazyka C#.

## Importovat jmenné prostory
V kódu C# nezapomeňte importovat potřebné jmenné prostory:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Chcete-li vykreslit archivy na jednu nebo více stránek HTML pomocí nástroje GroupDocs.Viewer pro .NET, postupujte takto:
## Krok 1: Nastavení výstupního adresáře
Definujte adresář, kam chcete ukládat vykreslené HTML stránky:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru
Zadejte formát cesty k souboru pro stránky HTML. Pro vykreslování jedné stránky:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Pro vykreslování více stránek:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Krok 3: Vykreslení do jednostránkového HTML kódu
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Krok 4: Vykreslení na více stránek HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Nastavit položky na stránku
    viewer.View(options);
}
```
## Krok 5: Zkontrolujte výstup
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Vykreslování archivů do HTML stránek pomocí GroupDocs.Viewer pro .NET je jednoduchý proces. Dodržováním kroků popsaných v tomto tutoriálu můžete bezproblémově integrovat funkce prohlížení dokumentů do svých .NET aplikací.
## Často kladené otázky
### Mohu vykreslovat dokumenty i v jiných formátech než archivech?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, DOCX, XLSX, PPTX a dalších.
### Je GroupDocs.Viewer vhodný pro desktopové i webové aplikace?
GroupDocs.Viewer lze bez problémů používat jak v desktopových, tak i webových aplikacích.
### Nabízí GroupDocs.Viewer možnosti přizpůsobení rozhraní prohlížeče?
Ano, rozhraní prohlížeče si můžete přizpůsobit podle svých požadavků.
### Mohu vykreslovat dokumenty asynchronně pomocí GroupDocs.Viewer?
Ano, GroupDocs.Viewer poskytuje asynchronní vykreslování pro lepší výkon.
### Podporuje GroupDocs.Viewer anotace dokumentů?
Ano, GroupDocs.Viewer umožňuje uživatelům efektivně prohlížet a spravovat anotace dokumentů.