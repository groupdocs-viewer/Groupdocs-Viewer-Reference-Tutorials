---
"description": "Tanulja meg, hogyan módosíthatja a CAD-rajzok kimeneti képméretét a GroupDocs.Viewer for .NET segítségével. Növelje a láthatóságot és a használhatóságot könnyedén."
"linktitle": "Kimeneti képméret beállítása CAD rajzokhoz"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Kimeneti képméret beállítása CAD rajzokhoz"
"url": "/hu/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Kimeneti képméret beállítása CAD rajzokhoz

## Bevezetés
CAD-rajzok optimális megtekintéséhez és megjelenítéséhez gyakran speciális beállításokra van szükség. A GroupDocs.Viewer for .NET hatékony eszközkészletet biztosít a CAD-rajzok kimenetének kezeléséhez és testreszabásához. Ebben az oktatóanyagban lépésről lépésre végigvezetjük a CAD-rajzok kimeneti képméretének beállításán.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételekkel rendelkezik:
1. GroupDocs.Viewer .NET-hez: Töltse le és telepítse a GroupDocs.Viewer .NET-hez alkalmazást innen: [itt](https://releases.groupdocs.com/viewer/net/).
2. Dokumentumkönyvtár: Készítse elő a könyvtárat, ahol a dokumentum található.
3. Alapismeretek: Ismerkedjen meg a .NET programozás alapfogalmaival.

## Névterek importálása
Először is, importáld a szükséges névtereket a GroupDocs.Viewer funkcióinak eléréséhez:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Kimeneti könyvtár beállítása
Adja meg azt a könyvtárat, ahová a CAD rajzok kimeneti képeit tárolni szeretné:
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása
Állítsa be az oldalfájlok elérési útjának formátumát. Ezt a formátumot fogja használni a rendszer az egyes oldalak HTML-fájlként történő elnevezéséhez és mentéséhez:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Képméret beállítása
A Viewer objektum használati blokkján belül állítsa be a CAD rajzok képméretét a megfelelő beállítások megadásával:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## 4. lépés: Kimeneti könyvtár megjelenítése
A dokumentum renderelése után jelenítsen meg egy üzenetet, amely jelzi a sikeres renderelést, és adja meg a kimeneti könyvtár helyét:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
A CAD-rajzok kimeneti képméretének módosítása kulcsfontosságú a láthatóság és a használhatóság javítása érdekében. A GroupDocs.Viewer for .NET segítségével ez a folyamat egyszerűsödik és hatékonnyá válik, lehetővé téve a kimenet testreszabását az Ön egyedi igényei szerint.
## GYIK
### Beállíthatom a kimeneti kép méretét más típusú dokumentumokhoz is, nem csak CAD rajzokhoz?
Igen, a GroupDocs.Viewer for .NET különféle dokumentumtípusokat támogat, és a legtöbb dokumentumformátumhoz beállíthatja a kimeneti kép méretét.
### Kompatibilis a GroupDocs.Viewer for .NET a .NET keretrendszer különböző verzióival?
Igen, a GroupDocs.Viewer for .NET kompatibilis a .NET keretrendszer több verziójával is, így rugalmasságot és használhatóságot biztosít a különböző környezetekben.
### Vannak licencelési lehetőségek a GroupDocs.Viewer for .NET-hez?
Igen, az igényeidnek megfelelően különböző licencelési lehetőségeket fedezhetsz fel, beleértve az ideiglenes licenceket és a kereskedelmi licenceket is.
### Testreszabhatom a renderelt dokumentumok kimeneti formátumát?
Természetesen a GroupDocs.Viewer for .NET számos testreszabási lehetőséget kínál, lehetővé téve a kimeneti formátum testreszabását az oktatóanyag igényei szerint.
### Hol találok további támogatást vagy segítséget a GroupDocs.Viewer for .NET-hez?
Meglátogathatod a GroupDocs.Viewer fórumot [itt](https://forum.groupdocs.com/c/viewer/9) hogy támogatást kapjon, kérdéseket tegyen fel és kapcsolatba lépjen a közösséggel.