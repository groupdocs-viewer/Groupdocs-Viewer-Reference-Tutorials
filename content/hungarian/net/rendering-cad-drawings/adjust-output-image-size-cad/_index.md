---
title: Állítsa be a kimeneti kép méretét a CAD-rajzokhoz
linktitle: Állítsa be a kimeneti kép méretét a CAD-rajzokhoz
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan állíthatja be a kimeneti képméretet CAD-rajzokhoz a GroupDocs.Viewer for .NET segítségével. Fokozatmentesen javítja a láthatóságot és a használhatóságot.
weight: 15
url: /hu/net/rendering-cad-drawings/adjust-output-image-size-cad/
---
## Bevezetés
A CAD-rajzok gyakran speciális beállításokat igényelnek az optimális megtekintéshez és megjelenítéshez. A GroupDocs.Viewer for .NET hatékony eszközkészletet biztosít a CAD-rajzok kimenetének kezeléséhez és testreszabásához. Ebben az oktatóanyagban lépésről lépésre végigvezetjük a CAD-rajzok kimeneti képméretének beállításán.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  GroupDocs.Viewer for .NET: Töltse le és telepítse a GroupDocs.Viewer for .NET programot innen[itt](https://releases.groupdocs.com/viewer/net/).
2. Dokumentumkönyvtár: Készítse elő azt a könyvtárat, ahol a dokumentuma található.
3. Alapvető ismeretek: Ismerkedjen meg a .NET programozás alapvető fogalmaival.

## Névterek importálása
Először is importálja a szükséges névtereket a GroupDocs.Viewer funkcióinak eléréséhez:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Állítsa be a kimeneti könyvtárat
Határozza meg a könyvtárat, ahol a CAD-rajzok kimeneti képeit tárolni kívánja:
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
Állítsa be az oldalfájl elérési útjainak formátumát. Ez a formátum az egyes oldalak elnevezésére és HTML-fájlként való mentésére szolgál:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Állítsa be a képméretet
Viewer objektum használati blokkjában állítsa be a CAD-rajzok képméretét a megfelelő beállítások megadásával:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## 4. lépés: Jelenítse meg a kimeneti könyvtárat
A dokumentum megjelenítése után jelenítsen meg egy üzenetet, amely jelzi a sikeres megjelenítést, és adja meg a kimeneti könyvtár helyét:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
A CAD-rajzok kimeneti képméretének beállítása döntő fontosságú a láthatóság és a használhatóság javítása szempontjából. A GroupDocs.Viewer for .NET segítségével ez a folyamat leegyszerűsödik és hatékony, lehetővé téve a kimenet testreszabását sajátos igényei szerint.
## GYIK
### Beállíthatom a kimeneti kép méretét a CAD-rajzokon kívül más típusú dokumentumokhoz is?
Igen, a GroupDocs.Viewer for .NET különféle dokumentumtípusokat támogat, és a legtöbb dokumentumformátumhoz beállíthatja a kimeneti képméretet.
### A GroupDocs.Viewer for .NET kompatibilis a .NET keretrendszer különböző verzióival?
Igen, a GroupDocs.Viewer for .NET kompatibilis a .NET keretrendszer több verziójával, rugalmasságot és használhatóságot biztosítva a különböző környezetekben.
### Rendelkezésre állnak-e licencelési lehetőségek a GroupDocs.Viewer for .NET számára?
Igen, az igényeinek megfelelően különféle licencelési lehetőségeket fedezhet fel, beleértve az ideiglenes licenceket és a kereskedelmi licenceket.
### Testreszabhatom a renderelt dokumentumok kimeneti formátumát?
Természetesen a GroupDocs.Viewer for .NET különféle testreszabási lehetőségeket kínál, amelyek lehetővé teszik a kimeneti formátum testreszabását az Ön igényei szerint.
### Hol találok további támogatást vagy segítséget a GroupDocs.Viewer for .NET-hez?
 Látogassa meg a GroupDocs.Viewer fórumot[itt](https://forum.groupdocs.com/c/viewer/9) támogatást kapni, kérdéseket feltenni, és kapcsolatba lépni a közösséggel.