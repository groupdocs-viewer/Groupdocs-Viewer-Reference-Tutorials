---
"description": "V tomto komplexním tutoriálu se naučte, jak extrahovat informace o zobrazení z dokumentů PDF pomocí nástroje GroupDocs.Viewer pro .NET."
"linktitle": "Získat informace o zobrazení pro dokument PDF"
"second_title": "Rozhraní GroupDocs.Viewer .NET API"
"title": "Získat informace o zobrazení pro dokument PDF"
"url": "/cs/net/pdf-rendering-options/get-view-info-pdf-document/"
"weight": 16
type: docs
---
# Získat informace o zobrazení pro dokument PDF

## Zavedení
GroupDocs.Viewer pro .NET je výkonný nástroj určený pro zefektivnění prohlížení dokumentů v aplikacích .NET. Ať už pracujete s PDF, dokumenty Word, tabulkami Excel nebo prezentacemi PowerPoint, tato knihovna zjednodušuje proces vykreslování a interakce s různými formáty souborů. V tomto tutoriálu se zaměříme na využití možností GroupDocs.Viewer konkrétně pro extrakci informací o zobrazení z dokumentů PDF.

![Získejte informace o zobrazení PDF dokumentu pomocí GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/get-view-iInfo-for-pdf-document.png)

## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:
1. Instalace GroupDocs.Viewer pro .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu GroupDocs.Viewer. Můžete ji získat z [odkaz ke stažení](https://releases.groupdocs.com/viewer/net/).   
2. Základní znalost jazyka C#: Znalost programovacího jazyka C# je nezbytná pro pochopení a implementaci uvedených příkladů kódu.
3. Přístup k dokumentu PDF: Mějte připravený dokument PDF, který použijete k extrakci informací o zobrazení.

## Importovat jmenné prostory
Ve vašem projektu C# importujte potřebné jmenné prostory pro využití funkcí GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Nyní si rozebereme proces načítání informací o zobrazení z dokumentu PDF pomocí GroupDocs.Viewer pro .NET.
## Krok 1: Inicializace objektu prohlížeče
Vytvořte objekt Viewer a jako parametr zadejte cestu k dokumentu PDF.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Krok 2: Definování ViewInfoOptions
Zadejte možnosti zobrazení, například zobrazení HTML, pro načtení informací o zobrazení.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Krok 3: Získejte informace o zobrazení
Voláním metody GetViewInfo extrahujte informace o zobrazení z dokumentu PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Krok 4: Výstup informací o zobrazení
Zobrazit extrahované informace o zobrazení, jako je typ dokumentu, počet stránek a oprávnění k tisku.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Závěr
V tomto tutoriálu jsme prozkoumali, jak pomocí nástroje GroupDocs.Viewer pro .NET extrahovat informace o zobrazení z dokumentů PDF. Dodržením uvedených kroků můžete tuto funkci bezproblémově integrovat do svých aplikací .NET a vylepšit tak správu a možnosti prohlížení dokumentů.
## Často kladené otázky
### Je GroupDocs.Viewer kompatibilní s jinými formáty souborů než PDF?
Ano, GroupDocs.Viewer podporuje širokou škálu formátů dokumentů, včetně Wordu, Excelu, PowerPointu a dalších.
### Mohu si přizpůsobit možnosti zobrazení podle požadavků mé aplikace?
GroupDocs.Viewer samozřejmě nabízí různé možnosti, jak si přizpůsobit zážitek ze sledování podle vašich specifických potřeb.
### Je GroupDocs.Viewer vhodný pro desktopové i webové aplikace?
Ano, GroupDocs.Viewer je všestranný a lze jej bez problémů integrovat do desktopových i webových .NET aplikací.
### Poskytuje GroupDocs.Viewer podporu a pomoc, pokud se během implementace setkám s nějakými problémy?
Jistě můžete vyhledat pomoc na komunitním fóru GroupDocs.Viewer nebo se obrátit na profesionální podpůrné služby pro rychlé vyřešení jakýchkoli problémů.
### Mohu si před nákupem vyzkoušet GroupDocs.Viewer?
Ano, funkce GroupDocs.Viewer si můžete prohlédnout v bezplatné zkušební verzi dostupné na [webové stránky](https://purchase.groupdocs.com/buy).