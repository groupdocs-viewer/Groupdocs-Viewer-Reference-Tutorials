---
"description": "Vylepšete své .NET aplikace pomocí GroupDocs.Viewer pro bezproblémové prohlížení dokumentů. Postupujte podle našeho podrobného návodu a bez námahy integrujte výkonné funkce prohlížení dokumentů."
"linktitle": "Nastavení licence ze streamu"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Nastavení licence ze streamu"
"url": "/cs/net/getting-started/set-license-from-stream/"
"weight": 11
---

# Nastavení licence ze streamu

## Zavedení
Hledáte způsob, jak vylepšit své .NET aplikace pokročilými funkcemi prohlížení dokumentů? GroupDocs.Viewer pro .NET nabízí komplexní řešení pro bezproblémovou integraci funkcí prohlížení dokumentů do vašich projektů. V tomto tutoriálu se ponoříme do procesu využití GroupDocs.Viewer pro .NET k obohacení vašich aplikací o výkonné funkce prohlížení dokumentů. 

![Nastavení licence ze streamu pomocí GroupDocs.Viewer pro .NET](/viewer/getting-started/set-license-from-stream.png)

## Předpoklady
Než se pustíme do procesu integrace, ujistěte se, že máte splněny následující předpoklady:
1. Základní znalosti vývoje v .NET: Znalost C# a .NET frameworku je nezbytná pro absolvování tohoto tutoriálu.
   
2. Balíček GroupDocs.Viewer pro .NET: Ujistěte se, že jste si stáhli a nainstalovali balíček GroupDocs.Viewer pro .NET. Můžete ho získat z [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Přístup k dokumentaci GroupDocs: Uchovávejte [dokumentace](https://tutorials.groupdocs.com/viewer/net/) užitečné pro tutoriály během procesu integrace.

## Importovat jmenné prostory
Nejprve importujte potřebné jmenné prostory do vaší .NET aplikace. Postupujte takto:
### Krok 1: Otevřete svůj projekt .NET.
Ujistěte se, že máte svůj .NET projekt otevřený ve vámi preferovaném vývojovém prostředí.
### Krok 2: Přidejte jmenný prostor GroupDocs.Viewer.
Do souboru s kódem přidejte následující jmenný prostor pro přístup k funkcím GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Nastavení licence ze streamu
Dalším krokem je nastavení licence ze streamu. Postupujte podle těchto podrobných kroků:
### Krok 1: Definujte výstupní adresář.
Nastavte adresář, kam budou vaše dokumenty uloženy, definováním výstupního adresáře:
```csharp
string outputDirectory = "Your Document Directory";
```
### Krok 2: Zkontrolujte existenci licenčního souboru.
Zkontrolujte, zda se soubor s licencí nachází ve vašem projektovém adresáři:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Krok 3: Nastavení licence.
Pokud licenční soubor existuje, nastavte licenci pomocí poskytnutého streamu:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Krok 4: Řešení absence licence.
Pokud soubor s licencí není nalezen, uveďte pokyny k jeho získání:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing.
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak integrovat GroupDocs.Viewer pro .NET do vašich aplikací. S tímto výkonným nástrojem nyní můžete bez námahy prohlížet různé formáty dokumentů ve vašich .NET projektech, což zvyšuje uživatelský komfort a produktivitu.
## Často kladené otázky
### Potřebuji licenci k používání GroupDocs.Viewer pro .NET?
Ano, k používání GroupDocs.Viewer pro .NET potřebujete licenci. Dočasnou nebo trvalou licenci můžete získat na webových stránkách GroupDocs.
### Mohu integrovat GroupDocs.Viewer do své ASP.NET aplikace?
Rozhodně! GroupDocs.Viewer pro .NET se bez problémů integruje do desktopových i webových aplikací, včetně ASP.NET.
### Které formáty dokumentů podporuje GroupDocs.Viewer?
GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, Microsoft Office (Word, Excel, PowerPoint), obrázků a dalších.
### Je GroupDocs.Viewer kompatibilní s .NET Core?
Ano, GroupDocs.Viewer pro .NET je kompatibilní s .NET Framework i .NET Core.
### Mohu si přizpůsobit rozhraní prohlížeče podle tématu mé aplikace?
Ano, GroupDocs.Viewer nabízí rozsáhlé možnosti přizpůsobení, které vám umožňují přizpůsobit rozhraní prohlížeče tak, aby bez problémů odpovídalo tématu vaší aplikace.