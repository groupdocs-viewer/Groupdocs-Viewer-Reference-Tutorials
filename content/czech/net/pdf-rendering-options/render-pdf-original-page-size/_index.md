---
"description": "Naučte se, jak vykreslovat PDF soubory s původními velikostmi stránek pomocí GroupDocs.Viewer pro .NET. Postupujte podle našeho podrobného návodu a bezproblémově integrujte tuto funkci."
"linktitle": "Vykreslit PDF s původní velikostí stránky"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslit PDF s původní velikostí stránky"
"url": "/cs/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
type: docs
---
# Vykreslit PDF s původní velikostí stránky

## Zavedení
oblasti vývoje pro .NET vyniká GroupDocs.Viewer jako výkonný nástroj pro vykreslování různých formátů dokumentů, včetně PDF. Jedním z běžných požadavků při práci s dokumenty je vykreslování PDF souborů se zachováním jejich původní velikosti stránky. Bezproblémové dosažení tohoto úkolu vyžaduje komplexní znalost GroupDocs.Viewer pro .NET a jeho funkcí.

![Vykreslení PDF s původní velikostí stránky pomocí GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Předpoklady
Než se pustíte do vykreslování PDF souborů s původními velikostmi stránek pomocí nástroje GroupDocs.Viewer pro .NET, ujistěte se, že máte splněny následující předpoklady:
### 1. Nainstalujte GroupDocs.Viewer pro .NET
Začněte stažením knihovny GroupDocs.Viewer z webových stránek. Knihovnu můžete získat z dodaného [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/)Pro efektivní integraci do vašeho .NET projektu postupujte podle pokynů k instalaci uvedených v dokumentaci.
### 2. Nastavení vývojového prostředí
Ujistěte se, že máte nastavené vývojové prostředí pro vývoj v .NET. To zahrnuje instalaci kompatibilního IDE, jako je Visual Studio, a základní znalost programování v C#.
### 3. Získejte dokument PDF
Pro vykreslení pomocí GroupDocs.Viewer budete potřebovat vzorový PDF dokument. Pro testovací účely můžete použít libovolný PDF dokument. Pokud žádný nemáte, můžete si vzorový PDF stáhnout z různých online zdrojů.

## Importovat jmenné prostory
Než budete pokračovat s vykreslováním PDF souborů, je nezbytné importovat potřebné jmenné prostory do vašeho projektu C#. Tento krok vám umožní přístup k požadovaným třídám a metodám z knihovny GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní, když máte splněny předpoklady a importovány potřebné jmenné prostory, pojďme si rozebrat proces vykreslování PDF s původními velikostmi stránek pomocí GroupDocs.Viewer pro .NET do jednoduchých kroků:
## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Ujistěte se, že jste zadali adresář, kam chcete uložit vykreslené stránky. Nahraďte `"Your Document Directory"` s cestou k požadovanému adresáři.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Nastavte formát pro pojmenování vykreslených souborů stránek. V tomto příkladu budou stránky uloženy jako obrázky PNG s názvy souborů ve formátu `"page_1.png"`, `"page_2.png"`, a tak dále.
## Krok 3: Vykreslení PDF s původní velikostí stránky
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Vytvořte instanci `Viewer` objekt s cestou k vašemu PDF souboru. Poté vytvořte `PngViewOptions` se zadaným formátem cesty k souboru stránky. Nastavit `RenderOriginalPageSize` majetek `true` zachovat původní velikosti stránky při vykreslování.
## Krok 4: Zobrazení umístění vykresleného dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Vytiskněte zprávu oznamující úspěšné vykreslení a zadejte adresář, kam jsou uloženy vykreslené stránky.

## Závěr
Vykreslování PDF souborů s původními velikostmi stránek pomocí GroupDocs.Viewer pro .NET je při dodržení kroků uvedených v tomto tutoriálu snadnou záležitostí. Importem potřebných jmenných prostorů a dodržením podrobných pokynů můžete tuto funkci bezproblémově integrovat do svých aplikací .NET.
## Často kladené otázky
### Může GroupDocs.Viewer vykreslit i jiné formáty dokumentů než PDF?
Ano, GroupDocs.Viewer podporuje vykreslování různých formátů dokumentů, včetně Wordu, Excelu, PowerPointu a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer je kompatibilní s prostředím .NET Framework i .NET Core.
### Mohu si přizpůsobit výstupní formát vykreslených stránek?
Ano, výstupní formát si můžete přizpůsobit úpravou možností, které nabízí GroupDocs.Viewer, například nastavením různých formátů obrázků nebo zadáním vlastních možností vykreslování.
### Nabízí GroupDocs.Viewer podporu pro cloudové vykreslování dokumentů?
Ano, GroupDocs.Viewer poskytuje API pro cloudové vykreslování dokumentů, což vám umožňuje vykreslovat dokumenty přímo od poskytovatelů cloudového úložiště.
### Je k dispozici bezplatná zkušební verze GroupDocs.Viewer?
Ano, GroupDocs.Viewer si můžete vyzkoušet s bezplatnou zkušební verzí na poskytnuté stránce. [odkaz](https://releases.groupdocs.com/).