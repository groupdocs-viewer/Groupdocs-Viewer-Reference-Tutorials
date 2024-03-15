---
title: Vyloučit písma z vykresleného HTML
linktitle: Vyloučit písma z vykresleného HTML
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak vyloučit písma z vykreslovaného HTML pomocí GroupDocs.Viewer for .NET. Postupujte podle tohoto podrobného průvodce pro bezproblémové zobrazení dokumentů.
type: docs
weight: 10
url: /cs/net/rendering-documents-html/exclude-fonts-html/
---
## Úvod
GroupDocs.Viewer for .NET je výkonná knihovna pro vykreslování dokumentů, která umožňuje vývojářům zobrazovat více než 50 formátů dokumentů v jejich aplikacích .NET bez nutnosti externích závislostí. V tomto tutoriálu se zaměříme na specifickou funkci GroupDocs.Viewer: vyloučení písem z vykresleného výstupu HTML. 
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Základní znalost vývoje C# a .NET.
2.  GroupDocs.Viewer pro .NET nainstalován. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio nebo jakékoli jiné IDE pro vývoj v C#.

## Importovat jmenné prostory
V kódu C# nezapomeňte zahrnout potřebné jmenné prostory:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Definujte výstupní adresář
Nastavte adresář, kam chcete ukládat vykreslené soubory HTML.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
Zadejte formát cest k souborům jednotlivých stránek vykreslovaného dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Inicializujte objekt prohlížeče
Vytvořte instanci objektu Viewer s dokumentem, který chcete vykreslit.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Váš kód je zde
}
```
## Krok 4: Nastavte možnosti zobrazení HTML
Definujte možnosti pro vykreslování HTML, včetně formátu vložených prostředků a písem, která se mají vyloučit.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Krok 5: Vykreslení dokumentu
Chcete-li dokument vykreslit, předejte možnosti zobrazení HTML objektu Viewer.
```csharp
viewer.View(options);
```
## Krok 6: Výstup umístění vykresleného dokumentu
Informujte uživatele o umístění, kde jsou uloženy vykreslené soubory HTML.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak používat GroupDocs.Viewer pro .NET k vyloučení písem z vykresleného výstupu HTML. Podle výše uvedených kroků můžete přizpůsobit proces vykreslování tak, aby vyhovoval vašim konkrétním požadavkům, a zajistit tak optimální zobrazení dokumentů ve vašich aplikacích.
## FAQ
### Mohu z vykresleného HTML vyloučit více písem?
 Ano, do souboru můžete přidat více názvů písem`FontsToExclude` seznam v možnostech zobrazení HTML.
### Je GroupDocs.Viewer kompatibilní se všemi .NET frameworky?
Ano, GroupDocs.Viewer podporuje rozhraní .NET Framework 4.6.1 a vyšší.
### Mohu renderovat dokumenty ze vzdálených úložišť?
Ano, GroupDocs.Viewer podporuje vykreslování dokumentů z místního úložiště i ze vzdálených úložišť a streamů.
### Podporuje GroupDocs.Viewer responzivní design pro výstup HTML?
Ano, můžete povolit responzivní vykreslování odpovídající úpravou možností zobrazení HTML.
### Je pro GroupDocs.Viewer k dispozici technická podpora?
 Ano, můžete vyhledat pomoc a účastnit se diskusí na[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).