---
title: Upravte velikost stránky při vykreslování e-mailových zpráv
linktitle: Upravte velikost stránky při vykreslování e-mailových zpráv
second_title: GroupDocs.Viewer .NET API
description: Přečtěte si, jak upravit velikost stránky při vykreslování e-mailových zpráv do PDF pomocí GroupDocs.Viewer for .NET. Zvyšte efektivitu prohlížení dokumentů.
type: docs
weight: 10
url: /cs/net/rendering-email-messages/adjust-page-size-email/
---
## Úvod
V oblasti vývoje .NET poskytuje GroupDocs.Viewer komplexní řešení pro vykreslování různých formátů dokumentů, včetně e-mailových zpráv. Tento výukový program se zaměřuje na úpravu velikosti stránky při vykreslování e-mailových zpráv do formátu PDF pomocí GroupDocs.Viewer for .NET. Podle kroků uvedených v této příručce se naučíte, jak plynule manipulovat s velikostí stránky tak, aby vyhovovala vašim konkrétním požadavkům.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
### 1. GroupDocs.Viewer pro .NET nainstalován
 Ujistěte se, že máte ve vývojovém prostředí nainstalovaný GroupDocs.Viewer for .NET. Můžete si jej stáhnout z[tady](https://releases.groupdocs.com/viewer/net/).
### 2. Základní pochopení .NET Development
Seznamte se se základy vývoje .NET, včetně programování v C# a práce se soubory.
### 3. IDE (Integrované vývojové prostředí)
Mějte nainstalované IDE, jako je Visual Studio, pro psaní a spouštění kódu .NET.

## Importovat jmenné prostory
Do svého projektu C# importujte potřebné jmenné prostory, abyste mohli využívat funkce GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Nastavte výstupní adresář
Definujte adresář, kam se uloží výstupní soubor PDF.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte cestu k souboru
Zkombinujte výstupní adresář s názvem výstupního souboru.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 3: Inicializujte objekt prohlížeče
Vytvořte instanci třídy Viewer a zadejte cestu k souboru e-mailové zprávy.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## Krok 4: Nakonfigurujte možnosti zobrazení PDF
Vytvořte instanci PdfViewOptions a nastavte cestu k výstupnímu souboru.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## Krok 5: Upravte velikost stránky
Upravte vlastnost velikosti stránky v EmailOptions PdfViewOptions.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## Krok 6: Vykreslení dokumentu
Vyvolejte metodu View objektu prohlížeče a předejte nakonfigurované možnosti PdfViewOptions.
```csharp
viewer.View(options);
```
## Krok 7: Zobrazte zprávu o úspěchu
Informujte uživatele o úspěšném vykreslení a výstupním adresáři.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Na závěr tento tutoriál ukázal, jak upravit velikost stránky při vykreslování e-mailových zpráv do formátu PDF pomocí GroupDocs.Viewer for .NET. Dodržováním těchto podrobných pokynů můžete efektivně manipulovat s velikostmi stránek tak, aby vyhovovaly vašim specifickým požadavkům, a vylepšit tak možnosti prohlížení a správy dokumentů ve vašich aplikacích .NET.
## FAQ
### Je GroupDocs.Viewer kompatibilní s různými formáty e-mailových zpráv?
GroupDocs.Viewer podporuje vykreslování různých formátů e-mailových zpráv, včetně MSG a EML.
### Mohu upravit velikost stránky podle svých preferencí?
Ano, můžete upravit velikost stránky pomocí GroupDocs.Viewer's PdfViewOptions, což nabízí flexibilitu při vykreslování dokumentů.
### Poskytuje GroupDocs.Viewer podporu pro jiné formáty dokumentů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office, obrázků a dalších.
### Je GroupDocs.Viewer vhodný pro aplikace na podnikové úrovni?
GroupDocs.Viewer rozhodně nabízí robustní funkce vhodné pro malé i podnikové aplikace a zajišťuje efektivní vykreslování a správu dokumentů.
### Kde mohu vyhledat pomoc nebo další podporu pro GroupDocs.Viewer?
 Můžete navštívit fórum GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9) hledat pomoc, klást otázky a zapojit se do komunity.