---
title: Nastavit časový limit načítání zdroje (pokročilé)
linktitle: Nastavit časový limit načítání zdroje (pokročilé)
second_title: GroupDocs.Viewer .NET API
description: Zjistěte, jak efektivně nakonfigurovat časové limity načítání prostředků v GroupDocs.Viewer pro .NET. Vykreslování hlavního dokumentu s přesností a stabilitou.
weight: 13
url: /cs/net/advanced-loading/set-resource-loading-timeout/
---
## Úvod
oblasti vývoje .NET poskytuje GroupDocs.Viewer výkonnou sadu nástrojů pro přesné a efektivní vykreslování dokumentů a obrázků. Využití jeho schopností vyžaduje pochopení jeho složitostí, včetně nastavení časových limitů načítání zdrojů. V tomto tutoriálu se ponoříme do procesu konfigurace časových limitů načítání prostředků v GroupDocs.Viewer pro .NET.
## Předpoklady
Než se pustíte do tohoto kurzu, ujistěte se, že máte následující předpoklady:
1. Základní znalost vývoje .NET: Znalost programování v C# a základů .NET frameworku je nezbytná.
2.  Instalace GroupDocs.Viewer for .NET: Stáhněte a nainstalujte knihovnu GroupDocs.Viewer for .NET z[stránka ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Integrované vývojové prostředí (IDE): Mějte na svém systému nainstalované IDE, jako je Visual Studio.

## Importovat jmenné prostory
Než se ponoříte do procesu kódování, importujte potřebné jmenné prostory:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Definujte výstupní adresář
Nejprve definujte adresář, kam se budou ukládat vykreslené dokumenty:
```csharp
string outputDirectory = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` cestou, kam chcete uložit vykreslené dokumenty.
## Krok 2: Definujte formát cesty k souboru stránky
Definujte formát pro cesty k souborům jednotlivých stránek:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Tento formát vygeneruje názvy souborů jako`page_1.html`, `page_2.html`atd. v zadaném výstupním adresáři.
## Krok 3: Nakonfigurujte možnosti načítání
Nakonfigurujte možnosti načítání, včetně časového limitu načítání zdroje:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
V tomto příkladu je pro načítání prostředků nastaven časový limit 5 sekund.
## Krok 4: Inicializujte objekt prohlížeče
 Inicializujte`Viewer` objekt s dokumentem, který se má vykreslit, a definovanými možnostmi načtení:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Nahradit`TestFiles.WITH_EXTERNAL_IMAGE_DOC` s cestou k dokumentu, který chcete vykreslit.
## Krok 5: Nakonfigurujte možnosti zobrazení HTML
Konfigurace možností zobrazení HTML pro vložené zdroje:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Tato konfigurace zajišťuje, že ve vykresleném HTML budou zahrnuty vložené zdroje, jako jsou obrázky.
## Krok 6: Vykreslení dokumentu
Vykreslete dokument pomocí nakonfigurovaných možností:
```csharp
viewer.View(options);
```
Tento krok zahájí proces vykreslování.
## Krok 7: Zobrazte výstupní adresář
Zobrazte zprávu o úspěšném vykreslení a umístění výstupního adresáře:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Zvládnutí časových limitů načítání prostředků v GroupDocs.Viewer pro .NET je zásadní pro zajištění hladkých procesů vykreslování dokumentů. Sledováním tohoto výukového programu jste získali přehled o efektivní konfiguraci časových limitů a zlepšili své znalosti ve vývoji .NET.
## FAQ
### Jaký význam má nastavení časových limitů načítání zdrojů?
Nastavení časových limitů načítání prostředků zajišťuje, že procesy vykreslování nebudou donekonečna zablokovány, což zvyšuje stabilitu aplikace.
### Lze časové limity načítání prostředků přizpůsobit na základě typů dokumentů?
Ano, časové limity načítání zdrojů lze upravit na základě složitosti a velikosti vykreslovaných dokumentů.
### Má nastavení kratších časových limitů nějaké dopady na výkon?
Kratší časové limity mohou vést k neúplnému vykreslování složitých dokumentů, pokud zdroje nelze načíst během zadané doby.
### Je GroupDocs.Viewer vhodný pro vykreslování různých formátů dokumentů?
Ano, GroupDocs.Viewer podporuje vykreslování široké škály formátů dokumentů včetně PDF, DOCX, XLSX a dalších.
### Lze zakázat časové limity načítání zdrojů?
I když to není doporučeno, časové limity načítání zdrojů lze nastavit na vysokou hodnotu nebo zcela zakázat v závislosti na konkrétních požadavcích.