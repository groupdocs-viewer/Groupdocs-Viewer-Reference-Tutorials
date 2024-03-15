---
title: Dátum-idő formátum és időzóna eltolás beállítása (e-mail)
linktitle: Dátum-idő formátum és időzóna eltolás beállítása (e-mail)
second_title: GroupDocs.Viewer .NET API
description: Integrálja a GroupDocs.Viewer for .NET-et zökkenőmentesen alkalmazásaiba a hatékony dokumentummegtekintési lehetőségek érdekében. Növelje a felhasználói élményt testreszabható opciókkal.
type: docs
weight: 11
url: /hu/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Bevezetés
GroupDocs.Viewer for .NET egy hatékony eszköz, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen integrálják a dokumentummegtekintési képességeket .NET-alkalmazásaikba. A GroupDocs.Viewer segítségével a dokumentumformátumok széles skáláját jelenítheti meg, beleértve a PDF-eket, Microsoft Office dokumentumokat, képeket és még sok mást, közvetlenül az alkalmazáson belül, anélkül, hogy külső bővítményekre vagy megjelenítőkre lenne szüksége. Ebben az átfogó oktatóanyagban végigvezetjük a GroupDocs.Viewer for .NET beállításának folyamatán, feltárjuk annak funkcióit, és bemutatjuk, hogyan lehet hatékonyan felhasználni az alkalmazás dokumentummegtekintési képességeinek javítására.
## Előfeltételek
Mielőtt belevágna ebbe az oktatóanyagba, győződjön meg arról, hogy beállította a következő előfeltételeket:
1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren. A GroupDocs.Viewer for .NET teljes mértékben kompatibilis a Visual Studióval, lehetővé téve a .NET-projektekbe való zökkenőmentes integrációt.
2.  GroupDocs.Viewer for .NET: Töltse le és telepítse a GroupDocs.Viewer for .NET programot a[letöltési link](https://releases.groupdocs.com/viewer/net/). Kövesse a kapott telepítési utasításokat a könyvtár beállításához a fejlesztői környezetben.
3. .NET-keretrendszer: Győződjön meg arról, hogy a .NET-keretrendszer megfelelő verziója telepítve van. A GroupDocs.Viewer for .NET támogatja a .NET-keretrendszer különféle verzióit, köztük a .NET Core-t és a .NET Standard-t.

## Névterek importálása
A GroupDocs.Viewer for .NET hatékony használatához importálnia kell a szükséges névtereket a projektbe. Kövesse az alábbi lépéseket a szükséges névterek importálásához:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Bontsuk fel a megadott példát több lépésre, hogy megértsük az egyes összetevőket és funkcióikat.
## 1. lépés: Állítsa be a kimeneti könyvtárat és a fájl elérési útját
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Ebben a lépésben meghatározzuk a kimeneti könyvtárat, ahová a renderelt dokumentumot menteni kell, és megadjuk a kimeneti HTML fájl elérési útját.
## 2. lépés: Példányosítsa a Viewer objektumot
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Itt létrehozzuk a`Viewer` osztályban, paraméterként átadva a megtekinteni kívánt dokumentum (jelen esetben egy minta EML fájl) elérési útját.
## 3. lépés: Adja meg a HTML nézet beállításait
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Ebben a lépésben konfiguráljuk a dokumentum-megjelenítés HTML-nézeti beállításait, megadva a renderelt HTML-dokumentum kimeneti fájljának elérési útját.
## 4. lépés: Állítsa be a dátum és idő formátumát és az időzóna eltolását
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Itt testreszabjuk az e-mail üzenetek dátum- és időformátumát, és beállítjuk az időzóna eltolását a kívánt időzónának megfelelően.
## 5. lépés: Renderelje le a dokumentumot
```csharp
viewer.View(options);
```
 Végül hívjuk a`View` módszere a`Viewer` objektumot, átadva a konfigurált HTML nézetbeállításokat, hogy a dokumentumot HTML formátumba renderelje.
## 6. lépés: Jelenítse meg a kimeneti könyvtárat
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ez a lépés egyszerűen megjelenít egy üzenetet, amely jelzi a dokumentum sikeres megjelenítését, és megadja a kimeneti könyvtár elérési útját, ahol a renderelt HTML-dokumentum található.

## Következtetés
GroupDocs.Viewer for .NET robusztus megoldást kínál a dokumentummegtekintési képességek .NET-alkalmazásaiba való integrálására. Az oktatóanyagban ismertetett lépések követésével könnyedén beállíthatja a GroupDocs.Viewer programot, importálhatja a szükséges névtereket, és funkcióit használhatja a dokumentumok testreszabható opciókkal történő megjelenítésére. Függetlenül attól, hogy PDF-ekkel, Microsoft Office dokumentumokkal vagy más formátumokkal dolgozik, a GroupDocs.Viewer leegyszerűsíti a dokumentumok megtekintésének folyamatát, javítva az alkalmazások felhasználói élményét.
## GYIK
### A GroupDocs.Viewer kompatibilis a .NET Core programmal?
Igen, a GroupDocs.Viewer for .NET támogatja a .NET Core-t, lehetővé téve az alkalmazások platformok közötti kompatibilitását.
### Testreszabhatom a renderelt dokumentumok megjelenését?
Teljesen! A GroupDocs.Viewer különféle testreszabási lehetőségeket kínál, beleértve a nagyítási szinteket, az oldalelforgatást és még sok mást, hogy a megtekintési élményt az Ön preferenciái szerint szabja személyre.
### Létezik próbaverzió tesztelési célból?
 Igen, letöltheti a GroupDocs.Viewer .NET ingyenes próbaverzióját a webhelyről[weboldal link](https://releases.groupdocs.com/viewer/net/) hogy vásárlás előtt értékelje tulajdonságait.
### A GroupDocs.Viewer támogatja a jelszóval védett dokumentumok megjelenítését?
Igen, a GroupDocs.Viewer beépített támogatással rendelkezik a jelszóval védett dokumentumok megjelenítéséhez, így biztosítva a biztonságos dokumentummegtekintést az alkalmazásokon belül.
### Hol találok további támogatást vagy segítséget a GroupDocs.Viewer programhoz?
 Bármilyen technikai kérdéssel vagy segítséggel kapcsolatban keresse fel a GroupDocs.Viewer webhelyet[fórum](https://forum.groupdocs.com/c/viewer/9) vagy azonnali segítségért és útmutatásért forduljon ügyfélszolgálati csapatához.