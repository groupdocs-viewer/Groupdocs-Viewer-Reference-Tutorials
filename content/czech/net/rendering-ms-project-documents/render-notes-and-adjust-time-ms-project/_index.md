---
title: Vykreslování poznámek a úprava časových jednotek (MS Project)
linktitle: Vykreslování poznámek a úprava časových jednotek (MS Project)
second_title: GroupDocs.Viewer .NET API
description: Zvládněte vykreslování dokumentů MS Project pomocí GroupDocs.Viewer pro .NET. Vykreslujte poznámky, upravujte časové jednotky a prozkoumávejte různé výstupní formáty bez námahy.
type: docs
weight: 11
url: /cs/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Úvod
GroupDocs.Viewer for .NET je výkonné rozhraní API pro vykreslování dokumentů, které umožňuje vývojářům prohlížet a manipulovat s různými formáty dokumentů v rámci jejich aplikací .NET. V tomto tutoriálu se zaměříme na vykreslování poznámek a úpravu časových jednotek speciálně pro dokumenty MS Project.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer for .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu GroupDocs.Viewer for .NET. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
2. Vývojové prostředí: Nastavte si preferované vývojové prostředí s podporou .NET.
3. Dokument MS Project: Připravte si vzorový dokument MS Project k testování.
## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory, abychom mohli začít s vykreslováním dokumentů MS Project:
## Krok 1: Import jmenných prostorů
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nyní, když jsme importovali požadované jmenné prostory, rozdělme každý příklad do několika kroků pro komplexní pochopení.
## Vykreslování dokumentu MS Project do HTML
Chcete-li vykreslit dokument MS Project do formátu HTML s poznámkami, postupujte takto:
### Krok 2: Nastavte výstupní adresář a formát souboru
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Krok 3: Inicializujte objekt prohlížeče a nastavte možnosti
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
## Vykreslování dokumentu MS Project do obrazových formátů
Dokumenty MS Project můžete také vykreslovat do obrazových formátů jako JPG a PNG. Zde je postup:
### Krok 5: Nastavte výstupní adresář a formát souboru pro JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Krok 6: Inicializujte objekt prohlížeče a nastavte možnosti JPG
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
Opakujte podobné kroky pro vykreslování do PNG a dalších obrazových formátů.
## Vykreslování dokumentu MS Project do PDF
Chcete-li vykreslit dokument MS Project do formátu PDF, postupujte následovně:
### Krok 8: Nastavte výstupní adresář a formát souboru pro PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Krok 9: Inicializujte objekt prohlížeče a nastavte možnosti PDF
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
Gratulujeme! Úspěšně jste se naučili vykreslovat dokumenty MS Project a upravovat časové jednotky pomocí GroupDocs.Viewer pro .NET. Zahrňte tyto znalosti do svých projektů a vylepšete možnosti prohlížení dokumentů.
## FAQ
### Mohu vykreslit dokumenty MS Project do jiných formátů kromě HTML, obrázků a PDF?
Ano, GroupDocs.Viewer for .NET podporuje vykreslování do různých formátů, jako jsou DOCX, XLSX, PPTX a další.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.groupdocs.com/).
### Jak mohu získat dočasné licencování pro GroupDocs.Viewer pro .NET?
 Návštěva[tento odkaz](https://purchase.groupdocs.com/temporary-license/) získat dočasnou licenci.
### Kde najdu dokumentaci k GroupDocs.Viewer pro .NET?
 Viz dokumentace[tady](https://reference.groupdocs.com/viewer/net/).
### Kde mohu hledat podporu nebo klást otázky týkající se GroupDocs.Viewer pro .NET?
 Můžete navštívit fórum podpory[tady](https://forum.groupdocs.com/c/viewer/9).