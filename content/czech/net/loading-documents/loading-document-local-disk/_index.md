---
title: Načíst dokumenty z místního disku
linktitle: Načíst dokumenty z místního disku
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak plynule vykreslovat dokumenty z místního disku pomocí Groupdocs.Viewer for .NET. Vylepšete své aplikace .NET pomocí efektivních dokumentů.
weight: 10
url: /cs/net/loading-documents/loading-document-local-disk/
---

# Načíst dokumenty z místního disku

## Úvod
dnešní digitální době je efektivní vykreslování dokumentů zásadní pro různé aplikace. Groupdocs.Viewer for .NET nabízí výkonné řešení pro vykreslování dokumentů přímo z vašeho lokálního disku. V tomto tutoriálu vás provedeme procesem načítání dokumentů z místního disku pomocí Groupdocs.Viewer for .NET. Ať už jste zkušený vývojář nebo teprve začínáte, tento podrobný průvodce vám pomůže bezproblémově integrovat vykreslování dokumentů do vašich aplikací .NET.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1.  Groupdocs.Viewer pro .NET: Stáhněte a nainstalujte nejnovější verzi z[tady](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí .NET: Ujistěte se, že máte ve svém systému nastaveno funkční vývojové prostředí .NET.
3. Místní dokumenty: Dokumenty, které chcete vykreslit, mějte uložené lokálně na vašem disku.

## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory pro přístup k funkcím Groupdocs.Viewer pro .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Načtěte dokumenty z místního disku
Začněte nastavením výstupního adresáře, kam se budou ukládat vykreslené HTML stránky.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 2: Inicializujte prohlížeč a vykreslujte dokumenty
Inicializujte objekt Viewer s cestou k dokumentu a vykreslete jej pomocí voleb zobrazení HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Zobrazení výstupu
Po dokončení vykreslování zobrazte zprávu o úspěšném vykreslení zdrojového dokumentu a umístění výstupních souborů.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak načítat dokumenty z místního disku pomocí Groupdocs.Viewer for .NET. Tento výkonný nástroj otevírá svět možností pro vykreslování dokumentů ve vašich aplikacích .NET.
## FAQ
### Mohu renderovat dokumenty různých formátů pomocí Groupdocs.Viewer pro .NET?
Ano, Groupdocs.Viewer for .NET podporuje širokou škálu formátů dokumentů včetně DOCX, PDF, XLSX, PPTX a dalších.
### Je Groupdocs.Viewer for .NET kompatibilní se všemi frameworky .NET?
Groupdocs.Viewer for .NET je kompatibilní s většinou .NET frameworků včetně .NET Core, .NET Framework a .NET Standard.
### Mohu přizpůsobit možnosti vykreslování pro své dokumenty?
Absolutně! Groupdocs.Viewer for .NET poskytuje rozsáhlé možnosti přizpůsobení, které vám umožní přizpůsobit proces vykreslování vašim konkrétním požadavkům.
### Je k dispozici zkušební verze pro Groupdocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.groupdocs.com/).
### Kde najdu podporu nebo další zdroje pro Groupdocs.Viewer pro .NET?
 Pro podporu a další zdroje navštivte Groupdocs.Viewer pro .NET[Fórum](https://forum.groupdocs.com/c/viewer/9).