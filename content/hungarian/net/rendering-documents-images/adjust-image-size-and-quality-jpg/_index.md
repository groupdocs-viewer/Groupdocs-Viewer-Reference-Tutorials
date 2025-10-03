---
"description": "Ismerje meg, hogyan optimalizálhatja a képméretet és -minőséget JPEG formátumban a Groupdocs.Viewer for .NET segítségével. Fokozza dokumentummegtekintési élményét."
"linktitle": "Képméret és -minőség beállítása (JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Képméret és -minőség beállítása (JPG)"
"url": "/hu/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
type: docs
---
# Képméret és -minőség beállítása (JPG)

## Bevezetés
A Groupdocs.Viewer for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen integrálják a dokumentummegjelenítő funkciókat .NET alkalmazásaikba. A dokumentummegjelenítő alkalmazások egyik gyakori követelménye a képek méretének és minőségének beállítási lehetősége, különösen JPEG (JPG) képek esetén. Ebben az oktatóanyagban végigvezetjük a képméret és -minőség beállításának folyamatán a Groupdocs.Viewer for .NET segítségével.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következőkkel rendelkezünk:
1. C# programozási nyelv alapismeretek.
2. Visual Studio telepítve a rendszeredre.
3. Groupdocs.Viewer for .NET könyvtár telepítve. Letöltheti innen: [itt](https://releases.groupdocs.com/viewer/net/).

## Névterek importálása
Először importálnod kell a szükséges névtereket a C# kódodba. Ezek a névterek hozzáférést biztosítanak a Groupdocs.Viewer használatához szükséges osztályokhoz és metódusokhoz.
## 1. lépés: Névterek importálása
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most pedig bontsuk a megadott példakódot több lépésre a jobb megértés érdekében.
## 2. lépés: A kimeneti könyvtár és az oldalfájl elérési útjának formátumának beállítása
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Ebben a lépésben megadjuk azt a kimeneti könyvtárat, ahová a renderelt képek mentésre kerülnek, és definiáljuk az egyes oldalképek fájlelérési útjának formátumát.
## 3. lépés: A megjelenítő inicializálása és a JPG nézet beállításainak konfigurálása
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Itt inicializáljuk a Viewer objektumot a megtekintendő dokumentum elérési útjával. Ezután létrehozunk egy JpgViewOptions példányt, és beállítjuk a JPEG képek kívánt szélességét és magasságát.
## 4. lépés: Forrásdokumentum renderelése
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Végül kinyomtatunk egy üzenetet, amely jelzi a forrásdokumentum sikeres renderelését és a kimeneti képek mentési helyét.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthatjuk be a JPEG képek méretét és minőségét a Groupdocs.Viewer for .NET segítségével. A fent vázolt lépéseket követve könnyedén beépíthetjük ezt a funkciót .NET alkalmazásainkba, optimalizált képmegjelenítési élményt nyújtva a felhasználóknak.
## GYIK
### A képminőséget is tudom állítani?
Igen, a képminőséget a JpgViewOptions Quality tulajdonságának beállításával állíthatja be.
### Milyen dokumentumformátumokat támogat a Groupdocs.Viewer for .NET?
A Groupdocs.Viewer for .NET számos dokumentumformátumot támogat, beleértve a DOCX, PDF, PPTX, XLSX és egyebeket.
### Kompatibilis a Groupdocs.Viewer for .NET a .NET Core-ral?
Igen, a Groupdocs.Viewer for .NET kompatibilis a .NET Core-ral és a hagyományos .NET keretrendszerrel is.
### Testreszabhatom a kimeneti fájl elnevezési formátumát?
Igen, testreszabhatja a kimeneti fájl elnevezési formátumát a pageFilePathFormat változó módosításával a kódban.
### Groupdocs.Viewer for .NET támogatja a dokumentumokhoz fűzött megjegyzéseket?
Igen, a Groupdocs.Viewer for .NET átfogó támogatást nyújt a dokumentumokhoz fűzött megjegyzésekhez, beleértve a szöveg kiemelését, aláhúzását és megjegyzésekkel való ellátását.