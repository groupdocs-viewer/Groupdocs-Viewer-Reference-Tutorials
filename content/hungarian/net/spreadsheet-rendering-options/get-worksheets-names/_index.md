---
"description": "Fedezze fel a GroupDocs.Viewer for .NET varázsát – zökkenőmentesen integrálja a dokumentummegtekintést alkalmazásaiba. Próbálja ki az ingyenes próbaverziót most!"
"linktitle": "Munkalapok nevének lekérése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Munkalapok nevének lekérése"
"url": "/hu/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
type: docs
---
# Munkalapok nevének lekérése

## Bevezetés
Üdvözlünk a GroupDocs.Viewer for .NET lenyűgöző világában! Ha fejlesztő vagy lelkes rajongó vagy, és szeretnéd felfedezni a .NET-alkalmazásaidban rejlő hatékony dokumentummegjelenítési lehetőségeket, akkor igazi élményben lesz részed. Ebben az átfogó útmutatóban elmerülünk a munkalapnevek GroupDocs.Viewer segítségével történő lekérésének bonyolultságaiban. Kapcsold be a biztonsági övedet, és vágjunk bele ebbe az izgalmas utazásba!
## Előfeltételek
Mielőtt belevágnánk a kódolási varázslatba, győződjünk meg róla, hogy mindent beállítottunk:
1. GroupDocs.Viewer telepítése .NET-hez: Lépjen a következőre: [letöltési link](https://releases.groupdocs.com/viewer/net/) GroupDocs.Viewer for .NET legújabb verziójának letöltéséhez. Kövesse a telepítési utasításokat, hogy zökkenőmentesen integrálhassa a fejlesztői környezetébe.
2. Készítse elő a dokumentumot: Győződjön meg arról, hogy van egy céldokumentum, mondjuk egy „file.xlsx” nevű Excel fájl a kijelölt dokumentumkönyvtárban.
## Névterek importálása
Most, hogy megvannak az előfeltételek, kezdjük a szükséges névterek importálásával. Ez biztosítja, hogy az alkalmazás felismerje és használni tudja a GroupDocs.Viewer for .NET által biztosított funkciókat.
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
Cserélje le a „Saját dokumentumkönyvtár” részt a céldokumentum könyvtárának elérési útjára.
## 2. A néző inicializálása
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Ebben a lépésben létrehozunk egy példányt a Viewer osztályból, amely megadja az Excel-fájl elérési útját.
## 3. Információk megtekintésének beállításainak konfigurálása
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Itt konfiguráljuk a ViewInfoOptions paramétereket HTML nézetek generálásához, és további beállításokat adunk meg a táblázatkezelő rendereléséhez.
## 4. Nézetinformációk lekérése
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
A Viewer példány segítségével a konfigurált beállítások alapján kérheti le a nézet adatait.
## 5. Munkalapnevek megjelenítése
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Végigjárja a lekért oldalakat, és kiírja az egyes munkalapok nevét a konzolra.
## Következtetés
Gratulálunk! Sikeresen végigvezette magát a munkalapnevek lekérésének folyamatán a GroupDocs.Viewer for .NET használatával. Ez számos lehetőséget nyit meg az alkalmazások dokumentummegjelenítési funkcióinak fejlesztésére.
## GYIK
### Használhatom a GroupDocs.Viewer for .NET-et más dokumentumformátumokkal?
Abszolút! A GroupDocs.Viewer számos dokumentumformátumot támogat, beleértve a PDF-et, a Microsoft Office-t és egyebeket.
### Van ingyenes próbaverzió?
Igen, a GroupDocs.Viewer for .NET-et a mi oldalunkon is felfedezheti. [ingyenes próba](https://releases.groupdocs.com/).
### Hol találok további támogatást?
Menj a [GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) közösségi támogatásért és a beszélgetésekért.
### Szerezhetek ideiglenes jogosítványt?
Természetesen! Látogasson el [ezt a linket](https://purchase.groupdocs.com/temporary-license/) hogy megszerezd az ideiglenes jogosítványodat.
### Vannak részletes dokumentációs források?
Feltétlenül! Nézd meg a [hivatalos dokumentáció](https://tutorials.groupdocs.com/viewer/net/) részletes információkért és útmutatókért.