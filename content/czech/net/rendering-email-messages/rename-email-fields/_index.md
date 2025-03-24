---
title: Přejmenujte pole e-mailu během vykreslování
linktitle: Přejmenujte pole e-mailu během vykreslování
second_title: GroupDocs.Viewer .NET API
description: Vylepšete prohlížení dokumentů pomocí GroupDocs.Viewer pro .NET. Bezproblémově vykreslujte a přizpůsobujte e-maily.
weight: 12
url: /cs/net/rendering-email-messages/rename-email-fields/
---

# Přejmenujte pole e-mailu během vykreslování

## Úvod

dnešní digitální době je efektivní správa a prohlížení dokumentů prvořadé pro firmy i jednotlivce. Ať už se jedná o smlouvy, sestavy nebo e-maily, možnost bezproblémového procházení těmito dokumenty může výrazně zvýšit produktivitu. Zde vstupuje do hry GroupDocs.Viewer for .NET. Tato výkonná knihovna umožňuje vývojářům integrovat možnosti prohlížení dokumentů přímo do jejich aplikací .NET a nabízí širokou škálu funkcí pro vykreslování různých formátů dokumentů.

## Předpoklady

Než se pustíte do výukového programu o přejmenování e-mailových polí během vykreslování pomocí GroupDocs.Viewer for .NET, ujistěte se, že máte následující předpoklady:

1.  Knihovna GroupDocs.Viewer for .NET: Stáhněte a nainstalujte knihovnu GroupDocs.Viewer for .NET z[tady](https://releases.groupdocs.com/viewer/net/).

2. Vývojové prostředí: Ujistěte se, že máte pro vývoj .NET nastaveno vhodné vývojové prostředí, jako je Visual Studio.

3. Základní porozumění C#: Seznamte se se základy programovacího jazyka C#, protože tutoriál bude zahrnovat úryvky kódu C#.

4. Adresář dokumentů: Připravte adresář, kde jsou uloženy dokumenty, které se mají vykreslit.

## Importovat jmenné prostory

Abyste mohli používat funkce GroupDocs.Viewer ve vaší aplikaci .NET, musíte importovat potřebné jmenné prostory.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si rozdělme proces přejmenování e-mailových polí během vykreslování pomocí GroupDocs.Viewer for .NET do několika kroků:

## Krok 1: Definujte výstupní adresář

Nejprve zadejte adresář, kam se budou ukládat vykreslené HTML stránky.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Definujte formát cesty k souboru stránky

Definujte formát pro cesty k souborům vykreslených stránek HTML. Každá stránka bude uložena jako samostatný soubor HTML.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Inicializujte objekt prohlížeče

Vytvořte instanci třídy Viewer a předejte cestu k dokumentu, který se má zobrazit, jako parametr.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Krok 4: Nakonfigurujte možnosti zobrazení HTML

Nakonfigurujte možnosti pro zobrazení HTML, včetně zadání formátu výstupního souboru a nastavení mapování e-mailových polí.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Krok 5: Vykreslení dokumentu

Vyvolejte metodu View objektu Viewer a předejte nakonfigurované možnosti zobrazení HTML.

```csharp
viewer.View(options);
```

## Krok 6: Zobrazte zprávu o úspěchu

Informujte uživatele, že dokument byl úspěšně vykreslen.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr

Na závěr, GroupDocs.Viewer for .NET poskytuje bezproblémové řešení pro vykreslování dokumentů v aplikacích .NET. Podle kroků uvedených v tomto kurzu můžete snadno přejmenovat pole e-mailu během vykreslování, čímž se zlepší čitelnost a použitelnost e-mailových dokumentů. Díky intuitivnímu rozhraní API a komplexním funkcím umožňuje GroupDocs.Viewer vývojářům efektivně zefektivnit procesy prohlížení dokumentů.

## FAQ

### Otázka: Mohu pomocí GroupDocs.Viewer for .NET vykreslovat jiné dokumenty než e-maily?

Odpověď: Ano, GroupDocs.Viewer podporuje vykreslování různých formátů dokumentů včetně PDF, dokumentů Microsoft Office, obrázků a dalších.

### Otázka: Je GroupDocs.Viewer kompatibilní s .NET Core?

Odpověď: Ano, GroupDocs.Viewer podporuje .NET Core spolu s tradičním .NET Framework.

### Otázka: Mohu upravit vzhled vykreslených dokumentů?

Odpověď: GroupDocs.Viewer rozhodně nabízí rozsáhlé možnosti přizpůsobení pro ovládání vzhledu a chování vykreslených dokumentů.

### Otázka: Podporuje GroupDocs.Viewer streamování dokumentů?

Odpověď: Ano, GroupDocs.Viewer umožňuje streamování dokumentů přímo do prohlížeče klienta bez nutnosti jejich ukládání na server.

### Otázka: Je GroupDocs.Viewer vhodný pro aplikace na podnikové úrovni?

Odpověď: GroupDocs.Viewer je samozřejmě navržen tak, aby splňoval požadavky aplikací na podnikové úrovni díky své škálovatelnosti, spolehlivosti a robustní sadě funkcí.
