---
"description": "Naučte se, jak upravit velikost stránky při vykreslování e-mailových zpráv do PDF pomocí GroupDocs.Viewer pro .NET. Zvyšte efektivitu prohlížení dokumentů."
"linktitle": "Úprava velikosti stránky při vykreslování e-mailových zpráv"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Úprava velikosti stránky při vykreslování e-mailových zpráv"
"url": "/cs/net/rendering-email-messages/adjust-page-size-email/"
"weight": 10
type: docs
---
# Úprava velikosti stránky při vykreslování e-mailových zpráv

## Zavedení
V oblasti vývoje pro .NET nabízí GroupDocs.Viewer komplexní řešení pro vykreslování různých formátů dokumentů, včetně e-mailových zpráv. Tento tutoriál se zaměřuje na úpravu velikosti stránky při vykreslování e-mailových zpráv do formátu PDF pomocí GroupDocs.Viewer pro .NET. Dodržováním kroků uvedených v tomto průvodci se naučíte, jak bezproblémově manipulovat s velikostí stránky tak, aby splňovala vaše specifické požadavky.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
### 1. Nainstalován GroupDocs.Viewer pro .NET
Ujistěte se, že máte ve svém vývojovém prostředí nainstalovaný GroupDocs.Viewer pro .NET. Můžete si ho stáhnout z [zde](https://releases.groupdocs.com/viewer/net/).
### 2. Základní znalosti vývoje v .NET
Seznamte se se základy vývoje v .NET, včetně programování v C# a práce se soubory.
### 3. IDE (integrované vývojové prostředí)
Mějte nainstalované IDE, například Visual Studio, pro psaní a spouštění kódu .NET.

## Importovat jmenné prostory
Ve vašem projektu C# importujte potřebné jmenné prostory pro využití funkcí GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Nastavení výstupního adresáře
Definujte adresář, kam bude uložen výstupní soubor PDF.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování cesty k souboru
Spojte výstupní adresář s názvem výstupního souboru.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 3: Inicializace objektu prohlížeče
Vytvořte instanci třídy Viewer a zadejte cestu k souboru e-mailové zprávy.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## Krok 4: Konfigurace možností zobrazení PDF
Vytvořte instanci PdfViewOptions a nastavte cestu k výstupnímu souboru.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## Krok 5: Úprava velikosti stránky
Upravte vlastnost velikosti stránky v EmailOptions v PdfViewOptions.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## Krok 6: Vykreslení dokumentu
Vyvolejte metodu View objektu prohlížeče a předejte jí nakonfigurované možnosti PdfViewOptions.
```csharp
viewer.View(options);
```
## Krok 7: Zobrazení zprávy o úspěchu
Informujte uživatele o úspěšném vykreslení a výstupním adresáři.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
Závěrem lze říci, že tento tutoriál ukázal, jak upravit velikost stránky při vykreslování e-mailových zpráv do formátu PDF pomocí GroupDocs.Viewer pro .NET. Dodržováním těchto podrobných pokynů můžete efektivně manipulovat s velikostmi stránek tak, aby splňovaly vaše specifické požadavky, a vylepšit tak možnosti prohlížení a správy dokumentů ve vašich aplikacích .NET.
## Často kladené otázky
### Je GroupDocs.Viewer kompatibilní s různými formáty e-mailových zpráv?
GroupDocs.Viewer podporuje vykreslování různých formátů e-mailových zpráv, včetně MSG a EML.
### Mohu si přizpůsobit velikost stránky podle mých tutoriálů?
Ano, velikost stránky můžete upravit pomocí PdfViewOptions v GroupDocs.Viewer, což nabízí flexibilitu při vykreslování dokumentů.
### Poskytuje GroupDocs.Viewer podporu i pro jiné formáty dokumentů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office, obrázků a dalších.
### Je GroupDocs.Viewer vhodný pro podnikové aplikace?
GroupDocs.Viewer rozhodně nabízí robustní funkce vhodné pro malé i podnikové aplikace a zajišťuje efektivní vykreslování a správu dokumentů.
### Kde mohu hledat pomoc nebo další podporu pro GroupDocs.Viewer?
Můžete navštívit fórum GroupDocs.Viewer [zde](https://forum.groupdocs.com/c/viewer/9) vyhledat pomoc, klást otázky a zapojit se do komunity.