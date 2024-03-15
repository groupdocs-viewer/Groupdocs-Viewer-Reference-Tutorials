---
title: Lapok átfordítása és forgatása
linktitle: Lapok átfordítása és forgatása
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan integrálhatja a Groupdocs.Viewer for .NET-et alkalmazásaiba a zökkenőmentes dokumentum-megjelenítés, lapozás és elforgatás érdekében.
type: docs
weight: 12
url: /hu/net/rendering-options/flip-rotate-pages/
---
## Bevezetés
Ebben az oktatóanyagban a Groupdocs.Viewer for .NET funkcióival foglalkozunk, különös tekintettel az oldalak lapozására és forgatására. A Groupdocs.Viewer for .NET egy hatékony eszköz, amelyet különféle formátumú dokumentumok megjelenítésére terveztek .NET-alkalmazásokon belül. Akár dokumentumkezelő rendszert fejleszt, akár dokumentummegtekintési képességeket szeretne szoftverébe integrálni, a Groupdocs.Viewer for .NET hatékony megoldást kínál.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy beállította a következő előfeltételeket:
### A Groupdocs.Viewer for .NET telepítése
 A Groupdocs.Viewer for .NET használatához telepítenie kell a csomagot a NuGet Package Manageren keresztül. A részletes telepítési útmutatót a[dokumentáció](https://reference.groupdocs.com/viewer/net/).

## Névterek importálása
Győződjön meg arról, hogy a szükséges névtereket importálta a projektbe a Groupdocs.Viewer for .NET hatékony használatához.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bontsuk le egyszerű lépésekre a Groupdocs.Viewer for .NET segítségével történő lapozási és forgatási folyamatot:
## 1. lépés: Állítsa be a kimeneti könyvtárat és a fájl elérési útját
Határozza meg a könyvtárat, ahová a kimeneti fájlt menteni szeretné, és adja meg a kimeneti fájl elérési útját.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## 2. lépés: Inicializálja a Viewer Object-et
Hozzon létre egy példányt a Viewer osztályból a megtekinteni kívánt dokumentum elérési útjának átadásával.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## 3. lépés: Állítsa be a nézetbeállításokat
Állítsa be a nézetbeállításokat, például adja meg a kimeneti fájl formátumát és minden további beállítást, például az oldalelforgatást.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## 4. lépés: Renderelje le a dokumentumot
Hívja meg a Viewer objektum View metódusát, és adja át a nézetbeállításokat.
```csharp
viewer.View(viewOptions);
```
## 5. lépés: Jelenítse meg a sikeres üzenetet
Tájékoztassa a felhasználót a dokumentum sikeres megjelenítéséről, és adja meg a kimeneti könyvtárat az ellenőrzéshez.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Összefoglalva, a Groupdocs.Viewer for .NET hatékony lehetőségeket kínál a dokumentumok renderelésére, beleértve az oldalak lapozását és elforgatását. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen integrálhatja ezeket a szolgáltatásokat .NET-alkalmazásaiba, javítva a felhasználók dokumentummegtekintési élményét.
## GYIK
### A Groupdocs.Viewer for .NET kompatibilis az összes dokumentumformátummal?
Igen, a Groupdocs.Viewer for .NET a dokumentumformátumok széles skáláját támogatja, beleértve a DOCX, PDF, PPTX és egyebeket.
### Testreszabhatom a megtekintési beállításokat a lapozáson és az elforgatáson túl?
Természetesen a Groupdocs.Viewer for .NET különféle testreszabási lehetőségeket kínál a dokumentumok megtekintésére, lehetővé téve, hogy az élményt az Ön igényei szerint szabja.
### Elérhető ingyenes próbaverzió a Groupdocs.Viewer for .NET számára?
 Igen, igénybe veheti a Groupdocs.Viewer for .NET ingyenes próbaverzióját, ha felkeresi a[weboldal](https://releases.groupdocs.com/).
### Hogyan kaphatok támogatást a Groupdocs.Viewer for .NET számára?
 Segítséget kérhet, és kapcsolatba léphet a közösséggel a[Groupdocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9).
### Hol szerezhetek ideiglenes licencet a Groupdocs.Viewer for .NET számára?
 Ideiglenes licencek a Groupdocs.Viewer for .NET-hez a következő webhelyen szerezhetők be[vásárlási oldal](https://purchase.groupdocs.com/temporary-license/).