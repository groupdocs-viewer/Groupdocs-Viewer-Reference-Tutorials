---
title: Načíst a uložit přílohy dokumentů
linktitle: Načíst a uložit přílohy dokumentů
second_title: GroupDocs.Viewer .NET API
description: Efektivně spravujte přílohy dokumentů v rámci aplikací .NET pomocí GroupDocs.Viewer. Bezproblémové načítání a ukládání příloh.
weight: 12
url: /cs/net/processing-document-attachments/retrieve-and-save-attachments/
---

# Načíst a uložit přílohy dokumentů

## Úvod
V digitální éře je efektivní zpracování dokumentů zásadní pro podniky i jednotlivce. Ať už jde o správu e-mailů, prohlížení smluv nebo přístup k sestavám, mít spolehlivý nástroj pro vizualizaci dokumentů je zásadní. GroupDocs.Viewer for .NET se ukazuje jako robustní řešení, které uživatelům umožňuje bez námahy prohlížet různé formáty dokumentů a pracovat s nimi přímo v jejich aplikacích .NET.
## Předpoklady
Než se ponoříte do používání GroupDocs.Viewer pro .NET pro načítání a ukládání příloh dokumentů, ujistěte se, že máte následující předpoklady:
1. Operační prostředí: Pracovní prostředí nastavené pomocí .NET frameworku.
2.  Instalace: Stažena a nainstalována knihovna GroupDocs.Viewer for .NET. Do knihovny se dostanete z[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).
3. Základní porozumění: Znalost programovacího jazyka C#.
4. Zdroj dokumentu: Přístup k ukázkovému dokumentu s přílohami pro demonstrační účely.

## Importovat jmenné prostory
Chcete-li začít používat GroupDocs.Viewer pro .NET pro načítání a ukládání příloh dokumentů, importujte potřebné jmenné prostory:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Krok 1: Definujte výstupní adresář
```csharp
string outputDirectory = "Your Document Directory";
```
Definujte adresář, kam chcete uložit přílohy načtené z dokumentu.
## Krok 2: Vytvořte objekt prohlížeče
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Vytvořte instanci objektu Viewer s cestou k dokumentu obsahujícímu přílohy.
## Krok 3: Načtěte přílohy
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Získejte seznam příloh přítomných v dokumentu.
## Krok 4: Uložte přílohy
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Projděte každou přílohu, definujte cestu k souboru a uložte přílohu do určeného adresáře.
## Krok 5: Zobrazte zprávu o úspěchu
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Zobrazte zprávu o úspěchu označující úspěšné uložení příloh spolu s cestou k adresáři.

## Závěr
Začlenění GroupDocs.Viewer for .NET do vašich pracovních postupů při manipulaci s dokumenty zjednodušuje proces správy příloh a nabízí efektivitu a pohodlí. Podle výše uvedeného podrobného průvodce mohou uživatelé bez problémů načítat a ukládat přílohy dokumentů v rámci svých aplikací .NET.
## FAQ
### Dokáže GroupDocs.Viewer for .NET zpracovat různé formáty dokumentů?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně PDF, dokumentů Microsoft Office, obrázků a dalších.
### Je k dispozici bezplatná zkušební verze pro GroupDocs.Viewer pro .NET?
 Ano, máte přístup k bezplatné zkušební verzi z[tady](https://releases.groupdocs.com/).
### Jak mohu získat dočasné licence pro GroupDocs.Viewer for .NET?
 Dočasné licence lze získat od[tento odkaz](https://purchase.groupdocs.com/temporary-license/).
### Kde najdu dokumentaci k GroupDocs.Viewer pro .NET?
 K dispozici je obsáhlá dokumentace[tady](https://tutorials.groupdocs.com/viewer/net/).
### Jaké možnosti podpory jsou k dispozici pro GroupDocs.Viewer pro .NET?
 Můžete požádat o pomoc na fóru komunity[tady](https://forum.groupdocs.com/c/viewer/9).