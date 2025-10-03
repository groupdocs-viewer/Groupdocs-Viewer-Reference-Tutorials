---
"description": "Vylepšete si prohlížení dokumentů v .NET! Naučte se vykreslovat záhlaví řádků a sloupců pomocí GroupDocs.Viewer pro .NET. Prozkoumejte výstupy HTML, JPG, PNG a PDF."
"linktitle": "Vykreslení záhlaví řádků a sloupců"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení záhlaví řádků a sloupců"
"url": "/cs/net/spreadsheet-rendering-options/render-row-column-headings/"
"weight": 18
type: docs
---
# Vykreslení záhlaví řádků a sloupců

## Zavedení
Chcete vylepšit zážitek z prohlížení dokumentů v aplikacích .NET? S nástrojem GroupDocs.Viewer pro .NET můžete bez problémů vykreslovat záhlaví řádků a sloupců z tabulek. V tomto tutoriálu vás provedeme procesem vykreslování záhlaví řádků a sloupců pomocí různých výstupních formátů, jako jsou HTML, JPG, PNG a PDF.
## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Nainstalována knihovna GroupDocs.Viewer pro .NET.
- Ukázkový soubor XLSX pro testovací účely.
- Praktická znalost vývoje v C# a .NET.
## Importovat jmenné prostory
kódu C# nezapomeňte importovat potřebné jmenné prostory pro použití GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Nastavení výstupního adresáře
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
## 3. Vykreslení do JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. Vykreslení do PNG
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
Gratulujeme! Úspěšně jste vykreslili záhlaví řádků a sloupců z tabulky pomocí nástroje GroupDocs.Viewer pro .NET. Experimentujte s různými výstupními formáty, které vyhovují potřebám vaší aplikace.
## Často kladené otázky
### Otázka: Mohu si přizpůsobit výstupní adresář pro vykreslené dokumenty?
A: Ano, požadovaný výstupní adresář můžete nastavit v kódu, kde `outputDirectory` proměnná je definována.
### Otázka: Je GroupDocs.Viewer kompatibilní s jinými formáty tabulek?
A: Ano, GroupDocs.Viewer podporuje různé formáty tabulek, včetně XLS, XLSX, CSV a dalších.
### Otázka: Jak mohu během procesu vykreslování ošetřit výjimky?
A: Můžete implementovat bloky try-catch pro zpracování výjimek a zaznamenávání nebo zobrazování příslušných zpráv uživateli.
### Otázka: Existují nějaké licenční požadavky pro používání GroupDocs.Viewer v mé aplikaci?
A: Ano, potřebujete platnou licenci. Můžete si pořídit dočasnou licenci pro testovací účely nebo si zakoupit plnou licenci pro produkční prostředí.
### Otázka: Kde najdu další podporu nebo diskuze v komunitě?
A: Navštivte [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za podporu a diskuze.