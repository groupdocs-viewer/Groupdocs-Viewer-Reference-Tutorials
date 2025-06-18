---
"description": "Naučte se, jak optimalizovat velikost a kvalitu obrázků ve formátu JPEG pomocí nástroje Groupdocs.Viewer pro .NET. Vylepšete si zážitek ze prohlížení dokumentů."
"linktitle": "Úprava velikosti a kvality obrázku (JPG)"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Úprava velikosti a kvality obrázku (JPG)"
"url": "/cs/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Úprava velikosti a kvality obrázku (JPG)

## Zavedení
Groupdocs.Viewer pro .NET je výkonná knihovna, která umožňuje vývojářům bezproblémově integrovat funkce prohlížení dokumentů do jejich .NET aplikací. Jedním z běžných požadavků v aplikacích pro prohlížení dokumentů je možnost upravovat velikost a kvalitu obrázků, zejména při práci s obrázky JPEG (JPG). V tomto tutoriálu vás provedeme procesem úpravy velikosti a kvality obrázků pomocí Groupdocs.Viewer pro .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Základní znalost programovacího jazyka C#.
2. Visual Studio nainstalované ve vašem systému.
3. Je nainstalována knihovna Groupdocs.Viewer pro .NET. Můžete si ji stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Nejprve je třeba importovat potřebné jmenné prostory do kódu C#. Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro práci s Groupdocs.Viewer.
## Krok 1: Import jmenných prostorů
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nyní si pro lepší pochopení rozdělme uvedený příklad kódu do několika kroků.
## Krok 2: Nastavení výstupního adresáře a formátu cesty k souboru stránky
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
V tomto kroku určíme výstupní adresář, kam budou uloženy vykreslené obrázky, a definujeme formát cesty k souboru každého obrázku stránky.
## Krok 3: Inicializace prohlížeče a konfigurace možností zobrazení JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Zde inicializujeme objekt Viewer cestou k dokumentu, který se má zobrazit. Poté vytvoříme instanci JpgViewOptions a nastavíme požadovanou šířku a výšku obrázků JPEG.
## Krok 4: Vykreslení zdrojového dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nakonec vypíšeme zprávu o úspěšném vykreslení zdrojového dokumentu a umístění, kam jsou uloženy výstupní obrázky.

## Závěr
tomto tutoriálu jsme se naučili, jak upravit velikost a kvalitu obrázků JPEG pomocí nástroje Groupdocs.Viewer pro .NET. Dodržením výše uvedených kroků můžete tuto funkci snadno začlenit do svých aplikací .NET a poskytnout tak uživatelům optimalizovaný zážitek z prohlížení obrázků.
## Často kladené otázky
### Mohu si také upravit kvalitu obrazu?
Ano, kvalitu obrázku můžete upravit nastavením vlastnosti Quality v JpgViewOptions.
### Jaké formáty dokumentů podporuje Groupdocs.Viewer pro .NET?
Groupdocs.Viewer pro .NET podporuje širokou škálu formátů dokumentů, včetně DOCX, PDF, PPTX, XLSX a dalších.
### Je Groupdocs.Viewer pro .NET kompatibilní s .NET Core?
Ano, Groupdocs.Viewer pro .NET je kompatibilní s .NET Core i s tradičním .NET Frameworkem.
### Mohu si přizpůsobit formát pojmenování výstupních souborů?
Ano, formát pojmenování výstupních souborů můžete přizpůsobit úpravou proměnné pageFilePathFormat v kódu.
### Podporuje Groupdocs.Viewer pro .NET anotace dokumentů?
Ano, Groupdocs.Viewer pro .NET poskytuje komplexní podporu pro anotace dokumentů, včetně zvýrazňování textu, podtrhávání a komentování.