---
title: A kép méretének és minőségének beállítása (JPG)
linktitle: A kép méretének és minőségének beállítása (JPG)
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan optimalizálhatja a képméretet és -minőséget JPEG formátumban a Groupdocs.Viewer for .NET segítségével. Fokozza a dokumentummegtekintési élményt.
type: docs
weight: 11
url: /hu/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Bevezetés
A Groupdocs.Viewer for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen integrálják a dokumentummegtekintési funkciókat .NET-alkalmazásaikba. A dokumentummegjelenítő alkalmazások egyik általános követelménye a képek méretének és minőségének módosítása, különösen JPEG (JPG) képek kezelésekor. Ebben az oktatóanyagban végigvezetjük a képméret és -minőség beállításának folyamatán a Groupdocs.Viewer for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. C# programozási nyelv alapvető ismerete.
2. A Visual Studio telepítve van a rendszerére.
3.  A Groupdocs.Viewer for .NET könyvtár telepítve. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).

## Névterek importálása
Először is importálnia kell a szükséges névtereket a C# kódjába. Ezek a névterek hozzáférést biztosítanak a Groupdocs.Viewer használatához szükséges osztályokhoz és metódusokhoz.
## 1. lépés: Névterek importálása
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most bontsuk le a példakódot több lépésre a jobb megértés érdekében.
## 2. lépés: Állítsa be a kimeneti könyvtárat és az oldalfájl elérési út formátumát
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Ebben a lépésben megadjuk a kimeneti könyvtárat, ahová a renderelt képeket elmentjük, és meghatározzuk az egyes oldalképek fájlútvonalának formátumát.
## 3. lépés: Inicializálja a Viewer-t és konfigurálja a JPG nézet opciókat
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Itt inicializáljuk a Viewer objektumot a megtekinteni kívánt dokumentum elérési útjával. Ezután létrehozzuk a JpgViewOptions példányt, és beállítjuk a kívánt szélességet és magasságot a JPEG képekhez.
## 4. lépés: Renderelje le a forrásdokumentumot
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Végül kinyomtatunk egy üzenetet, amely jelzi a forrásdokumentum sikeres megjelenítését és a kimeneti képek mentésének helyét.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthatjuk be a JPEG-képek méretét és minőségét a Groupdocs.Viewer for .NET segítségével. A fent vázolt lépések követésével könnyedén beépítheti ezt a funkciót .NET-alkalmazásaiba, így a felhasználók számára optimalizált képmegtekintési élményt nyújt.
## GYIK
### Beállíthatom a képminőséget is?
Igen, módosíthatja a képminőséget a Minőség tulajdonság beállításával a JpgViewOptionsben.
### Milyen dokumentumformátumokat támogat a Groupdocs.Viewer for .NET?
A Groupdocs.Viewer for .NET a dokumentumformátumok széles skáláját támogatja, beleértve a DOCX, PDF, PPTX, XLSX és egyebeket.
### A Groupdocs.Viewer for .NET kompatibilis a .NET Core programmal?
Igen, a Groupdocs.Viewer for .NET kompatibilis a .NET Core-val, valamint a hagyományos .NET-keretrendszerrel.
### Testreszabhatom a kimeneti fájl elnevezési formátumát?
Igen, testreszabhatja a kimeneti fájl elnevezési formátumát a pageFilePathFormat változó módosításával a kódban.
### A Groupdocs.Viewer for .NET támogatja a dokumentumok megjegyzéseit?
Igen, a Groupdocs.Viewer for .NET átfogó támogatást nyújt a dokumentumok megjegyzéseihez, beleértve a szövegkiemelést, aláhúzást és megjegyzéseket.