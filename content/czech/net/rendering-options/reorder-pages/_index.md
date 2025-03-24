---
title: Změňte pořadí stránek v dokumentu
linktitle: Změňte pořadí stránek v dokumentu
second_title: GroupDocs.Viewer .NET API
description: Přečtěte si, jak změnit pořadí stránek v dokumentu pomocí GroupDocs.Viewer for .NET. Postupujte podle našeho podrobného návodu pro bezproblémovou správu dokumentů.
weight: 19
url: /cs/net/rendering-options/reorder-pages/
---

# Změňte pořadí stránek v dokumentu

## Úvod
Ve světě vývoje .NET je efektivní správa a manipulace s dokumenty zásadní. GroupDocs.Viewer for .NET poskytuje výkonné řešení pro prohlížení různých formátů dokumentů ve vašich aplikacích. Jedním ze základních úkolů, s nimiž se vývojáři často setkávají, je změna pořadí stránek v dokumentu. Ať už pracujete s PDF, dokumenty Wordu nebo jinými formáty, možnost přeskupit stránky může zjednodušit pracovní postupy a zlepšit uživatelský komfort. V tomto tutoriálu se ponoříme do toho, jak změnit pořadí stránek v dokumentu pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte nastaveny následující předpoklady:
### 1. Nainstalujte GroupDocs.Viewer pro .NET
 Ujistěte se, že máte ve vývojovém prostředí nainstalovaný GroupDocs.Viewer for .NET. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/) a postupujte podle pokynů k instalaci uvedených v dokumentaci.
### 2. Nastavte své vývojové prostředí
Ujistěte se, že máte na svém počítači nastavené funkční vývojové prostředí .NET, včetně sady Visual Studio nebo jakéhokoli jiného preferovaného IDE.
### 3. Získejte vzorové dokumenty
Připravte si vzorové dokumenty pro testovací účely. Můžete použít jakýkoli formát dokumentu podporovaný aplikací GroupDocs.Viewer, jako je PDF, DOCX, XLSX atd.

## Importovat jmenné prostory
Do své aplikace .NET importujte potřebné obory názvů potřebné pro využití funkce GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Zadejte výstupní adresář
Definujte adresář, kam chcete uložit přeuspořádaný dokument.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte cestu k výstupnímu souboru
Zkombinujte výstupní adresář s požadovaným názvem souboru pro změněný dokument.
```csharp
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 3: Vytvořte objekt prohlížeče
Vytvořte instanci třídy Viewer zadáním cesty ke vstupnímu dokumentu.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Zde bude kód pro změnu pořadí stránek
}
```
## Krok 4: Nastavte možnosti zobrazení PDF
Určete volby pro vykreslení dokumentu jako PDF a definujte cestu k výstupnímu souboru.
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Krok 5: Definujte pořadí stránek
Předejte čísla stránek v požadovaném pořadí pro vykreslení.
```csharp
viewer.View(options, 2, 1);
```
## Krok 6: Zobrazte zprávu o úspěchu
Informujte uživatele, že dokument byl úspěšně vykreslen.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Závěrem lze říci, že přeuspořádání stránek v dokumentu je jednoduché s GroupDocs.Viewer pro .NET. Dodržováním kroků uvedených v tomto kurzu můžete efektivně spravovat stránky dokumentů ve svých aplikacích .NET a zvýšit tak použitelnost a produktivitu.
## FAQ
### Dokáže GroupDocs.Viewer for .NET zpracovat více formátů dokumentů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, DOCX, XLSX, PPTX a dalších.
### Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, máte přístup k bezplatné zkušební verzi GroupDocs.Viewer z[tady](https://releases.groupdocs.com/).
### Vyžaduje GroupDocs.Viewer for .NET trvalou licenci pro vývoj?
 Zatímco pro testování a vývoj je k dispozici dočasná licence, pro produkční použití je vyžadována trvalá licence. Můžete získat dočasnou licenci[tady](https://purchase.groupdocs.com/temporary-license/).
### Mohu upravit vzhled vykresleného dokumentu pomocí GroupDocs.Viewer for .NET?
Ano, GroupDocs.Viewer poskytuje různé možnosti pro přizpůsobení výstupu vykreslování, včetně otáčení stránky, vodoznaku a dalších.
### Kde najdu další pomoc nebo podporu pro GroupDocs.Viewer pro .NET?
 Můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9) pro jakékoli dotazy nebo potřeby podpory.