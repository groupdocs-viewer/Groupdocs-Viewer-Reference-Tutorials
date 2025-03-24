---
title: Vykreslit vybrané stránky
linktitle: Vykreslit vybrané stránky
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat vybrané stránky z dokumentů pomocí Groupdocs.Viewer pro .NET. Výukový program krok za krokem včetně příkladů kódu.
weight: 17
url: /cs/net/rendering-options/render-selected-pages/
---

# Vykreslit vybrané stránky

## Úvod

V tomto tutoriálu se ponoříme do toho, jak využít Groupdocs.Viewer pro .NET k vykreslení vybraných stránek z dokumentu. Ať už jste zkušený vývojář nebo teprve začínáte, tento podrobný průvodce vás procesem snadno provede.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

### 1. Instalace

 Ujistěte se, že máte ve svém vývojovém prostředí nainstalovaný Groupdocs.Viewer for .NET. Pokud ne, můžete si jej stáhnout z[Odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).

## Import jmenných prostorů

Do souboru kódu C# importujte potřebné jmenné prostory pro přístup k požadovaným třídám a metodám. Můžete to udělat pomocí`using` směrnice:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní rozdělíme poskytnutý příklad kódu do několika kroků:

## Krok 1: Nastavte výstupní adresář

 Definujte adresář, kam chcete ukládat vykreslené stránky. Nahradit`"Your Document Directory"` s požadovanou cestou k adresáři.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Definujte formát cesty k souboru stránky

Zadejte formát cest k souborům vykreslených stránek. To se použije k uložení každé stránky jako souboru HTML do výstupního adresáře.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Vytvořte objekt prohlížeče

Vytvořte instanci třídy Viewer a jako argument předejte cestu dokumentu, který chcete vykreslit.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Krok 4: Nakonfigurujte možnosti zobrazení HTML

Nastavte možnosti zobrazení HTML pro vykreslování. V tomto příkladu konfigurujeme možnosti pro vkládání zdrojů do výstupu HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Krok 5: Vykreslení vybraných stránek

Zadejte čísla stránek, které chcete vykreslit. V tomto případě vykreslujeme stránky 1 až 3. Poté zavolejte metodu View na objektu Viewer a předejte možnosti a čísla stránek jako argumenty.

```csharp
viewer.View(options, 1, 3);
```

## Krok 6: Výstup Výsledek

Nakonec zobrazte zprávu o úspěšném vykreslení dokumentu a umístění, kde jsou uloženy výstupní soubory.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak vykreslit vybrané stránky z dokumentu pomocí Groupdocs.Viewer for .NET. S těmito znalostmi nyní můžete snadno integrovat možnosti vykreslování dokumentů do vašich aplikací .NET.

## FAQ

### Otázka: Mohu vykreslit stránky z různých typů dokumentů, jako jsou soubory PDF nebo obrázky?

Odpověď: Ano, Groupdocs.Viewer for .NET podporuje vykreslování stránek z různých formátů dokumentů, včetně PDF, dokumentů Microsoft Office a obrazových souborů.

### Otázka: Je k dispozici zkušební verze pro testování před zakoupením?

 Odpověď: Ano, máte přístup k bezplatné zkušební verzi Groupdocs.Viewer pro .NET z webu[webová stránka](https://releases.groupdocs.com/).

### Otázka: Mohu přizpůsobit výstupní formát jiný než HTML?

A: Rozhodně, Groupdocs.Viewer pro .NET poskytuje kromě HTML možnosti vykreslování stránek jako obrázky, PDF a další.

### Otázka: Jak mohu získat dočasné licence pro testovací účely?

Odpověď: Dočasné licence lze získat z[dočasná licenční stránka](https://purchase.groupdocs.com/temporary-license/) na webu Groupdocs.

### Otázka: Kde mohu vyhledat pomoc nebo získat pomoc s jakýmikoli problémy, na které narazím?

 A: Můžete navštívit[Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za podporu a vedení od komunity a vývojářů.