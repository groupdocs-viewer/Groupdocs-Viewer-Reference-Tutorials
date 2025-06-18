---
"description": "Tanulja meg, hogyan jeleníthet meg PDF-fájlokat eredeti oldalméretekkel a GroupDocs.Viewer for .NET segítségével. Kövesse lépésről lépésre szóló útmutatónkat, és integrálja zökkenőmentesen ezt a funkciót."
"linktitle": "PDF renderelése az eredeti oldalmérettel"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF renderelése az eredeti oldalmérettel"
"url": "/hu/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# PDF renderelése az eredeti oldalmérettel

## Bevezetés
.NET fejlesztés területén a GroupDocs.Viewer kiemelkedően hatékony eszköz különféle dokumentumformátumok, köztük PDF-ek megjelenítéséhez. A dokumentumkezelés egyik gyakori követelménye a PDF-ek megjelenítése az eredeti oldalméret megőrzése mellett. Ennek a feladatnak a zökkenőmentes megvalósításához átfogó ismeretekre van szükség a GroupDocs.Viewer for .NET alkalmazásban és annak funkcióiban.

![PDF renderelése az eredeti oldalmérettel a GroupDocs.Viewer .NET segítségével](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Előfeltételek
Mielőtt belevágna a PDF-ek eredeti oldalméretekkel történő renderelésében a GroupDocs.Viewer for .NET segítségével, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
### 1. Telepítse a GroupDocs.Viewer for .NET programot
Kezdje a GroupDocs.Viewer könyvtár letöltésével a weboldalról. A könyvtárat a mellékelt [letöltési link](https://releases.groupdocs.com/viewer/net/)Kövesse a dokumentációban található telepítési utasításokat a .NET projektbe való hatékony integráláshoz.
### 2. Fejlesztői környezet beállítása
Győződjön meg arról, hogy rendelkezik egy .NET fejlesztéshez beállított fejlesztői környezettel. Ez magában foglalja egy kompatibilis IDE telepítését, például a Visual Studio használatát, valamint a C# programozás alapvető ismeretét.
### 3. PDF dokumentum beszerzése
Szükséged lesz egy minta PDF dokumentumra a GroupDocs.Viewerrel való megjelenítéshez. Bármely PDF dokumentumot használhatsz tesztelési célokra. Ha nincs ilyened, letölthetsz egy minta PDF dokumentumot különböző online forrásokból.

## Névterek importálása
A PDF-ek renderelésének folytatása előtt elengedhetetlen a szükséges névterek importálása a C#-projektbe. Ez a lépés lehetővé teszi a szükséges osztályok és metódusok elérését a GroupDocs.Viewer könyvtárból.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most, hogy megvannak az előfeltételek és importálva vannak a szükséges névterek, bontsuk le egyszerű lépésekre a PDF-ek eredeti oldalméretekkel történő renderelésének folyamatát a GroupDocs.Viewer for .NET használatával:
## 1. lépés: Kimeneti könyvtár definiálása
```csharp
string outputDirectory = "Your Document Directory";
```
Győződjön meg arról, hogy megadta azt a könyvtárat, ahová a renderelt oldalakat menteni szeretné. `"Your Document Directory"` a kívánt könyvtár elérési útjával.
## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Állítsa be a renderelt oldalfájlok elnevezési formátumát. Ebben a példában az oldalak PNG képként lesznek mentve, a fájlnevek formátuma a következő: `"page_1.png"`, `"page_2.png"`, és így tovább.
## 3. lépés: PDF renderelése az eredeti oldalméretben
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Példányosítás egy `Viewer` objektum a PDF-fájl elérési útjával. Ezután hozzon létre `PngViewOptions` a megadott lapozófájl elérési útjának formátumával. Beállítás `RenderOriginalPageSize` ingatlan `true` hogy a renderelés során megőrizze az eredeti oldalméreteket.
## 4. lépés: A renderelt dokumentum helyének megjelenítése
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nyomtasson ki egy üzenetet a sikeres renderelést jelzően, és adja meg a renderelt oldalak mentési könyvtárát.

## Következtetés
PDF-ek eredeti oldalméretekkel történő renderelése a GroupDocs.Viewer for .NET segítségével egyszerűen elvégezhető, ha követi az ebben az oktatóanyagban ismertetett lépéseket. A szükséges névterek importálásával és a lépésenkénti útmutató követésével zökkenőmentesen integrálhatja ezt a funkciót .NET-alkalmazásaiba.
## GYIK
### A GroupDocs.Viewer képes a PDF-en kívül más dokumentumformátumokat is megjeleníteni?
Igen, a GroupDocs.Viewer különféle dokumentumformátumok renderelését támogatja, beleértve a Wordöt, az Excelt, a PowerPointot és egyebeket.
### Kompatibilis a GroupDocs.Viewer a .NET Core-ral?
Igen, a GroupDocs.Viewer kompatibilis mind a .NET Framework, mind a .NET Core környezetekkel.
### Testreszabhatom a renderelt oldalak kimeneti formátumát?
Igen, testreszabhatja a kimeneti formátumot a GroupDocs.Viewer által biztosított beállítások módosításával, például különböző képformátumok beállításával vagy egyéni renderelési beállítások megadásával.
### A GroupDocs.Viewer támogatja a felhőalapú dokumentumrenderelést?
Igen, a GroupDocs.Viewer API-kat biztosít a felhőalapú dokumentumrendereléshez, lehetővé téve a dokumentumok közvetlen felhőalapú tárhelyszolgáltatókból történő renderelését.
### Van ingyenes próbaverzió a GroupDocs.Viewerhez?
Igen, kipróbálhatja a GroupDocs.Viewer programot ingyenesen a megadott weboldalon. [link](https://releases.groupdocs.com/).