---
"description": "Prozkoumejte bezproblémové vykreslování souborů XML SpreadSheetML v různých formátech pomocí GroupDocs.Viewer pro .NET. Snadno se integrujte do svých aplikací."
"linktitle": "Vykreslování XML SpreadSheetML"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslování XML SpreadSheetML"
"url": "/cs/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
---

# Vykreslování XML SpreadSheetML

## Zavedení
Vítejte ve světě GroupDocs.Viewer pro .NET! V tomto tutoriálu vás provedeme snadným vykreslováním souborů XML SpreadSheetML pomocí GroupDocs.Viewer, výkonné knihovny pro .NET. Ať už jste zkušený vývojář, nebo teprve začínáte, tento podrobný návod vám pomůže bez námahy integrovat vykreslování XML SpreadSheetML do vašich aplikací.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Vývojové prostředí s podporou .NET.
- Knihovna GroupDocs.Viewer pro .NET je nainstalována. Můžete si ji stáhnout. [zde](https://releases.groupdocs.com/viewer/net/).
- Základní znalost programování v C#.
## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů do vašeho projektu v C#. Tím zajistíte přístup k funkcím poskytovaným nástrojem GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Nastavení adresáře dokumentů
Definujte cestu k adresáři s dokumenty, kam bude výstup uložen.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zadejte cesty k výstupním souborům
Nastavte úplné cesty pro výstupní soubory HTML, JPG, PNG a PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Krok 3: Zadejte možnosti načtení
Pro přesné vykreslení explicitně zadejte typ souboru jako Excel 2003 XML SpreadSheetML.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Krok 4: Vykreslení do vícestránkového HTML
Pomocí možností zobrazení HTML vykreslete soubor XML SpreadSheetML do vícestránkového dokumentu HTML.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 5: Vykreslení do JPG
Vykreslete soubor XML SpreadSheetML do obrázku JPG s použitím zadaných možností.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 6: Vykreslení do PNG
Podobně vykreslete soubor do PNG obrázku se zadanými možnostmi.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 7: Vykreslení do PDF
Nakonec vykreslete soubor XML SpreadSheetML do dokumentu PDF s použitím zadaných možností.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vykreslovat soubory XML SpreadSheetML pomocí GroupDocs.Viewer pro .NET. Vylepšete si možnosti prohlížení dokumentů prozkoumáním dalších funkcí a možností, které tato všestranná knihovna nabízí.
## Často kladené otázky
### Je GroupDocs.Viewer kompatibilní s jinými formáty souborů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Wordu, Excelu a dalších.
### Mohu si přizpůsobit vzhled vykreslených dokumentů?
Rozhodně! GroupDocs.Viewer nabízí různé možnosti přizpůsobení, které vám umožňují přizpůsobit výstup vašim specifickým potřebám.
### Kde mohu najít další podporu a zdroje?
Navštivte [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) pro podporu komunity a prozkoumat [dokumentace](https://tutorials.groupdocs.com/viewer/net/) pro podrobné informace.
### Je k dispozici bezplatná zkušební verze?
Ano, máte přístup k bezplatné zkušební verzi [zde](https://releases.groupdocs.com/).
### Jak získám dočasnou licenci?
Můžete získat dočasnou licenci [zde](https://purchase.groupdocs.com/temporary-license/).