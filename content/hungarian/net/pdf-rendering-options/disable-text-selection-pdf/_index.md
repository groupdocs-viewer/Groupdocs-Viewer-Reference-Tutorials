---
"description": "Ismerje meg, hogyan tilthatja le a szövegkijelölést PDF-ben a GroupDocs.Viewer for .NET használatával. Kövesse lépésről lépésre szóló útmutatónkat a zökkenőmentes integráció érdekében."
"linktitle": "Szövegkijelölés letiltása PDF-ben"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Szövegkijelölés letiltása PDF-ben"
"url": "/hu/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# Szövegkijelölés letiltása PDF-ben

## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony dokumentummegjelenítő API, amely lehetővé teszi a fejlesztők számára, hogy könnyedén integrálják a dokumentummegjelenítési funkciókat .NET alkalmazásaikba. A GroupDocs.Viewer egyik legfontosabb funkciója a szövegkijelölés letiltása a PDF dokumentumokban. Ez a funkció különösen hasznos olyan esetekben, amikor meg kell akadályozni, hogy a felhasználók szöveget másoljanak érzékeny dokumentumokból, biztosítva a dokumentum biztonságát és integritását.

![Szövegkijelölés letiltása PDF-ben a GroupDocs.Viewer .NET segítségével](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Előfeltételek
Mielőtt belemerülnénk a PDF-fájlok szövegkijelölésének a GroupDocs.Viewer for .NET használatával történő letiltásának lépésről lépésre történő útmutatójába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. GroupDocs.Viewer for .NET telepítése: Győződjön meg arról, hogy letöltötte és telepítette a GroupDocs.Viewer for .NET programot a következő helyről: [letöltési link](https://releases.groupdocs.com/viewer/net/).
2. Dokumentumkönyvtár: Készítsen elő egy könyvtárat, ahová a dokumentumokat tárolni fogja. Ezt a könyvtárat meg kell adnia a kódrészletben a PDF dokumentum megjelenítéséhez.

## Névterek importálása
Először importálnia kell a szükséges névtereket a GroupDocs.Viewer for .NET által biztosított funkciók eléréséhez. Így teheti meg:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most bontsuk le több lépésre a szövegkijelölés letiltásának folyamatát egy PDF dokumentumban a GroupDocs.Viewer for .NET használatával:
## 1. lépés: Kimeneti könyvtár megadása
```csharp
string outputDirectory = "Your Document Directory";
```
Ebben a lépésben cserélje ki `"Your Document Directory"` a PDF dokumentum könyvtárának elérési útjával.
## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ez a lépés határozza meg a renderelt HTML-oldalak fájlelérési útvonalainak formátumát. A PDF-dokumentum minden oldala egy folytonos oldalszámmal rendelkező HTML-fájllá lesz konvertálva.
## 3. lépés: PDF dokumentum renderelése letiltott szövegkijelöléssel
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Csere `"Path to Your PDF Document"` a PDF-fájl tényleges elérési útjával. Ez a kódrészlet inicializál egy `Viewer` objektum, konfigurálja a HTML nézet beállításait az erőforrások beágyazásához, és letiltja a szövegkijelölést a beállítással `RenderTextAsImage` ingatlan `true`.
## 4. lépés: Sikeres üzenet megjelenítése
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
A PDF dokumentum renderelése után ez a lépés egy sikeres üzenetet jelenít meg, valamint azt a könyvtárat, ahol a renderelt HTML oldalak tárolva vannak.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan tiltható le a szövegkijelölés PDF dokumentumokban a GroupDocs.Viewer for .NET segítségével. A lépésről lépésre haladó útmutató követésével zökkenőmentesen integrálhatja ezt a funkciót .NET alkalmazásaiba, biztosítva a dokumentumok biztonságát és javítva a felhasználói élményt.
## GYIK
### Testreszabhatom a renderelt HTML oldalak kimeneti könyvtárát?
Igen, megadhatsz bármilyen könyvtár elérési utat, ahová a megjelenített HTML oldalakat tárolni szeretnéd.
### Kompatibilis a GroupDocs.Viewer for .NET a .NET keretrendszer különböző verzióival?
Igen, a GroupDocs.Viewer for .NET kompatibilis a .NET keretrendszer különböző verzióival, beleértve a .NET Core-t és a .NET Frameworköt.
### A szövegkijelölés letiltása befolyásolja a PDF dokumentum más funkcióit?
Nem, a szövegkijelölés letiltása csak azt akadályozza meg, hogy a felhasználók szöveget jelöljenek ki és másoljanak a dokumentumból. A többi funkció változatlan marad.
### Újra engedélyezhetem a szövegkijelölést a dokumentum renderelése után?
Igen, engedélyezheti a szövegkijelölést egyszerűen a beállítással. `RenderTextAsImage` ingatlan `false` a HTML nézet beállításainál.
### Van elérhető próbaverzió a GroupDocs.Viewer for .NET-hez?
Igen, hozzáférhet a GroupDocs.Viewer for .NET ingyenes próbaverziójához a következő címen: [weboldal](https://releases.groupdocs.com/).