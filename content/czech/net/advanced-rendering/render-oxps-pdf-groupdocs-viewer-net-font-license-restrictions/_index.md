---
"date": "2025-04-25"
"description": "Naučte se, jak vykreslovat dokumenty PDF a OXPS a zároveň obejít omezení licencí písem pomocí GroupDocs.Viewer pro .NET. Seznamte se s nastavením, implementací a praktickými aplikacemi."
"title": "Vykreslení PDF/OXPS s omezeními písma pomocí GroupDocs.Viewer .NET – Komplexní průvodce"
"url": "/cs/net/advanced-rendering/render-oxps-pdf-groupdocs-viewer-net-font-license-restrictions/"
"weight": 1
---

# Vykreslení PDF/OXPS s omezeními písma pomocí GroupDocs.Viewer .NET: Komplexní průvodce

## Zavedení

Vykreslování dokumentů XPS nebo OXPS může být náročné kvůli omezením licencí písem. Tento tutoriál vás provede efektivním vykreslováním těchto dokumentů pomocí **GroupDocs.Viewer pro .NET**Toto řešení je neocenitelné, ideální pro systémy správy dokumentů, platformy pro publikování obsahu a aplikace vyžadující bezproblémovou konverzi dokumentů.

![Vykreslení PDF/OXPS s omezeními písma v GroupDocs.Viewer pro .NET](/viewer/advanced-rendering/render-pdf-oxps-font-restrictions-img.png)

V této příručce se naučíte, jak:
- Nastavení GroupDocs.Vieweru pro .NET
- Vykreslování dokumentů XPS/OXPS s vloženými fonty
- Zakázat omezení licencí písem během vykreslování

## Předpoklady

Před zahájením se ujistěte o následujícím:

### Požadované knihovny a verze
- **GroupDocs.Viewer pro .NET**Verze 25.3.0 nebo novější.
- **Vývojové prostředí**Visual Studio (2017 nebo novější) nebo jakékoli kompatibilní IDE podporující vývoj v .NET.

### Požadavky na nastavení prostředí
- Projekt AC# ve vámi zvoleném IDE.
- Přístup k NuGet Package Manageru pro instalaci knihovny.

### Předpoklady znalostí
- Základní znalost konceptů C# a .NET frameworku.
- Znalost práce s cestami k souborům a adresáři v prostředí .NET.

Po splnění všech předpokladů si nastavme GroupDocs.Viewer pro .NET.

## Nastavení GroupDocs.Viewer pro .NET

### Informace o instalaci

Nainstalujte GroupDocs.Viewer pomocí konzole Správce balíčků NuGet nebo rozhraní .NET CLI:

**Konzola Správce balíčků NuGet**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**Rozhraní příkazového řádku .NET**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Kroky získání licence
- **Bezplatná zkušební verze**Začněte s bezplatnou zkušební verzí a prozkoumejte funkce.
- **Dočasná licence**Získejte dočasnou licenci pro rozšířené vyhodnocení.
- **Nákup**Zvažte zakoupení pro plný přístup a podporu.

### Základní inicializace a nastavení

Po instalaci inicializujte GroupDocs.Viewer ve vašem projektu C#:

```csharp
using System;
using GroupDocs.Viewer;

namespace DocumentRendering
{
    class Program
    {
        static void Main(string[] args)
        {
            // Inicializujte objekt Viewer cestou k vašemu dokumentu.
            using (Viewer viewer = new Viewer("path/to/your/document.oxps"))
            {
                Console.WriteLine("GroupDocs.Viewer is set up and ready!");
            }
        }
    }
}
```

S nakonfigurovaným GroupDocs.Viewer implementujme vykreslování dokumentů OXPS s vypnutými omezeními licence fontů.

## Průvodce implementací

### Vykreslování dokumentů XPS/OXPS s vypnutými omezeními licence písma

#### Přehled
Tato funkce umožňuje vykreslovat dokumenty XPS nebo OXPS a obejít ověřování licencí vložených písem. Je užitečná při práci s proprietárními písmy, která mají licenční omezení.

#### Postupná implementace
**Definování výstupního adresáře a formátu cesty k souboru stránky**
Nastavte si výstupní adresář:

```csharp
string outputDirectory = "YOUR_OUTPUT_DIRECTORY"; // Použijte požadovanou cestu k výstupnímu adresáři
string pageFilePathFormat = System.IO.Path.Combine(outputDirectory, "page_{0}.png");
```
Tento úryvek určuje, kam budou uloženy vykreslené stránky.

**Vytvoření instance prohlížeče**
Inicializujte `Viewer` objekt pro dokument OXPS:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TestFiles.OXPS_EMBEDDED_FONT")) // Nahraďte skutečnou cestou k dokumentu
{
    // Další kroky konfigurace a vykreslování budou zde.
}
```
Tento krok připraví dokument k vykreslení.

**Nastavení možností zobrazení HTML**
Konfigurovat `HtmlViewOptions` vykreslit s vloženými zdroji:

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Tato možnost zajišťuje, že všechny potřebné zdroje jsou vloženy do každého stránkovacího souboru, což usnadňuje offline přístup.

**Zakázat ověřování licencí písem**
Zakažte ověřování licencí písem nastavením této vlastnosti:

```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
Zakázáním tohoto ověřování můžete vykreslovat dokumenty, aniž by vás omezovaly problémy s licencováním písem.

**Vykreslení dokumentu**
Nakonec použijte `View` metoda pro vykreslení dokumentu se zadanými možnostmi:

```csharp
viewer.View(options);
```
Tento příkaz provede proces vykreslování na základě vašich konfigurací.

#### Tipy pro řešení problémů
- **Chybějící písma**Ujistěte se, že jsou v dokumentu nainstalována nebo vložena všechna požadovaná písma.
- **Problémy s cestou k souboru**Zkontrolujte dvakrát cesty k adresářům a názvy souborů, zda neobsahují překlepy.
- **Chyby licence**: Pokud narazíte na problémy s licencováním, ověřte si, zda máte platnou licenci.

## Praktické aplikace

### Případy použití v reálném světě
1. **Platformy pro publikování obsahu**Vykreslování dokumentů s proprietárními fonty bez právních omezení.
2. **Systémy pro správu dokumentů**Zajistěte bezproblémové prohlížení dokumentů na různých platformách.
3. **Právní a finanční odvětví**Zpracování citlivých dokumentů vyžadujících specifické použití písma.
4. **Akademické instituce**Sdílejte výzkumné práce s vloženými diagramy a textem.
5. **Marketingové agentury**Vytvářejte vizuálně konzistentní prezentace a zprávy.

### Možnosti integrace
- Integrace s webovými aplikacemi .NET pro dynamické prohlížení dokumentů.
- Používejte v desktopových aplikacích k zajištění offline přístupu k vykresleným dokumentům.
- Kombinujte s cloudovými úložnými řešeními, jako je Azure Blob Storage nebo AWS S3, pro škálovatelnou správu dokumentů.

## Úvahy o výkonu

### Optimalizace výkonu
- **Správa paměti**Efektivní správa paměti likvidací `Viewer` předměty po použití.
- **Využití zdrojů**Sledování využití zdrojů, zejména při vykreslování velkých dávek dokumentů.
- **Dávkové zpracování**Implementujte dávkové zpracování pro efektivní práci s více dokumenty.

### Nejlepší postupy pro správu paměti .NET pomocí GroupDocs.Viewer
- Vždy zabalte `Viewer` případy v `using` prohlášení k zajištění správné likvidace.
- Profilujte svou aplikaci, abyste identifikovali a řešili úniky paměti nebo oblasti s vysokou spotřebou zdrojů.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak vykreslit dokumenty XPS/OXPS a zároveň zakázat omezení licencí písem pomocí **GroupDocs.Viewer pro .NET**Dodržováním uvedených kroků můžete efektivně spravovat vykreslování dokumentů v různých aplikacích.

Jako další kroky zvažte prozkoumání dalších funkcí GroupDocs.Viewer a jejich integraci do vašich projektů. Experimentujte s různými typy a konfiguracemi dokumentů, abyste mohli plně využít tuto výkonnou knihovnu.

## Sekce Často kladených otázek

1. **Co je GroupDocs.Viewer pro .NET?**
   - Je to všestranná knihovna, která umožňuje vývojářům vykreslovat různé formáty dokumentů v rámci jejich aplikací bez nutnosti instalace nativního softwaru.

2. **Jak mohu řešit problémy s licencováním písem pomocí GroupDocs.Viewer?**
   - Použitím `DisableFontLicenseVerifications` vlastnost, můžete během vykreslování obejít omezení licence písma.

3. **Mohu používat GroupDocs.Viewer v cloudovém prostředí?**
   - Ano, je navržen tak, aby bezproblémově fungoval v rámci cloudových aplikací a služeb.

4. **Jaké jsou některé běžné problémy při integraci GroupDocs.Viewer?**
   - Mezi výzvy může patřit správa závislostí, konfigurace výstupních cest a efektivní zpracování velkých objemů dokumentů.

5. **Je v GroupDocs.Viewer podporována nestandardní fonty?**
   - I když dokáže zpracovat vložená písma, ujistěte se, že všechna potřebná písma jsou k dispozici nebo vložena do dokumentů, abyste předešli problémům s vykreslováním.