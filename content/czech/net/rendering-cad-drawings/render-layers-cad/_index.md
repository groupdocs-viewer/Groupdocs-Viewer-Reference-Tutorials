---
title: Vykreslování vrstev ve výkresech CAD
linktitle: Vykreslování vrstev ve výkresech CAD
second_title: GroupDocs.Viewer .NET API
description: Bezproblémově vykreslujte výkresy CAD v aplikacích .NET pomocí GroupDocs.Viewer pro .NET. Prozkoumejte možnosti vykreslování, přizpůsobte vrstvy a další.
weight: 13
url: /cs/net/rendering-cad-drawings/render-layers-cad/
---

# Vykreslování vrstev ve výkresech CAD

## Úvod
GroupDocs.Viewer for .NET je výkonný nástroj, který umožňuje vývojářům bezproblémově integrovat funkce vykreslování dokumentů do jejich aplikací .NET. Ať už potřebujete vykreslit výkresy CAD, soubory PDF, dokumenty Microsoft Office nebo další, GroupDocs.Viewer poskytuje komplexní řešení.
## Předpoklady
Než se pustíte do používání GroupDocs.Viewer pro .NET, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka C#.
- Vývojové prostředí .NET nastavené na vašem počítači.
-  GroupDocs.Viewer pro .NET nainstalován. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
-  Přístup k dokumentaci GroupDocs.Viewer for .NET pro referenci, kterou lze nalézt[tady](https://tutorials.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Chcete-li začít používat GroupDocs.Viewer pro .NET, musíte do projektu importovat požadované jmenné prostory. Následuj tyto kroky:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Rozdělme poskytnutý příklad do několika kroků:
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Inicializujte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Blok kódu pokračuje...
}
```
## Krok 4: Nastavte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Definujte vrstvy CAD
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Krok 6: Vykreslení dokumentu
```csharp
viewer.View(options);
```
## Krok 7: Výstup umístění vykresleného dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
S GroupDocs.Viewer pro .NET se vykreslování CAD výkresů ve vašich aplikacích .NET stává bezproblémovým procesem. Podle kroků uvedených v této příručce můžete snadno integrovat funkce vykreslování dokumentů do svých projektů.
## FAQ
### Je GroupDocs.Viewer kompatibilní se všemi typy CAD výkresů?
Ano, GroupDocs.Viewer podporuje vykreslování široké škály výkresových formátů CAD, včetně DWG a DXF.
### Mohu přizpůsobit možnosti vykreslování pro výkresy CAD?
GroupDocs.Viewer rozhodně nabízí různé možnosti přizpůsobení, jako je určení vrstev k vykreslení nebo nastavení výstupních formátů.
### Vyžaduje GroupDocs.Viewer připojení k internetu pro vykreslování dokumentů?
Ne, GroupDocs.Viewer provádí vykreslování lokálně bez nutnosti připojení k internetu.
### Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, máte přístup k bezplatné zkušební verzi GroupDocs.Viewer pro .NET[tady](https://releases.groupdocs.com/).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
 Pro jakoukoli technickou pomoc nebo dotazy můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9).