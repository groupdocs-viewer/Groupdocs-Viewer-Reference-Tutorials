---
"description": "Ismerje meg, hogyan módosíthatja az oldalméretet e-mailek PDF formátumba renderelésekor a GroupDocs.Viewer for .NET használatával. Növelje a dokumentumok megtekintésének hatékonyságát."
"linktitle": "Oldalméret beállítása e-mail üzenetek megjelenítésekor"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Oldalméret beállítása e-mail üzenetek megjelenítésekor"
"url": "/hu/net/rendering-email-messages/adjust-page-size-email/"
"weight": 10
---

# Oldalméret beállítása e-mail üzenetek megjelenítésekor

## Bevezetés
A .NET fejlesztés területén a GroupDocs.Viewer átfogó megoldást kínál különféle dokumentumformátumok, beleértve az e-mail üzeneteket is, megjelenítésére. Ez az oktatóanyag az oldalméret beállítására összpontosít, amikor az e-mail üzeneteket PDF formátumba rendereljük a GroupDocs.Viewer for .NET használatával. Az útmutatóban ismertetett lépéseket követve megtanulhatja, hogyan manipulálhatja zökkenőmentesen az oldalméretet az Ön egyedi igényeinek megfelelően.
## Előfeltételek
Mielőtt belemerülnél ebbe az oktatóanyagba, győződj meg róla, hogy a következő előfeltételekkel rendelkezel:
### 1. GroupDocs.Viewer .NET-hez telepítve
Győződjön meg arról, hogy a GroupDocs.Viewer for .NET telepítve van a fejlesztői környezetében. Letöltheti innen: [itt](https://releases.groupdocs.com/viewer/net/).
### 2. A .NET fejlesztés alapjai
Ismerkedjen meg a .NET fejlesztés alapjaival, beleértve a C# programozást és a fájlkezelést.
### 3. IDE (Integrált Fejlesztői Környezet)
Telepített IDE-vel, például Visual Studio-val kell rendelkeznie .NET kód írásához és végrehajtásához.

## Névterek importálása
A C# projektedben importáld a szükséges névtereket a GroupDocs.Viewer funkcióinak használatához.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Kimeneti könyvtár beállítása
Adja meg azt a könyvtárat, ahová a kimeneti PDF fájl mentésre kerül.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Fájlútvonal meghatározása
Kombinálja a kimeneti könyvtárat a kimeneti fájl nevével.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 3. lépés: Viewer objektum inicializálása
Hozz létre egy példányt a Viewer osztályból, és add meg az e-mail üzenetfájl elérési útját.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## 4. lépés: PDF nézetbeállítások konfigurálása
Hozza létre a PdfViewOptions példányát, és állítsa be a kimeneti fájl elérési útját.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## 5. lépés: Oldalméret beállítása
Módosítsa az oldalméret tulajdonságot a PdfViewOptions EmailOptions paraméterében.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## 6. lépés: Dokumentum renderelése
Hívd meg a viewer objektum View metódusát, átadva a konfigurált PdfViewOptions értékeket.
```csharp
viewer.View(options);
```
## 7. lépés: Sikeres üzenet megjelenítése
Tájékoztassa a felhasználót a sikeres rendereléssel kapcsolatban és a kimeneti könyvtárról.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Összefoglalva, ez az oktatóanyag bemutatta, hogyan módosítható az oldalméret e-mailek PDF formátumba renderelésekor a GroupDocs.Viewer for .NET segítségével. A lépésről lépésre haladó utasításokat követve hatékonyan módosíthatja az oldalméreteket az Ön egyedi igényeinek megfelelően, javítva a dokumentumok megtekintését és kezelését a .NET alkalmazásokban.
## GYIK
### Kompatibilis a GroupDocs.Viewer a különböző e-mail formátumokkal?
A GroupDocs.Viewer különféle e-mail formátumok megjelenítését támogatja, beleértve az MSG-t és az EML-t.
### Testreszabhatom az oldalméretet a ptutorials-om szerint?
Igen, a GroupDocs.Viewer PdfViewOptions funkciójával módosíthatja az oldalméretet, ami rugalmasságot biztosít a dokumentumok renderelésében.
### A GroupDocs.Viewer támogat más dokumentumformátumokat is?
Igen, a GroupDocs.Viewer számos dokumentumformátumot támogat, beleértve a PDF-et, a Microsoft Office-t, a képeket és egyebeket.
### Alkalmas a GroupDocs.Viewer vállalati szintű alkalmazásokhoz?
A GroupDocs.Viewer robusztus funkciókat kínál mind kisméretű, mind vállalati szintű alkalmazásokhoz, biztosítva a hatékony dokumentummegjelenítést és -kezelést.
### Hol kérhetek segítséget vagy további támogatást a GroupDocs.Viewerhez?
Meglátogathatod a GroupDocs.Viewer fórumot [itt](https://forum.groupdocs.com/c/viewer/9) segítséget kérni, kérdéseket feltenni és kapcsolatba lépni a közösséggel.