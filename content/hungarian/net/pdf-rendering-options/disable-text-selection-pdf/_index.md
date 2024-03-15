---
title: Szövegkijelölés letiltása PDF-ben
linktitle: Szövegkijelölés letiltása PDF-ben
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan tilthatja le a szövegkijelölést PDF-ben a GroupDocs.Viewer for .NET segítségével. Kövesse lépésenkénti útmutatónkat a zökkenőmentes integráció érdekében.
type: docs
weight: 13
url: /hu/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony dokumentum-megjelenítő API, amely lehetővé teszi a fejlesztők számára, hogy könnyedén integrálják a dokumentummegtekintési képességeket .NET-alkalmazásaikba. A GroupDocs.Viewer egyik kulcsfontosságú funkciója a szövegkiválasztás letiltása a PDF dokumentumokban. Ez a funkció különösen hasznos olyan esetekben, amikor meg kell akadályozni, hogy a felhasználók szöveget másoljanak érzékeny dokumentumokból, ezzel biztosítva a dokumentumok biztonságát és integritását.
## Előfeltételek
Mielőtt belemerülnénk a PDF-ben található szövegkijelölések GroupDocs.Viewer for .NET használatával letiltására vonatkozó, lépésről lépésre szóló útmutatóba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1.  A GroupDocs.Viewer for .NET telepítése: Győződjön meg arról, hogy letöltötte és telepítette a GroupDocs.Viewer for .NET programot a[letöltési link](https://releases.groupdocs.com/viewer/net/).
2. Dokumentumkönyvtár: Készítsen egy könyvtárat, ahol a dokumentumokat tárolni fogja. A PDF-dokumentum megjelenítéséhez meg kell adnia ezt a könyvtárat a kódrészletben.

## Névterek importálása
Először is importálnia kell a szükséges névtereket, hogy hozzáférjen a GroupDocs.Viewer for .NET szolgáltatásaihoz. A következőképpen teheti meg:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most bontsuk le több lépésre a PDF-dokumentum szövegkijelölésének letiltásának folyamatát a GroupDocs.Viewer for .NET használatával:
## 1. lépés: Adja meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
 Ebben a lépésben cserélje ki`"Your Document Directory"` a könyvtár elérési útjával, ahol a PDF-dokumentum található.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ez a lépés határozza meg a megjelenített HTML-oldalak fájlútvonalainak formátumát. A PDF-dokumentum minden oldala HTML-fájllá alakul, szekvenciális oldalszámmal.
## 3. lépés: PDF-dokumentum megjelenítése letiltott szövegkijelölés mellett
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Cserélje ki`"Path to Your PDF Document"` a PDF-fájl tényleges elérési útjával. Ez a kódrészlet inicializálja a`Viewer` objektumot, konfigurálja a HTML nézet beállításait az erőforrások beágyazásához, és letiltja a szövegkijelölést beállítással`RenderTextAsImage` tulajdonát`true`.
## 4. lépés: Jelenítse meg a sikeres üzenetet
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
A PDF-dokumentum megjelenítése után ez a lépés egy sikerüzenetet jelenít meg, valamint a megjelenített HTML-oldalak tárolási könyvtárát.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet letiltani a szövegkijelölést PDF-dokumentumokban a GroupDocs.Viewer for .NET használatával. A lépésenkénti útmutató követésével zökkenőmentesen integrálhatja ezt a funkciót .NET-alkalmazásaiba, így biztosítva a dokumentumok biztonságát és javítva a felhasználói élményt.
## GYIK
### Testreszabhatom a kimeneti könyvtárat a renderelt HTML-oldalak számára?
Igen, megadhat bármilyen könyvtár elérési utat, ahol a renderelt HTML-oldalakat tárolni szeretné.
### A GroupDocs.Viewer for .NET kompatibilis a .NET keretrendszer különböző verzióival?
Igen, a GroupDocs.Viewer for .NET kompatibilis a .NET-keretrendszer különféle verzióival, beleértve a .NET Core-t és a .NET-keretrendszert.
### A szövegkijelölés letiltása hatással van a PDF-dokumentum egyéb funkcióira?
Nem, a szövegkijelölés letiltása csak azt akadályozza meg, hogy a felhasználók szöveget válasszanak ki és másoljanak a dokumentumból. A többi funkció érintetlen marad.
### Újra engedélyezhetem a szövegkijelölést a dokumentum megjelenítése után?
 Igen, engedélyezheti a szövegkiválasztást a`RenderTextAsImage` tulajdonát`false` a HTML nézetben.
### Elérhető a GroupDocs.Viewer for .NET próbaverziója?
 Igen, elérheti a GroupDocs.Viewer for .NET ingyenes próbaverzióját a webhelyről[weboldal](https://releases.groupdocs.com/).