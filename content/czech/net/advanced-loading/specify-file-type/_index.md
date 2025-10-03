---
"description": "Naučte se, jak zadat typ souboru při načítání dokumentů pomocí nástroje GroupDocs.Viewer pro .NET. Přesně vykreslujte různé formáty ve svých aplikacích .NET."
"linktitle": "Zadejte typ souboru při načítání dokumentů"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Zadejte typ souboru při načítání dokumentů"
"url": "/cs/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Zadejte typ souboru při načítání dokumentů

## Zavedení
GroupDocs.Viewer pro .NET je všestranné API pro vykreslování dokumentů, které podporuje širokou škálu formátů souborů, včetně DOCX, PDF, PPTX a dalších. Zadáním typu souboru při načítání dokumentů můžete zajistit přesné vykreslování a plynulé prohlížení pro vaše uživatele.

![Zadání typu souboru při načítání dokumentů v GroupDocs.Viewer pro .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
- Základní znalost C# a .NET frameworku.
- Visual Studio nainstalované ve vašem systému.
- Ve vašem projektu je nainstalován GroupDocs.Viewer pro .NET. Můžete si ho stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
##
## Importovat jmenné prostory
Nejprve je třeba do kódu C# importovat potřebné jmenné prostory. Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro vykreslování dokumentů.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavení výstupního adresáře
Definujte adresář, kam chcete ukládat vykreslené stránky dokumentu.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru stránky
Zadejte formát pro pojmenování výstupních souborů HTML pro každou stránku dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Zadejte možnosti načtení
Vytvořte instanci `LoadOptions` třídu a nastavte požadovaný typ souboru.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Krok 4: Načtení dokumentu a vykreslení
Použijte `Viewer` třída pro načtení dokumentu a jeho vykreslení do formátu HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 5: Zobrazení zprávy o úspěchu
Informujte uživatele, že dokument byl úspěšně vykreslen, a uveďte umístění výstupních souborů.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
tomto tutoriálu jsme se naučili, jak pomocí nástroje GroupDocs.Viewer pro .NET určit typ souboru při načítání dokumentů. Dodržením těchto jednoduchých kroků zajistíte přesné vykreslování různých formátů dokumentů ve vašich .NET aplikacích.
## Často kladené otázky
### Mohu pomocí GroupDocs.Viewer pro .NET vykreslovat dokumenty jiné než DOCX?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů souborů, včetně PDF, PPTX, XLSX a dalších.
### Je GroupDocs.Viewer pro .NET kompatibilní s .NET Core?
Ano, GroupDocs.Viewer pro .NET je kompatibilní s .NET Framework i .NET Core.
### Mohu si přizpůsobit výstupní HTML soubory generované nástrojem GroupDocs.Viewer?
Ano, výstup HTML si můžete přizpůsobit pomocí různých možností, které API nabízí.
### Vyžaduje GroupDocs.Viewer pro .NET nějaké externí závislosti?
Ne, GroupDocs.Viewer pro .NET je samostatná knihovna a nevyžaduje žádné externí závislosti.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.groupdocs.com/viewer/net/).