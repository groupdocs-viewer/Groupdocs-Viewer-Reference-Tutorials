---
"description": "Zvládněte renderování dokumentů MS Project s GroupDocs.Viewer pro .NET. Renderujte poznámky, upravujte časové jednotky a prozkoumávejte různé výstupní formáty bez námahy."
"linktitle": "Vykreslení poznámek a úprava časových jednotek (MS Project)"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení poznámek a úprava časových jednotek (MS Project)"
"url": "/cs/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# Vykreslení poznámek a úprava časových jednotek (MS Project)

## Zavedení
GroupDocs.Viewer pro .NET je výkonné API pro vykreslování dokumentů, které umožňuje vývojářům prohlížet a manipulovat s různými formáty dokumentů v rámci jejich .NET aplikací. V tomto tutoriálu se zaměříme na vykreslování poznámek a úpravu časových jednotek konkrétně pro dokumenty MS Project.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer pro .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu GroupDocs.Viewer pro .NET. Můžete si ji stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Nastavte si preferované vývojové prostředí s podporou .NET.
3. Dokument MS Project: Mějte připravený vzorový dokument MS Project k testování.
## Importovat jmenné prostory
Nejprve si importujme potřebné jmenné prostory, abychom mohli začít s vykreslováním dokumentů MS Project:
## Krok 1: Import jmenných prostorů
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nyní, když jsme importovali požadované jmenné prostory, rozdělme si každý příklad do několika kroků pro komplexní pochopení.
## Vykreslování dokumentu MS Project do HTML
Chcete-li vykreslit dokument MS Project do formátu HTML s poznámkami, postupujte takto:
### Krok 2: Nastavení výstupního adresáře a formátu souboru
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Krok 3: Inicializace objektu prohlížeče a nastavení možností
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 4: Vykreslení dokumentu do HTML
```csharp
viewer.View(options);
```
## Vykreslování dokumentů MS Project do obrazových formátů
Dokumenty MS Project můžete také vykreslit do obrazových formátů, jako jsou JPG a PNG. Postupujte takto:
### Krok 5: Nastavení výstupního adresáře a formátu souboru pro JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Krok 6: Inicializace objektu prohlížeče a nastavení možností JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 7: Vykreslení dokumentu do formátu JPG
```csharp
viewer.View(options);
```
Podobné kroky opakujte pro vykreslování do PNG a dalších obrazových formátů.
## Vykreslení dokumentu MS Project do PDF
Chcete-li vykreslit dokument MS Project do formátu PDF, postupujte takto:
### Krok 8: Nastavení výstupního adresáře a formátu souboru pro PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Krok 9: Inicializace objektu prohlížeče a nastavení možností PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 10: Vykreslení dokumentu do PDF
```csharp
viewer.View(options);
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vykreslovat dokumenty MS Project a upravovat časové jednotky pomocí GroupDocs.Viewer pro .NET. Začleňte tyto znalosti do svých projektů a vylepšete si možnosti prohlížení dokumentů.
## Často kladené otázky
### Mohu vykreslit dokumenty MS Project do jiných formátů než HTML, obrázků a PDF?
Ano, GroupDocs.Viewer pro .NET podporuje vykreslování do různých formátů, jako jsou DOCX, XLSX, PPTX a další.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete získat bezplatnou zkušební verzi od [zde](https://releases.groupdocs.com/).
### Jak mohu získat dočasnou licenci pro GroupDocs.Viewer pro .NET?
Návštěva [tento odkaz](https://purchase.groupdocs.com/temporary-license/) k získání dočasné licence.
### Kde najdu dokumentaci k GroupDocs.Viewer pro .NET?
Viz dokumentace [zde](https://tutorials.groupdocs.com/viewer/net/).
### Kde mohu vyhledat podporu nebo se zeptat na otázky týkající se GroupDocs.Viewer pro .NET?
Můžete navštívit fórum podpory [zde](https://forum.groupdocs.com/c/viewer/9).