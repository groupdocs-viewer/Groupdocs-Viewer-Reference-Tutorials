---
"description": "Integrujte Groupdocs.Viewer pro .NET bezproblémově do svých .NET projektů pro efektivní prohlížení dokumentů."
"linktitle": "Zrušit vykreslení pomocí tokenu zrušení"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Zrušit vykreslení pomocí tokenu zrušení"
"url": "/cs/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# Zrušit vykreslení pomocí tokenu zrušení

## Zavedení
Groupdocs.Viewer pro .NET je výkonný nástroj určený ke zjednodušení prohlížení a zpracování dokumentů v aplikacích .NET. Ať už pracujete s PDF, dokumenty Microsoft Office nebo jinými běžnými formáty, tato knihovna nabízí robustní funkce pro bezproblémovou integraci možností prohlížení dokumentů do vašich projektů .NET.
## Předpoklady
Než se pustíte do integrace Groupdocs.Viewer pro .NET, ujistěte se, že máte splněny následující předpoklady:
1. Instalace: Stáhněte a nainstalujte knihovnu Groupdocs.Viewer pro .NET z dodaného [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
   
2. Licence: Získejte licenci od [Skupinové dokumenty](https://purchase.groupdocs.com/buy) abyste odemkli plný potenciál knihovny. Případně můžete začít s bezplatnou zkušební verzí pomocí [dočasná licence](https://purchase.groupdocs.com/temporary-license/).
   
3. Vývojové prostředí: Ujistěte se, že máte nastavené kompatibilní vývojové prostředí, včetně Visual Studia nebo jiného .NET IDE dle vašeho výběru.

## Importovat jmenné prostory
Abyste mohli efektivně využívat Groupdocs.Viewer pro .NET, musíte do projektu importovat potřebné jmenné prostory. Postupujte takto:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Nyní si pro lepší pochopení a implementaci rozdělme uvedený příklad do několika kroků:
## Krok 1: Definování výstupního adresáře
```csharp
string outputDirectory = "Your Document Directory";
```
Tento krok nastaví adresář, kam budou uloženy vykreslené stránky dokumentu.
## Krok 2: Definování formátu cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Zde definujeme formát cest k souborům jednotlivých stránek dokumentu.
## Krok 3: Inicializace zdroje tokenu zrušení
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource se používá ke generování instancí CancellationToken, které lze použít ke zrušení asynchronních operací.
## Krok 4: Získejte CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Tento krok načte token z CancellationTokenSource, který bude použit ke zrušení operace vykreslování.
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
Zde asynchronně zahájíme vykreslování stránek dokumentu pomocí metody Task.Run(). Instance třídy Viewer se vytvoří se zadaným souborem dokumentu (SAMPLE_DOCX) a nakonfigurují se možnosti vykreslování. Proces vykreslování se poté spustí pomocí metody View třídy Viewer.
## Krok 6: Nastavení časového limitu vykreslování
```csharp
cancellationTokenSource.CancelAfter(10);
```
Tento krok nastaví časový limit 10 milisekund pro operaci vykreslování. Pokud operace tento časový limit překročí, bude automaticky zrušena.
## Krok 7: Zobrazení zprávy o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nakonec se zobrazí zpráva o úspěchu, která označuje, že dokument byl úspěšně vykreslen.

## Závěr
tomto tutoriálu jsme se zabývali základy integrace Groupdocs.Viewer pro .NET do vašich projektů. Dodržením výše uvedených kroků můžete bezproblémově začlenit funkce prohlížení dokumentů do vašich .NET aplikací, a tím zlepšit uživatelský komfort a produktivitu.
## Často kladené otázky
### Je Groupdocs.Viewer pro .NET kompatibilní se všemi formáty dokumentů?
Groupdocs.Viewer pro .NET podporuje širokou škálu formátů dokumentů, včetně PDF, dokumentů Microsoft Office, obrázků a dalších.
### Mohu si přizpůsobit vzhled vykreslených stránek dokumentu?
Ano, můžete si přizpůsobit různé aspekty procesu vykreslování, včetně velikosti stránky, kvality, vodoznaků a dalších.
### Vyžaduje Groupdocs.Viewer pro .NET připojení k internetu?
Ne, Groupdocs.Viewer pro .NET funguje lokálně ve vašem prostředí .NET a pro prohlížení dokumentů nevyžaduje připojení k internetu.
### Je k dispozici technická podpora pro Groupdocs.Viewer pro .NET?
Ano, technická podpora je k dispozici prostřednictvím [Fórum Groupdocs](https://forum.groupdocs.com/c/viewer/9), kde můžete klást otázky, hlásit problémy a komunikovat s komunitou.
### Mohu si před zakoupením vyzkoušet Groupdocs.Viewer pro .NET?
Ano, můžete začít s bezplatnou zkušební verzí s využitím poskytnuté [zkušební verze](https://releases.groupdocs.com/).