---
title: Omezte počet položek k vykreslení v datových souborech aplikace Outlook
linktitle: Omezte počet položek k vykreslení v datových souborech aplikace Outlook
second_title: GroupDocs.Viewer .NET API
description: Přečtěte si, jak omezit počet položek vykreslených v datových souborech aplikace Outlook pomocí Groupdocs.Viewer for .NET. Postupujte krok za krokem pro bezproblémovou integraci.
weight: 12
url: /cs/net/rendering-outlook-data-files/limit-items-to-render-outlook-data-files/
---
## Úvod
Groupdocs.Viewer for .NET je výkonný nástroj pro vývojáře, kteří chtějí bezproblémově integrovat možnosti prohlížení dokumentů do svých aplikací .NET. Ať už potřebujete ve své aplikaci zobrazit soubory PDF, dokumenty Microsoft Office nebo datové soubory aplikace Outlook, Groupdocs.Viewer nabízí robustní řešení. V tomto tutoriálu se ponoříme do toho, jak omezit počet položek vykreslených konkrétně v datových souborech aplikace Outlook pomocí podrobných pokynů.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
1. Visual Studio IDE: Ujistěte se, že máte v systému nainstalované Visual Studio.
2.  Groupdocs.Viewer for .NET: Stáhněte a nainstalujte knihovnu Groupdocs.Viewer z[stránka ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Základní porozumění C#: Seznamte se se základy programovacího jazyka C#.

## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu C#. Tento krok zajistí, že budete mít přístup k požadovaným třídám a metodám z knihovny Groupdocs.Viewer.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Definujte výstupní adresář
Nejprve zadejte adresář, kam chcete ukládat vykreslené HTML stránky. Tento adresář bude obsahovat jednotlivé soubory HTML pro každou vykreslenou stránku datového souboru aplikace Outlook.
```csharp
string outputDirectory = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` s cestou k adresáři, kam chcete uložit vykreslené HTML stránky.
## Krok 2: Definujte formát cesty k souboru stránky
 Dále definujte formát cest k souborům vykreslených stránek HTML. Každá stránka HTML bude uložena s názvem souboru, který odpovídá tomuto formátu, s`{0}` nahrazeno číslem stránky.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tento krok zajistí, že každá vykreslená stránka bude uložena s jedinečným názvem souboru na základě čísla stránky.
## Krok 3: Omezte položky v datovém souboru aplikace Outlook
 Nyní vytvořte instanci`Viewer` třídy a zadejte cestu k datovému souboru aplikace Outlook (`*.ost`), který chcete vykreslit.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST))
```
 Nahradit`TestFiles.SAMPLE_OST` s cestou k datovému souboru aplikace Outlook.
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
Nakonfigurujte možnosti zobrazení HTML, včetně určení maximálního počtu položek k vykreslení v každé složce datového souboru aplikace Outlook.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.MaxItemsInFolder = 3;
```
 V tomto příkladu nastavíme`MaxItemsInFolder` majetek do`3`, což omezuje počet položek (jako jsou e-maily nebo složky), které se mají vykreslit v každé složce datového souboru aplikace Outlook.
## Krok 5: Vykreslení dokumentu
 Nakonec zavolejte na`View` metoda`Viewer` předáním možností zobrazení HTML.
```csharp
viewer.View(options);
```
Tato metoda vykreslí datový soubor aplikace Outlook podle zadaných možností a pro každou položku vygeneruje stránky HTML.
## Krok 6: Zobrazte cestu výstupního adresáře
Volitelně můžete vytisknout cestu k výstupnímu adresáři, kde jsou uloženy vykreslené HTML stránky.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
V tomto tutoriálu jsme prozkoumali, jak omezit počet položek vykreslených v datových souborech aplikace Outlook pomocí Groupdocs.Viewer pro .NET. Pokud budete postupovat podle podrobného průvodce, můžete snadno integrovat tuto funkci do svých aplikací .NET a poskytnout uživatelům zjednodušené prohlížení dokumentů.
## FAQ
### Mohu dále upravit možnosti vykreslování HTML?
Ano, Groupdocs.Viewer poskytuje rozsáhlé možnosti přizpůsobení procesu vykreslování a umožňuje vám ovládat různé aspekty, jako je velikost stránky, nastavení písma a další.
### Je Groupdocs.Viewer kompatibilní s jinými formáty dokumentů kromě datových souborů aplikace Outlook?
Groupdocs.Viewer rozhodně podporuje širokou škálu formátů dokumentů, včetně PDF, souborů Microsoft Office, obrázků a dalších.
### Nabízí Groupdocs.Viewer kompatibilitu napříč platformami?
Ano, Groupdocs.Viewer je kompatibilní s aplikacemi .NET spuštěnými v prostředích Windows, Linux a macOS.
### Mohu integrovat Groupdocs.Viewer do webových aplikací?
Groupdocs.Viewer lze samozřejmě bez problémů integrovat do desktopových i webových aplikací a nabízí flexibilitu a všestrannost.
### Je pro Groupdocs.Viewer k dispozici technická podpora?
 Ano, technická podpora je k dispozici prostřednictvím Groupdocs[Fórum](https://forum.groupdocs.com/c/viewer/9), kde můžete hledat pomoc, klást otázky a zapojit se do komunity vývojářů.