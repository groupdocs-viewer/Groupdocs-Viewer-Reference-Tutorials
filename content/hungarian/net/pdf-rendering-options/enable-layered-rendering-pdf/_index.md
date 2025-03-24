---
title: Réteges megjelenítés engedélyezése PDF-ben
linktitle: Réteges megjelenítés engedélyezése PDF-ben
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan engedélyezheti a réteges megjelenítést PDF-dokumentumokban a GroupDocs.Viewer for .NET segítségével. Fokozza a dokumentummegtekintési élményt könnyedén.
weight: 15
url: /hu/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Bevezetés
Ebben az oktatóanyagban a GroupDocs.Viewer for .NET használatával lehetővé teszi a réteges megjelenítést PDF dokumentumokban. A réteges megjelenítés lehetővé teszi a dokumentumok jobb megjelenítését és kezelését, így a felhasználók interaktívabb megtekintési élményt nyújtanak.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. GroupDocs.Viewer for .NET: Győződjön meg arról, hogy telepítette a GroupDocs.Viewer for .NET projektben való használatához szükséges csomagot vagy könyvtárat.
2. Visual Studio: A rendszerre telepítve kell lennie a Visual Studionak a megadott példák kódolásához és végrehajtásához.
3. A C# alapvető ismerete: Ez az oktatóanyag feltételezi a C# programozási nyelv szintaxisának és fogalmainak ismeretét.

## Névterek importálása
Kezdje azzal, hogy importálja a szükséges névtereket a projektbe:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
Győződjön meg arról, hogy megadta a könyvtár elérési útját, ahová a renderelt kimenetet menteni szeretné.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Ez a lépés beállítja az egyes oldalak fájlútvonalainak formátumát a renderelt kimenetben.`{0}` az oldalszám helyőrzője.
## 3. lépés: Engedélyezze a réteges megjelenítést
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Itt létrehozunk a`Viewer` objektumot, és adja meg a feldolgozandó PDF-dokumentumot. Ezután konfiguráljuk`HtmlViewOptions` a megadott oldalfájl elérési út formátummal. A beállítással`EnableLayeredRendering` tulajdonát`true` ban ben`PdfOptions`, engedélyezzük a réteges megjelenítést a PDF-dokumentum számára.
## 4. lépés: Jelenítse meg a kimeneti könyvtárat
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Végül egy üzenetet nyomtatunk, amely jelzi a forrásdokumentum sikeres megjelenítését, és felszólítja a felhasználót, hogy ellenőrizze a kimenetet a megadott könyvtárban.

## Következtetés
A réteges megjelenítés engedélyezése PDF-dokumentumokban a GroupDocs.Viewer for .NET segítségével javítja a dokumentummegtekintési képességeket, gazdagabb és interaktívabb élményt biztosítva a felhasználóknak. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen integrálhatja ezt a funkciót .NET-alkalmazásaiba.
## GYIK
### Mi az a réteges megjelenítés a PDF dokumentumokban?
réteges megjelenítés lehetővé teszi a PDF-dokumentum különböző összetevőinek szétválasztását és kezelését, lehetővé téve az interaktív megtekintést és a jobb felhasználói élményt.
### Testreszabhatom a kimeneti könyvtárat a renderelt dokumentumokhoz?
Igen, tetszőleges könyvtárútvonalat megadhat a kimenethez az igényeinek megfelelően.
### A GroupDocs.Viewer a PDF-en kívül más fájlformátumokat is támogat?
Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a Word, Excel, PowerPoint és egyebeket.
### A GroupDocs.Viewer kompatibilis a .NET Core programmal?
Igen, a GroupDocs.Viewer kompatibilis mind a .NET-keretrendszerrel, mind a .NET Core környezettel.
### Hol találhatok további támogatást vagy segítséget?
Látogassa meg a GroupDocs.Viewer fórumot, ha bármilyen kérdése van, vagy segítségre van szüksége a megjelenítő könyvtárral kapcsolatban.