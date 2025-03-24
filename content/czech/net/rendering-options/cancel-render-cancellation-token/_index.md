---
title: Zrušte vykreslování pomocí tokenu zrušení
linktitle: Zrušte vykreslování pomocí tokenu zrušení
second_title: GroupDocs.Viewer .NET API
description: Integrujte Groupdocs.Viewer for .NET hladce do svých projektů .NET pro efektivní prohlížení dokumentů.
weight: 11
url: /cs/net/rendering-options/cancel-render-cancellation-token/
---
## Úvod
Groupdocs.Viewer for .NET je výkonný nástroj navržený pro zjednodušení prohlížení a zpracování dokumentů v aplikacích .NET. Ať už pracujete s PDF, dokumenty Microsoft Office nebo jinými běžnými formáty, tato knihovna nabízí robustní funkce pro bezproblémovou integraci možností prohlížení dokumentů do vašich projektů .NET.
## Předpoklady
Než se pustíte do integrace Groupdocs.Viewer for .NET, ujistěte se, že máte splněny následující předpoklady:
1.  Instalace: Stáhněte a nainstalujte knihovnu Groupdocs.Viewer for .NET z poskytnutého souboru[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
   
2.  Licence: Získejte licenci od[Groupdocs](https://purchase.groupdocs.com/buy) odemknout plný potenciál knihovny. Případně můžete začít s bezplatnou zkušební verzí pomocí[dočasná licence](https://purchase.groupdocs.com/temporary-license/).
   
3. Vývojové prostředí: Ujistěte se, že máte nastavené kompatibilní vývojové prostředí, včetně Visual Studia nebo jakéhokoli jiného .NET IDE dle vašeho výběru.

## Importovat jmenné prostory
Abyste mohli Groupdocs.Viewer for .NET využívat efektivně, musíte do svého projektu importovat potřebné jmenné prostory. Následuj tyto kroky:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Nyní rozdělme poskytnutý příklad do několika kroků pro lepší pochopení a implementaci:
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Tento krok nastavuje adresář, kam se budou ukládat vykreslené stránky dokumentu.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Zde definujeme formát pro cesty k souborům jednotlivých stránek dokumentu.
## Krok 3: Inicializujte CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource se používá ke generování instancí CancellationToken, které lze použít ke zrušení asynchronních operací.
## Krok 4: Získejte CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Tento krok načte token ze zdroje CancellationTokenSource, který bude použit ke zrušení operace vykreslování.
## Krok 5: Vykreslení stránek dokumentu
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Zde zahájíme vykreslování stránek dokumentu asynchronně pomocí Task.Run(). Instance prohlížeče je vytvořena se zadaným souborem dokumentu (SAMPLE_DOCX) a jsou nakonfigurovány možnosti vykreslování. Proces vykreslování se pak spustí pomocí metody View třídy Viewer.
## Krok 6: Nastavte časový limit vykreslení
```csharp
cancellationTokenSource.CancelAfter(10);
```
Tento krok nastavuje časový limit 10 milisekund pro operaci vykreslování. Pokud operace překročí tento časový limit, bude automaticky zrušena.
## Krok 7: Zobrazte zprávu o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nakonec se zobrazí zpráva o úspěchu indikující, že dokument byl úspěšně vykreslen.

## Závěr
V tomto tutoriálu jsme probrali základy integrace Groupdocs.Viewer for .NET do vašich projektů. Dodržením výše uvedených kroků můžete do svých aplikací .NET bez problémů začlenit možnosti prohlížení dokumentů, čímž zvýšíte uživatelský komfort a produktivitu.
## FAQ
### Je Groupdocs.Viewer for .NET kompatibilní se všemi formáty dokumentů?
Groupdocs.Viewer for .NET podporuje širokou škálu formátů dokumentů, včetně PDF, dokumentů Microsoft Office, obrázků a dalších.
### Mohu upravit vzhled vykreslených stránek dokumentu?
Ano, můžete přizpůsobit různé aspekty procesu vykreslování, včetně velikosti stránky, kvality, vodoznaku a dalších.
### Vyžaduje Groupdocs.Viewer for .NET připojení k internetu?
Ne, Groupdocs.Viewer for .NET funguje lokálně ve vašem prostředí .NET a pro prohlížení dokumentů nevyžaduje připojení k internetu.
### Je k dispozici technická podpora pro Groupdocs.Viewer pro .NET?
 Ano, technická podpora je k dispozici prostřednictvím[Groupdocs fórum](https://forum.groupdocs.com/c/viewer/9), kde můžete klást otázky, hlásit problémy a komunikovat s komunitou.
### Mohu vyzkoušet Groupdocs.Viewer pro .NET před nákupem?
 Ano, můžete začít s bezplatnou zkušební verzí pomocí poskytnutého[zkušební verze](https://releases.groupdocs.com/).