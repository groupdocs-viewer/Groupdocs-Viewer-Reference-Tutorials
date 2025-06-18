---
"description": "Vylepšete si prohlížení dokumentů s GroupDocs.Viewer pro .NET. Bezproblémově vykreslujte a upravujte e-maily."
"linktitle": "Přejmenování polí e-mailu během vykreslování"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Přejmenování polí e-mailu během vykreslování"
"url": "/cs/net/rendering-email-messages/rename-email-fields/"
"weight": 12
---

# Přejmenování polí e-mailu během vykreslování

## Zavedení

V dnešní digitální době je efektivní správa a prohlížení dokumentů zásadní pro firmy i jednotlivce. Ať už se jedná o smlouvy, zprávy nebo e-maily, možnost bezproblémové procházení těchto dokumentů může výrazně zvýšit produktivitu. A právě zde přichází na řadu GroupDocs.Viewer pro .NET. Tato výkonná knihovna umožňuje vývojářům integrovat funkce prohlížení dokumentů přímo do jejich .NET aplikací a nabízí širokou škálu funkcí pro vykreslování různých formátů dokumentů.

## Předpoklady

Než se ponoříte do tutoriálu o přejmenování polí e-mailu během vykreslování pomocí GroupDocs.Viewer pro .NET, ujistěte se, že máte následující předpoklady:

1. Knihovna GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte knihovnu GroupDocs.Viewer pro .NET z [zde](https://releases.groupdocs.com/viewer/net/).

2. Vývojové prostředí: Ujistěte se, že máte nastavené vhodné vývojové prostředí pro vývoj v .NET, například Visual Studio.

3. Základní znalost jazyka C#: Seznamte se se základy programovacího jazyka C#, protože tutoriál bude zahrnovat úryvky kódu v jazyce C#.

4. Adresář dokumentů: Připravte adresář, kde budou uloženy dokumenty, které mají být vykresleny.

## Importovat jmenné prostory

Abyste mohli ve své .NET aplikaci používat funkce GroupDocs.Viewer, musíte importovat potřebné jmenné prostory.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme proces přejmenování polí e-mailu během vykreslování pomocí GroupDocs.Viewer pro .NET do několika kroků:

## Krok 1: Definování výstupního adresáře

Nejprve určete adresář, kam budou uloženy vykreslené HTML stránky.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Definování formátu cesty k souboru stránky

Definujte formát cest k souborům vykreslených HTML stránek. Každá stránka bude uložena jako samostatný HTML soubor.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Inicializace objektu prohlížeče

Vytvořte instanci třídy Viewer a jako parametr předejte cestu k dokumentu, který se má zobrazit.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Krok 4: Konfigurace možností zobrazení HTML

Nakonfigurujte možnosti zobrazení HTML, včetně určení formátu výstupního souboru a nastavení mapování polí e-mailu.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Krok 5: Vykreslení dokumentu

Volejte metodu View objektu Viewer a předejte jí nakonfigurované možnosti zobrazení HTML.

```csharp
viewer.View(options);
```

## Krok 6: Zobrazení zprávy o úspěchu

Informujte uživatele, že dokument byl úspěšně vykreslen.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Závěrem lze říci, že GroupDocs.Viewer pro .NET poskytuje bezproblémové řešení pro vykreslování dokumentů v .NET aplikacích. Dodržováním kroků popsaných v tomto tutoriálu můžete snadno přejmenovat pole e-mailů během vykreslování, čímž se zlepší čitelnost a použitelnost e-mailových dokumentů. Díky intuitivnímu API a komplexním funkcím umožňuje GroupDocs.Viewer vývojářům efektivně zefektivnit procesy prohlížení dokumentů.

## Často kladené otázky

### Otázka: Mohu pomocí GroupDocs.Viewer pro .NET vykreslovat i jiné dokumenty než e-maily?

A: Ano, GroupDocs.Viewer podporuje vykreslování různých formátů dokumentů, včetně PDF, dokumentů Microsoft Office, obrázků a dalších.

### Otázka: Je GroupDocs.Viewer kompatibilní s .NET Core?

A: Ano, GroupDocs.Viewer podporuje .NET Core spolu s tradičním .NET Frameworkem.

### Otázka: Mohu si přizpůsobit vzhled vykreslených dokumentů?

A: Rozhodně, GroupDocs.Viewer nabízí rozsáhlé možnosti přizpůsobení pro ovládání vzhledu a chování vykreslených dokumentů.

### Otázka: Podporuje GroupDocs.Viewer streamování dokumentů?

A: Ano, GroupDocs.Viewer umožňuje streamování dokumentů přímo do prohlížeče klienta bez nutnosti jejich ukládání na server.

### Otázka: Je GroupDocs.Viewer vhodný pro podnikové aplikace?

A: GroupDocs.Viewer je jistě navržen tak, aby splňoval požadavky podnikových aplikací díky své škálovatelnosti, spolehlivosti a robustní sadě funkcí.