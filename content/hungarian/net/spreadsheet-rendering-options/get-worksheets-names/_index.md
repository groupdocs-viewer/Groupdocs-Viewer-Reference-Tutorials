---
title: Get munkalapok nevek
linktitle: Get munkalapok nevek
second_title: GroupDocs.Viewer .NET API
description: Fedezze fel a GroupDocs.Viewer for .NET varázsát – zökkenőmentesen integrálja a dokumentumok megtekintését alkalmazásaiba. Próbálja ki most az ingyenes próbaverziót!
weight: 11
url: /hu/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Bevezetés
Üdvözöljük a GroupDocs.Viewer for .NET lenyűgöző világában! Ha Ön fejlesztő vagy rajongó, aki szeretné felfedezni a hatékony dokumentummegtekintési lehetőségeket .NET-alkalmazásaiban, akkor ez egy csemege. Ebben az átfogó útmutatóban a munkalapnevek GroupDocs.Viewer segítségével történő lekérésének bonyolultságába fogunk elmélyülni. Szóval, kapcsold be a biztonsági övet, és induljunk el erre az izgalmas utazásra!
## Előfeltételek
Mielőtt belemerülnénk a kódolási varázslatba, győződjünk meg arról, hogy mindent beállítottunk:
1.  A GroupDocs.Viewer for .NET telepítése: Menjen át a[letöltési link](https://releases.groupdocs.com/viewer/net/) GroupDocs.Viewer for .NET legújabb verziójának megszerzéséhez. Kövesse a telepítési utasításokat, hogy zökkenőmentesen integrálja a fejlesztői környezetébe.
2. Készítse elő a dokumentumot: Győződjön meg arról, hogy a kijelölt dokumentumkönyvtárban van egy céldokumentum, mondjuk egy „file.xlsx” nevű Excel-fájl.
## Névterek importálása
Most, hogy megvannak az előfeltételek, kezdjük a dolgokat a szükséges névterek importálásával. Ez biztosítja, hogy az alkalmazás felismerje és tudja használni a GroupDocs.Viewer for .NET által biztosított funkciókat.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. A dokumentumkönyvtár beállítása
```csharp
string outputDirectory = "Your Document Directory";
```
Cserélje ki a „Saját dokumentumkönyvtár” elemet annak a könyvtárnak az elérési útjával, ahol a céldokumentum található.
## 2. A Viewer inicializálása
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Ebben a lépésben létrehozzuk a Viewer osztály egy példányát, amely megadja az Excel-fájl elérési útját.
## 3. A Nézet információs beállításainak konfigurálása
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Itt konfiguráljuk a ViewInfoOptions-t HTML-nézetek generálására, és további beállításokat állítunk be a táblázatok megjelenítéséhez.
## 4. Nézet információk lekérése
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Használja a Viewer példányt a nézetadatok lekéréséhez a konfigurált beállítások alapján.
## 5. Munkalapnevek megjelenítése
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Lapozzon át a letöltött oldalakon, és nyomtassa ki az egyes munkalapok nevét a konzolra.
## Következtetés
Gratulálunk! Sikeresen navigált a munkalapnevek lekérésének folyamatán a GroupDocs.Viewer for .NET használatával. Ez számtalan lehetőséget nyit meg az alkalmazások dokumentummegtekintési funkcióinak bővítésére.
## GYIK
### Használhatom a GroupDocs.Viewer for .NET programot más dokumentumformátumokkal?
Teljesen! A GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF-t, a Microsoft Office-t és egyebeket.
### Van ingyenes próbaverzió?
 Igen, a .NET-hez készült GroupDocs.Viewer-t felfedezheti nálunk[ingyenes próbaverzió](https://releases.groupdocs.com/).
### Hol találhatok további támogatást?
 Irány a[GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) közösségi támogatásra és beszélgetésekre.
### Kaphatok ideiglenes engedélyt?
 Biztosan! Látogatás[ez a link](https://purchase.groupdocs.com/temporary-license/) hogy megszerezze az ideiglenes engedélyét.
### Rendelkezésre állnak-e részletes dokumentációs források?
 Teljesen! Nézze meg a[hivatalos dokumentáció](https://tutorials.groupdocs.com/viewer/net/) részletes információkért és útmutatókért.