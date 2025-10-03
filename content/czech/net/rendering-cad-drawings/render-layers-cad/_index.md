---
"description": "Vytvářejte bezproblémové CAD výkresy v .NET aplikacích s GroupDocs.Viewer pro .NET. Prozkoumejte možnosti vykreslování, upravte vrstvy a proveďte další."
"linktitle": "Renderování vrstev ve výkresech CAD"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Renderování vrstev ve výkresech CAD"
"url": "/cs/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
type: docs
---
# Renderování vrstev ve výkresech CAD

## Zavedení
GroupDocs.Viewer pro .NET je výkonný nástroj, který umožňuje vývojářům bezproblémově integrovat funkce vykreslování dokumentů do jejich .NET aplikací. Ať už potřebujete vykreslovat CAD výkresy, PDF, dokumenty Microsoft Office nebo další, GroupDocs.Viewer poskytuje komplexní řešení.
## Předpoklady
Než se pustíte do používání GroupDocs.Viewer pro .NET, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka C#.
- Vývojové prostředí .NET nastavené na vašem počítači.
- Nainstalován je GroupDocs.Viewer pro .NET. Můžete si ho stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
- Přístup k dokumentaci k nástroji GroupDocs.Viewer pro .NET s tutoriály, kterou lze nalézt [zde](https://tutorials.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Chcete-li začít používat GroupDocs.Viewer pro .NET, je třeba importovat požadované jmenné prostory do projektu. Postupujte takto:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Rozdělme si uvedený příklad do několika kroků:
## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Inicializace objektu prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Blok kódu pokračuje...
}
```
## Krok 4: Nastavení možností zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Definování vrstev CAD
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
## Krok 7: Umístění výstupního vykresleného dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
S GroupDocs.Viewer pro .NET se vykreslování CAD výkresů ve vašich .NET aplikacích stává bezproblémovým procesem. Dodržováním kroků uvedených v této příručce můžete snadno integrovat funkce vykreslování dokumentů do svých projektů.
## Často kladené otázky
### Je GroupDocs.Viewer kompatibilní se všemi typy CAD výkresů?
Ano, GroupDocs.Viewer podporuje vykreslování široké škály formátů CAD výkresů, včetně DWG a DXF.
### Mohu si přizpůsobit možnosti vykreslování pro výkresy CAD?
GroupDocs.Viewer samozřejmě nabízí různé možnosti přizpůsobení, jako je například určení vrstev k vykreslení nebo nastavení výstupních formátů.
### Vyžaduje GroupDocs.Viewer pro vykreslování dokumentů připojení k internetu?
Ne, GroupDocs.Viewer provádí vykreslování lokálně bez nutnosti připojení k internetu.
### Je k dispozici bezplatná zkušební verze GroupDocs.Viewer pro .NET?
Ano, máte přístup k bezplatné zkušební verzi GroupDocs.Viewer pro .NET. [zde](https://releases.groupdocs.com/).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
Pro jakoukoli technickou pomoc nebo dotazy můžete navštívit fórum GroupDocs.Viewer. [zde](https://forum.groupdocs.com/c/viewer/9).