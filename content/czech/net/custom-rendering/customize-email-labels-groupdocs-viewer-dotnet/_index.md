---
"date": "2025-04-25"
"description": "Naučte se, jak přizpůsobit štítky e-mailů pomocí GroupDocs.Viewer pro .NET v tomto podrobném návodu. Vylepšete uživatelské rozhraní vaší aplikace přejmenováním polí, jako je „Od“ a „Komu“."
"title": "Úprava štítků e-mailů v GroupDocs.Viewer pro .NET – Kompletní průvodce přejmenováním polí"
"url": "/cs/net/custom-rendering/customize-email-labels-groupdocs-viewer-dotnet/"
"weight": 1
---

# Úprava štítků e-mailů v GroupDocs.Viewer pro .NET: Kompletní průvodce přejmenováním polí

## Zavedení

Už vás někdy frustrovaly rigidní názvy polí jako „Od“ a „Komu“ v e-mailových klientech? Úprava těchto popisků na něco intuitivnějšího může výrazně zlepšit uživatelský komfort. Tato příručka vám ukáže, jak pomocí GroupDocs.Viewer pro .NET přejmenovat pole e-mailu při vykreslování zpráv, což vaší aplikaci dodá elegantní vzhled.

![Přizpůsobení štítků e-mailů pomocí GroupDocs.Viewer pro .NET](/viewer/custom-rendering/customize-email-labels-img.png)

**Co se naučíte:**
- Jak nastavit GroupDocs.Viewer pro .NET
- Kroky pro přejmenování polí e-mailu pomocí C#
- Tipy pro optimalizaci výkonu a integraci s jinými systémy

Jste připraveni změnit způsob zobrazování vašich e-mailů? Pojďme se nejprve ponořit do předpokladů!

## Předpoklady

Než začneme, ujistěte se, že máte připraveno následující:

- **Knihovny a závislosti:** Budete potřebovat GroupDocs.Viewer pro .NET verze 25.3.0.
- **Nastavení prostředí:** Tento tutoriál je kompatibilní s projekty .NET Framework a .NET Core.
- **Předpoklady znalostí:** Základní znalost programování v C# a znalost používání NuGet nebo .NET CLI.

## Nastavení GroupDocs.Viewer pro .NET

Chcete-li začít, musíte nainstalovat potřebný balíček. Můžete použít buď konzoli Správce balíčků NuGet, nebo rozhraní .NET CLI:

**Konzola Správce balíčků NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**Rozhraní příkazového řádku .NET**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Získání licence
- **Bezplatná zkušební verze:** Můžete si stáhnout zkušební verzi pro otestování funkcí.
- **Dočasná licence:** Pokud potřebujete prodloužený přístup bez omezení, požádejte o dočasnou licenci.
- **Nákup:** Pro plné a neomezené použití si zakupte licenci od GroupDocs.

Inicializujte a nastavte objekt prohlížeče takto:

```csharp
using (Viewer viewer = new Viewer("SampleEmail.msg"))
{
    // Váš kód zde
}
```

## Průvodce implementací

Pojďme si rozebrat proces přejmenování polí e-mailu na jednotlivé kroky.

### Inicializace prohlížeče e-mailů

Nejprve vytvořte `Viewer` instance s vaším vzorovým souborem e-mailu. Tento objekt je klíčový pro vykreslování e-mailů:

```csharp
using (Viewer viewer = new Viewer("SampleEmail.msg"))
{
    // Další možnosti konfigurace a vykreslování naleznete zde
}
```

#### Konfigurace možností zobrazení HTML

Dále nakonfigurujte možnosti zobrazení HTML pro efektivní zpracování vložených zdrojů:

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

### Přejmenování polí e-mailu

Zde upravujeme názvy polí. Stávající pole namapujeme na nové popisky pomocí struktury podobné slovníku, kterou poskytuje GroupDocs.Viewer.

#### Názvy mapovacích polí

Zde je návod, jak změnit výchozí názvy polí e-mailu:

```csharp
options.EmailOptions.FieldTextMap[Field.From] = "Sender";   // Přejmenujte pole „Od“ na „Odesílatel“.
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";  // Přejmenujte pole „Komu“ na „Příjemce“.
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";     // Přejmenujte pole „Odesláno“ na „Datum“.
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic"; // Přejmenujte pole „Předmět“ na „Téma“.
```

- **Proč?** Vlastní štítky zvyšují uživatelskou přívětivost vaší aplikace a přizpůsobují ji specifickým obchodním požadavkům.

### Vykreslení dokumentu

Nakonec vykreslete dokument se všemi zadanými možnostmi:

```csharp
viewer.View(options);
```

## Praktické aplikace

Tuto funkci lze použít v různých scénářích:

1. **Systémy zákaznické podpory:** Při prezentování protokolů e-mailové komunikace přejmenujte pole pro lepší přehlednost.
2. **Nástroje pro analýzu e-mailů:** Upravte názvy polí tak, aby odpovídaly analytické terminologii.
3. **CRM systémy:** Přizpůsobte popisky jazykovému stylu CRM a zlepšete tak uživatelský zážitek.

## Úvahy o výkonu

Pro zajištění optimálního výkonu při používání GroupDocs.Viewer:
- **Optimalizace využití zdrojů:** Efektivně spravujte paměť likvidací objektů po jejich použití, jak je ukázáno v našem `using` prohlášení.
- **Nejlepší postupy:** Vyhněte se vykreslování velkého množství e-mailů současně. Dávkové zpracování může pomoci zmírnit omezení zdrojů.

## Závěr

Naučili jste se, jak přejmenovat pole e-mailu při vykreslování zpráv pomocí GroupDocs.Viewer pro .NET. Toto přizpůsobení nejen vylepšuje uživatelské rozhraní, ale také umožňuje vaší aplikaci lépe splňovat specifické obchodní potřeby. 

Dále zvažte integraci tohoto řešení do vašeho širšího systému nebo prozkoumejte další funkce GroupDocs.Viewer.

## Sekce Často kladených otázek

**Otázka: Jak mohu začít s GroupDocs.Viewer?**
A: Nainstalujte jej pomocí NuGet nebo .NET CLI a inicializujte objekt Viewer ve vašem projektu C#.

**Otázka: Mohu přejmenovat i jiná pole e-mailu kromě „Od“ a „Komu“?**
A: Ano, použijte FieldTextMap k namapování libovolného pole na vlastní popisek.

**Otázka: Co když je vykreslování e-mailů pomalé?**
A: Zkontrolujte úniky paměti nebo zvažte dávkové zpracování velkých datových sad.

**Otázka: Je GroupDocs.Viewer zdarma?**
A: K dispozici je zkušební verze. Pro plný přístup si zakupte licenci.

**Otázka: Mohu to integrovat s jinými frameworky?**
A: Ano, funguje to dobře s aplikacemi .NET Core a ASP.NET mimo jiné.

## Zdroje
- **Dokumentace:** [Dokumentace prohlížeče GroupDocs](https://docs.groupdocs.com/viewer/net/)
- **Referenční informace k API:** [Referenční informace k API](https://reference.groupdocs.com/viewer/net/)
- **Stáhnout:** [Nejnovější vydání](https://releases.groupdocs.com/viewer/net/)
- **Nákup:** [Koupit GroupDocs](https://purchase.groupdocs.com/buy)
- **Bezplatná zkušební verze:** [Zkušební verze](https://releases.groupdocs.com/viewer/net/)
- **Dočasná licence:** [Žádost o dočasnou licenci](https://purchase.groupdocs.com/temporary-license/)
- **Podpora:** [Fórum podpory GroupDocs](https://forum.groupdocs.com/c/viewer/9)

Začněte vylepšovat vykreslování e-mailů ještě dnes s GroupDocs.Viewer pro .NET!