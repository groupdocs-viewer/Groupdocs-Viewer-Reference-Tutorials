---
title: Egyetlen elrendezés renderelése CAD-rajzokban
linktitle: Egyetlen elrendezés renderelése CAD-rajzokban
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan jeleníthet meg egyetlen elrendezést CAD-rajzokban a GroupDocs.Viewer for .NET segítségével. Egyszerű lépések a .NET-alkalmazásokba való zökkenőmentes integrációhoz.
weight: 14
url: /hu/net/rendering-cad-drawings/render-single-layout-cad/
---
## Bevezetés
.NET fejlesztés területén általános követelmény a CAD-rajzok kezelése és megtekintése. A GroupDocs.Viewer for .NET leegyszerűsíti ezt a feladatot, mivel átfogó megoldást kínál a CAD-rajzok .NET-alkalmazásokon belüli megjelenítésére. Ebben az oktatóanyagban a GroupDocs.Viewer for .NET segítségével egyetlen elrendezés CAD-rajzokban történő megjelenítésével foglalkozunk.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- A C# programozási nyelv és a .NET keretrendszer alapvető ismerete.
- A Visual Studio telepítve van a rendszerére.
-  A GroupDocs.Viewer for .NET könyvtár letöltve és hivatkozva a projektben. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
- A CAD fájlformátumok és azok szerkezetének ismerete.

## Névterek importálása
Először is importálja a szükséges névtereket a C# kódjába a GroupDocs.Viewer funkcióinak eléréséhez.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Határozza meg a kimeneti könyvtárat
Adja meg azt a könyvtárat, ahová a renderelt kimenetet menteni szeretné.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
Határozza meg az egyes megjelenített oldalak fájlútvonalának formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Példányosítsa a Viewer objektumot
Hozzon létre egy példányt a GroupDocs.Viewer által biztosított Viewer osztályból.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## 4. lépés: Konfigurálja a HTML nézet beállításait
Konfigurálja a HTML-kimenet beágyazott erőforrásokkal történő megjelenítési beállításait.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5. lépés: Adja meg a CAD elrendezés nevét
Adja meg a renderelni kívánt CAD-elrendezés nevét.
```csharp
options.CadOptions.LayoutName = "Model";
```
## 6. lépés: Renderelje le a CAD-rajzot
Hívja meg a Viewer objektum View metódusát a megadott beállításokkal.
```csharp
viewer.View(options);
```
## 7. lépés: Jelenítse meg a sikeres üzenetet
Tájékoztassa a felhasználót a forrásdokumentum sikeres megjelenítéséről.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
A CAD-rajzok renderelése, különösen, ha elrendezésekkel foglalkozik, ijesztő feladat lehet. A GroupDocs.Viewer for .NET segítségével azonban a folyamat zökkenőmentes és hatékony lesz. Az oktatóanyagban ismertetett lépések követésével könnyedén előállíthat egyetlen elrendezést CAD-rajzokban a .NET-alkalmazásokon belül.
## GYIK
### Renderelhetek egyidejűleg több elrendezést a GroupDocs.Viewer for .NET használatával?
Igen, a GroupDocs.Viewer for .NET támogatja több elrendezés megjelenítését CAD-rajzokból.
### A GroupDocs.Viewer kompatibilis a különböző CAD fájlformátumokkal?
A GroupDocs.Viewer természetesen a CAD-fájlformátumok széles skáláját támogatja, beleértve a DWG-t, DXF-et, DGN-t és még sok mást.
### Testreszabhatom a CAD-rajzok renderelési beállításait?
Igen, a GroupDocs.Viewer kiterjedt lehetőségeket kínál a megjelenítési beállítások testreszabásához az Ön igényei szerint.
### Elérhető ingyenes próbaverzió a GroupDocs.Viewer for .NET számára?
 Igen, felfedezheti a GroupDocs.Viewer szolgáltatásait egy ingyenes próbaverzióval[itt](https://releases.groupdocs.com/).
### Hol kaphatok támogatást a GroupDocs.Viewer for .NET-hez?
 Ha kérdése van, vagy segítségre van szüksége, keresse fel a GroupDocs.Viewer fórumot[itt](https://forum.groupdocs.com/c/viewer/9).