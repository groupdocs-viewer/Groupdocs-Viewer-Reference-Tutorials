---
"date": "2025-04-25"
"description": "Naučte se, jak efektivně extrahovat archivní informace pomocí nástroje GroupDocs.Viewer pro .NET. Tato příručka se zabývá nastavením, příklady kódu a praktickými aplikacemi."
"title": "Jak načíst informace z archivu pomocí GroupDocs.Viewer pro .NET – Komplexní průvodce"
"url": "/cs/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
---

# Jak načíst informace z archivu pomocí GroupDocs.Viewer pro .NET: Komplexní průvodce

## Zavedení

Hledáte způsob, jak efektivně extrahovat podrobné informace z archivních souborů, jako jsou ZIP soubory? Pochopení struktury může být pro správu dokumentů zásadní. Tato příručka vám ukáže, jak ji používat **GroupDocs.Viewer pro .NET** načíst a zobrazit komplexní informace o archivním souboru.

![Načtení informací z archivu pomocí GroupDocs.Viewer pro .NET](/viewer/metadata-properties/retrieve-archive-information.png)

V tomto tutoriálu se budeme zabývat:
- Nastavení GroupDocs.Viewer ve vaší .NET aplikaci
- Načítání informací o zobrazení z archivních souborů
- Zobrazení struktury složek v archivech

Na konci této příručky budete mít důkladné znalosti o implementaci těchto funkcí. Než se ponoříme do kódu, začněme s tím, co potřebujete.

### Předpoklady

Ujistěte se, že máte připravené následující:

- **Knihovny a verze**Nainstalujte si GroupDocs.Viewer pro .NET (verze 25.3.0).
- **Nastavení prostředí**Použijte vhodné vývojové prostředí .NET, jako je Visual Studio.
- **Předpoklady znalostí**Základní znalost jazyka C# a práce se soubory v .NET aplikacích.

## Nastavení GroupDocs.Viewer pro .NET

Chcete-li používat GroupDocs.Viewer pro .NET, nainstalujte si ho pomocí Správce balíčků NuGet:

### Pokyny k instalaci

**Konzola Správce balíčků NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**Rozhraní příkazového řádku .NET**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Získání licence

GroupDocs.Viewer nabízí několik možností licencování:
- **Bezplatná zkušební verze**Prozkoumejte základní funkce.
- **Dočasná licence**Přístup k plným funkcím během hodnocení.
- **Nákup**Pro dlouhodobé používání zvažte zakoupení licence.

Po instalaci a nastavení licence inicializujte ve vaší aplikaci soubor GroupDocs.Viewer. Zde je příklad nastavení:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // Zde použijte funkce prohlížeče.
}
```

## Průvodce implementací

Pro strukturovaný přístup rozdělíme implementaci na klíčové funkce.

### Načíst informace o zobrazení archivních souborů

Pochopení struktury vašeho archivu je klíčové. Zde je návod, jak toho dosáhnout:

#### Inicializace objektu prohlížeče

Vytvořte instanci `Viewer` třída s cestou k archivnímu souboru:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // Váš kód pro zpracování bude zde.
}
```

#### Získat informace o zobrazení

Načíst informace o zobrazení ve formátu JPG:

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### Zobrazit informace o kořenové složce

Pro úplný přehled si vytiskněte podrobnosti o kořenové složce:

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### Rekurzivně číst a vypisovat názvy podsložek

Chcete-li prozkoumat podsložky v archivu, použijte tuto rekurzivní metodu:

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### Praktické aplikace

GroupDocs.Viewer pro .NET lze použít v různých scénářích:
- **Systémy pro správu dokumentů**: Automaticky extrahovat a zobrazit struktury archivu.
- **Platformy pro distribuci obsahu**: Poskytnout uživatelům náhledy archivovaného obsahu.
- **Nástroje pro analýzu dat**Analyzujte hierarchie složek v archivech pro obchodní přehledy.

Integrace s jinými frameworky, jako je ASP.NET nebo WPF, je přímočará a umožňuje bezproblémové začlenění do stávajících systémů.

## Úvahy o výkonu

Pro optimální výkon:
- **Optimalizace využití zdrojů**Efektivní správa paměti a zpracování velkých souborů.
- **Nejlepší postupy pro správu paměti**: Zlikvidujte `Viewer` objekty správně, aby se zdroje rychle uvolnily.

## Závěr

tomto tutoriálu jste se naučili, jak používat GroupDocs.Viewer pro .NET k načtení podrobných informací z archivních souborů. Implementace těchto funkcí může výrazně vylepšit vaše možnosti správy dokumentů.

### Další kroky

Zvažte prozkoumání pokročilejších funkcí, které nabízí GroupDocs.Viewer, nebo jeho integraci s dalšími komponentami vaší aplikace. Experimentujte s různými typy souborů a složitými strukturami složek, abyste si prohloubili znalosti.

## Sekce Často kladených otázek

1. **Jaký je účel `ViewInfoOptions`?**
   - Konfiguruje způsob zobrazení dokumentu, například vykreslování specifických formátů, jako je JPG.

2. **Jak efektivně zpracovat velké archivy?**
   - Používejte techniky správy paměti a správně nakládejte se zdroji.

3. **Může GroupDocs.Viewer zpracovávat soubory chráněné heslem?**
   - Ano, se správnou licencí a konfigurací dokáže zpracovat šifrované dokumenty.

4. **Existuje nějaký limit velikosti archivního souboru, který lze zpracovat?**
   - Limit závisí na kapacitě paměti vašeho systému; větší soubory vyžadují více zdrojů.

5. **Jak integruji GroupDocs.Viewer s aplikacemi ASP.NET?**
   - Použijte třídu Viewer v rámci akcí nebo služeb kontroleru, podobně jako v konzolové aplikaci.

## Zdroje

- [Dokumentace](https://docs.groupdocs.com/viewer/net/)
- [Referenční informace k API](https://reference.groupdocs.com/viewer/net/)
- [Stáhnout GroupDocs.Viewer pro .NET](https://releases.groupdocs.com/viewer/net/)
- [Zakoupit licenci](https://purchase.groupdocs.com/buy)
- [Bezplatná zkušební verze](https://releases.groupdocs.com/viewer/net/)
- [Žádost o dočasnou licenci](https://purchase.groupdocs.com/temporary-license/)
- [Fórum podpory](https://forum.groupdocs.com/c/viewer/9)