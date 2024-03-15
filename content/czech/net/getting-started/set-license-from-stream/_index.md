---
title: Nastavit licenci ze streamu
linktitle: Nastavit licenci ze streamu
second_title: GroupDocs.Viewer .NET API
description: Vylepšete své aplikace .NET pomocí GroupDocs.Viewer pro bezproblémové prohlížení dokumentů. Postupujte podle našeho podrobného průvodce a bez námahy integrujte výkonné funkce pro prohlížení dokumentů.
type: docs
weight: 11
url: /cs/net/getting-started/set-license-from-stream/
---
## Úvod
Chcete svým aplikacím .NET rozšířit možnosti pokročilého prohlížení dokumentů? GroupDocs.Viewer for .NET nabízí komplexní řešení pro bezproblémovou integraci funkcí prohlížení dokumentů do vašich projektů. V tomto tutoriálu se ponoříme do procesu využití GroupDocs.Viewer for .NET k obohacení vašich aplikací o výkonné možnosti prohlížení dokumentů. 
## Předpoklady
Než se ponoříme do procesu integrace, ujistěte se, že máte splněny následující předpoklady:
1. Základní znalost vývoje .NET: Znalost jazyka C# a .NET frameworku je nezbytná pro dodržení tohoto návodu.
   
2.  Balíček GroupDocs.Viewer for .NET: Ujistěte se, že jste si stáhli a nainstalovali balíček GroupDocs.Viewer for .NET. Můžete jej získat z[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
3.  Přístup k dokumentaci GroupDocs: Uschovejte[dokumentace](https://reference.groupdocs.com/viewer/net/) užitečné pro referenci během integračního procesu.

## Importovat jmenné prostory
Nejprve importujte potřebné jmenné prostory do vaší aplikace .NET. Následuj tyto kroky:
### Krok 1: Otevřete svůj projekt .NET.
Ujistěte se, že máte svůj projekt .NET otevřený ve vámi preferovaném vývojovém prostředí.
### Krok 2: Přidejte jmenný prostor GroupDocs.Viewer.
Do souboru kódu přidejte následující jmenný prostor, abyste získali přístup k funkcím GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Nastavit licenci ze streamu
Další krok zahrnuje nastavení licence ze streamu. Postupujte podle těchto podrobných kroků:
### Krok 1: Definujte výstupní adresář.
Definováním výstupního adresáře nastavte adresář, kam budou vaše dokumenty uloženy:
```csharp
string outputDirectory = "Your Document Directory";
```
### Krok 2: Zkontrolujte existenci licenčního souboru.
Zkontrolujte, zda licenční soubor existuje v adresáři vašeho projektu:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Krok 3: Nastavte licenci.
Pokud licenční soubor existuje, nastavte licenci pomocí poskytnutého streamu:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Krok 4: Řešení absence licence.
Pokud licenční soubor není nalezen, poskytněte pokyny k získání licence:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. "+
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak integrovat GroupDocs.Viewer for .NET do vašich aplikací. S tímto výkonným nástrojem můžete nyní bez námahy prohlížet různé formáty dokumentů v rámci svých projektů .NET, což zvyšuje uživatelskou zkušenost a produktivitu.
## FAQ
### Potřebuji licenci k používání GroupDocs.Viewer pro .NET?
Ano, k používání GroupDocs.Viewer pro .NET potřebujete licenci. Dočasnou nebo trvalou licenci můžete získat z webu GroupDocs.
### Mohu integrovat GroupDocs.Viewer do své aplikace ASP.NET?
Absolutně! GroupDocs.Viewer for .NET se hladce integruje do desktopových i webových aplikací, včetně ASP.NET.
### Jaké formáty dokumentů podporuje GroupDocs.Viewer?
GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office (Word, Excel, PowerPoint), obrázků a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer for .NET je kompatibilní s .NET Framework i .NET Core.
### Mohu přizpůsobit rozhraní prohlížeče podle tématu mé aplikace?
Ano, GroupDocs.Viewer poskytuje rozsáhlé možnosti přizpůsobení, které vám umožní přizpůsobit rozhraní prohlížeče tak, aby hladce odpovídalo tématu vaší aplikace.