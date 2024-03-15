---
title: Render s vloženými nebo externími zdroji
linktitle: Render s vloženými nebo externími zdroji
second_title: GroupDocs.Viewer .NET API
description: Vylepšete prohlížení .NET dokumentů pomocí GroupDocs.Viewer pro bezproblémové vykreslování. Postupujte podle našeho výukového programu pro efektivní integraci a vynikající uživatelskou zkušenost.
type: docs
weight: 12
url: /cs/net/rendering-documents-html/render-html-resources/
---
## Úvod

Ve světě vývoje .NET je efektivní prohlížení dokumentů klíčovým aspektem mnoha aplikací. GroupDocs.Viewer for .NET poskytuje výkonné řešení pro vykreslování dokumentů s vloženými nebo externími zdroji. V tomto tutoriálu prozkoumáme, jak využít GroupDocs.Viewer k bezproblémovému vykreslování dokumentů, přičemž každý krok rozebereme pro jasnost a porozumění.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:

1. Základní pochopení vývoje .NET: Je nutná znalost programovacího jazyka C# a frameworku .NET.
2.  Instalace GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z[tady](https://releases.groupdocs.com/viewer/net/).
3. Soubor dokumentu k vykreslení: Připravte vzorový soubor dokumentu (např. DOCX, PDF) pro vykreslení.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory pro náš projekt .NET:

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

Nyní si rozdělme proces vykreslování dokumentu s vloženými nebo externími zdroji do zvládnutelných kroků:

## Krok 1: Definujte výstupní adresář

```csharp
string outputDirectory = "Your Document Directory";
```

Zadejte adresář, kam chcete ukládat vykreslené HTML stránky.

## Krok 2: Definujte formát cesty k souboru stránky

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Nastavte formát cesty k souboru, kam se uloží každá vykreslená stránka.`{0}` je zástupný symbol pro číslo stránky.

## Krok 3: Inicializujte instanci prohlížeče

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // Zde je inicializační kód prohlížeče
}
```

Vytvořte instanci prohlížeče předáním cesty k souboru dokumentu, který má být vykreslen.

## Krok 4: Nakonfigurujte možnosti zobrazení HTML

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

Nakonfigurujte volby zobrazení HTML, určete formát pro vložené prostředky a formát cesty k souboru stránky.

## Krok 5: Vykreslení dokumentu

```csharp
viewer.View(options);
```

 Vyvolat`View` metoda na instanci Viewer, předání nakonfigurovaných voleb zobrazení HTML.

## Krok 6: Zobrazte cestu výstupního adresáře

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

Vytiskněte zprávu o úspěšném vykreslení spolu s cestou k výstupnímu adresáři.

## Závěr

GroupDocs.Viewer for .NET zjednodušuje proces vykreslování dokumentů pomocí vestavěných nebo externích zdrojů a zlepšuje možnosti prohlížení dokumentů v aplikacích .NET. Podle kroků popsaných v tomto kurzu mohou vývojáři bezproblémově integrovat funkce vykreslování dokumentů do svých projektů a poskytovat uživatelům plynulé a efektivní prohlížení dokumentů.

## FAQ

### Otázka: Je GroupDocs.Viewer for .NET kompatibilní s různými formáty dokumentů?

Odpověď: Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně DOCX, PDF, XLSX a dalších.

### Otázka: Mohu přizpůsobit možnosti vykreslování podle svých požadavků?

A: Rozhodně, GroupDocs.Viewer poskytuje rozsáhlé možnosti pro konfiguraci procesu vykreslování tak, aby vyhovoval specifickým potřebám.

### Otázka: Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?

 Odpověď: Ano, můžete využít bezplatnou zkušební verzi[tady](https://releases.groupdocs.com/).

### Otázka: Jak mohu získat podporu nebo pomoc s integrací GroupDocs.Viewer?

 Odpověď: Pomoc můžete vyhledat na fóru komunity GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9).

### Otázka: Jsou k dispozici dočasné licence pro účely testování?

 Odpověď: Ano, dočasné licence lze získat od[tady](https://purchase.groupdocs.com/temporary-license/).