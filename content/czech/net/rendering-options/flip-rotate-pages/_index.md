---
title: Otočit a otočit stránky
linktitle: Otočit a otočit stránky
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak integrovat Groupdocs.Viewer for .NET do vašich aplikací pro bezproblémové vykreslování, překlápění a otáčení dokumentů.
weight: 12
url: /cs/net/rendering-options/flip-rotate-pages/
---
## Úvod
tomto tutoriálu se ponoříme do funkcí Groupdocs.Viewer pro .NET, konkrétně se zaměříme na překlápění a otáčení stránek. Groupdocs.Viewer for .NET je výkonný nástroj určený k vykreslování dokumentů v různých formátech v rámci aplikací .NET. Ať už vyvíjíte systém správy dokumentů nebo potřebujete integrovat možnosti prohlížení dokumentů do svého softwaru, Groupdocs.Viewer for .NET poskytuje efektivní řešení.
## Předpoklady
Než začneme, ujistěte se, že máte nastaveny následující předpoklady:
### Instalace Groupdocs.Viewer pro .NET
 Chcete-li používat Groupdocs.Viewer pro .NET, musíte balíček nainstalovat pomocí Správce balíčků NuGet. Podrobné pokyny k instalaci naleznete v[dokumentace](https://tutorials.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Ujistěte se, že máte do projektu importovány potřebné jmenné prostory, abyste mohli efektivně využívat Groupdocs.Viewer pro .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Pojďme si proces překlápění a otáčení stránek pomocí Groupdocs.Viewer for .NET rozdělit do jednoduchých kroků:
## Krok 1: Nastavte výstupní adresář a cestu k souboru
Definujte adresář, kam chcete uložit výstupní soubor, a zadejte cestu k výstupnímu souboru.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 2: Inicializujte objekt prohlížeče
Vytvořte instanci třídy Viewer předáním cesty k dokumentu, který chcete zobrazit.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Krok 3: Konfigurace možností zobrazení
Nastavte možnosti zobrazení, jako je určení formátu výstupního souboru a jakákoli další nastavení, jako je otáčení stránky.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Krok 4: Vykreslení dokumentu
Vyvolejte metodu View objektu Viewer a předejte možnosti zobrazení.
```csharp
viewer.View(viewOptions);
```
## Krok 5: Zobrazte zprávu o úspěchu
Informujte uživatele, že dokument byl úspěšně vykreslen, a zadejte výstupní adresář pro ověření.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Na závěr, Groupdocs.Viewer for .NET nabízí výkonné funkce pro vykreslování dokumentů, včetně obracení a otáčení stránek. Podle kroků uvedených v tomto kurzu můžete tyto funkce bez problémů integrovat do svých aplikací .NET a zlepšit tak možnosti prohlížení dokumentů pro vaše uživatele.
## FAQ
### Je Groupdocs.Viewer for .NET kompatibilní se všemi formáty dokumentů?
Ano, Groupdocs.Viewer for .NET podporuje širokou škálu formátů dokumentů, včetně DOCX, PDF, PPTX a dalších.
### Mohu přizpůsobit možnosti zobrazení kromě překlápění a otáčení stránek?
Groupdocs.Viewer for .NET samozřejmě poskytuje různé možnosti přizpůsobení pro prohlížení dokumentů, což vám umožňuje přizpůsobit prostředí vašim požadavkům.
### Je k dispozici bezplatná zkušební verze pro Groupdocs.Viewer pro .NET?
 Ano, můžete využít bezplatnou zkušební verzi Groupdocs.Viewer pro .NET, když navštívíte stránku[webová stránka](https://releases.groupdocs.com/).
### Jak mohu získat podporu pro Groupdocs.Viewer pro .NET?
 Můžete vyhledat pomoc a zapojit se do komunity prostřednictvím[Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Kde mohu získat dočasnou licenci pro Groupdocs.Viewer pro .NET?
 Dočasné licence pro Groupdocs.Viewer for .NET lze získat z webu[nákupní stránku](https://purchase.groupdocs.com/temporary-license/).