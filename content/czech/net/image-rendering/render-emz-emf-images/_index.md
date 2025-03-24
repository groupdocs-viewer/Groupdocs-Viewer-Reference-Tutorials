---
title: Vykreslování EMZ a EMF obrázků
linktitle: Vykreslování EMZ a EMF obrázků
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat obrázky EMZ a EMF do různých formátů pomocí GroupDocs.Viewer pro .NET. Snadno sledovatelný tutoriál pro vývojáře.
weight: 14
url: /cs/net/image-rendering/render-emz-emf-images/
---

# Vykreslování EMZ a EMF obrázků

## Úvod

GroupDocs.Viewer for .NET je výkonné rozhraní API pro vykreslování dokumentů, které umožňuje vývojářům zobrazovat různé typy dokumentů, včetně obrázků EMZ (Enhanced Windows Metafile) a EMF (Enhanced Metafile) v jejich aplikacích .NET. V tomto tutoriálu prozkoumáme, jak vykreslit obrázky EMZ a EMF do různých formátů, jako jsou HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer pro .NET.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

1.  GroupDocs.Viewer for .NET: Knihovnu si můžete stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Ujistěte se, že máte pro vývoj .NET nastaveno kompatibilní vývojové prostředí.
3. Ukázkové obrázky EMZ/EMF: Mějte k dispozici ukázkové obrázky EMZ a EMF pro vykreslení.

## Importovat jmenné prostory

Než se ponoříme do kódu, importujme potřebné jmenné prostory:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Nyní si každý příklad rozdělíme do několika kroků ve formátu podrobného průvodce:

## Vykreslování EMZ/EMF obrázků do HTML

### Krok 1: Nastavte výstupní adresář:
```csharp
string outputDirectory = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` cestou, kam chcete uložit vykreslený soubor HTML.

### Krok 2: Definujte formát cesty souboru stránky:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Tím určíte formát cesty k souboru vykresleného souboru HTML.

### Krok 3: Vykreslení do HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Tento kód inicializuje`Viewer` objekt s ukázkovým obrázkem EMZ a vykreslí jej do formátu HTML pomocí zadaných voleb.

## Vykreslování EMZ/EMF obrázků do JPG, PNG a PDF

Pro vykreslení do formátů JPG, PNG a PDF opakujte následující kroky:

### Krok 1: Definujte formát cesty souboru stránky:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Upravte název a příponu souboru podle požadovaného výstupního formátu (`jpg`, `png` nebo`pdf`).

### Krok 2: Vykreslení do příslušného formátu:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Upravte možnosti podle výstupního formátu (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Nahradit`JpgViewOptions` s`PngViewOptions` nebo`PdfViewOptions` na základě požadovaného výstupního formátu.

## Závěr

Na závěr, GroupDocs.Viewer for .NET poskytuje bezproblémové řešení pro vykreslování obrázků EMZ a EMF do různých formátů v aplikacích .NET. Podle kroků uvedených v tomto kurzu mohou vývojáři bez námahy integrovat možnosti vykreslování dokumentů do svých aplikací.

## FAQ

### Otázka: Dokáže GroupDocs.Viewer vykreslit jiné formáty dokumentů kromě obrázků EMZ a EMF?
Odpověď: Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů včetně PDF, DOCX, PPTX, XLSX a dalších.

### Otázka: Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.groupdocs.com/).

### Otázka: Nabízí GroupDocs.Viewer podporu pro vývojáře?
 Odpověď: Ano, GroupDocs poskytuje podporu prostřednictvím svého[Fórum](https://forum.groupdocs.com/c/viewer/9) kde mohou vývojáři klást otázky a hledat pomoc.

### Otázka: Mohu si zakoupit dočasnou licenci pro GroupDocs.Viewer pro .NET?
 Odpověď: Ano, dočasné licence je možné zakoupit[tady](https://purchase.groupdocs.com/temporary-license/).

### Otázka: Kde najdu podrobnou dokumentaci k GroupDocs.Viewer pro .NET?
 Odpověď: Můžete se podívat do dokumentace[tady](https://tutorials.groupdocs.com/viewer/net/)pro komplexní návod k používání API.