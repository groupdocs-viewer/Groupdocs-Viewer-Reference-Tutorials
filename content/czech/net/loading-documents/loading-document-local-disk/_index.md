---
"description": "Naučte se, jak bezproblémově vykreslovat dokumenty z lokálního disku pomocí Groupdocs.Viewer pro .NET. Vylepšete své .NET aplikace efektivním zpracováním dokumentů."
"linktitle": "Načítání dokumentů z lokálního disku"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Načítání dokumentů z lokálního disku"
"url": "/cs/net/loading-documents/loading-document-local-disk/"
"weight": 10
---

# Načítání dokumentů z lokálního disku

## Zavedení
V dnešní digitální době je efektivní vykreslování dokumentů nezbytné pro různé aplikace. Groupdocs.Viewer pro .NET nabízí výkonné řešení pro vykreslování dokumentů přímo z vašeho lokálního disku. V tomto tutoriálu vás provedeme procesem načítání dokumentů z vašeho lokálního disku pomocí Groupdocs.Viewer pro .NET. Ať už jste zkušený vývojář, nebo teprve začínáte, tento podrobný návod vám pomůže bezproblémově integrovat vykreslování dokumentů do vašich .NET aplikací.

![Načítání dokumentů z lokálního disku pomocí GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-local-disk.png)

## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:
1. Groupdocs.Viewer pro .NET: Stáhněte a nainstalujte nejnovější verzi z [zde](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí .NET: Ujistěte se, že máte v systému nainstalované funkční vývojové prostředí .NET.
3. Lokální dokumenty: Dokumenty, které chcete vykreslit, můžete mít uložené lokálně na disku.

## Importovat jmenné prostory
Nejprve si importujme potřebné jmenné prostory pro přístup k funkcím Groupdocs.Viewer pro .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Načtení dokumentů z lokálního disku
Začněte nastavením výstupního adresáře, kam budou uloženy vykreslené HTML stránky.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 2: Inicializace prohlížeče a vykreslení dokumentů
Inicializujte objekt Viewer cestou k dokumentu a vykreslete jej pomocí voleb zobrazení HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Zobrazení výstupu
Po dokončení vykreslování se zobrazí zpráva oznamující úspěšné vykreslení zdrojového dokumentu a umístění výstupních souborů.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak načítat dokumenty z lokálního disku pomocí nástroje Groupdocs.Viewer pro .NET. Tento výkonný nástroj otevírá svět možností pro vykreslování dokumentů ve vašich .NET aplikacích.
## Často kladené otázky
### Mohu pomocí Groupdocs.Viewer pro .NET vykreslovat dokumenty různých formátů?
Ano, Groupdocs.Viewer pro .NET podporuje širokou škálu formátů dokumentů, včetně DOCX, PDF, XLSX, PPTX a dalších.
### Je Groupdocs.Viewer pro .NET kompatibilní se všemi .NET frameworky?
Groupdocs.Viewer pro .NET je kompatibilní s většinou frameworků .NET, včetně .NET Core, .NET Framework a .NET Standard.
### Mohu si přizpůsobit možnosti vykreslování pro své dokumenty?
Rozhodně! Groupdocs.Viewer pro .NET nabízí rozsáhlé možnosti přizpůsobení, které vám umožňují přizpůsobit proces vykreslování vašim specifickým požadavkům.
### Je k dispozici zkušební verze pro Groupdocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.groupdocs.com/).
### Kde najdu podporu nebo další zdroje pro Groupdocs.Viewer pro .NET?
Pro podporu a další zdroje navštivte Groupdocs.Viewer pro .NET. [forum](https://forum.groupdocs.com/c/viewer/9).