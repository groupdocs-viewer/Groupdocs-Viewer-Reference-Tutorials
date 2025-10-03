---
"description": "Naučte se, jak vykreslit obrázky CDR do formátu HTML, JPG, PNG a PDF pomocí nástroje GroupDocs.Viewer pro .NET. S tímto tutoriálem snadno převedete soubory CorelDRAW."
"linktitle": "Vykreslení obrázků CDR"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Vykreslení obrázků CDR"
"url": "/cs/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# Vykreslení obrázků CDR

## Zavedení
tomto tutoriálu vás provedeme procesem vykreslování obrázků CDR (CorelDRAW) pomocí nástroje GroupDocs.Viewer pro .NET. CDR je formát souboru primárně spojený s CorelDRAW, editorem vektorové grafiky. Pomocí nástroje GroupDocs.Viewer můžete snadno převádět soubory CDR do různých formátů, jako jsou HTML, JPG, PNG a PDF.

![Vykreslení obrázků CDR pomocí GroupDocs.Viewer pro .NET](/viewer/image-rendering/render-cdr-images.png)

## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
1. GroupDocs.Viewer pro .NET: Ujistěte se, že máte nainstalovaný GroupDocs.Viewer pro .NET. Můžete si ho stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
2. Adresář dokumentů: Připravte si adresář, kam chcete ukládat vykreslené obrázky.
3. Základní znalost jazyka C#: Znalost programovacího jazyka C# je nezbytná pro pochopení příkladů kódu.
## Importovat jmenné prostory
Než se ponoříme do příkladů kódu, importujte potřebné jmenné prostory do souboru C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nyní si každý příklad rozdělme do několika kroků:
## Vykreslování do HTML
1. Definujte výstupní adresář, kam chcete ukládat vykreslené soubory HTML:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Zadejte formát cesty k souboru pro soubory HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Pro vykreslení souboru CDR do HTML použijte třídu Viewer:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Vykreslování do JPG
1. Definujte formát cesty k souboru pro soubory JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Pro vykreslení souboru CDR do formátu JPG použijte třídu Viewer:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Vykreslování do PNG
1. Definujte formát cesty k souboru pro soubory PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Pro vykreslení souboru CDR do formátu PNG použijte třídu Viewer:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Vykreslování do PDF
1. Definujte formát cesty k souboru pro PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Pro vykreslení souboru CDR do PDF použijte třídu Viewer:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Volitelně můžete zadat možnosti vykreslování nebo vykreslit konkrétní stránky předáním dalších parametrů do `viewer.View()` metoda.
## Závěr
Vykreslování obrázků CDR do různých formátů, jako je HTML, JPG, PNG a PDF, pomocí GroupDocs.Viewer pro .NET je jednoduchý proces. Dodržováním kroků popsaných v tomto tutoriálu můžete efektivně převádět soubory CDR do různých formátů na základě vašich požadavků.
## Často kladené otázky
### Je GroupDocs.Viewer pro .NET kompatibilní se všemi verzemi souborů CDR?
GroupDocs.Viewer pro .NET podporuje vykreslování souborů CDR vytvořených různými verzemi CorelDRAW.
### Mohu si přizpůsobit výstup vykreslených souborů?
Ano, GroupDocs.Viewer pro .NET nabízí různé možnosti pro přizpůsobení výstupu, jako je úprava kvality obrazu, nastavení vodoznaku atd.
### Vyžaduje GroupDocs.Viewer pro .NET nějaké externí závislosti?
Ne, GroupDocs.Viewer pro .NET je samostatná knihovna a pro vykreslování dokumentů nevyžaduje žádné externí závislosti.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi GroupDocs.Viewer pro .NET z [zde](https://releases.groupdocs.com/).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
Podporu můžete získat na fóru komunity GroupDocs.Viewer. [zde](https://forum.groupdocs.com/c/viewer/9).