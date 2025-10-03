---
"description": "Naučte se, jak převádět archivy RAR do formátů HTML, JPG, PNG nebo PDF pomocí nástroje GroupDocs.Viewer pro .NET. Snadno si prohlížejte a sdílejte obsah archivů RAR."
"linktitle": "Render RAR archivů"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Render RAR archivů"
"url": "/cs/net/rendering-archive-files/render-rar/"
"weight": 13
type: docs
---
# Render RAR archivů

## Zavedení
Archivy RAR jsou oblíbeným formátem pro kompresi a ukládání více souborů a složek do jednoho kontejneru. Vykreslování archivů RAR do různých formátů, jako je HTML, JPG, PNG nebo PDF, může být nezbytné pro prohlížení nebo sdílení obsahu těchto archivů. V tomto tutoriálu se podíváme na to, jak vykreslit archivy RAR pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer pro .NET: Nainstalujte knihovnu GroupDocs.Viewer pro .NET z [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
2. Ukázkový archiv RAR: Mějte připravený ukázkový archiv RAR k vykreslení.

## Importovat jmenné prostory
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Vykreslení do HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Vykreslení do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 4: Vykreslení do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 5: Vykreslení do PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Závěr
Renderování archivů RAR do různých formátů je díky GroupDocs.Viewer pro .NET snadné. Dodržováním kroků popsaných v tomto tutoriálu můžete bez námahy převést archivy RAR do formátů HTML, JPG, PNG nebo PDF, což umožní snadné prohlížení a sdílení jejich obsahu.
## Často kladené otázky
### Může GroupDocs.Viewer pro .NET zpracovat šifrované RAR archivy?
Ano, GroupDocs.Viewer pro .NET podporuje vykreslování šifrovaných archivů RAR za předpokladu, že jsou během procesu vykreslování zadána potřebná hesla.
### Je možné přizpůsobit vzhled výstupu vykreslených dokumentů?
Rozhodně! GroupDocs.Viewer pro .NET nabízí rozsáhlé možnosti přizpůsobení, které uživatelům umožňují přizpůsobit vzhled vykreslených dokumentů podle jejich požadavků.
### Podporuje GroupDocs.Viewer pro .NET vykreslování i jiných archivních formátů kromě RAR?
Ano, GroupDocs.Viewer pro .NET podporuje vykreslování různých archivních formátů včetně ZIP, TAR, 7z a dalších.
### Mohu integrovat GroupDocs.Viewer pro .NET do své webové aplikace?
Jistě! GroupDocs.Viewer pro .NET poskytuje API, která jsou vhodná pro integraci do desktopových i webových aplikací.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete využít bezplatnou zkušební verzi GroupDocs.Viewer pro .NET z [webové stránky](https://releases.groupdocs.com/).