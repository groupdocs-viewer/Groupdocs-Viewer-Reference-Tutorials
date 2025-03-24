---
title: Nastavte měřenou licenci
linktitle: Nastavte měřenou licenci
second_title: GroupDocs.Viewer .NET API
description: Vylepšete své aplikace .NET pomocí GroupDocs.Viewer pro bezproblémové prohlížení dokumentů. Snadno integrujte funkce vykreslování dokumentů do svých projektů.
weight: 12
url: /cs/net/getting-started/set-metered-license/
---

# Nastavte měřenou licenci

## Úvod
Ve světě vývoje .NET je začlenění výkonných možností prohlížení dokumentů do vašich aplikací zásadní pro zlepšení uživatelské zkušenosti a funkčnosti. GroupDocs.Viewer for .NET nabízí robustní řešení pro bezproblémovou integraci funkcí prohlížení dokumentů do vašich projektů .NET. Ať už pracujete s PDF, dokumenty Microsoft Office nebo různými formáty obrázků, GroupDocs.Viewer zjednodušuje proces vykreslování a zobrazování těchto dokumentů ve vašich aplikacích.
## Předpoklady
Než se pustíte do implementace GroupDocs.Viewer for .NET, ujistěte se, že máte splněny následující předpoklady:
### 1. Nainstalujte GroupDocs.Viewer pro .NET
 Chcete-li začít, budete si muset stáhnout a nainstalovat GroupDocs.Viewer for .NET. Odkaz ke stažení najdete[tady](https://releases.groupdocs.com/viewer/net/). Postupujte podle pokynů k instalaci a nastavte knihovnu ve svém vývojovém prostředí.
### 2. Získejte měřenou licenci
Abyste mohli používat GroupDocs.Viewer pro .NET, musíte získat měřenou licenci. Tato licence vám umožňuje řídit a sledovat vaše využití API na základě předem definovaných kvót. Chcete-li nastavit měřenou licenci, postupujte takto:

## Importovat jmenné prostory
Nejprve se ujistěte, že importujete potřebné jmenné prostory pro přístup k funkcím, které poskytuje GroupDocs.Viewer pro .NET:
```csharp
using System;
```

Nyní si rozeberme poskytnutý příklad kódu do několika kroků:
## Krok 1: Deklarujte veřejný a soukromý klíč
Deklarujte proměnné pro uložení vašich veřejných a soukromých klíčů:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Zajistěte výměnu`"YOUR_PUBLIC_KEY"` a`"YOUR_PRIVATE_KEY"` se svými skutečnými klíči.
## Krok 2: Nastavte měřenou licenci
Zkontrolujte, zda je poskytnut veřejný klíč. Pokud ne, požádejte uživatele, aby nastavil klíče:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Krok 3: Inicializujte měřený objekt a nastavte licenci
Inicializujte objekt Metered a nastavte měřenou licenci pomocí vašeho veřejného a soukromého klíče:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Krok 4: Potvrzující zpráva
Zobrazte potvrzovací zprávu o úspěšném nastavení licence:
```csharp
Console.WriteLine("License set successfully.");
```

## Závěr
Na závěr, GroupDocs.Viewer for .NET poskytuje komplexní řešení pro začlenění funkcí pro prohlížení dokumentů do vašich aplikací .NET. Podle nastíněných kroků můžete snadno nastavit měřenou licenci a začít využívat možnosti GroupDocs.Viewer ve svých projektech.
## FAQ
### Otázka: Kde najdu dokumentaci k GroupDocs.Viewer pro .NET?
 Dokumentaci najdete[tady](https://tutorials.groupdocs.com/viewer/net/).
### Otázka: Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.groupdocs.com/).
### Otázka: Jak mohu získat dočasné licence pro testovací účely?
 Lze získat dočasné licence[tady](https://purchase.groupdocs.com/temporary-license/).
### Otázka: Kde mohu hledat podporu nebo klást otázky týkající se GroupDocs.Viewer pro .NET?
 Můžete hledat podporu a klást otázky na fóru GroupDocs.Viewer[tady](https://forum.groupdocs.com/c/viewer/9).
### Otázka: Kde si mohu zakoupit licenci pro GroupDocs.Viewer for .NET?
 Můžete si zakoupit licenci[tady](https://purchase.groupdocs.com/buy).