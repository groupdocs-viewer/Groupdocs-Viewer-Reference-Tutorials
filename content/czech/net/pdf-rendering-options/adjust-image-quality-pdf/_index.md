---
title: Upravte kvalitu obrazu v PDF
linktitle: Upravte kvalitu obrazu v PDF
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak upravit kvalitu obrazu v dokumentech PDF pomocí GroupDocs.Viewer pro .NET. Postupujte podle našeho podrobného návodu pro bezproblémovou integraci.
weight: 10
url: /cs/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## Úvod
GroupDocs.Viewer for .NET je výkonná knihovna, která umožňuje vývojářům bez námahy integrovat funkce vykreslování dokumentů do jejich aplikací .NET. Jednou z klíčových funkcí této knihovny je možnost upravit kvalitu obrazu při vykreslování dokumentů PDF. V tomto tutoriálu vás provedeme procesem úpravy kvality obrazu krok za krokem pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Základní znalost programování v C#.
2. Visual Studio nainstalované ve vašem systému.
3. Knihovna GroupDocs.Viewer pro .NET byla stažena a nainstalována. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory pro práci s GroupDocs.Viewer pro .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` s cestou, kam chcete uložit vykreslené HTML stránky.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Tento řádek definuje formát pro cestu k souboru každé vykreslené stránky HTML.`{0}` je zástupný symbol pro číslo stránky.
## Krok 3: Upravte kvalitu obrazu
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 Nahradit`"Your PDF File Path"` s cestou k vašemu PDF dokumentu.
## Krok 4: Zobrazte výstupní cestu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tento řádek zobrazuje cestu, kam jsou uloženy vykreslené HTML stránky.

## Závěr
V tomto tutoriálu jsme se naučili, jak upravit kvalitu obrazu při vykreslování dokumentů PDF pomocí GroupDocs.Viewer for .NET. Pomocí výše uvedených jednoduchých kroků můžete snadno upravit kvalitu obrazu podle svých požadavků.
## FAQ
### Mohu upravit kvalitu obrazu pro jiné formáty dokumentů kromě PDF?
Ano, GroupDocs.Viewer for .NET podporuje různé formáty dokumentů a u většiny z nich můžete upravit kvalitu obrazu.
### Jaké jsou dostupné možnosti kvality obrazu?
GroupDocs.Viewer pro .NET poskytuje možnosti pro nízkou, střední a vysokou kvalitu obrazu.
### Existuje způsob, jak zobrazit náhled dokumentu před vykreslením s upravenou kvalitou obrazu?
Ano, můžete použít GroupDocs.Viewer pro .NET ke generování náhledů dokumentů s různým nastavením kvality obrazu.
### Vyžaduje GroupDocs.Viewer for .NET licenci pro komerční použití?
 Ano, pro komerční využití je potřeba získat licenci. Licenci si můžete zakoupit od[tady](https://purchase.groupdocs.com/buy).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
 Podporu můžete získat na fóru GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9).