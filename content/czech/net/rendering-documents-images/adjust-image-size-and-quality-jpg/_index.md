---
title: Upravit velikost a kvalitu obrázku (JPG)
linktitle: Upravit velikost a kvalitu obrázku (JPG)
second_title: GroupDocs.Viewer .NET API
description: Naučte se optimalizovat velikost a kvalitu obrázku ve formátu JPEG pomocí Groupdocs.Viewer pro .NET. Vylepšete si zážitek ze sledování dokumentů.
weight: 11
url: /cs/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Úvod
Groupdocs.Viewer for .NET je výkonná knihovna, která umožňuje vývojářům bezproblémově integrovat funkce prohlížení dokumentů do jejich aplikací .NET. Jedním z běžných požadavků v aplikacích pro prohlížení dokumentů je schopnost upravit velikost a kvalitu obrázků, zejména při práci s obrázky JPEG (JPG). V tomto tutoriálu vás provedeme procesem úpravy velikosti a kvality obrazu pomocí Groupdocs.Viewer pro .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Základní znalost programovacího jazyka C#.
2. Visual Studio nainstalované ve vašem systému.
3.  Nainstalovaná knihovna Groupdocs.Viewer for .NET. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Nejprve musíte do kódu C# importovat potřebné jmenné prostory. Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro práci s Groupdocs.Viewer.
## Krok 1: Import jmenných prostorů
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si pro lepší pochopení rozdělíme poskytnutý příklad kódu do několika kroků.
## Krok 2: Nastavte výstupní adresář a formát cesty k souboru stránky
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
V tomto kroku určíme výstupní adresář, kam se budou ukládat vykreslené obrázky, a definujeme formát pro cestu k souboru každého obrázku stránky.
## Krok 3: Inicializujte prohlížeč a nakonfigurujte možnosti zobrazení JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Zde inicializujeme objekt Viewer s cestou k dokumentu, který má být zobrazen. Poté vytvoříme instanci JpgViewOptions a nastavíme požadovanou šířku a výšku obrázků JPEG.
## Krok 4: Vykreslení zdrojového dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nakonec vytiskneme zprávu o úspěšném vykreslení zdrojového dokumentu a umístění, kam jsou uloženy výstupní obrázky.

## Závěr
tomto tutoriálu jsme se naučili, jak upravit velikost a kvalitu obrázků JPEG pomocí Groupdocs.Viewer pro .NET. Podle výše uvedených kroků můžete tuto funkci snadno začlenit do svých aplikací .NET a poskytnout uživatelům optimalizovaný zážitek ze sledování obrázků.
## FAQ
### Mohu upravit i kvalitu obrazu?
Ano, kvalitu obrazu můžete upravit nastavením vlastnosti Quality v JpgViewOptions.
### Jaké formáty dokumentů podporuje Groupdocs.Viewer pro .NET?
Groupdocs.Viewer for .NET podporuje širokou škálu formátů dokumentů včetně DOCX, PDF, PPTX, XLSX a dalších.
### Je Groupdocs.Viewer for .NET kompatibilní s .NET Core?
Ano, Groupdocs.Viewer for .NET je kompatibilní s .NET Core spolu s tradičním .NET Framework.
### Mohu přizpůsobit formát pojmenování výstupního souboru?
Ano, formát pojmenování výstupního souboru můžete přizpůsobit úpravou proměnné pageFilePathFormat v kódu.
### Podporuje Groupdocs.Viewer for .NET anotace dokumentů?
Ano, Groupdocs.Viewer for .NET poskytuje komplexní podporu pro anotace dokumentů včetně zvýraznění textu, podtržení a komentářů.