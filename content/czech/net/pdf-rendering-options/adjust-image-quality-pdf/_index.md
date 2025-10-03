---
"description": "Naučte se, jak upravit kvalitu obrazu v PDF dokumentech pomocí GroupDocs.Viewer pro .NET. Pro bezproblémovou integraci postupujte podle našeho podrobného návodu."
"linktitle": "Úprava kvality obrazu v PDF"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Úprava kvality obrazu v PDF"
"url": "/cs/net/pdf-rendering-options/adjust-image-quality-pdf/"
"weight": 10
type: docs
---
# Úprava kvality obrazu v PDF

## Zavedení
GroupDocs.Viewer pro .NET je výkonná knihovna, která umožňuje vývojářům snadno integrovat funkce vykreslování dokumentů do jejich .NET aplikací. Jednou z klíčových funkcí této knihovny je možnost úpravy kvality obrazu při vykreslování PDF dokumentů. V tomto tutoriálu vás krok za krokem provedeme procesem úpravy kvality obrazu pomocí GroupDocs.Viewer pro .NET.

![Úprava kvality obrazu v PDF pomocí GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/adjust-image-quality-in-pdf.png)

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Základní znalost programování v C#.
2. Visual Studio nainstalované ve vašem systému.
3. Knihovna GroupDocs.Viewer pro .NET byla stažena a nainstalována. Můžete si ji stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Nejprve je třeba importovat potřebné jmenné prostory pro práci s GroupDocs.Viewer pro .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Nahradit `"Your Document Directory"` s cestou, kam chcete uložit vykreslené HTML stránky.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tento řádek definuje formát cesty k souboru každé vykreslené HTML stránky. `{0}` je zástupný symbol pro číslo stránky.
## Krok 3: Úprava kvality obrazu
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
Nahradit `"Your PDF File Path"` s cestou k vašemu PDF dokumentu.
## Krok 4: Zobrazení výstupní cesty
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tento řádek zobrazuje cestu, kam jsou uloženy vykreslené HTML stránky.

## Závěr
V tomto tutoriálu jsme se naučili, jak upravit kvalitu obrazu při vykreslování PDF dokumentů pomocí GroupDocs.Viewer pro .NET. Dodržením výše uvedených jednoduchých kroků si můžete snadno přizpůsobit kvalitu obrazu podle svých požadavků.
## Často kladené otázky
### Mohu upravit kvalitu obrazu i pro jiné formáty dokumentů než PDF?
Ano, GroupDocs.Viewer pro .NET podporuje různé formáty dokumentů a u většiny z nich můžete upravit kvalitu obrazu.
### Jaké jsou dostupné možnosti kvality obrazu?
GroupDocs.Viewer pro .NET nabízí možnosti pro nízkou, střední a vysokou kvalitu obrazu.
### Existuje způsob, jak zobrazit náhled dokumentu před jeho vykreslením s upravenou kvalitou obrazu?
Ano, můžete použít GroupDocs.Viewer pro .NET k vygenerování náhledů dokumentů s různým nastavením kvality obrazu.
### Vyžaduje GroupDocs.Viewer pro .NET licenci pro komerční použití?
Ano, pro komerční použití musíte získat licenci. Licenci si můžete zakoupit od [zde](https://purchase.groupdocs.com/buy).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
Podporu můžete získat na fóru GroupDocs.Viewer. [zde](https://forum.groupdocs.com/c/viewer/9).