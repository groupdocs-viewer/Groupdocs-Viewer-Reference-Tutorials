---
title: Vykreslování CDR obrázků
linktitle: Vykreslování CDR obrázků
second_title: GroupDocs.Viewer .NET API
description: Naučte se vykreslovat obrázky CDR do HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer pro .NET. Pomocí tohoto výukového programu můžete snadno převádět soubory CorelDRAW.
type: docs
weight: 12
url: /cs/net/image-rendering/render-cdr-images/
---
## Úvod
V tomto tutoriálu vás provedeme procesem vykreslování obrázků CDR (CorelDRAW) pomocí GroupDocs.Viewer pro .NET. CDR je formát souboru primárně spojený s CorelDRAW, editorem vektorové grafiky. Pomocí GroupDocs.Viewer můžete snadno převádět soubory CDR do různých formátů, jako jsou HTML, JPG, PNG a PDF.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
1.  GroupDocs.Viewer for .NET: Ujistěte se, že jste nainstalovali GroupDocs.Viewer for .NET. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
2. Adresář dokumentů: Připravte si adresář, kam chcete uložit vykreslené obrázky.
3. Základní znalost C#: Pro pochopení příkladů kódu je nutná znalost programovacího jazyka C#.
## Importovat jmenné prostory
Než se ponoříte do příkladů kódu, importujte potřebné jmenné prostory do souboru C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nyní si každý příklad rozdělíme do několika kroků:
## Vykreslování do HTML
1. Definujte výstupní adresář, kam chcete uložit vykreslené soubory HTML:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Zadejte formát cesty k souboru pro soubory HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. K vykreslení souboru CDR do HTML použijte třídu Viewer:
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
2. K vykreslení souboru CDR do formátu JPG použijte třídu Viewer:
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
2. K vykreslení souboru CDR do formátu PNG použijte třídu Viewer:
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
2. K vykreslení souboru CDR do PDF použijte třídu Viewer:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Volitelně můžete zadat volby vykreslování nebo vykreslit konkrétní stránky předáním dalších parametrů`viewer.View()` metoda.
## Závěr
Vykreslování CDR obrázků do různých formátů jako HTML, JPG, PNG a PDF pomocí GroupDocs.Viewer pro .NET je jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete efektivně převádět soubory CDR do různých formátů na základě vašich požadavků.
## FAQ
### Je GroupDocs.Viewer for .NET kompatibilní se všemi verzemi souborů CDR?
GroupDocs.Viewer for .NET podporuje vykreslování souborů CDR vytvořených různými verzemi aplikace CorelDRAW.
### Mohu přizpůsobit výstup vykreslených souborů?
Ano, GroupDocs.Viewer for .NET poskytuje různé možnosti přizpůsobení výstupu, jako je úprava kvality obrazu, nastavení vodoznaku atd.
### Vyžaduje GroupDocs.Viewer for .NET nějaké externí závislosti?
Ne, GroupDocs.Viewer for .NET je samostatná knihovna a pro vykreslování dokumentů nevyžaduje žádné externí závislosti.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi GroupDocs.Viewer pro .NET z[tady](https://releases.groupdocs.com/).
### Kde mohu získat podporu pro GroupDocs.Viewer pro .NET?
 Podporu můžete získat na fóru komunity GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9).