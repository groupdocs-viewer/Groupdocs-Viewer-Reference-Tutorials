---
title: Vykreslit dokument s poznámkami
linktitle: Vykreslit dokument s poznámkami
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat dokumenty s poznámkami pomocí GroupDocs.Viewer pro .NET. Výukový program krok za krokem pro bezproblémovou integraci do vašich aplikací .NET.
weight: 14
url: /cs/net/rendering-options/render-document-notes/
---

# Vykreslit dokument s poznámkami

## Úvod
oblasti manipulace a prohlížení dokumentů představuje GroupDocs.Viewer for .NET robustní řešení, které nabízí bezproblémovou integraci a výkonné funkce. Tento výukový program vás provede procesem vykreslování dokumentů s poznámkami pomocí GroupDocs.Viewer pro .NET. Ať už jste zkušený vývojář nebo se jen ponoříte do světa .NET, tento podrobný průvodce vám pomůže snadno se orientovat ve složitosti vykreslování dokumentů.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
### 1. Instalace GroupDocs.Viewer pro .NET
 V první řadě je potřeba mít ve vývojovém prostředí nainstalovaný GroupDocs.Viewer for .NET. Potřebné soubory si můžete stáhnout z poskytnutého[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/) a postupujte podle pokynů k instalaci.
### 2. Základní znalost .NET Framework
Základní porozumění frameworku .NET je nezbytné pro pochopení konceptů a implementaci kroků uvedených v tomto kurzu. Pokud s .NET teprve začínáte, zvažte seznámení se s jeho základy prostřednictvím online zdrojů nebo výukových programů.
### 3. Znalost programovacího jazyka C#
Protože GroupDocs.Viewer for .NET funguje v prostředí C#, je znalost programovacího jazyka C# zásadní. Ujistěte se, že máte pracovní znalosti syntaxe C#, datových typů a principů objektově orientovaného programování.
### 4. Soubory dokumentů s poznámkami
Ujistěte se, že máte soubory dokumentů obsahující poznámky, které chcete vykreslit pomocí GroupDocs.Viewer for .NET. Podporované formáty zahrnují, ale nejsou omezeny na PDF, DOCX, PPTX atd.

## Importovat jmenné prostory
Nyní, když máte připravené předpoklady, pojďme pokračovat v importu potřebných jmenných prostorů, aby se nastartoval proces vykreslování dokumentu.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
Jmenný prostor System.IO poskytuje třídy pro čtení a zápis do souborů a proudů, které budou využity pro správu cest k souborům během procesu vykreslování.

Nyní si rozeberme proces vykreslování dokumentů s poznámkami do série pokynů krok za krokem.
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Určete adresář, kam chcete uložit soubory vykreslených dokumentů. Ujistěte se, že máte příslušná oprávnění k zápisu do tohoto adresáře.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definujte formát cesty k souboru pro jednotlivé stránky vykreslovaného dokumentu. Tento formát určí, jak budou stránky pojmenovány a uspořádány ve výstupním adresáři.
## Krok 3: Inicializujte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.PPTX_WITH_NOTES))
```
 Inicializujte objekt Viewer poskytnutím cesty k souboru dokumentu s poznámkami. Nahradit`TestFiles.PPTX_WITH_NOTES` se skutečnou cestou k souboru vašeho dokumentu.
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderNotes = true;
```
 Nakonfigurujte možnosti zobrazení HTML pro vykreslení dokumentu. Povolte vykreslování poznámek nastavením`RenderNotes` majetek do`true`.
## Krok 5: Vykreslení dokumentu
```csharp
viewer.View(options);
```
 Vyvolat`View` metoda objektu Viewer, předá nakonfigurované možnosti zobrazení HTML. Tím zahájíte proces vykreslování dokumentu s poznámkami.
## Krok 6: Zobrazte výstupní adresář
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Zobrazte zprávu o úspěšném vykreslení a uveďte cestu k výstupnímu adresáři, kde jsou umístěny soubory vykreslených dokumentů.

## Závěr
Závěrem lze říci, že vykreslování dokumentů s poznámkami pomocí GroupDocs.Viewer for .NET je přímočarý proces, který lze provést pomocí několika řádků kódu. Dodržováním kroků uvedených v tomto kurzu a využitím výkonných funkcí GroupDocs.Viewer můžete bezproblémově integrovat možnosti prohlížení dokumentů do vašich aplikací .NET.
## FAQ
### Je GroupDocs.Viewer for .NET kompatibilní se všemi formáty dokumentů?
GroupDocs.Viewer for .NET podporuje širokou škálu formátů dokumentů, včetně PDF, DOCX, PPTX, XLSX a dalších. Úplný seznam podporovaných formátů naleznete v dokumentaci.
### Mohu přizpůsobit možnosti vykreslování tak, aby vyhovovaly konkrétním požadavkům?
Ano, GroupDocs.Viewer for .NET poskytuje rozsáhlé možnosti přizpůsobení pro vykreslování dokumentů, což vám umožní přizpůsobit výstup podle vašich potřeb.
### Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, můžete využít bezplatnou zkušební verzi GroupDocs.Viewer pro .NET z poskytnutého[odkaz](https://releases.groupdocs.com/).
### Kde najdu technickou podporu nebo pomoc pro GroupDocs.Viewer pro .NET?
 Pro technickou podporu a pomoc můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9).
### Mohu získat dočasnou licenci pro GroupDocs.Viewer for .NET?
 Ano, dočasnou licenci pro GroupDocs.Viewer for .NET můžete získat z poskytnutého[odkaz](https://purchase.groupdocs.com/temporary-license/).