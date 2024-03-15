---
title: Načítání dokumentů z FTP (pokročilé)
linktitle: Načítání dokumentů z FTP (pokročilé)
second_title: GroupDocs.Viewer .NET API
description: Integrujte GroupDocs.Viewer for .NET hladce do svých aplikací pro efektivní prohlížení dokumentů. Vykreslujte dokumenty z FTP bez námahy.
type: docs
weight: 13
url: /cs/net/loading-documents/loading-document-ftp/
---
## Úvod
GroupDocs.Viewer for .NET je výkonné rozhraní API, které umožňuje vývojářům bezproblémově integrovat možnosti prohlížení dokumentů do jejich aplikací .NET. Ať už pracujete s PDF, dokumenty Microsoft Office nebo jinými oblíbenými formáty souborů, GroupDocs.Viewer zjednodušuje proces vykreslování dokumentů pro zobrazení, takže je snazší než kdy jindy poskytnout uživatelům bohatý zážitek ze sledování.
## Předpoklady
Než začnete pracovat s GroupDocs.Viewer for .NET, ujistěte se, že máte splněny následující předpoklady:
1. Vývojové prostředí: Nastavte vývojové prostředí s nainstalovaným Visual Studio a .NET Framework.
2.  Instalace GroupDocs.Viewer: Stáhněte a nainstalujte GroupDocs.Viewer for .NET z[webová stránka](https://releases.groupdocs.com/viewer/net/).
3.  Licence: Získejte platnou licenci pro GroupDocs.Viewer. Licenci si můžete zakoupit buď u[Web GroupDocs](https://purchase.groupdocs.com/buy) nebo využít dočasnou licenci pro testovací účely ([dočasná licence](https://purchase.groupdocs.com/temporary-license/)).
4. Základní porozumění .NET: Seznamte se se základy vývoje .NET, včetně syntaxe C# a práce se streamy.

## Importovat jmenné prostory
Chcete-li ve své aplikaci začít používat GroupDocs.Viewer for .NET, importujte potřebné jmenné prostory:
```csharp
using System;
using System.IO;
using System.Net;
using GroupDocs.Viewer.Options;
```
#Nyní si uvedený příklad rozdělíme do několika kroků:
## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Nastavte výstupní adresář, kam chcete ukládat vykreslené HTML stránky.
## Krok 2: Definujte formát cesty k souboru stránky
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Zadejte formát pro pojmenování HTML stránek, které budou generovány.
## Krok 3: Nastavte cestu k souboru dokumentu
```csharp
string filePath = ""; // např. ftp://localhost/sample.doc
```
Zadejte cestu k souboru dokumentu, který chcete načíst. Může to být cesta k místnímu souboru nebo adresa URL.
## Krok 4: Ověřte cestu k souboru
```csharp
if (string.IsNullOrEmpty(filePath))
{
    Console.WriteLine("\n[LoadDocumentFromFtp] Please make sure to set a proper path to the file.");
    return;
}
```
Ujistěte se, že cesta k souboru není prázdná nebo null.
## Krok 5: Načtěte dokument z FTP
```csharp
Stream stream = GetFileFromFtp(filePath);
```
Načtěte soubor dokumentu ze serveru FTP.
## Krok 6: Vykreslení dokumentu
```csharp
using (Viewer viewer = new Viewer(stream))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Vytvořte novou instanci prohlížeče a vykreslete dokument pomocí voleb zobrazení HTML.
## Krok 7: Zobrazte zprávu o úspěchu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informujte uživatele, že dokument byl úspěšně vykreslen, a zadejte výstupní adresář.

## Závěr
Na závěr, GroupDocs.Viewer for .NET poskytuje vývojářům robustní řešení pro integraci možností prohlížení dokumentů do jejich aplikací .NET. Podle kroků uvedených v tomto kurzu můžete rychle načíst dokumenty ze serverů FTP a vykreslit je pro zobrazení, čímž vylepšíte uživatelský dojem z vaší aplikace.
## FAQ
### Mohu použít GroupDocs.Viewer pro .NET k vykreslování dokumentů z jiných zdrojů kromě FTP?
Ano, GroupDocs.Viewer podporuje vykreslování dokumentů z různých zdrojů, včetně místních souborových systémů, adres URL a streamů.
### Je k použití GroupDocs.Viewer pro .NET nutná licence?
Ano, k používání GroupDocs.Viewer v produkčním prostředí potřebujete platnou licenci. Můžete však také získat dočasnou licenci pro testovací účely.
### Mohu přizpůsobit možnosti vykreslování dokumentů?
Absolutně! GroupDocs.Viewer nabízí širokou škálu možností přizpůsobení procesu vykreslování, včetně rotace stránky, vodoznaku a dalších.
### Podporuje GroupDocs.Viewer všechny formáty dokumentů?
GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, dokumentů Microsoft Office, obrázků a dalších.
### Je k dispozici technická podpora pro GroupDocs.Viewer pro .NET?
 Ano, máte přístup k technické podpoře a zdrojům prostřednictvím[Fórum GroupDocs](https://forum.groupdocs.com/c/viewer/9) pro pomoc s jakýmikoli dotazy nebo problémy, se kterými se setkáte.