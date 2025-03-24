---
title: Vykreslit dokument do formátu JPGPNG
linktitle: Vykreslit dokument do formátu JPGPNG
second_title: GroupDocs.Viewer .NET API
description: Objevte, jak plynule vykreslovat dokumenty do formátu JPG/PNG v .NET pomocí GroupDocs.Viewer pro lepší uživatelský zážitek a produktivitu.
weight: 10
url: /cs/net/rendering-documents-images/render-jpg-png/
---

# Vykreslit dokument do formátu JPGPNG

## Úvod

Ve světě vývoje .NET je efektivní nakládání s dokumenty pro různé aplikace zásadní. Ať už budujete systém správy dokumentů, platformu elektronického obchodování nebo aplikaci s bohatým obsahem, schopnost bezproblémového prohlížení dokumentů je zásadní. Zde vstupuje do hry GroupDocs.Viewer for .NET, který nabízí komplexní řešení pro vykreslování dokumentů do různých formátů, jako jsou JPG a PNG.

## Předpoklady

Než se pustíte do používání GroupDocs.Viewer pro .NET, je třeba zajistit několik předpokladů:

1. Vývojové prostředí .NET: Ujistěte se, že máte na svém počítači nastavené funkční vývojové prostředí .NET. To zahrnuje instalaci sady .NET SDK.

2. Licence GroupDocs.Viewer: Získejte platnou licenci pro GroupDocs.Viewer. Můžete si zakoupit licenci nebo použít dočasnou pro účely hodnocení.

3.  Instalace: Stáhněte a nainstalujte GroupDocs.Viewer for .NET z poskytnutého[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).

4. Soubory dokumentů: Připravte si soubory dokumentů, které chcete vykreslit. GroupDocs.Viewer podporuje různé formáty včetně DOCX, PDF, PPT a dalších.

## Importovat jmenné prostory

Chcete-li začít s vykreslováním dokumentů pomocí GroupDocs.Viewer for .NET, musíte do projektu importovat potřebné jmenné prostory. To vám umožní přístup k funkcím, které knihovna poskytuje.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Vykreslení dokumentu do formátu JPG nebo PNG je s GroupDocs.Viewer pro .NET jednoduchý proces. Níže je uveden podrobný průvodce, který vám toho pomůže:

## Krok 1: Definujte výstupní adresář

Nejprve definujte adresář, kam chcete ukládat vykreslené stránky. Tento adresář by měl existovat a být přístupný pro aplikaci.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Definujte formát cesty k souboru stránky

 Zadejte formát cest k souboru každé vykreslené stránky. GroupDocs.Viewer nahradí`{0}` s číslem stránky při ukládání souborů.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Krok 3: Vytvořte objekt prohlížeče

 Vytvořte instanci souboru`Viewer` třídy zadáním cesty k souboru dokumentu, který chcete vykreslit.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Kód pro vykreslování je zde
}
```

## Krok 4: Definujte možnosti vykreslování

Zadejte možnosti vykreslení podle svých požadavků. Pro vykreslování JPG/PNG použijete`JpgViewOptions` nebo`PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Krok 5: Vykreslení dokumentu

 Vyvolat`View` metoda`Viewer` objekt a předat možnosti vykreslování vytvořené dříve.

```csharp
viewer.View(options);
```

## Krok 6: Výstup výsledků

Jakmile je proces vykreslování dokončen, můžete uživatele informovat o úspěšném vykreslování a poskytnout adresář, do kterého jsou vyrenderované stránky uloženy.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Na závěr, GroupDocs.Viewer for .NET nabízí výkonné řešení pro vykreslování dokumentů do různých formátů, včetně JPG a PNG. Dodržováním kroků uvedených v tomto kurzu můžete bezproblémově integrovat funkce vykreslování dokumentů do vašich aplikací .NET a zlepšit tak uživatelskou zkušenost a produktivitu.

## FAQ

### Otázka: Mohu pomocí GroupDocs.Viewer for .NET vykreslit jiné dokumenty než DOCX?

Odpověď: Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů včetně PDF, PPT, XLS a dalších.

### Otázka: Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?

 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.groupdocs.com/).

### Otázka: Jak mohu získat dočasnou licenci pro účely hodnocení?

Odpověď: Můžete požádat o dočasnou licenci od[tady](https://purchase.groupdocs.com/temporary-license/).

### Otázka: Kde najdu dokumentaci k GroupDocs.Viewer pro .NET?

 Odpověď: K dispozici je podrobná dokumentace[tady](https://tutorials.groupdocs.com/viewer/net/).

### Otázka: Kde mohu získat podporu nebo klást otázky týkající se GroupDocs.Viewer pro .NET?

 Odpověď: Můžete navštívit fórum podpory[tady](https://forum.groupdocs.com/c/viewer/9) pro pomoc.