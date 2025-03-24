---
title: Vykreslit záhlaví řádků a sloupců
linktitle: Vykreslit záhlaví řádků a sloupců
second_title: GroupDocs.Viewer .NET API
description: Vylepšete prohlížení dokumentů v .NET! Naučte se vykreslovat záhlaví řádků a sloupců pomocí GroupDocs.Viewer pro .NET. Prozkoumejte výstupy HTML, JPG, PNG a PDF.
weight: 18
url: /cs/net/spreadsheet-rendering-options/render-row-column-headings/
---

# Vykreslit záhlaví řádků a sloupců

## Úvod
Chcete vylepšit své možnosti prohlížení dokumentů v aplikacích .NET? S GroupDocs.Viewer for .NET můžete bez problémů vykreslovat záhlaví řádků a sloupců ze souborů tabulkového procesoru. V tomto tutoriálu vás provedeme procesem vykreslování záhlaví řádků a sloupců pomocí různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Nainstalovaná knihovna GroupDocs.Viewer pro .NET.
- Ukázkový soubor XLSX pro testovací účely.
- Pracovní znalost vývoje C# a .NET.
## Importovat jmenné prostory
Ujistěte se, že ve svém kódu C# importujete potřebné jmenné prostory pro použití GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Nastavte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. Vykreslení do HTML
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. Vykreslení do formátu JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. Vykreslení do formátu PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. Vykreslení do PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## Závěr
Gratulujeme! Úspěšně jste vykreslili záhlaví řádků a sloupců z tabulky pomocí GroupDocs.Viewer pro .NET. Experimentujte s různými výstupními formáty, aby vyhovovaly potřebám vaší aplikace.
## Často kladené otázky
### Otázka: Mohu přizpůsobit výstupní adresář pro vykreslené dokumenty?
 Odpověď: Ano, můžete nastavit požadovaný výstupní adresář v kódu, kde je`outputDirectory` proměnná je definována.
### Otázka: Je GroupDocs.Viewer kompatibilní s jinými formáty tabulek?
Odpověď: Ano, GroupDocs.Viewer podporuje různé formáty tabulek, včetně XLS, XLSX, CSV a dalších.
### Otázka: Jak mohu zpracovat výjimky během procesu vykreslování?
Odpověď: Můžete implementovat bloky try-catch pro zpracování výjimek a protokolování nebo zobrazování příslušných zpráv uživateli.
### Otázka: Existují nějaké licenční požadavky pro používání GroupDocs.Viewer v mé aplikaci?
Odpověď: Ano, potřebujete platnou licenci. Můžete získat dočasnou licenci pro testovací účely nebo zakoupit plnou licenci pro produkci.
### Otázka: Kde najdu další podporu nebo komunitní diskuse?
 A: Navštivte[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za podporu a diskuze.