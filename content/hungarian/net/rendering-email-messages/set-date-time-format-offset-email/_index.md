---
"description": "Integrálja zökkenőmentesen a GroupDocs.Viewer for .NET alkalmazást alkalmazásaiba a hatékony dokumentummegtekintési funkciók érdekében. Javítsa a felhasználói élményt testreszabható beállításokkal."
"linktitle": "Dátum/idő formátum és időzóna eltolás beállítása (e-mail)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Dátum/idő formátum és időzóna eltolás beállítása (e-mail)"
"url": "/hu/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
---

# Dátum/idő formátum és időzóna eltolás beállítása (e-mail)


## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony eszköz, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen integrálják a dokumentummegtekintési funkciókat .NET alkalmazásaikba. A GroupDocs.Viewer segítségével számos dokumentumformátumot, többek között PDF-eket, Microsoft Office dokumentumokat, képeket és egyebeket jeleníthet meg közvetlenül az alkalmazáson belül, külső bővítmények vagy megjelenítők használata nélkül. Ebben az átfogó oktatóanyagban végigvezetjük a GroupDocs.Viewer for .NET beállításának folyamatán, megismerkedünk a funkcióival, és bemutatjuk, hogyan használhatja hatékonyan az alkalmazás dokumentummegtekintési képességeinek bővítésére.
## Előfeltételek
Mielőtt belemerülnél ebbe az oktatóanyagba, győződj meg arról, hogy a következő előfeltételek teljesülnek:
1. Visual Studio: Győződjön meg róla, hogy a Visual Studio telepítve van a rendszerén. A GroupDocs.Viewer for .NET teljes mértékben kompatibilis a Visual Studio programmal, így zökkenőmentesen integrálható a .NET projektekbe.
2. GroupDocs.Viewer .NET-hez: Töltse le és telepítse a GroupDocs.Viewer .NET-hez alkalmazást a következő helyről: [letöltési link](https://releases.groupdocs.com/viewer/net/)Kövesse a mellékelt telepítési utasításokat a könyvtár fejlesztői környezetében történő beállításához.
3. .NET-keretrendszer: Győződjön meg arról, hogy a .NET-keretrendszer megfelelő verziója telepítve van. A GroupDocs.Viewer for .NET a .NET-keretrendszer számos verzióját támogatja, beleértve a .NET Core-t és a .NET Standardot is.

## Névterek importálása
A GroupDocs.Viewer for .NET hatékony használatához importálnia kell a szükséges névtereket a projektjébe. A szükséges névterek importálásához kövesse az alábbi lépéseket:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Bontsuk le a bemutatott példát több lépésre, hogy megértsük az egyes komponenseket és azok funkcióit.
## 1. lépés: Kimeneti könyvtár és fájlútvonal beállítása
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Ebben a lépésben meghatározzuk a kimeneti könyvtárat, ahová a renderelt dokumentum mentésre kerül, és megadjuk a kimeneti HTML-fájl elérési útját.
## 2. lépés: Viewer objektum példányosítása
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Itt létrehozunk egy új példányt a `Viewer` osztály, paraméterként átadva a megtekintendő dokumentum (jelen esetben egy minta EML fájl) elérési útját.
## 3. lépés: HTML nézetbeállítások meghatározása
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Ebben a lépésben konfiguráljuk a dokumentum renderelésének HTML nézetbeállításait, megadva a renderelt HTML dokumentum kimeneti fájl elérési útját.
## 4. lépés: Dátum/idő formátum és időzóna eltolásának beállítása
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Itt testreszabhatjuk az e-mailek dátum- és időformátumát, és a kívánt időzónának megfelelően állítjuk be az időzóna-eltolást.
## 5. lépés: Dokumentum renderelése
```csharp
viewer.View(options);
```
Végül, hívjuk a `View` a módszer `Viewer` objektum, amely átadja a konfigurált HTML nézetbeállításokat a dokumentum HTML formátumba rendereléséhez.
## 6. lépés: Kimeneti könyvtár megjelenítése
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ez a lépés egyszerűen egy üzenetet jelenít meg, amely jelzi a dokumentum sikeres renderelését, és megadja a kimeneti könyvtár elérési útját, ahol a renderelt HTML dokumentum található.

## Következtetés
A GroupDocs.Viewer for .NET robusztus megoldást kínál a dokumentummegtekintési funkciók integrálására a .NET alkalmazásokba. Az ebben az oktatóanyagban ismertetett lépéseket követve könnyedén beállíthatja a GroupDocs.Viewert, importálhatja a szükséges névtereket, és funkcióinak segítségével testreszabható beállításokkal jelenítheti meg a dokumentumokat. Akár PDF-ekkel, Microsoft Office-dokumentumokkal vagy más formátumokkal dolgozik, a GroupDocs.Viewer leegyszerűsíti a dokumentumok megtekintésének folyamatát, javítva az alkalmazások felhasználói élményét.
## GYIK
### Kompatibilis a GroupDocs.Viewer a .NET Core-ral?
Igen, a GroupDocs.Viewer for .NET támogatja a .NET Core-t, lehetővé téve az alkalmazásai számára a platformfüggetlen kompatibilitást.
### Testreszabhatom a megjelenített dokumentumok megjelenését?
Abszolút! A GroupDocs.Viewer számos testreszabási lehetőséget kínál, beleértve a nagyítási szinteket, az oldal elforgatását és egyebeket, hogy a megtekintési élményt az oktatóanyagaid igényei szerint szabd testre.
### Van elérhető próbaverzió tesztelési célokra?
Igen, letöltheti a GroupDocs.Viewer for .NET ingyenes próbaverzióját a következő címről: [weboldal link](https://releases.groupdocs.com/viewer/net/) hogy vásárlás előtt felmérje a tulajdonságait.
### A GroupDocs.Viewer támogatja a jelszóval védett dokumentumok renderelését?
Igen, a GroupDocs.Viewer beépített támogatással rendelkezik a jelszóval védett dokumentumok rendereléséhez, biztosítva a dokumentumok biztonságos megtekintését az alkalmazásain belül.
### Hol találok további támogatást vagy segítséget a GroupDocs.Viewerhez?
Bármilyen technikai kérdéssel vagy segítséggel kapcsolatban látogassa meg a GroupDocs.Viewer weboldalt. [fórum](https://forum.groupdocs.com/c/viewer/9) vagy forduljon az ügyfélszolgálatukhoz gyors segítségért és útmutatásért.