---
title: Vykreslování AI obrázků
linktitle: Vykreslování AI obrázků
second_title: GroupDocs.Viewer .NET API
description: Naučte se, jak bez námahy vykreslovat obrázky AI v aplikacích .NET pomocí GroupDocs.Viewer pro .NET. Postupujte podle našeho podrobného návodu pro bezproblémovou integraci.
weight: 10
url: /cs/net/image-rendering/render-ai-images/
---

# Vykreslování AI obrázků

## Úvod
GroupDocs.Viewer for .NET je výkonná knihovna, která umožňuje vývojářům bez námahy vykreslovat různé formáty dokumentů v rámci jejich aplikací .NET. Ať už potřebujete zobrazit obrázky AI, PDF nebo jiné typy dokumentů, GroupDocs.Viewer zjednodušuje proces a nabízí více výstupních formátů pro bezproblémovou integraci do vašich projektů. Tento tutoriál vás provede vykreslováním obrázků AI krok za krokem pomocí GroupDocs.Viewer pro .NET.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1. Visual Studio: Nainstalujte Visual Studio IDE do vašeho systému.
2.  GroupDocs.Viewer for .NET: Stáhněte si a nainstalujte GroupDocs.Viewer pro .NET z webu[webová stránka](https://releases.groupdocs.com/viewer/net/).
3. Základní znalost C#: Pro pochopení příkladů kódu je nutná znalost programovacího jazyka C#.

## Importovat jmenné prostory
Ve svém projektu C# importujte potřebné jmenné prostory pro přístup k funkcím GroupDocs.Viewer for .NET.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Vykreslování obrazů AI pomocí GroupDocs.Viewer for .NET zahrnuje několik kroků, z nichž každý je zaměřen na konkrétní výstupní formát. Níže si pro přehlednost rozdělíme proces na jednotlivé kroky.
## Krok 1: Zadejte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Vykreslení do HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Vykreslení do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 4: Vykreslení do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 5: Vykreslení do PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Závěr
GroupDocs.Viewer for .NET nabízí bezproblémové řešení pro vykreslování obrázků AI a různých formátů dokumentů v rámci aplikací .NET. Podle podrobného průvodce v tomto kurzu mohou vývojáři bez námahy integrovat funkce vykreslování dokumentů do svých projektů.
## FAQ
### Mohu přizpůsobit výstupní vzhled při vykreslování obrázků AI?
Ano, GroupDocs.Viewer for .NET poskytuje různé možnosti přizpůsobení vzhledu výstupu, včetně velikosti stránky, kvality obrazu a dalších.
### Je k dispozici zkušební verze pro účely testování?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z GroupDocs[webová stránka](https://releases.groupdocs.com/viewer/net/) před nákupem zhodnotit funkce knihovny.
### Podporuje GroupDocs.Viewer vykreslování šifrovaných obrázků AI?
Ano, GroupDocs.Viewer for .NET podporuje vykreslování zašifrovaných obrázků AI s příslušnými poskytnutými dešifrovacími klíči.
### Mohu vykreslovat obrázky AI přímo z adres URL?
Ano, GroupDocs.Viewer for .NET umožňuje vykreslování obrázků AI z adres URL zadáním cesty URL místo cesty k místnímu souboru.
### Je k dispozici technická podpora pro GroupDocs.Viewer pro .NET?
 Ano, technická podpora je k dispozici prostřednictvím GroupDocs[Fórum](https://forum.groupdocs.com/c/viewer/9), kde můžete klást otázky, hlásit problémy a hledat pomoc od komunity.