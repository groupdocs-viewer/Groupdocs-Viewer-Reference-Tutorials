---
title: Časový interval konkrétního projektu vykreslení (MS Project)
linktitle: Časový interval konkrétního projektu vykreslení (MS Project)
second_title: GroupDocs.Viewer .NET API
description: Integrujte GroupDocs.Viewer for .NET hladce do svých aplikací pro efektivní prohlížení dokumentů. Zvyšte produktivitu pomocí všestranných možností vykreslování.
weight: 12
url: /cs/net/rendering-ms-project-documents/render-project-time-interval-ms-project/
---

# Časový interval konkrétního projektu vykreslení (MS Project)

## Úvod
V oblasti vývoje softwaru je prvořadá efektivní manipulace a vykreslování různých formátů dokumentů. Ať už jde o prohlížení dokumentů nebo manipulaci s nimi, správné nástroje mohou výrazně zvýšit produktivitu a zefektivnit procesy. GroupDocs.Viewer for .NET vyniká jako všestranné řešení, které vývojářům nabízí možnost bezproblémově integrovat možnosti prohlížení dokumentů do jejich aplikací .NET.
## Předpoklady
Než se pustíte do integrace GroupDocs.Viewer for .NET, ujistěte se, že máte následující předpoklady:
### 1. Seznámení s .NET Framework
Ujistěte se, že máte základní znalosti o frameworku .NET, včetně programovacího jazyka C# a Visual Studio IDE.
### 2. Instalace GroupDocs.Viewer pro .NET
 Stáhněte a nainstalujte GroupDocs.Viewer for .NET z[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/). Postupujte podle pokynů k instalaci a nastavte knihovnu ve svém vývojovém prostředí.
### 3. Platná licence nebo dočasná licence
 Získejte platnou licenci od[GroupDocs](https://purchase.groupdocs.com/buy) nebo získat dočasnou licenci od[tady](https://purchase.groupdocs.com/temporary-license/) k využití všech funkcí GroupDocs.Viewer pro .NET.
### 4. Vzorový dokument
Připravte si vzorový dokument, například soubor MS Project, pro testování funkčnosti vykreslování.

## Importovat jmenné prostory
Zahrňte do svého projektu potřebné jmenné prostory pro přístup k funkcím, které poskytuje GroupDocs.Viewer pro .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Rozdělme příklad vykreslení určitého časového intervalu projektu ze souboru MS Project do několika kroků:
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Zadejte adresář, do kterého se budou ukládat vykreslené HTML stránky.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Nastavte formát pro cestu k souboru každé vykreslené stránky HTML.
## Krok 3: Vytvořte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Vytvořte instanci třídy Viewer a předejte cestu k ukázkovému souboru MS Project.
## Krok 4: Nakonfigurujte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Nakonfigurujte možnosti zobrazení HTML pro vykreslování a určete formát pro vložené prostředky.
## Krok 5: Načtení informací o zobrazení správy projektu
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
Získejte informace o zobrazení řízení projektu a určete datum zahájení a ukončení projektu.
## Krok 6: Nastavte počáteční a koncové datum
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
Nastavte počáteční a koncové datum pro interval projektu, který se má vykreslit.
## Krok 7: Vykreslení dokumentu
```csharp
viewer.View(options);
```
Spusťte proces vykreslování se zadanými možnostmi.
## Krok 8: Zobrazte výstupní adresář
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informujte uživatele o úspěšném vykreslení a zobrazte adresář, do kterého je výstup uložen.

## Závěr
Integrace GroupDocs.Viewer for .NET do vašich projektů vám umožní efektivně zpracovávat úlohy související se zobrazením dokumentů, čímž se zlepší uživatelská zkušenost a produktivita. Podle poskytnutého podrobného průvodce můžete bezproblémově začlenit funkce vykreslování dokumentů do svých aplikací .NET.
## FAQ
### Je GroupDocs.Viewer for .NET kompatibilní se všemi formáty dokumentů?
GroupDocs.Viewer for .NET podporuje širokou škálu formátů dokumentů, včetně Microsoft Office, PDF, CAD a dalších.
### Mohu upravit vzhled vykreslených dokumentů?
Ano, můžete přizpůsobit různé aspekty procesu vykreslování, jako je rozvržení stránky, vodoznak a rotace stránky.
### Je GroupDocs.Viewer for .NET vhodný pro webové aplikace?
GroupDocs.Viewer for .NET lze bez problémů integrovat do webových aplikací a poskytovat tak možnosti prohlížení dokumentů.
### Nabízí GroupDocs.Viewer for .NET podporu pro mobilní platformy?
Ano, GroupDocs.Viewer for .NET podporuje mobilní platformy, což vám umožňuje vytvářet aplikace s responzivními funkcemi pro prohlížení dokumentů.
### Existuje komunitní fórum, kde mohu vyhledat pomoc s GroupDocs.Viewer pro .NET?
 Ano, můžete navštívit[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) klást otázky, sdílet nápady a komunikovat s ostatními uživateli a vývojáři.