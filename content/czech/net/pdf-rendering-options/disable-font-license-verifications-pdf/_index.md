---
"description": "Získejte bezproblémové možnosti prohlížení dokumentů ve vašem .NET s GroupDocs.Viewer pro .NET. Snadno integrujte a přizpůsobte vykreslování dokumentů s minimálními závislostmi."
"linktitle": "Zakázat ověřování licencí písem v PDF"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Zakázat ověřování licencí písem v PDF"
"url": "/cs/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
type: docs
---
# Zakázat ověřování licencí písem v PDF

## Zavedení
oblasti vývoje v .NET je správa a manipulace s dokumenty často klíčovým aspektem mnoha aplikací. Ať už se jedná o prohlížení PDF, dokumentů Word nebo jiných typů souborů, je nezbytné mít robustní nástroje pro efektivní zvládnutí těchto úkolů. A zde přichází na řadu GroupDocs.Viewer pro .NET. Tato výkonná knihovna poskytuje vývojářům možnost bezproblémově integrovat funkce prohlížení dokumentů do jejich .NET aplikací.

![Zakázat ověřování licencí písem v PDF pomocí GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## Předpoklady
Než se pustíte do používání GroupDocs.Viewer pro .NET, je třeba splnit několik předpokladů:
### 1. Instalace Visual Studia
V první řadě se ujistěte, že máte v systému nainstalované Visual Studio. Pokud ho ještě nemáte, můžete si ho stáhnout z webových stránek společnosti Microsoft.
### 2. Stáhněte si GroupDocs.Viewer pro .NET
Zamiřte k [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/) Chcete-li získat nejnovější verzi GroupDocs.Viewer pro .NET, postupujte podle pokynů k instalaci a nastavte jej ve svém vývojovém prostředí.
### 3. Získejte dočasnou licenci
Abyste během vývoje a testování odemkli plný potenciál GroupDocs.Viewer pro .NET, doporučuje se získat dočasnou licenci. Můžete si ji vyžádat od [zde](https://purchase.groupdocs.com/temporary-license/).

## Importovat jmenné prostory
Jakmile splníte všechny předpoklady, můžete začít používat GroupDocs.Viewer pro .NET ve svých projektech. Začněte importem potřebných jmenných prostorů do vaší kódové základny.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Pro lepší pochopení si uvedený příklad rozdělme do několika kroků:
## Krok 1: Definování výstupního adresáře
Začněte definováním adresáře, kam chcete ukládat vykreslené stránky dokumentu.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definování formátu cesty k souboru stránky
Nastavte formát cest k souborům jednotlivých stránek dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Krok 3: Inicializace objektu prohlížeče
Vytvořte instanci třídy Viewer a předejte jí cestu k dokumentu, který chcete zobrazit.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Krok 4: Konfigurace možností zobrazení HTML
Definujte možnosti pro zobrazení dokumentu ve formátu HTML a určete formát pro vložené zdroje (např. obrázky).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Zakažte ověřování licencí písem
Povolte možnost zakázat ověřování licencí písem, abyste zajistili plynulé vykreslování.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Krok 6: Zobrazení dokumentu
Volejte metodu View objektu Viewer a předejte jí nakonfigurované možnosti.
```csharp
viewer.View(options);
```
## Krok 7: Zobrazení výstupního adresáře
Informujte uživatele o umístění, kde jsou uloženy vykreslené stránky dokumentu.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
GroupDocs.Viewer pro .NET nabízí vývojářům komplexní řešení pro snadnou integraci funkcí prohlížení dokumentů do jejich .NET aplikací. Dodržováním kroků popsaných v tomto tutoriálu můžete tuto výkonnou knihovnu efektivně využít ke zlepšení pracovních postupů správy dokumentů.
## Často kladené otázky
### Může GroupDocs.Viewer pro .NET zpracovat více formátů dokumentů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Word, Excel, PowerPoint a dalších.
### Je GroupDocs.Viewer pro .NET vhodný pro webové aplikace?
GroupDocs.Viewer lze bez problémů integrovat do desktopových i webových aplikací vyvinutých pomocí technologií .NET.
### Vyžaduje GroupDocs.Viewer nějaké další závislosti?
Ne, GroupDocs.Viewer pro .NET má minimální závislosti a lze jej snadno integrovat do vašich stávajících projektů.
### Mohu si přizpůsobit vzhled vykreslených dokumentů?
Ano, GroupDocs.Viewer nabízí různé možnosti pro přizpůsobení vzhledu a chování vykreslených dokumentů vašim specifickým požadavkům.
### Je k dispozici technická podpora pro GroupDocs.Viewer pro .NET?
Ano, můžete vyhledat pomoc a poradenství od specializovaného týmu podpory prostřednictvím [forum](https://forum.groupdocs.com/c/viewer/9).