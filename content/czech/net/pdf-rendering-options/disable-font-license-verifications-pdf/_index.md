---
title: Zakázat ověřování licencí písem v PDF
linktitle: Zakázat ověřování licencí písem v PDF
second_title: GroupDocs.Viewer .NET API
description: Odemkněte bezproblémové možnosti prohlížení dokumentů ve vašem .NET s GroupDocs.Viewer pro .NET. Snadno integrujte a přizpůsobte vykreslování dokumentů s minimálními závislostmi.
type: docs
weight: 12
url: /cs/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## Úvod
V oblasti vývoje .NET je správa a manipulace s dokumenty často klíčovým aspektem mnoha aplikací. Ať už jde o prohlížení souborů PDF, dokumentů aplikace Word nebo jiných typů souborů, je nezbytné mít k dispozici robustní nástroje pro efektivní zpracování těchto úkolů. Zde vstupuje do hry GroupDocs.Viewer for .NET. Tato výkonná knihovna poskytuje vývojářům možnost bezproblémově integrovat funkce prohlížení dokumentů do jejich aplikací .NET.
## Předpoklady
Než se pustíte do používání GroupDocs.Viewer pro .NET, musíte mít splněno několik předpokladů:
### 1. Nainstalujte Visual Studio
Nejprve se ujistěte, že máte v systému nainstalované Visual Studio. Pokud jste tak ještě neučinili, můžete si jej stáhnout z webu společnosti Microsoft.
### 2. Stáhněte si GroupDocs.Viewer pro .NET
 Zamiřte k[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/) získat nejnovější verzi GroupDocs.Viewer pro .NET. Postupujte podle pokynů k instalaci a nastavte ji ve svém vývojovém prostředí.
### 3. Získejte dočasnou licenci
 Chcete-li využít plný potenciál GroupDocs.Viewer for .NET během vývoje a testování, doporučujeme získat dočasnou licenci. Můžete o něj požádat[tady](https://purchase.groupdocs.com/temporary-license/).

## Importovat jmenné prostory
Jakmile splníte předpoklady, jste připraveni začít používat GroupDocs.Viewer for .NET ve svých projektech. Začněte importováním potřebných jmenných prostorů do vaší kódové základny.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Pojďme si poskytnutý příklad rozdělit do několika kroků pro jasnější pochopení:
## Krok 1: Definujte výstupní adresář
Začněte definováním adresáře, kam chcete ukládat vykreslené stránky dokumentu.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Definujte formát cesty k souboru stránky
Nastavte formát cest k souborům jednotlivých stránek dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Krok 3: Inicializujte objekt prohlížeče
Vytvořte instanci třídy Viewer a předejte cestu k dokumentu, který chcete zobrazit.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
Definujte volby pro zobrazení dokumentu jako HTML a určete formát pro vložené zdroje (např. obrázky).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Zakažte ověřování licencí písem
Povolte možnost zakázat ověřování licencí písem, abyste zajistili plynulé vykreslování.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Krok 6: Zobrazení dokumentu
Vyvolejte metodu View objektu Viewer a předejte nakonfigurované možnosti.
```csharp
viewer.View(options);
```
## Krok 7: Zobrazte výstupní adresář
Informujte uživatele o umístění, kde jsou uloženy vykreslené stránky dokumentu.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Závěr
GroupDocs.Viewer for .NET nabízí vývojářům komplexní řešení pro snadnou integraci možností prohlížení dokumentů do jejich aplikací .NET. Dodržováním kroků uvedených v tomto kurzu můžete efektivně využít tuto výkonnou knihovnu k vylepšení pracovních postupů správy dokumentů.
## FAQ
### Dokáže GroupDocs.Viewer for .NET zpracovat více formátů dokumentů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů včetně PDF, Microsoft Word, Excel, PowerPoint a dalších.
### Je GroupDocs.Viewer for .NET vhodný pro webové aplikace?
GroupDocs.Viewer lze bez problémů integrovat do desktopových i webových aplikací vyvinutých pomocí technologií .NET.
### Vyžaduje GroupDocs.Viewer nějaké další závislosti?
Ne, GroupDocs.Viewer for .NET má minimální závislosti a lze jej snadno integrovat do vašich stávajících projektů.
### Mohu upravit vzhled vykreslených dokumentů?
Ano, GroupDocs.Viewer poskytuje různé možnosti pro přizpůsobení vzhledu a chování vykreslených dokumentů tak, aby vyhovovaly vašim specifickým požadavkům.
### Je k dispozici technická podpora pro GroupDocs.Viewer pro .NET?
 Ano, můžete vyhledat pomoc a pokyny od specializovaného týmu podpory prostřednictvím webu[Fórum](https://forum.groupdocs.com/c/viewer/9).