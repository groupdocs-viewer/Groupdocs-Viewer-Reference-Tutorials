---
"description": "Vylepšete své .NET aplikace pomocí GroupDocs.Viewer pro bezproblémové prohlížení dokumentů. Snadno integrujte funkce vykreslování dokumentů do svých projektů."
"linktitle": "Nastavit měřenou licenci"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Nastavit měřenou licenci"
"url": "/cs/net/getting-started/set-metered-license/"
"weight": 12
---

# Nastavit měřenou licenci

## Zavedení
Ve světě vývoje v .NET je začlenění výkonných funkcí prohlížení dokumentů do vašich aplikací nezbytné pro zlepšení uživatelského prostředí a funkčnosti. GroupDocs.Viewer pro .NET nabízí robustní řešení pro bezproblémovou integraci funkcí prohlížení dokumentů do vašich .NET projektů. Ať už pracujete s PDF soubory, dokumenty Microsoft Office nebo různými obrazovými formáty, GroupDocs.Viewer zjednodušuje proces vykreslování a zobrazování těchto dokumentů ve vašich aplikacích.

![Nastavení měřené licence pomocí GroupDocs.Viewer pro .NET](/viewer/getting-started/set-metered-license.png)

## Předpoklady
Než se pustíte do implementace GroupDocs.Viewer pro .NET, ujistěte se, že máte splněny následující předpoklady:
### 1. Nainstalujte GroupDocs.Viewer pro .NET
Nejprve si budete muset stáhnout a nainstalovat GroupDocs.Viewer pro .NET. Odkaz ke stažení najdete [zde](https://releases.groupdocs.com/viewer/net/)Postupujte podle pokynů k instalaci a nastavte knihovnu ve vašem vývojovém prostředí.
### 2. Získejte licenci pro měření
Abyste mohli používat GroupDocs.Viewer pro .NET, musíte si zakoupit měřenou licenci. Tato licence vám umožňuje řídit a monitorovat využití API na základě předdefinovaných kvót. Pro nastavení měřené licence postupujte podle následujících kroků:

## Importovat jmenné prostory
Nejprve se ujistěte, že jste importovali potřebné jmenné prostory pro přístup k funkcím poskytovaným GroupDocs.Viewer pro .NET:
```csharp
using System;
```

Nyní si rozdělme uvedený příklad kódu do několika kroků:
## Krok 1: Deklarace veřejných a soukromých klíčů
Deklarujte proměnné pro uložení veřejných a soukromých klíčů:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Ujistěte se, že vyměníte `"YOUR_PUBLIC_KEY"` a `"YOUR_PRIVATE_KEY"` s vašimi skutečnými klíči.
## Krok 2: Nastavení měřené licence
Zkontrolujte, zda je zadán veřejný klíč. Pokud ne, vyzvěte uživatele k nastavení klíčů:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Krok 3: Inicializace měřeného objektu a nastavení licence
Inicializujte objekt Metered a nastavte licenci pro měření pomocí veřejného a soukromého klíče:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Krok 4: Potvrzovací zpráva
Zobrazit potvrzovací zprávu oznamující, že licence byla úspěšně nastavena:
```csharp
Console.WriteLine("License set successfully.");
```

## Závěr
Závěrem lze říci, že GroupDocs.Viewer pro .NET poskytuje komplexní řešení pro začlenění funkcí prohlížení dokumentů do vašich .NET aplikací. Dodržením uvedených kroků si můžete snadno nastavit měřenou licenci a začít využívat možnosti GroupDocs.Viewer ve svých projektech.
## Často kladené otázky
### Otázka: Kde najdu dokumentaci k GroupDocs.Viewer pro .NET?
Dokumentaci najdete [zde](https://tutorials.groupdocs.com/viewer/net/).
### Otázka: Je k dispozici bezplatná zkušební verze GroupDocs.Viewer pro .NET?
Ano, máte přístup k bezplatné zkušební verzi [zde](https://releases.groupdocs.com/).
### Otázka: Jak mohu získat dočasné licence pro účely testování?
Dočasné licence lze získat [zde](https://purchase.groupdocs.com/temporary-license/).
### Otázka: Kde mohu vyhledat podporu nebo se zeptat na otázky týkající se GroupDocs.Viewer pro .NET?
Podporu a dotazy můžete hledat na fóru GroupDocs.Viewer. [zde](https://forum.groupdocs.com/c/viewer/9).
### Otázka: Kde si mohu zakoupit licenci pro GroupDocs.Viewer pro .NET?
Můžete si zakoupit licenci [zde](https://purchase.groupdocs.com/buy).