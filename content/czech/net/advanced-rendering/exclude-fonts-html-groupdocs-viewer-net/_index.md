---
"date": "2025-04-25"
"description": "Naučte se, jak vyloučit fonty jako Arial z HTML konverzí pomocí GroupDocs.Viewer pro .NET a zajistit tak konzistentní branding napříč platformami."
"title": "Jak vyloučit konkrétní písma z HTML výstupu pomocí GroupDocs.Viewer pro .NET"
"url": "/cs/net/advanced-rendering/exclude-fonts-html-groupdocs-viewer-net/"
"weight": 1
---

# Jak vyloučit písma z HTML výstupu pomocí GroupDocs.Viewer pro .NET

## Zavedení

Při převodu dokumentů do formátu HTML je klíčové udržovat kontrolu nad použitými fonty, zejména pro konzistenci značky. Tento tutoriál vám ukáže, jak vyloučit konkrétní fonty, například Arial, pomocí GroupDocs.Viewer pro .NET. Dodržováním tohoto návodu se naučíte efektivní způsoby správy vykreslování fontů při transformacích dokumentů do HTML.

![Vyloučení konkrétních písem z HTML výstupu v GroupDocs.Viewer pro .NET](/viewer/advanced-rendering/exclude-specific-fonts-from-html-output-img.png)

### Co se naučíte:
- Nastavení a konfigurace GroupDocs.Viewer pro .NET
- Techniky pro vyloučení konkrétních písem z HTML výstupu
- Praktické tipy pro optimalizaci výkonu a integraci s jinými systémy .NET
- Reálné aplikace těchto technik

## Předpoklady

Než začnete, ujistěte se, že máte následující:
- **Knihovny a verze**GroupDocs.Viewer verze 25.3.0 nebo novější.
- **Nastavení prostředí**Vývojové prostředí nastavené s .NET Framework nebo .NET Core.
- **Předpoklady znalostí**Základní znalost vývoje v C# a .NET.

## Nastavení GroupDocs.Viewer pro .NET

### Pokyny k instalaci:

**Použití konzole Správce balíčků NuGet:**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**Použití .NET CLI:**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Získání licence:
Můžete si pořídit bezplatnou zkušební verzi nebo si zakoupit licenci od [Stránka nákupu GroupDocs](https://purchase.groupdocs.com/buy)Pro dočasný přístup zvažte žádost o [dočasná licence](https://purchase.groupdocs.com/temporary-license/).

### Základní inicializace a nastavení:

Zde je návod, jak inicializovat GroupDocs.Viewer ve vašem projektu .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}

using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Vaše konfigurace budou zde
}
```
Toto nastavení zajišťuje, že jste připraveni manipulovat s vykreslováním dokumentů pomocí GroupDocs.Viewer.

## Průvodce implementací

### Vyloučení písem z HTML výstupu

V této části se zaměříme na to, jak vyloučit konkrétní písma z HTML výstupu pomocí GroupDocs.Viewer pro .NET. 

#### Krok 1: Připravte si prostředí
Ujistěte se, že výstupní adresář existuje a je správně nastaven:
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}
```
Tento krok zajistí, že vaše vykreslené soubory budou mít určené umístění.

#### Krok 2: Konfigurace možností zobrazení HTML
Zde je návod, jak nakonfigurovat prohlížeč pro výstup vložených souborů HTML zdrojů:
```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Ten/Ta/To `HtmlViewOptions` Objekt je klíčový pro určení, jak se vaše dokumenty vykreslují do HTML.

#### Krok 3: Vyloučení konkrétních písem
Chcete-li vyloučit písmo Arial, upravte `options` konfigurace:
```csharp
options.FontsToExclude.Add("Arial");
```
Tento řádek říká nástroji GroupDocs.Viewer, aby vynechal písmo Arial z písem, která vkládá do výstupního HTML. Zadáním `FontsToExclude`, získáte kontrolu nad tím, jak se vizuální styl dokumentu zachovává v různých prostředích.

#### Krok 4: Vykreslení dokumentu
Nakonec vykreslete dokument s tímto nastavením:
```csharp
viewer.View(options);
```
Zavoláním `View()`, GroupDocs.Viewer zpracuje váš dokument podle zadaných možností a vygeneruje jej ve formátu HTML bez vyloučených písem.

### Tipy pro řešení problémů
- Ujistěte se, že jsou cesty k souborům správně nastaveny.
- Ověřte, zda používáte kompatibilní verzi GroupDocs.Viewer pro .NET.
- Zkontrolujte si názvy písem, musí se přesně shodovat, včetně citlivosti na velká a malá písmena.

## Praktické aplikace

### Případy použití:
1. **Konzistentní branding**Vyloučte nežádoucí fonty, abyste zajistili konzistenci typografie vaší značky na všech platformách.
2. **Webová integrace**Integrace s CMS systémy, které vyžadují specifická písma pro konzistenci webového designu.
3. **Archivace dokumentů**Archivace dokumentů ve formátu HTML bez zbytečných fontů, čímž se zmenší velikost souboru.

### Možnosti integrace:
- Využijte GroupDocs.Viewer v aplikacích .NET k vytváření vlastních řešení pro prohlížení dokumentů.
- Kombinujte s frameworky jako ASP.NET MVC nebo Blazor pro dynamické vykreslování dokumentů na webu.

## Úvahy o výkonu

Optimalizace výkonu je při práci s rozsáhlými dokumenty klíčová. Zde je několik tipů:

- **Správa zdrojů**Dávejte pozor na využití paměti vaší aplikací, zejména u velkých souborů.
- **Dávkové zpracování**V případě potřeby zpracovávejte dokumenty dávkově, abyste předešli zahlcení systémových zdrojů.
- **Efektivní ukládání do mezipaměti**Implementujte strategie ukládání do mezipaměti pro často používané dokumenty.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak pomocí nástroje GroupDocs.Viewer pro .NET vyloučit konkrétní písma z HTML výstupu. Dodržením těchto kroků si můžete udržet kontrolu nad vizuální prezentací převedených dokumentů. 

Pro další zkoumání zvažte integraci pokročilejších funkcí poskytovaných GroupDocs.Viewer nebo prozkoumejte jeho plné možnosti API.

## Sekce Často kladených otázek

**Q1: Mohu vyloučit více písem najednou?**
Ano, stačí zavolat `options.FontsToExclude.Add("FontName")` pro každé písmo, které chcete vyloučit.

**Q2: Co se stane, když zadané písmo v dokumentu nenajdete?**
GroupDocs.Viewer to bude ignorovat a bude pokračovat ve vykreslování s dostupnými fonty.

**Q3: Existuje omezení počtu písem, které mohu vyloučit?**
Neexistuje žádný konkrétní limit, ale při vyloučení velkého počtu písem je třeba zvážit dopady na výkon.

**Q4: Lze tuto funkci použít s jinými výstupními formáty, jako je PDF nebo obrázky?**
GroupDocs.Viewer podporuje různé formáty, ale specifika vyloučení písem se mohou lišit. Podrobnosti naleznete v dokumentaci.

**Q5: Jak mohu pomocí GroupDocs.Viewer zpracovat různé typy dokumentů?**
Knihovna je všestranná a nativně podporuje více formátů souborů. Seznam podporovaných funkcí pro jednotlivé formáty naleznete v referenční příručce API.

## Zdroje
- **Dokumentace**: [Dokumentace k .NET prohlížeči GroupDocs](https://docs.groupdocs.com/viewer/net/)
- **Referenční informace k API**: [Referenční příručka k rozhraní GroupDocs API](https://reference.groupdocs.com/viewer/net/)
- **Stáhnout**: [Soubory ke stažení GroupDocs](https://releases.groupdocs.com/viewer/net/)
- **Nákup**: [Koupit licenci GroupDocs](https://purchase.groupdocs.com/buy)
- **Bezplatná zkušební verze**: [Získejte bezplatnou zkušební verzi](https://releases.groupdocs.com/viewer/net/)
- **Dočasná licence**: [Žádost o dočasnou licenci](https://purchase.groupdocs.com/temporary-license/)
- **Podpora**: [Fórum podpory GroupDocs](https://forum.groupdocs.com/c/viewer/9)

Jste připraveni posunout své projekty vykreslování dokumentů na další úroveň? Zkuste implementovat tato řešení ještě dnes!