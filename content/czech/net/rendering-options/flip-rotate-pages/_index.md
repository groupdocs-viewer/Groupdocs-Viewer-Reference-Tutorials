---
"description": "Naučte se, jak integrovat Groupdocs.Viewer pro .NET do vašich aplikací pro bezproblémové vykreslování, převrácení a otáčení dokumentů."
"linktitle": "Otočení a převrácení stránek"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Otočení a převrácení stránek"
"url": "/cs/net/rendering-options/flip-rotate-pages/"
"weight": 12
---

# Otočení a převrácení stránek

## Zavedení
tomto tutoriálu se ponoříme do funkcí nástroje Groupdocs.Viewer pro .NET, konkrétně se zaměříme na otáčení a přepínání stránek. Groupdocs.Viewer pro .NET je výkonný nástroj určený k vykreslování dokumentů v různých formátech v rámci .NET aplikací. Ať už vyvíjíte systém pro správu dokumentů, nebo potřebujete do svého softwaru integrovat funkce prohlížení dokumentů, Groupdocs.Viewer pro .NET poskytuje efektivní řešení.
## Předpoklady
Než začneme, ujistěte se, že máte nastaveny následující předpoklady:
### Instalace Groupdocs.Viewer pro .NET
Chcete-li používat Groupdocs.Viewer pro .NET, je třeba nainstalovat balíček pomocí Správce balíčků NuGet. Podrobné pokyny k instalaci naleznete v [dokumentace](https://tutorials.groupdocs.com/viewer/net/).

## Importovat jmenné prostory
Ujistěte se, že máte v projektu importovány potřebné jmenné prostory, abyste mohli efektivně využívat Groupdocs.Viewer pro .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Pojďme si rozebrat proces otáčení a přetáčení stránek pomocí Groupdocs.Viewer pro .NET do jednoduchých kroků:
## Krok 1: Nastavení výstupního adresáře a cesty k souboru
Definujte adresář, kam chcete uložit výstupní soubor, a zadejte cestu k výstupnímu souboru.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 2: Inicializace objektu prohlížeče
Vytvořte instanci třídy Viewer předáním cesty k dokumentu, který chcete zobrazit.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Krok 3: Konfigurace možností zobrazení
Nastavte možnosti zobrazení, například určení formátu výstupního souboru a všechna další nastavení, jako je otočení stránky.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Krok 4: Vykreslení dokumentu
Zavolejte metodu View objektu Viewer a předejte jí možnosti zobrazení.
```csharp
viewer.View(viewOptions);
```
## Krok 5: Zobrazení zprávy o úspěchu
Informujte uživatele, že dokument byl úspěšně vykreslen, a zadejte výstupní adresář pro ověření.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Závěrem lze říci, že Groupdocs.Viewer pro .NET nabízí výkonné funkce pro vykreslování dokumentů, včetně otáčení a přepínání stránek. Dodržováním kroků popsaných v tomto tutoriálu můžete tyto funkce bezproblémově integrovat do svých .NET aplikací a vylepšit tak zážitek z prohlížení dokumentů pro vaše uživatele.
## Často kladené otázky
### Je Groupdocs.Viewer pro .NET kompatibilní se všemi formáty dokumentů?
Ano, Groupdocs.Viewer pro .NET podporuje širokou škálu formátů dokumentů, včetně DOCX, PDF, PPTX a dalších.
### Mohu si přizpůsobit možnosti zobrazení nad rámec otáčení a přepínání stránek?
Rozhodně, Groupdocs.Viewer pro .NET nabízí různé možnosti přizpůsobení prohlížení dokumentů, což vám umožňuje přizpůsobit si zážitek podle vašich požadavků.
### Je k dispozici bezplatná zkušební verze Groupdocs.Viewer pro .NET?
Ano, můžete využít bezplatnou zkušební verzi Groupdocs.Viewer pro .NET na adrese [webové stránky](https://releases.groupdocs.com/).
### Jak mohu získat podporu pro Groupdocs.Viewer pro .NET?
Můžete vyhledat pomoc a zapojit se do komunity prostřednictvím [Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Kde mohu získat dočasnou licenci pro Groupdocs.Viewer pro .NET?
Dočasné licence pro Groupdocs.Viewer pro .NET lze získat od [stránka nákupu](https://purchase.groupdocs.com/temporary-license/).