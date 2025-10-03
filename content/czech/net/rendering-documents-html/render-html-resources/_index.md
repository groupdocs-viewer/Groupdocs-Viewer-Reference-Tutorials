---
"description": "Vylepšete prohlížení dokumentů .NET pomocí GroupDocs.Viewer pro bezproblémové vykreslování. Pro efektivní integraci a vynikající uživatelský komfort se řiďte naším tutoriálem."
"linktitle": "Renderování s vloženými nebo externími zdroji"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Renderování s vloženými nebo externími zdroji"
"url": "/cs/net/rendering-documents-html/render-html-resources/"
"weight": 12
type: docs
---
# Renderování s vloženými nebo externími zdroji

## Zavedení

Ve světě vývoje v .NET je efektivní prohlížení dokumentů klíčovým aspektem mnoha aplikací. GroupDocs.Viewer pro .NET poskytuje výkonné řešení pro vykreslování dokumentů s vloženými nebo externími zdroji. V tomto tutoriálu se podíváme na to, jak využít GroupDocs.Viewer k bezproblémovému vykreslování dokumentů, a pro přehlednost a pochopení si jednotlivé kroky rozebereme podrobněji.

## Předpoklady

Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:

1. Základní znalost vývoje v .NET: Znalost programovacího jazyka C# a frameworku .NET je nezbytná.
2. Instalace GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z [zde](https://releases.groupdocs.com/viewer/net/).
3. Soubor dokumentu k vykreslení: Připravte si vzorový soubor dokumentu (např. DOCX, PDF) k vykreslení.

## Importovat jmenné prostory

Nejprve si importujme potřebné jmenné prostory pro náš .NET projekt:

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

Nyní si rozdělme proces vykreslování dokumentu s vloženými nebo externími zdroji na zvládnutelné kroky:

## Krok 1: Definování výstupního adresáře

```csharp
string outputDirectory = "Your Document Directory";
```

Zadejte adresář, kam chcete uložit vykreslené stránky HTML.

## Krok 2: Definování formátu cesty k souboru stránky

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Nastavte formát cesty k souboru, kam bude uložena každá vykreslená stránka. `{0}` je zástupný symbol pro číslo stránky.

## Krok 3: Inicializace instance prohlížeče

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // Sem se přidává inicializační kód prohlížeče
}
```

Vytvořte instanci prohlížeče předáním cesty k souboru dokumentu, který má být vykreslen.

## Krok 4: Konfigurace možností zobrazení HTML

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

Nakonfigurujte možnosti zobrazení HTML a určete formát pro vložené zdroje a formát cesty k souboru stránky.

## Krok 5: Vykreslení dokumentu

```csharp
viewer.View(options);
```

Vyvolat `View` metoda na instanci prohlížeče, která předá nakonfigurované možnosti zobrazení HTML.

## Krok 6: Zobrazení cesty k výstupnímu adresáři

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

Vytiskněte zprávu o úspěšném vykreslení spolu s cestou k výstupnímu adresáři.

## Závěr

GroupDocs.Viewer pro .NET zjednodušuje proces vykreslování dokumentů s vloženými nebo externími zdroji a vylepšuje možnosti prohlížení dokumentů v aplikacích .NET. Dodržováním kroků popsaných v tomto tutoriálu mohou vývojáři bezproblémově integrovat funkce vykreslování dokumentů do svých projektů a poskytnout uživatelům plynulé a efektivní prohlížení dokumentů.

## Často kladené otázky

### Otázka: Je GroupDocs.Viewer pro .NET kompatibilní s různými formáty dokumentů?

A: Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně DOCX, PDF, XLSX a dalších.

### Otázka: Mohu si přizpůsobit možnosti vykreslování podle svých požadavků?

A: Rozhodně, GroupDocs.Viewer nabízí rozsáhlé možnosti pro konfiguraci procesu vykreslování tak, aby splňoval specifické potřeby.

### Otázka: Je k dispozici bezplatná zkušební verze GroupDocs.Viewer pro .NET?

A: Ano, můžete využít bezplatnou zkušební verzi od [zde](https://releases.groupdocs.com/).

### Otázka: Jak mohu získat podporu nebo pomoc s integrací GroupDocs.Viewer?

A: Pomoc můžete vyhledat na fóru komunity GroupDocs.Viewer. [zde](https://forum.groupdocs.com/c/viewer/9).

### Otázka: Jsou k dispozici dočasné licence pro testovací účely?

A: Ano, dočasné licence lze získat od [zde](https://purchase.groupdocs.com/temporary-license/).