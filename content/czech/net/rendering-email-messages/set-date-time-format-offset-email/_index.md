---
title: Nastavit formát data a času a posun časového pásma (e-mail)
linktitle: Nastavit formát data a času a posun časového pásma (e-mail)
second_title: GroupDocs.Viewer .NET API
description: Integrujte GroupDocs.Viewer for .NET hladce do svých aplikací a získáte výkonné možnosti prohlížení dokumentů. Vylepšete uživatelskou zkušenost pomocí přizpůsobitelných možností.
weight: 11
url: /cs/net/rendering-email-messages/set-date-time-format-offset-email/
---

# Nastavit formát data a času a posun časového pásma (e-mail)


## Úvod
GroupDocs.Viewer for .NET je výkonný nástroj, který umožňuje vývojářům bezproblémově integrovat možnosti prohlížení dokumentů do jejich aplikací .NET. S GroupDocs.Viewer můžete zobrazit širokou škálu formátů dokumentů včetně PDF, dokumentů Microsoft Office, obrázků a dalších přímo ve vaší aplikaci, aniž byste potřebovali jakékoli externí pluginy nebo prohlížeče. V tomto obsáhlém tutoriálu vás provedeme procesem nastavení GroupDocs.Viewer pro .NET, prozkoumáme jeho funkce a předvedeme, jak jej efektivně využít ke zlepšení možností zobrazení dokumentů vaší aplikace.
## Předpoklady
Než se pustíte do tohoto výukového programu, ujistěte se, že máte nastaveny následující předpoklady:
1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio. GroupDocs.Viewer for .NET je plně kompatibilní se sadou Visual Studio a umožňuje bezproblémovou integraci do vašich projektů .NET.
2.  GroupDocs.Viewer for .NET: Stáhněte si a nainstalujte GroupDocs.Viewer pro .NET z webu[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/). Postupujte podle pokynů k instalaci a nastavte knihovnu ve svém vývojovém prostředí.
3. .NET Framework: Ujistěte se, že máte nainstalovanou příslušnou verzi .NET Framework. GroupDocs.Viewer for .NET podporuje různé verze rozhraní .NET Framework, včetně .NET Core a .NET Standard.

## Importovat jmenné prostory
Abyste mohli GroupDocs.Viewer for .NET využívat efektivně, musíte do svého projektu importovat potřebné jmenné prostory. Chcete-li importovat požadované jmenné prostory, postupujte takto:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Pojďme si poskytnutý příklad rozdělit do několika kroků, abychom porozuměli každé součásti a její funkčnosti.
## Krok 1: Nastavte výstupní adresář a cestu k souboru
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
V tomto kroku definujeme výstupní adresář, kam bude vykreslený dokument uložen, a určíme cestu k výstupnímu HTML souboru.
## Krok 2: Vytvořte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Zde vytvoříme novou instanci`Viewer` třídy, předá jako parametr cestu dokumentu, který má být zobrazen (v tomto případě ukázkový soubor EML).
## Krok 3: Definujte možnosti zobrazení HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
tomto kroku nakonfigurujeme možnosti zobrazení HTML pro vykreslování dokumentu, přičemž určíme cestu k výstupnímu souboru pro vykreslený dokument HTML.
## Krok 4: Nastavte formát DateTime Format a Time Zone Offset
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Zde přizpůsobíme formát data a času pro e-mailové zprávy a nastavíme posun časového pásma podle požadovaného časového pásma.
## Krok 5: Vykreslení dokumentu
```csharp
viewer.View(options);
```
 Nakonec zavoláme`View` metoda`Viewer` objekt, předáním konfigurovaných voleb zobrazení HTML pro vykreslení dokumentu do formátu HTML.
## Krok 6: Zobrazte výstupní adresář
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tento krok jednoduše zobrazí zprávu o úspěšném vykreslení dokumentu a poskytne cestu k výstupnímu adresáři, kde se nachází vykreslený dokument HTML.

## Závěr
GroupDocs.Viewer for .NET nabízí robustní řešení pro integraci možností prohlížení dokumentů do vašich aplikací .NET. Podle kroků uvedených v tomto návodu můžete snadno nastavit GroupDocs.Viewer, importovat potřebné jmenné prostory a využívat jeho funkce k vykreslování dokumentů s přizpůsobitelnými možnostmi. Ať už pracujete s PDF, dokumenty Microsoft Office nebo jinými formáty, GroupDocs.Viewer zjednodušuje proces prohlížení dokumentů a zlepšuje uživatelské prostředí vašich aplikací.
## FAQ
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer for .NET podporuje .NET Core a umožňuje vašim aplikacím kompatibilitu napříč platformami.
### Mohu upravit vzhled vykreslených dokumentů?
Absolutně! GroupDocs.Viewer poskytuje různé možnosti přizpůsobení, včetně úrovní přiblížení, rotace stránky a dalších, aby bylo možné přizpůsobit zážitek ze sledování podle vašich preferencí.
### Je k dispozici zkušební verze pro účely testování?
 Ano, můžete si stáhnout bezplatnou zkušební verzi GroupDocs.Viewer pro .NET z webu[odkaz na webovou stránku](https://releases.groupdocs.com/viewer/net/) před nákupem vyhodnotit jeho vlastnosti.
### Podporuje GroupDocs.Viewer vykreslování dokumentů chráněných heslem?
Ano, GroupDocs.Viewer má vestavěnou podporu pro vykreslování dokumentů chráněných heslem, což zajišťuje bezpečné prohlížení dokumentů ve vašich aplikacích.
### Kde najdu další podporu nebo pomoc s GroupDocs.Viewer?
 Pro jakékoli technické dotazy nebo pomoc můžete navštívit GroupDocs.Viewer[Fórum](https://forum.groupdocs.com/c/viewer/9) nebo se obraťte na jejich tým podpory a požádejte o rychlou pomoc a radu.