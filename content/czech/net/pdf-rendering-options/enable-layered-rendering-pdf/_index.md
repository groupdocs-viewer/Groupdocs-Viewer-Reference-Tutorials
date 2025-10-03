---
"description": "Naučte se, jak povolit vrstvené vykreslování v dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Vylepšete si zážitek ze prohlížení dokumentů bez námahy."
"linktitle": "Povolit vrstvené vykreslování v PDF"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Povolit vrstvené vykreslování v PDF"
"url": "/cs/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
type: docs
---
# Povolit vrstvené vykreslování v PDF

## Zavedení
tomto tutoriálu se ponoříme do procesu povolení vrstveného vykreslování v dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Vrstvené vykreslování umožňuje vylepšené zobrazení a manipulaci s dokumenty a poskytuje uživatelům interaktivnější zážitek ze sledování.

![Povolení vrstvené rendering v PDF pomocí GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer pro .NET: Ujistěte se, že máte nainstalovaný potřebný balíček nebo knihovnu pro použití GroupDocs.Viewer pro .NET ve vašem projektu.
2. Visual Studio: Pro kódování a spouštění uvedených příkladů byste měli mít v systému nainstalované Visual Studio.
3. Základní znalost jazyka C#: Tento tutoriál předpokládá znalost syntaxe a konceptů programovacího jazyka C#.

## Importovat jmenné prostory
Začněte importem požadovaných jmenných prostorů do projektu:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Nezapomeňte zadat cestu k adresáři, kam chcete uložit vykreslený výstup.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tento krok nastavuje formát cest k souborům jednotlivých stránek ve vykresleném výstupu. `{0}` je zástupný symbol pro číslo stránky.
## Krok 3: Povolte vrstvené vykreslování
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Zde vytváříme `Viewer` objekt a určíme PDF dokument, který má být zpracován. Poté nakonfigurujeme `HtmlViewOptions` s definovaným formátem cesty k souboru stránky. Nastavením `EnableLayeredRendering` majetek `true` v `PdfOptions`, povolíme pro dokument PDF vykreslování ve vrstvách.
## Krok 4: Zobrazení výstupního adresáře
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nakonec vypíšeme zprávu o úspěšném vykreslení zdrojového dokumentu a vyzveme uživatele ke kontrole výstupu v zadaném adresáři.

## Závěr
Povolení vrstevnatého vykreslování v dokumentech PDF pomocí nástroje GroupDocs.Viewer pro .NET vylepšuje možnosti prohlížení dokumentů a poskytuje uživatelům bohatší a interaktivnější zážitek. Dodržením kroků popsaných v tomto tutoriálu můžete tuto funkci bezproblémově integrovat do svých aplikací .NET.
## Často kladené otázky
### Co je vrstvené vykreslování v dokumentech PDF?
Vrstvené vykreslování umožňuje oddělení a manipulaci s různými komponentami v dokumentu PDF, což umožňuje interaktivní prohlížení a vylepšený uživatelský zážitek.
### Mohu si přizpůsobit výstupní adresář pro vykreslené dokumenty?
Ano, můžete zadat libovolnou cestu k adresáři pro výstup dle vašich požadavků.
### Podporuje GroupDocs.Viewer i jiné formáty souborů než PDF?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně Wordu, Excelu, PowerPointu a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer je kompatibilní s prostředím .NET Framework i .NET Core.
### Kde mohu najít další podporu nebo pomoc?
S případnými dotazy nebo s žádostí o pomoc ohledně knihovny prohlížečů můžete navštívit fórum GroupDocs.Viewer.