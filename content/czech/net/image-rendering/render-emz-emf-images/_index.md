---
"description": "Naučte se, jak vykreslovat obrázky EMZ a EMF do různých formátů pomocí GroupDocs.Viewer pro .NET. Snadno srozumitelný tutoriál pro vývojáře."
"linktitle": "Renderování obrázků EMZ a EMF"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Renderování obrázků EMZ a EMF"
"url": "/cs/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# Renderování obrázků EMZ a EMF

## Zavedení

GroupDocs.Viewer pro .NET je výkonné API pro vykreslování dokumentů, které umožňuje vývojářům zobrazovat v jejich .NET aplikacích různé typy dokumentů, včetně obrázků EMZ (Enhanced Windows Metafile) a EMF (Enhanced Metafile). V tomto tutoriálu se podíváme na to, jak pomocí GroupDocs.Viewer pro .NET vykreslit obrázky EMZ a EMF do různých formátů, jako jsou HTML, JPG, PNG a PDF.

![Renderování obrázků EMZ a EMF pomocí GroupDocs.Viewer pro .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

1. GroupDocs.Viewer pro .NET: Knihovnu si můžete stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Ujistěte se, že máte nastavené kompatibilní vývojové prostředí pro vývoj v .NET.
3. Ukázkové obrázky EMZ/EMF: Mějte k dispozici ukázkové obrázky EMZ a EMF pro vykreslení.

## Importovat jmenné prostory

Než se ponoříme do kódu, importujme potřebné jmenné prostory:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Nyní si každý příklad rozdělme do několika kroků ve formátu podrobného návodu:

## Vykreslování obrázků EMZ/EMF do HTML

### Krok 1: Nastavení výstupního adresáře:
```csharp
string outputDirectory = "Your Document Directory";
```
Nahradit `"Your Document Directory"` s cestou, kam chcete uložit vykreslený soubor HTML.

### Krok 2: Definování formátu cesty k souboru stránky:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Toto určí formát cesty k souboru pro vykreslený HTML soubor.

### Krok 3: Vykreslení do HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Tento kód inicializuje `Viewer` objekt s ukázkovým obrázkem EMZ a vykreslí jej do formátu HTML pomocí zadaných možností.

## Renderování obrázků EMZ/EMF do formátů JPG, PNG a PDF

Pro vykreslení do formátů JPG, PNG a PDF opakujte následující kroky:

### Krok 1: Definování formátu cesty k souboru stránky:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Upravte název a příponu souboru podle požadovaného výstupního formátu (`jpg`, `png`, nebo `pdf`).

### Krok 2: Vykreslení do příslušného formátu:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Upravte možnosti podle výstupního formátu (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Nahradit `JpgViewOptions` s `PngViewOptions` nebo `PdfViewOptions` na základě požadovaného výstupního formátu.

## Závěr

Závěrem lze říci, že GroupDocs.Viewer pro .NET poskytuje bezproblémové řešení pro vykreslování obrázků EMZ a EMF do různých formátů v aplikacích .NET. Dodržením kroků popsaných v tomto tutoriálu mohou vývojáři snadno integrovat funkce vykreslování dokumentů do svých aplikací.

## Často kladené otázky

### Otázka: Může GroupDocs.Viewer vykreslit i jiné formáty dokumentů než obrázky EMZ a EMF?
A: Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, DOCX, PPTX, XLSX a dalších.

### Otázka: Je k dispozici bezplatná zkušební verze GroupDocs.Viewer pro .NET?
A: Ano, máte přístup k bezplatné zkušební verzi [zde](https://releases.groupdocs.com/).

### Otázka: Nabízí GroupDocs.Viewer podporu pro vývojáře?
A: Ano, GroupDocs poskytuje podporu prostřednictvím svých [forum](https://forum.groupdocs.com/c/viewer/9) kde se vývojáři mohou ptát a vyhledávat pomoc.

### Otázka: Mohu si zakoupit dočasnou licenci pro GroupDocs.Viewer pro .NET?
A: Ano, dočasné licence jsou k dispozici ke koupi. [zde](https://purchase.groupdocs.com/temporary-license/).

### Otázka: Kde najdu podrobnou dokumentaci k GroupDocs.Viewer pro .NET?
A: Můžete se podívat na dokumentaci [zde](https://tutorials.groupdocs.com/viewer/net/) pro komplexní pokyny k používání API.