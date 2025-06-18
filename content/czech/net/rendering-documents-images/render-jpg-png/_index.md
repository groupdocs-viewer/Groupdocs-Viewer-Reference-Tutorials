---
"description": "Zjistěte, jak bezproblémově vykreslovat dokumenty do formátu JPG/PNG v prostředí .NET pomocí nástroje GroupDocs.Viewer pro lepší uživatelský komfort a produktivitu."
"linktitle": "Vykreslení dokumentu do formátu JPGPNG"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení dokumentu do formátu JPGPNG"
"url": "/cs/net/rendering-documents-images/render-jpg-png/"
"weight": 10
---

# Vykreslení dokumentu do formátu JPGPNG

## Zavedení

Ve světě vývoje v .NET je efektivní práce s dokumenty nezbytná pro různé aplikace. Ať už vytváříte systém pro správu dokumentů, platformu pro elektronické obchodování nebo aplikaci bohatou na obsah, schopnost bezproblémového prohlížení dokumentů je klíčová. A právě zde přichází na řadu GroupDocs.Viewer pro .NET, který nabízí komplexní řešení pro vykreslování dokumentů do různých formátů, jako jsou JPG a PNG.

## Předpoklady

Než se pustíte do používání GroupDocs.Viewer pro .NET, je třeba splnit několik předpokladů:

1. Vývojové prostředí .NET: Ujistěte se, že máte na svém počítači nainstalované funkční vývojové prostředí .NET. To zahrnuje i instalaci sady .NET SDK.

2. Licence pro GroupDocs.Viewer: Získejte platnou licenci pro GroupDocs.Viewer. Licenci si můžete buď zakoupit, nebo použít dočasnou licenci pro účely zkušebního používání.

3. Instalace: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z dodaného [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).

4. Soubory dokumentů: Mějte připravené soubory dokumentů, které chcete vykreslit. GroupDocs.Viewer podporuje různé formáty včetně DOCX, PDF, PPT a dalších.

## Importovat jmenné prostory

Abyste mohli začít s vykreslováním dokumentů pomocí GroupDocs.Viewer pro .NET, je třeba do projektu importovat potřebné jmenné prostory. To vám umožní přístup k funkcím poskytovaným knihovnou.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Vykreslení dokumentu do formátu JPG nebo PNG je s GroupDocs.Viewer pro .NET jednoduchý proces. Níže je uveden podrobný návod, který vám s tím pomůže:

## Krok 1: Definování výstupního adresáře

Nejprve definujte adresář, kam chcete ukládat vykreslené stránky. Tento adresář by měl existovat a měl by být přístupný aplikaci.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Definování formátu cesty k souboru stránky

Zadejte formát cest k souborům každé vykreslené stránky. GroupDocs.Viewer nahradí `{0}` s číslem stránky při ukládání souborů.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Krok 3: Vytvoření instance objektu Viewer

Vytvořte instanci `Viewer` třídu zadáním cesty k souboru dokumentu, který chcete vykreslit.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Kód pro vykreslování se nachází zde
}
```

## Krok 4: Definování možností vykreslování

Zadejte možnosti vykreslování podle vašich požadavků. Pro vykreslování JPG/PNG použijete `JpgViewOptions` nebo `PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Krok 5: Vykreslení dokumentu

Vyvolat `View` metoda `Viewer` objekt a předat dříve vytvořené možnosti vykreslování.

```csharp
viewer.View(options);
```

## Krok 6: Výstup výsledků

Jakmile je proces vykreslování dokončen, můžete uživatele informovat o úspěšném vykreslování a poskytnout mu adresář, kam jsou vykreslené stránky uloženy.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Závěrem lze říci, že GroupDocs.Viewer pro .NET nabízí výkonné řešení pro vykreslování dokumentů do různých formátů, včetně JPG a PNG. Dodržováním kroků popsaných v tomto tutoriálu můžete bezproblémově integrovat funkce vykreslování dokumentů do svých .NET aplikací, a tím zlepšit uživatelský komfort a produktivitu.

## Často kladené otázky

### Otázka: Mohu pomocí GroupDocs.Viewer pro .NET vykreslovat dokumenty jiné než DOCX?

A: Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, PPT, XLS a dalších.

### Otázka: Je k dispozici bezplatná zkušební verze GroupDocs.Viewer pro .NET?

A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.groupdocs.com/).

### Otázka: Jak mohu získat dočasnou licenci pro účely hodnocení?

A: O dočasnou licenci můžete požádat od [zde](https://purchase.groupdocs.com/temporary-license/).

### Otázka: Kde najdu dokumentaci k GroupDocs.Viewer pro .NET?

A: Podrobná dokumentace je k dispozici [zde](https://tutorials.groupdocs.com/viewer/net/).

### Otázka: Kde mohu získat podporu nebo se zeptat na otázky týkající se GroupDocs.Viewer pro .NET?

A: Můžete navštívit fórum podpory [zde](https://forum.groupdocs.com/c/viewer/9) o pomoc.