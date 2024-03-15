---
title: Při načítání dokumentů zadejte typ souboru
linktitle: Při načítání dokumentů zadejte typ souboru
second_title: GroupDocs.Viewer .NET API
description: Přečtěte si, jak určit typ souboru při načítání dokumentů pomocí GroupDocs.Viewer for .NET. Vykreslujte přesně různé formáty ve vašich aplikacích .NET.
type: docs
weight: 10
url: /cs/net/advanced-loading/specify-file-type/
---
## Úvod
GroupDocs.Viewer for .NET je všestranné rozhraní API pro vykreslování dokumentů, které podporuje širokou škálu formátů souborů, včetně DOCX, PDF, PPTX a dalších. Zadáním typu souboru při načítání dokumentů můžete uživatelům zajistit přesné vykreslování a plynulé zobrazení.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
- Základní znalost C# a .NET frameworku.
- Visual Studio nainstalované ve vašem systému.
- GroupDocs.Viewer for .NET nainstalovaný ve vašem projektu. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
##
## Importovat jmenné prostory
Nejprve musíte do kódu C# importovat potřebné jmenné prostory. Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro vykreslování dokumentu.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Nastavte výstupní adresář
Definujte adresář, kam chcete uložit vykreslené stránky dokumentu.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
Zadejte formát pro pojmenování výstupních souborů HTML pro každou stránku dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Zadejte možnosti načtení
 Vytvořte instanci souboru`LoadOptions` třídy a nastavte požadovaný typ souboru.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Krok 4: Vložte dokument a vykreslete
 Použijte`Viewer` třídy k načtení dokumentu a jeho vykreslení do formátu HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 5: Zobrazte zprávu o úspěchu
Informujte uživatele, že dokument byl vykreslen úspěšně, a zadejte umístění výstupních souborů.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
tomto tutoriálu jsme se naučili, jak používat GroupDocs.Viewer for .NET k určení typu souboru při načítání dokumentů. Pomocí těchto jednoduchých kroků můžete zajistit přesné vykreslování různých formátů dokumentů ve vašich aplikacích .NET.
## FAQ
### Mohu pomocí GroupDocs.Viewer for .NET vykreslit jiné dokumenty než DOCX?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů souborů, včetně PDF, PPTX, XLSX a dalších.
### Je GroupDocs.Viewer for .NET kompatibilní s .NET Core?
Ano, GroupDocs.Viewer for .NET je kompatibilní s .NET Framework i .NET Core.
### Mohu přizpůsobit výstupní soubory HTML generované GroupDocs.Viewer?
Ano, výstup HTML můžete přizpůsobit pomocí různých možností poskytovaných rozhraním API.
### Vyžaduje GroupDocs.Viewer for .NET nějaké externí závislosti?
Ne, GroupDocs.Viewer for .NET je samostatná knihovna a nevyžaduje žádné externí závislosti.
### Je k dispozici zkušební verze pro GroupDocs.Viewer pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.groupdocs.com/viewer/net/).