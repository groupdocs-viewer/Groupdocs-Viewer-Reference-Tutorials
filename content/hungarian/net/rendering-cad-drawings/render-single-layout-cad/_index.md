---
"description": "Ismerje meg, hogyan jeleníthet meg egyetlen elrendezést CAD rajzokban a GroupDocs.Viewer for .NET segítségével. Egyszerű lépések a .NET alkalmazásokba való zökkenőmentes integrációhoz."
"linktitle": "Egyetlen elrendezés renderelése CAD rajzokban"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Egyetlen elrendezés renderelése CAD rajzokban"
"url": "/hu/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# Egyetlen elrendezés renderelése CAD rajzokban

## Bevezetés
A .NET fejlesztés területén a CAD-rajzok kezelése és megtekintése gyakori követelmény. A GroupDocs.Viewer for .NET leegyszerűsíti ezt a feladatot azáltal, hogy átfogó megoldást kínál a CAD-rajzok .NET-alkalmazásokon belüli renderelésére. Ebben az oktatóanyagban részletesebben bemutatjuk egyetlen elrendezés CAD-rajzokban történő renderelését a GroupDocs.Viewer for .NET segítségével.
## Előfeltételek
Mielőtt belemerülnél az oktatóanyagba, győződj meg róla, hogy a következő előfeltételekkel rendelkezel:
- C# programozási nyelv és .NET keretrendszer alapismeretek.
- Visual Studio telepítve a rendszeredre.
- A GroupDocs.Viewer for .NET könyvtár le van töltve, és a tutorialsd bekerült a projektedbe. Letöltheted innen: [itt](https://releases.groupdocs.com/viewer/net/).
- Ismeri a CAD fájlformátumokat és azok szerkezetét.

## Névterek importálása
Először importáld a szükséges névtereket a C# kódodba a GroupDocs.Viewer funkcióinak eléréséhez.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Kimeneti könyvtár definiálása
Adja meg azt a könyvtárat, ahová a renderelt kimenetet menteni szeretné.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása
Határozza meg az egyes renderelt oldalak fájlelérési útjának formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Viewer objektum példányosítása
Hozz létre egy példányt a GroupDocs.Viewer által biztosított Viewer osztályból.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## 4. lépés: HTML nézet beállításainak konfigurálása
Beágyazott erőforrásokkal rendelkező HTML-kimenet megjelenítési beállításainak konfigurálása.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5. lépés: CAD elrendezés nevének megadása
Adja meg a renderelni kívánt CAD-elrendezés nevét.
```csharp
options.CadOptions.LayoutName = "Model";
```
## 6. lépés: CAD rajz renderelése
Hívd meg a Viewer objektum View metódusát a megadott opciókkal.
```csharp
viewer.View(options);
```
## 7. lépés: Sikeres üzenet megjelenítése
Tájékoztassa a felhasználót a forrásdokumentum sikeres megjelenítéséről.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
A CAD-rajzok renderelése, különösen az elrendezések esetében, ijesztő feladat lehet. A GroupDocs.Viewer for .NET segítségével azonban a folyamat zökkenőmentessé és hatékonnyá válik. Az ebben az oktatóanyagban ismertetett lépéseket követve könnyedén renderelhet egyetlen elrendezést a CAD-rajzokban a .NET-alkalmazásaiban.
## GYIK
### Renderelhetek több elrendezést egyszerre a GroupDocs.Viewer for .NET használatával?
Igen, a GroupDocs.Viewer for .NET támogatja több elrendezés renderelését CAD rajzokból.
### Kompatibilis a GroupDocs.Viewer a különböző CAD fájlformátumokkal?
A GroupDocs.Viewer természetesen számos CAD fájlformátumot támogat, beleértve a DWG, DXF, DGN és egyebeket.
### Testreszabhatom a CAD rajzok renderelési beállításait?
Igen, a GroupDocs.Viewer széleskörű lehetőségeket kínál a renderelési beállítások testreszabásához az Ön igényei szerint.
### Van ingyenes próbaverzió a GroupDocs.Viewer for .NET-hez?
Igen, ingyenes próbaverzióval felfedezheti a GroupDocs.Viewer funkcióit. [itt](https://releases.groupdocs.com/).
### Hol kaphatok támogatást a GroupDocs.Viewer for .NET-hez?
Bármilyen kérdés vagy segítség esetén látogassa meg a GroupDocs.Viewer fórumot. [itt](https://forum.groupdocs.com/c/viewer/9).