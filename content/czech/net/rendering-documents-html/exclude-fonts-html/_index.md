---
"description": "Naučte se, jak vyloučit písma z vykresleného HTML pomocí GroupDocs.Viewer pro .NET. Pro bezproblémové zobrazení dokumentů postupujte podle tohoto podrobného návodu."
"linktitle": "Vyloučení fontů z vykresleného HTML"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vyloučení fontů z vykresleného HTML"
"url": "/cs/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# Vyloučení fontů z vykresleného HTML

## Zavedení
GroupDocs.Viewer pro .NET je výkonná knihovna pro vykreslování dokumentů, která vývojářům umožňuje zobrazovat v jejich .NET aplikacích více než 50 formátů dokumentů bez nutnosti externích závislostí. V tomto tutoriálu se zaměříme na specifickou funkci GroupDocs.Viewer: vyloučení písem z vykresleného HTML výstupu. 
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Základní znalost vývoje v C# a .NET.
2. Nainstalován je GroupDocs.Viewer pro .NET. Můžete si ho stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio nebo jakékoli jiné IDE pro vývoj v C#.

## Importovat jmenné prostory
Ve vašem kódu C# nezapomeňte zahrnout potřebné jmenné prostory:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Definování výstupního adresáře
Nastavte adresář, kam chcete ukládat vykreslené soubory HTML.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru stránky
Zadejte formát cest k souborům jednotlivých stránek vykresleného dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Inicializace objektu prohlížeče
Vytvořte instanci objektu Viewer s dokumentem, který chcete vykreslit.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Váš kód patří sem
}
```
## Krok 4: Nastavení možností zobrazení HTML
Definujte možnosti pro vykreslování HTML, včetně formátu vložených zdrojů a písem, které chcete vyloučit.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Krok 5: Vykreslení dokumentu
Předejte objekt Viewer možnosti zobrazení HTML pro vykreslení dokumentu.
```csharp
viewer.View(options);
```
## Krok 6: Výstup umístění vykresleného dokumentu
Informujte uživatele o umístění, kam jsou uloženy vykreslené soubory HTML.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak pomocí nástroje GroupDocs.Viewer pro .NET vyloučit fonty z vykresleného HTML výstupu. Dodržením výše uvedených kroků si můžete proces vykreslování přizpůsobit svým specifickým požadavkům a zajistit tak optimální zobrazení dokumentů ve vašich aplikacích.
## Často kladené otázky
### Mohu z vykresleného HTML kódu vyloučit více fontů?
Ano, můžete přidat více názvů písem `FontsToExclude` seznam v možnostech zobrazení HTML.
### Je GroupDocs.Viewer kompatibilní se všemi .NET frameworky?
Ano, GroupDocs.Viewer podporuje .NET Framework 4.6.1 a vyšší.
### Mohu vykreslovat dokumenty ze vzdálených úložišť?
Ano, GroupDocs.Viewer podporuje vykreslování dokumentů z lokálního úložiště i ze vzdálených úložišť a streamů.
### Podporuje GroupDocs.Viewer responzivní design pro HTML výstup?
Ano, responzivní vykreslování můžete povolit úpravou možností zobrazení HTML.
### Je k dispozici technická podpora pro GroupDocs.Viewer?
Ano, můžete vyhledat pomoc a účastnit se diskusí na [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).