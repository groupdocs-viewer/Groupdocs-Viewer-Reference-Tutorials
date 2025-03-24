---
title: Získejte informace o zobrazení pro dokument PDF
linktitle: Získejte informace o zobrazení pro dokument PDF
second_title: GroupDocs.Viewer .NET API
description: V tomto komplexním kurzu se dozvíte, jak extrahovat informace o zobrazení z dokumentů PDF pomocí GroupDocs.Viewer for .NET.
weight: 16
url: /cs/net/pdf-rendering-options/get-view-info-pdf-document/
---

# Získejte informace o zobrazení pro dokument PDF

## Úvod
GroupDocs.Viewer for .NET je výkonný nástroj navržený pro zefektivnění prohlížení dokumentů v aplikacích .NET. Ať už pracujete s PDF, Word dokumenty, excelovými tabulkami nebo powerpointovými prezentacemi, tato knihovna zjednodušuje proces vykreslování a interakci s různými formáty souborů. V tomto tutoriálu se zaměříme na využití schopností GroupDocs.Viewer speciálně pro extrahování informací o zobrazení z dokumentů PDF.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1.  Instalace GroupDocs.Viewer for .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu GroupDocs.Viewer. Můžete jej získat z[odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).   
2. Základní znalost C#: Pro pochopení a implementaci poskytnutých příkladů kódu je nezbytná znalost programovacího jazyka C#.
3. Přístup k dokumentu PDF: Připravte si dokument PDF, který použijete k extrahování informací o zobrazení.

## Importovat jmenné prostory
Do svého projektu C# importujte potřebné jmenné prostory, abyste mohli využívat funkce GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Nyní si rozeberme proces získávání informací o zobrazení z dokumentu PDF pomocí GroupDocs.Viewer for .NET.
## Krok 1: Inicializujte objekt prohlížeče
Vytvořte objekt Viewer a zadejte cestu k dokumentu PDF jako parametr.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Krok 2: Definujte ViewInfoOptions
Chcete-li získat informace o zobrazení, zadejte možnosti zobrazení, například zobrazení HTML.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Krok 3: Získejte informace o zobrazení
Chcete-li extrahovat informace o zobrazení z dokumentu PDF, vyvolejte metodu GetViewInfo.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Krok 4: Informace o zobrazení výstupu
Zobrazte extrahované informace o zobrazení, jako je typ dokumentu, počet stránek a oprávnění k tisku.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Závěr
V tomto tutoriálu jsme prozkoumali, jak využít GroupDocs.Viewer pro .NET k extrahování informací o zobrazení z dokumentů PDF. Dodržováním uvedených kroků můžete tuto funkci bez problémů integrovat do svých aplikací .NET a zlepšit tak možnosti správy a prohlížení dokumentů.
## FAQ
### Je GroupDocs.Viewer kompatibilní s jinými formáty souborů kromě PDF?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně Wordu, Excelu, PowerPointu a dalších.
### Mohu upravit možnosti zobrazení podle požadavků mé aplikace?
GroupDocs.Viewer rozhodně nabízí různé možnosti přizpůsobení zážitku ze sledování na základě vašich konkrétních potřeb.
### Je GroupDocs.Viewer vhodný pro desktopové i webové aplikace?
Ano, GroupDocs.Viewer je všestranný a lze jej bez problémů integrovat do desktopových i webových aplikací .NET.
### Poskytuje GroupDocs.Viewer podporu a pomoc, pokud během implementace narazím na nějaké problémy?
Určitě můžete vyhledat pomoc na fóru komunity GroupDocs.Viewer nebo využít služby profesionální podpory pro rychlé vyřešení jakýchkoli problémů.
### Mohu GroupDocs.Viewer před nákupem vyzkoušet?
 Ano, funkce GroupDocs.Viewer můžete prozkoumat přístupem k bezplatné zkušební verzi dostupné na webu[webová stránka](https://purchase.groupdocs.com/buy).