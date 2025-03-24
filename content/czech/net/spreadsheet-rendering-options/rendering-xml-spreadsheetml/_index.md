---
title: Vykreslování XML SpreadSheetML
linktitle: Vykreslování XML SpreadSheetML
second_title: GroupDocs.Viewer .NET API
description: Prozkoumejte bezproblémové vykreslování souborů XML SpreadSheetML v různých formátech pomocí GroupDocs.Viewer pro .NET. Snadná integrace do vašich aplikací.
weight: 16
url: /cs/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## Úvod
Vítejte ve světě GroupDocs.Viewer pro .NET! V tomto tutoriálu vás provedeme jednoduchým vykreslováním souborů XML SpreadSheetML pomocí GroupDocs.Viewer, výkonné knihovny .NET. Ať už jste zkušený vývojář nebo teprve začínáte, tento podrobný průvodce vám pomůže bez námahy integrovat vykreslování XML SpreadSheetML do vašich aplikací.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte nastaveny následující předpoklady:
- Vývojové prostředí s podporou .NET.
-  Nainstalovaná knihovna GroupDocs.Viewer for .NET. Můžete si jej stáhnout[tady](https://releases.groupdocs.com/viewer/net/).
- Základní znalost programování v C#.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu C#. To zajistí, že budete mít přístup k funkcím, které poskytuje GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Nastavte adresář dokumentů
Definujte cestu k adresáři dokumentů, kam se výstup uloží.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zadejte cesty k výstupním souborům
Nastavte úplné cesty pro výstupní soubory HTML, JPG, PNG a PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Krok 3: Zadejte možnosti načtení
Explicitně zadejte typ souboru jako Excel 2003 XML SpreadSheetML, aby byl přesně vykreslen.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Krok 4: Vykreslení do vícestránkového HTML
Využijte možnosti zobrazení HTML k vykreslení souboru XML SpreadSheetML do vícestránkového dokumentu HTML.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 5: Vykreslení do JPG
Vykreslete soubor XML SpreadSheetML do obrázku JPG pomocí zadaných možností.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 6: Vykreslení do PNG
Podobně vykreslete soubor do obrázku PNG se zadanými možnostmi.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 7: Vykreslení do PDF
Nakonec vykreslete soubor XML SpreadSheetML do dokumentu PDF pomocí zadaných možností.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Závěr
Gratulujeme! Úspěšně jste se naučili vykreslovat soubory XML SpreadSheetML pomocí GroupDocs.Viewer pro .NET. Vylepšete své možnosti prohlížení dokumentů prozkoumáním dalších funkcí a možností, které tato všestranná knihovna poskytuje.
## Nejčastější dotazy
### Je GroupDocs.Viewer kompatibilní s jinými formáty souborů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Wordu, Excelu a dalších.
### Mohu upravit vzhled vykreslených dokumentů?
Absolutně! GroupDocs.Viewer nabízí různé možnosti přizpůsobení, které vám umožní přizpůsobit výstup vašim konkrétním potřebám.
### Kde najdu další podporu a zdroje?
 Navštivte[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za podporu komunity a prozkoumejte[dokumentace](https://tutorials.groupdocs.com/viewer/net/)pro podrobné informace.
### Je k dispozici bezplatná zkušební verze?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.groupdocs.com/).
### Jak získám dočasnou licenci?
 Můžete získat dočasnou licenci[tady](https://purchase.groupdocs.com/temporary-license/).