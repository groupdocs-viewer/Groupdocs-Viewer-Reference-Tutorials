---
title: Rendereljen le minden elrendezést CAD-rajzokban
linktitle: Rendereljen le minden elrendezést CAD-rajzokban
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan jeleníthet meg minden elrendezést CAD-rajzokban a GroupDocs.Viewer for .NET segítségével. Kövesse átfogó oktatóanyagunkat a zökkenőmentes integráció érdekében.
weight: 11
url: /hu/net/rendering-cad-drawings/render-all-layouts-cad/
---
## Bevezetés
dokumentumkezelés és -vizualizáció területén a GroupDocs.Viewer for .NET sokoldalú megoldásként megállja a helyét, lehetővé téve a fejlesztők számára, hogy könnyedén készítsenek különféle dokumentumtípusokat .NET-alkalmazásaikon belül. Számtalan képessége közé tartozik a CAD-rajzok hatékony renderelése, beleértve a bonyolult elrendezéseket is. Ebben az oktatóanyagban a GroupDocs.Viewer for .NET kiaknázásának folyamatát mutatjuk be a CAD-rajzokban található összes elrendezés megjelenítéséhez. 
## Előfeltételek
Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. A .NET-fejlesztés alapjai: A .NET-fejlesztés alapjainak ismerete hasznos lesz az oktatóanyagban ismertetett megvalósítási lépések megértésében.
2.  A GroupDocs.Viewer for .NET telepítése: Győződjön meg arról, hogy telepítette a GroupDocs.Viewer for .NET könyvtárat. Letöltheti a[weboldal](https://releases.groupdocs.com/viewer/net/).
3. CAD rajzfájlok: Szerezze be a renderelni kívánt CAD rajzfájlokat. Ezek lehetnek több elrendezésű DWG-fájlok.
4. Fejlesztési környezet: Állítsa be kedvenc fejlesztői környezetét a szükséges eszközökkel és függőségekkel.

## Névterek importálása
Először is győződjön meg arról, hogy importálja a szükséges névtereket a .NET-projektbe. Ezek a névterek hozzáférést biztosítanak a CAD-rajzok GroupDocs.Viewer segítségével történő megjelenítéséhez szükséges funkciókhoz.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 2. lépés: Importálja a System.IO névteret
```csharp
using System.IO;
```
## 1. lépés: Adja meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
Határozza meg azt a könyvtárat, ahová a renderelt kimenetet menteni szeretné.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Állítsa be a megjelenített oldalak fájlútvonalának formátumát. Ebben az esetben az oldalak HTML-fájlként kerülnek mentésre.
## 3. lépés: Példányosítsa a Viewer objektumot
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Hozzon létre egy példányt a Viewer osztályból, paraméterként adja át a CAD rajzfájl elérési útját.
## 4. lépés: Konfigurálja a HTML nézet beállításait
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Állítsa be a HTML nézet beállításait, és adja meg, hogy a CAD-rajzokhoz az elrendezéseket meg kell jeleníteni.
## 5. lépés: Renderelje le a CAD-rajzot
```csharp
viewer.View(options);
```
Hívja meg a Viewer objektum View metódusát, és adja át a konfigurált beállításokat a CAD-rajz megjelenítéséhez.
## 6. lépés: Jelenítse meg a kimeneti könyvtárat
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tájékoztassa a felhasználót a sikeres renderelésről és a kimeneti könyvtár helyéről.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan használható a GroupDocs.Viewer for .NET a CAD-rajzokban található összes elrendezés megjelenítésére. A lépésenkénti útmutató követésével és a mellékelt kódrészletek implementálásával zökkenőmentesen integrálhatja ezt a funkciót .NET-alkalmazásaiba, ezáltal javítva a dokumentumok megjelenítési képességeit.
## GYIK
### A GroupDocs.Viewer kompatibilis a különböző CAD formátumokkal?
Igen, a GroupDocs.Viewer támogatja a CAD-rajzok megjelenítését olyan formátumokban, mint a DWG és a DXF.
### Testreszabhatom a renderelési kimenetet az alkalmazásom követelményei szerint?
Természetesen a GroupDocs.Viewer számos lehetőséget kínál a megjelenítési kimenet testreszabásához, beleértve a képminőséget, az oldalméretet és egyebeket.
### A GroupDocs.Viewernek szüksége van további licencekre kereskedelmi használatra?
Igen, kereskedelmi használatra lehet, hogy licencet kell szereznie. A webhelyről ideiglenes licenceket szerezhet tesztelési célokra, vagy vásárolhat kereskedelmi licencet.
### Renderelhetek CAD-rajzokat aszinkron módon a GroupDocs.Viewer programmal?
Igen, a GroupDocs.Viewer aszinkron megjelenítési képességeket biztosít, lehetővé téve a nagy CAD-rajzok hatékony kezelését a fő szál blokkolása nélkül.
### A GroupDocs.Viewer támogatja a hibaelhárítást és a technikai segítséget?
 Természetesen kérhet támogatást és segítséget a GroupDocs.Viewer közösségi fórumon, amely elérhető[itt](https://forum.groupdocs.com/c/viewer/9).