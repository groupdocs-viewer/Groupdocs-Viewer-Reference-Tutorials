---
title: Rendereljen PDF-et eredeti oldalmérettel
linktitle: Rendereljen PDF-et eredeti oldalmérettel
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet eredeti oldalmérettel PDF-eket renderelni a GroupDocs.Viewer for .NET segítségével. Kövesse lépésről lépésre útmutatónkat, és zökkenőmentesen integrálja ezt a funkciót.
weight: 17
url: /hu/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Bevezetés
A .NET fejlesztés területén a GroupDocs.Viewer hatékony eszköz a különféle dokumentumformátumok, köztük a PDF-ek renderelésére. A dokumentumkezelés egyik általános követelménye a PDF-ek eredeti oldalméretének megőrzése mellett történő megjelenítése. E feladat zökkenőmentes megvalósításához a GroupDocs.Viewer for .NET és funkcióinak átfogó ismerete szükséges.
## Előfeltételek
Mielőtt belevágna a PDF-ek eredeti oldalmérettel történő megjelenítésébe a GroupDocs.Viewer for .NET használatával, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
### 1. Telepítse a GroupDocs.Viewer for .NET programot
 Kezdje a GroupDocs.Viewer könyvtár letöltésével a webhelyről. A könyvtárat a rendelkezésre álló helyen szerezheti be[letöltési link](https://releases.groupdocs.com/viewer/net/). Kövesse a dokumentációban található telepítési utasításokat, hogy hatékonyan integrálja a .NET-projektbe.
### 2. Fejlesztői környezet beállítása
Győződjön meg arról, hogy be van állítva egy fejlesztői környezet a .NET fejlesztéshez. Ez magában foglalja a kompatibilis IDE telepítését, mint például a Visual Studio, és a C# programozás alapvető ismereteit.
### 3. Szerezzen be egy PDF-dokumentumot
Szüksége lesz egy minta PDF-dokumentumra a GroupDocs.Viewer programmal való megjelenítéshez. Tesztelési célokra bármilyen PDF dokumentumot használhat. Ha nem rendelkezik ilyennel, letölthet egy PDF-mintát különböző online forrásokból.

## Névterek importálása
Mielőtt folytatná a PDF-ek renderelését, elengedhetetlen, hogy a szükséges névtereket importálja a C#-projektbe. Ez a lépés lehetővé teszi a szükséges osztályok és metódusok elérését a GroupDocs.Viewer könyvtárból.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most, hogy megvannak az előfeltételek, és importálták a szükséges névtereket, bontsuk le egyszerű lépésekre a PDF-ek eredeti oldalmérettel történő megjelenítésének folyamatát a GroupDocs.Viewer for .NET segítségével:
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
 Győződjön meg arról, hogy megadta azt a könyvtárat, ahová a megjelenített oldalakat menteni szeretné. Cserélje ki`"Your Document Directory"` a kívánt könyvtár elérési útjával.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Állítsa be a megjelenített oldalfájlok elnevezésének formátumát. Ebben a példában az oldalakat PNG-képként menti a rendszer, a fájlnevekkel a formátumban`"page_1.png"`, `"page_2.png"`, stb.
## 3. lépés: Rendeljen PDF-et eredeti oldalmérettel
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Példányosítás a`Viewer` objektumot a PDF-fájl elérési útjával. Ezután hozzon létre`PngViewOptions` a megadott oldalfájl elérési út formátummal. Készlet`RenderOriginalPageSize` tulajdonát`true` hogy renderelés közben megőrizze az eredeti oldalméreteket.
## 4. lépés: Jelenítse meg a renderelt dokumentum helyét
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nyomtasson ki egy üzenetet, amely jelzi a sikeres renderelést, és adja meg a könyvtárat, ahová a renderelt oldalak mentésre kerültek.

## Következtetés
A PDF-ek eredeti oldalmérettel való megjelenítése a GroupDocs.Viewer for .NET segítségével egyszerű folyamat, ha követi az oktatóanyagban ismertetett lépéseket. A szükséges névterek importálásával és a lépésenkénti útmutató követésével zökkenőmentesen integrálhatja ezt a funkciót .NET-alkalmazásaiba.
## GYIK
### A GroupDocs.Viewer a PDF-en kívül más dokumentumformátumokat is megjeleníthet?
Igen, a GroupDocs.Viewer támogatja a különféle dokumentumformátumok renderelését, beleértve a Word, Excel, PowerPoint és egyebeket.
### A GroupDocs.Viewer kompatibilis a .NET Core programmal?
Igen, a GroupDocs.Viewer kompatibilis mind a .NET-keretrendszerrel, mind a .NET Core környezettel.
### Testreszabhatom a megjelenített oldalak kimeneti formátumát?
Igen, testreszabhatja a kimeneti formátumot a GroupDocs.Viewer által biztosított beállítások módosításával, például különböző képformátumok beállításával vagy egyéni megjelenítési beállítások megadásával.
### A GroupDocs.Viewer támogatja a felhő alapú dokumentum-megjelenítést?
Igen, a GroupDocs.Viewer API-kat biztosít a felhő alapú dokumentum-megjelenítéshez, lehetővé téve a dokumentumok közvetlenül a felhőalapú tárolási szolgáltatóktól való megjelenítését.
### Van ingyenes próbaverzió a GroupDocs.Viewer számára?
 Igen, felfedezheti a GroupDocs.Viewer programot egy ingyenes próbaverzióval, ha ellátogat a biztosított oldalra[link](https://releases.groupdocs.com/).