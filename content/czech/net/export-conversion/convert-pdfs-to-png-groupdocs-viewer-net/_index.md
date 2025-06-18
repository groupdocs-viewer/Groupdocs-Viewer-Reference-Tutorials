---
"date": "2025-04-25"
"description": "Naučte se, jak převádět stránky PDF do obrázků PNG se zachováním původních rozměrů pomocí nástroje GroupDocs.Viewer pro .NET. Tato příručka popisuje nastavení, konfiguraci a osvědčené postupy."
"title": "Převod PDF do PNG s původní velikostí pomocí GroupDocs.Viewer pro .NET"
"url": "/cs/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
---

# Převod PDF do PNG s původní velikostí pomocí GroupDocs.Viewer pro .NET

## Zavedení

Převod PDF souborů do obrázků PNG při zachování původní velikosti stránky je nezbytný pro vysoce kvalitní digitalizaci dokumentů nebo přípravu webového obsahu. Tento tutoriál vás provede použitím GroupDocs.Viewer pro .NET k vykreslení PDF stránek jako souborů PNG se zachováním jejich původních rozměrů.

![Převod PDF do PNG v původní velikosti pomocí GroupDocs.Viewer pro .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Co se naučíte:**
- Jak nastavit a konfigurovat GroupDocs.Viewer pro .NET ve vašem projektu
- Podrobný postup vykreslování PDF souborů do obrázků PNG při zachování velikosti stránky
- Klíčové možnosti konfigurace a osvědčené postupy pro optimální výkon

Po dokončení tohoto tutoriálu budete schopni tuto funkci bez problémů integrovat do svých aplikací. Začněme s předpoklady, které jsou pro začátek nezbytné.

## Předpoklady

Před implementací GroupDocs.Viewer pro .NET ve vašem projektu se ujistěte, že máte splněny následující požadavky:

### Požadované knihovny a verze
- **GroupDocs.Viewer pro .NET**Verze 25.3.0 nebo novější.

### Požadavky na nastavení prostředí
- Kompatibilní vývojové prostředí, jako je Visual Studio.
- Základní znalost programování v C#.

### Předpoklady znalostí
- Znalost správy balíčků NuGet.
- Zkušenosti s prací s PDF soubory a zpracováním obrázků v .NET aplikacích.

Jakmile splníte tyto předpoklady, můžeme pokračovat v nastavení GroupDocs.Viewer pro .NET.

## Nastavení GroupDocs.Viewer pro .NET

Chcete-li začít používat GroupDocs.Viewer pro .NET, postupujte podle následujících kroků instalace:

### Instalace pomocí konzole Správce balíčků NuGet
Otevřete projekt ve Visual Studiu a použijte následující příkaz:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Instalace přes .NET CLI
Případně jej můžete nainstalovat pomocí rozhraní .NET CLI pomocí tohoto příkazu:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Kroky získání licence
1. **Bezplatná zkušební verze**Stáhněte si zkušební verzi z [Soubory ke stažení GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **Dočasná licence**Získejte dočasnou licenci k prozkoumání všech funkcí na adrese [Stránka s dočasnou licencí](https://purchase.groupdocs.com/temporary-license/).
3. **Nákup**Pro delší použití si zakupte licenci prostřednictvím [Koupit stránku](https://purchase.groupdocs.com/buy).

### Základní inicializace a nastavení
Chcete-li inicializovat GroupDocs.Viewer pro .NET ve vašem projektu C#, postupujte takto:
1. Importujte potřebné jmenné prostory:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Nastavte cesty pro vstupní PDF a výstupní adresář.
3. Inicializovat `Viewer` s cestou ke zdrojovému dokumentu, jak je znázorněno v tomto úryvku:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Průvodce implementací
Tato část se zabývá implementací vykreslování stránek PDF jako obrázků PNG při zachování jejich původní velikosti.

### Vykreslování stránek PDF do PNG s původní velikostí stránky
#### Přehled
Tato funkce umožňuje vykreslit každou stránku dokumentu PDF do obrázku PNG a zachovat její původní rozměry. To je obzvláště užitečné pro aplikace vyžadující přesnou vizuální reprezentaci dokumentů.

##### Krok 1: Nastavení cest a inicializace prohlížeče
Vytvořte proměnné pro vstupní cestu k PDF a výstupní adresář:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Inicializujte `Viewer` třída s cestou k vašemu zdrojovému dokumentu:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Blok kódu bude pokračovat v dalším kroku
}
```
##### Krok 2: Konfigurace PngViewOptions
Vytvořte instanci `PngViewOptions`, přičemž se určuje vzor pojmenování souborů pro výstupní obrázky:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Nakonfigurujte možnosti prohlížeče tak, aby se každá stránka vykreslila v původní velikosti:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Krok 3: Vykreslení stránek dokumentu
Zavolejte `View` metoda na vašem `Viewer` instance, předáním nakonfigurovaných možností zobrazení:
```csharp
viewer.View(viewOptions);
```
### Tipy pro řešení problémů
- Ujistěte se, že cesty jsou správné a adresáře existují.
- Ověřte, zda máte potřebná oprávnění ke čtení ze vstupních adresářů a zápisu do výstupních adresářů.

## Praktické aplikace
1. **Digitalizace dokumentů**Převeďte archivní PDF dokumenty do digitálních obrázků pro snazší přístup a distribuci.
2. **Webové portály**Zobrazování náhledů dokumentů na webových stránkách bez nutnosti čteček PDF.
3. **Systémy pro správu obsahu (CMS)**Integrace s platformami CMS pro efektivní správu a zobrazení velkých objemů PDF obsahu.

## Úvahy o výkonu
Optimalizace výkonu vaší aplikace pomocí GroupDocs.Viewer pro .NET:
- Omezte využití paměti zpracováním dokumentů po částech, pokud pracujete s velkými soubory.
- Pokud je to možné, používejte asynchronní metody, abyste se vyhnuli blokování vláken během vykreslování.
- Disponovat `Viewer` instance ihned po použití, aby se uvolnily zdroje.

## Závěr
V tomto tutoriálu jste se naučili, jak vykreslovat stránky PDF jako obrázky PNG se zachováním jejich původní velikosti pomocí GroupDocs.Viewer pro .NET. Probrali jsme nastavení prostředí, konfiguraci potřebných možností pro optimální výsledky a prozkoumali praktické aplikace této funkce.

Další kroky zahrnují experimentování s dalšími možnostmi vykreslování dostupnými v GroupDocs.Viewer nebo jeho integraci do větších projektů pro rozšířené možnosti správy dokumentů.

## Sekce Často kladených otázek
1. **Jaký je nejlepší způsob, jak zpracovat velké soubory PDF pomocí GroupDocs.Viewer?**
   - Zpracovávejte dokumenty v menších částech a používejte asynchronní metody pro udržení výkonu.
2. **Mohu si přizpůsobit názvy výstupních souborů PNG?**
   - Ano, zadáním vzoru pojmenování v `PngViewOptions`.
3. **Je možné vykreslit pouze určité stránky?**
   - Samozřejmě, můžete nakonfigurovat `PageNumbers` v `PngViewOptions` určit, které stránky se mají vykreslit.
4. **Jak mám postupovat při licencování GroupDocs.Viewer?**
   - Možnosti zahrnují bezplatnou zkušební verzi, dočasnou licenci nebo zakoupení plné licence.
5. **Lze toto nastavení použít ve webových aplikacích?**
   - Ano, je vhodný pro vykreslování PDF souborů na straně serveru v ASP.NET Core a dalších webových frameworkech založených na .NET.

## Zdroje
- [Dokumentace](https://docs.groupdocs.com/viewer/net/)
- [Referenční informace k API](https://reference.groupdocs.com/viewer/net/)
- [Stáhnout GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [Zakoupit licenci](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/net/)
- [Dočasná licence](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory](https://forum.groupdocs.com/c/viewer/9)