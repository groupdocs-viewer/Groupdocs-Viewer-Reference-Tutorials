---
title: Vízjel hozzáadása a dokumentumhoz
linktitle: Vízjel hozzáadása a dokumentumhoz
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan adhat zökkenőmentesen vízjeleket a dokumentumokhoz a GroupDocs.Viewer for .NET segítségével. Fokozza a dokumentumok biztonságát és a márkaépítést ezzel a könnyen követhető oktatóanyaggal.
type: docs
weight: 10
url: /hu/net/rendering-options/add-watermark/
---
## Bevezetés
A mai digitális korban a különféle dokumentumformátumok zökkenőmentes kezelése és megtekintése sok vállalkozás és magánszemély számára egyaránt elengedhetetlen. Szerencsére az olyan eszközökkel, mint a GroupDocs.Viewer for .NET, a dokumentumok kezelése gyerekjáték lesz. Ez a nagy teljesítményű .NET-könyvtár lehetővé teszi a fejlesztők számára, hogy a dokumentummegtekintési funkciókat könnyedén integrálják alkalmazásaikba, így a felhasználók anélkül tekinthetik meg a dokumentumokat, hogy szükségük lenne az azokat létrehozó eredeti szoftverre.
## Előfeltételek
Mielőtt belevágna a GroupDocs.Viewer for .NET használatába vízjelek hozzáadásához a dokumentumokhoz, győződjön meg arról, hogy rendelkezik a következőkkel:
1. Környezet beállítása: .NET-keretrendszerrel vagy .NET Core-val telepített fejlesztői környezetet kell beállítani.
2.  GroupDocs.Viewer for .NET: Töltse le és telepítse a GroupDocs.Viewer for .NET könyvtárat a[letöltési oldal](https://releases.groupdocs.com/viewer/net/).
3. Dokumentumfájlok: Készítse elő azokat a dokumentumfájlokat, amelyekkel dolgozni szeretne, mint például a DOCX, PDF vagy egyéb.
4. Alapvető C# ismerete: A kódpéldák megvalósításához a C# programozási nyelv ismerete szükséges.

## Névterek importálása
Mielőtt elkezdené vízjelek hozzáadását a dokumentumokhoz a GroupDocs.Viewer for .NET segítségével, feltétlenül importálja a szükséges névtereket a C#-kódba. Ez a lépés lehetővé teszi a könyvtár által biztosított osztályok és metódusok zökkenőmentes elérését.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most pedig nézzük meg a vízjel dokumentumhoz való hozzáadásának folyamatát a GroupDocs.Viewer for .NET segítségével. Kövesse ezeket a lépéseket, hogy zökkenőmentesen integrálja a vízjel funkciót az alkalmazásba.
## 1. lépés: Állítsa be a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
Adja meg azt a könyvtárat, ahová a kimeneti fájlokat menteni szeretné a vízjel alkalmazása után.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Állítsa be a megjelenített oldalak fájlútvonalának formátumát. Ebben a példában oldalszámokat tartalmazó HTML-fájlok jönnek létre.
## 3. lépés: Példányosítsa a Viewer objektumot
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // A kód a következő lépésben folytatódik...
}
```
Hozzon létre egy példányt a Viewer osztályból, paraméterként átadva a dokumentumfájl elérési útját. Ebben a példában egy minta DOCX fájlt használunk.
## 4. lépés: Konfigurálja a HTML nézet beállításait
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Konfigurálja a HTML nézet beállításait, beleértve a dokumentumhoz hozzáadni kívánt vízjelszöveget.
## 5. lépés: Tekintse meg a dokumentumot vízjellel
```csharp
viewer.View(options);
```
Hívja meg a Viewer objektum View metódusát, átadva a beállított opciókat. Ez a dokumentum a megadott vízjellel jeleníti meg.
## 6. lépés: Jelenítse meg a kimeneti könyvtár elérési útját
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tájékoztassa a felhasználót a dokumentum sikeres megjelenítéséről, és adja meg a könyvtárat, ahová a kimeneti fájlok mentésre kerülnek.

## Következtetés
A GroupDocs.Viewer for .NET kényelmes módot biztosít vízjelek programozott hozzáadására a dokumentumokhoz. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen integrálhatja a vízjel funkciót .NET-alkalmazásaiba, javítva a dokumentumok biztonságát és a márkaépítést.
## GYIK
### Testreszabhatom a vízjel megjelenését?
Igen, testreszabhatja a vízjel különféle tulajdonságait, például szöveget, betűtípust, színt, méretet és pozíciót.
### A GroupDocs.Viewer támogatja a távoli forrásokból származó dokumentumok megtekintését?
Igen, a GroupDocs.Viewer támogatja a dokumentumok megtekintését a helyi tárhelyről, valamint a távoli URL-ekről.
### Elérhető a GroupDocs.Viewer for .NET próbaverziója?
Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.groupdocs.com/).
### Hozzáadhatok vízjelet egy dokumentum több oldalához?
Természetesen a GroupDocs.Viewer lehetővé teszi vízjelek hozzáadását a dokumentum egyes oldalaihoz vagy összes oldalához.
### Hogyan kaphatok támogatást vagy segítséget, ha bármilyen problémába ütközöm?
 Kérhet segítséget és támogatást a GroupDocs közösségi fórumain[itt](https://forum.groupdocs.com/c/viewer/9).