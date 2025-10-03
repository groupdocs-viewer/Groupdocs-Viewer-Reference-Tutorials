---
"description": "Naučte se, jak vykreslit vybrané stránky z dokumentů pomocí Groupdocs.Viewer pro .NET. Podrobný návod s příklady kódu."
"linktitle": "Vykreslení vybraných stránek"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení vybraných stránek"
"url": "/cs/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# Vykreslení vybraných stránek

## Zavedení

V tomto tutoriálu se ponoříme do toho, jak pomocí nástroje Groupdocs.Viewer pro .NET vykreslit vybrané stránky z dokumentu. Ať už jste zkušený vývojář, nebo teprve začínáte, tento podrobný návod vás celým procesem snadno provede.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

### 1. Instalace

Ujistěte se, že máte ve svém vývojovém prostředí nainstalovaný nástroj Groupdocs.Viewer pro .NET. Pokud ne, můžete si jej stáhnout z [Odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).

## Import jmenných prostorů

Do souboru kódu C# importujte potřebné jmenné prostory pro přístup k požadovaným třídám a metodám. To můžete provést pomocí `using` směrnice:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme uvedený příklad kódu do několika kroků:

## Krok 1: Nastavení výstupního adresáře

Definujte adresář, kam chcete ukládat vykreslené stránky. Nahraďte `"Your Document Directory"` s požadovanou cestou k adresáři.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Definování formátu cesty k souboru stránky

Zadejte formát cest k souborům vykreslených stránek. Tento formát bude použit k uložení každé stránky jako souboru HTML do výstupního adresáře.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Vytvoření instance objektu Viewer

Vytvořte instanci třídy Viewer a jako argument předejte cestu k dokumentu, který chcete vykreslit.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Krok 4: Konfigurace možností zobrazení HTML

Nastavte možnosti zobrazení HTML pro vykreslování. V tomto příkladu konfigurujeme možnosti pro vložení zdrojů do výstupu HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Krok 5: Vykreslení vybraných stránek

Zadejte čísla stránek, které chcete vykreslit. V tomto případě vykreslujeme stránky 1 až 3. Poté zavolejte metodu View objektu Viewer a předejte jí možnosti a čísla stránek jako argumenty.

```csharp
viewer.View(options, 1, 3);
```

## Krok 6: Výstup výsledku

Nakonec zobrazte zprávu o úspěšném vykreslení dokumentu a umístění, kam jsou uloženy výstupní soubory.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak vykreslit vybrané stránky z dokumentu pomocí Groupdocs.Viewer pro .NET. S těmito znalostmi nyní můžete snadno integrovat funkce vykreslování dokumentů do svých .NET aplikací.

## Často kladené otázky

### Otázka: Mohu vykreslovat stránky z různých typů dokumentů, jako jsou PDF nebo obrázky?

A: Ano, Groupdocs.Viewer pro .NET podporuje vykreslování stránek z různých formátů dokumentů, včetně PDF, dokumentů Microsoft Office a obrazových souborů.

### Otázka: Je k dispozici zkušební verze pro vyzkoušení před zakoupením?

A: Ano, můžete si zdarma stáhnout zkušební verzi Groupdocs.Viewer pro .NET z [webové stránky](https://releases.groupdocs.com/).

### Otázka: Mohu si přizpůsobit výstupní formát jiný než HTML?

A: Rozhodně, Groupdocs.Viewer pro .NET nabízí kromě HTML i možnosti vykreslování stránek jako obrázků, PDF a dalších formátů.

### Otázka: Jak mohu získat dočasné licence pro účely testování?

A: Dočasné licence lze získat od [stránka s dočasnou licencí](https://purchase.groupdocs.com/temporary-license/) na webových stránkách Groupdocs.

### Otázka: Kde mohu vyhledat pomoc nebo získat pomoc s jakýmikoli problémy, se kterými se setkám?

A: Můžete navštívit [Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za podporu a rady od komunity a vývojářů.