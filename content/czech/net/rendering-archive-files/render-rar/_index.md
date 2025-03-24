---
title: Vykreslit RAR archivy
linktitle: Vykreslit RAR archivy
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat archivy RAR do formátů HTML, JPG, PNG nebo PDF pomocí GroupDocs.Viewer pro .NET. Snadno prohlížejte a sdílejte obsah archivů RAR.
weight: 13
url: /cs/net/rendering-archive-files/render-rar/
---
## Úvod
Archivy RAR jsou oblíbeným formátem pro kompresi a ukládání více souborů a složek do jednoho kontejneru. Vykreslování archivů RAR do různých formátů, jako jsou HTML, JPG, PNG nebo PDF, může být nezbytné pro prohlížení nebo sdílení obsahu těchto archivů. V tomto tutoriálu prozkoumáme, jak vykreslit RAR archivy pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer for .NET: Nainstalujte knihovnu GroupDocs.Viewer pro .NET z[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
2. Ukázkový archiv RAR: Připravte si ukázkový archiv RAR k vykreslení.

## Importovat jmenné prostory
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Krok 1: Definujte výstupní adresář
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
Vykreslování RAR archivů do různých formátů je jednoduché s GroupDocs.Viewer pro .NET. Podle kroků uvedených v tomto tutoriálu můžete bez námahy převést archivy RAR do formátů HTML, JPG, PNG nebo PDF, což umožňuje snadné prohlížení a sdílení jejich obsahu.
## FAQ
### Dokáže GroupDocs.Viewer for .NET zpracovat šifrované archivy RAR?
Ano, GroupDocs.Viewer for .NET podporuje vykreslování šifrovaných archivů RAR za předpokladu, že jsou během procesu vykreslování poskytnuta nezbytná hesla.
### Je možné upravit výstupní vzhled vykreslených dokumentů?
Absolutně! GroupDocs.Viewer for .NET nabízí rozsáhlé možnosti přizpůsobení, které uživatelům umožňují přizpůsobit vzhled vykreslených dokumentů podle jejich preferencí.
### Podporuje GroupDocs.Viewer for .NET vykreslování jiných archivních formátů kromě RAR?
Ano, GroupDocs.Viewer for .NET podporuje vykreslování různých archivních formátů včetně ZIP, TAR, 7z a dalších.
### Mohu integrovat GroupDocs.Viewer for .NET do své webové aplikace?
Rozhodně! GroupDocs.Viewer for .NET poskytuje rozhraní API, která jsou vhodná pro integraci do desktopových i webových aplikací.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, můžete využít bezplatnou zkušební verzi GroupDocs.Viewer for .NET z webu[webová stránka](https://releases.groupdocs.com/).