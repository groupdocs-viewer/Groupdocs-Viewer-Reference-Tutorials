---
"description": "Integrujte GroupDocs.Viewer pro .NET bezproblémově do svých aplikací a získejte výkonné funkce prohlížení dokumentů. Vylepšete uživatelský zážitek pomocí přizpůsobitelných možností."
"linktitle": "Nastavení formátu data a času a časového posunu (e-mail)"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Nastavení formátu data a času a časového posunu (e-mail)"
"url": "/cs/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
---

# Nastavení formátu data a času a časového posunu (e-mail)


## Zavedení
GroupDocs.Viewer pro .NET je výkonný nástroj, který umožňuje vývojářům bezproblémově integrovat funkce prohlížení dokumentů do jejich .NET aplikací. S GroupDocs.Viewer můžete přímo ve své aplikaci zobrazovat širokou škálu formátů dokumentů, včetně PDF, dokumentů Microsoft Office, obrázků a dalších, bez nutnosti používat externí pluginy nebo prohlížeče. V tomto komplexním tutoriálu vás provedeme procesem nastavení GroupDocs.Viewer pro .NET, prozkoumáme jeho funkce a ukážeme, jak jej efektivně využívat k vylepšení možností prohlížení dokumentů ve vaší aplikaci.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte nastaveny následující předpoklady:
1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio. GroupDocs.Viewer pro .NET je plně kompatibilní s Visual Studiem, což umožňuje bezproblémovou integraci do vašich .NET projektů.
2. GroupDocs.Viewer pro .NET: Stáhněte a nainstalujte GroupDocs.Viewer pro .NET z [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/)Postupujte podle pokynů k instalaci a nastavte knihovnu ve vašem vývojovém prostředí.
3. .NET Framework: Ujistěte se, že máte nainstalovanou správnou verzi .NET Frameworku. GroupDocs.Viewer pro .NET podporuje různé verze .NET Frameworku, včetně .NET Core a .NET Standard.

## Importovat jmenné prostory
Abyste mohli efektivně využívat GroupDocs.Viewer pro .NET, musíte do projektu importovat potřebné jmenné prostory. Postupujte podle těchto kroků pro import požadovaných jmenných prostorů:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Rozdělme si uvedený příklad do několika kroků, abychom pochopili každou komponentu a její funkčnost.
## Krok 1: Nastavení výstupního adresáře a cesty k souboru
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
V tomto kroku definujeme výstupní adresář, kam bude vykreslený dokument uložen, a zadáme cestu k výstupnímu souboru HTML.
## Krok 2: Vytvoření instance objektu Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Zde vytvoříme novou instanci třídy `Viewer` třída, kde jako parametr předá cestu k dokumentu, který má být zobrazen (v tomto případě ukázkový soubor EML).
## Krok 3: Definování možností zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
V tomto kroku nakonfigurujeme možnosti zobrazení HTML pro vykreslování dokumentu a určíme cestu k výstupnímu souboru pro vykreslený HTML dokument.
## Krok 4: Nastavení formátu data a času a časového posunu
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Zde upravíme formát data a času pro e-mailové zprávy a nastavíme posun časového pásma podle požadovaného časového pásma.
## Krok 5: Vykreslení dokumentu
```csharp
viewer.View(options);
```
Nakonec nazýváme `View` metoda `Viewer` objekt, předáním nakonfigurovaných možností zobrazení HTML pro vykreslení dokumentu do formátu HTML.
## Krok 6: Zobrazení výstupního adresáře
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tento krok jednoduše zobrazí zprávu o úspěšném vykreslení dokumentu a poskytne cestu k výstupnímu adresáři, kde se nachází vykreslený dokument HTML.

## Závěr
GroupDocs.Viewer pro .NET nabízí robustní řešení pro integraci funkcí prohlížení dokumentů do vašich .NET aplikací. Dodržováním kroků popsaných v tomto tutoriálu můžete snadno nastavit GroupDocs.Viewer, importovat potřebné jmenné prostory a využít jeho funkce k vykreslování dokumentů s přizpůsobitelnými možnostmi. Ať už pracujete s PDF, dokumenty Microsoft Office nebo jinými formáty, GroupDocs.Viewer zjednodušuje proces prohlížení dokumentů a vylepšuje uživatelský komfort vašich aplikací.
## Často kladené otázky
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer pro .NET podporuje .NET Core, což umožňuje kompatibilitu vašich aplikací napříč platformami.
### Mohu si přizpůsobit vzhled vykreslených dokumentů?
Rozhodně! GroupDocs.Viewer nabízí různé možnosti přizpůsobení, včetně úrovní přiblížení, rotace stránek a dalších, aby si uživatel mohl přizpůsobit zážitek ze sledování vašim potřebám.
### Je k dispozici zkušební verze pro testovací účely?
Ano, můžete si stáhnout bezplatnou zkušební verzi GroupDocs.Viewer pro .NET z [odkaz na webové stránky](https://releases.groupdocs.com/viewer/net/) aby si před nákupem ohodnotil jeho vlastnosti.
### Podporuje GroupDocs.Viewer vykreslování dokumentů chráněných heslem?
Ano, GroupDocs.Viewer má vestavěnou podporu pro vykreslování dokumentů chráněných heslem, což zajišťuje bezpečné prohlížení dokumentů ve vašich aplikacích.
### Kde mohu najít další podporu nebo pomoc s GroupDocs.Viewer?
V případě technických dotazů nebo potřeby pomoci můžete navštívit stránku GroupDocs.Viewer. [forum](https://forum.groupdocs.com/c/viewer/9) nebo se obraťte na jejich tým podpory, kde vám poskytnou rychlou pomoc a rady.