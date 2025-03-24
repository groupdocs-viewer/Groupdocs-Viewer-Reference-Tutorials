---
title: Dokumentumok betöltése a Streamből
linktitle: Dokumentumok betöltése a Streamből
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan tölthet be zökkenőmentesen dokumentumokat adatfolyamokból a GroupDocs.Viewer for .NET segítségével. Bővítse .NET-alkalmazásait hatékony dokumentummegtekintési lehetőségekkel.
weight: 12
url: /hu/net/loading-documents/loading-document-stream/
---

# Dokumentumok betöltése a Streamből

## Bevezetés
.NET fejlesztés területén a dokumentumok hatékony kezelése és megtekintése a legfontosabb. A fejlett eszközök és könyvtárak megjelenésével az egykor ijesztőnek tűnő feladatok leegyszerűsödtek. Ezen eszközök közül a GroupDocs.Viewer for .NET kiemelkedik sokoldalú megoldásként a különféle dokumentumformátumok zökkenőmentes kezelésére. Ebben az átfogó útmutatóban a GroupDocs.Viewer for .NET használatának trükkjeit mutatjuk be dokumentumok adatfolyamból történő betöltéséhez. Akár tapasztalt fejlesztő, akár most kezdő, ez az oktatóanyag felvértezi a GroupDocs.Viewer erejének hatékony kihasználásához szükséges ismereteket.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. A C# és a .NET-keretrendszer alapvető ismerete: A C# programozási nyelv és a .NET-keretrendszer ismerete segít a tárgyalt fogalmak megértésében.
   
2.  A GroupDocs.Viewer for .NET telepítése: Töltse le és telepítse a GroupDocs.Viewer for .NET programot a[weboldal](https://releases.groupdocs.com/viewer/net/).
3. IDE: A kódoláshoz és teszteléshez telepítsen egy integrált fejlesztői környezetet (IDE), például a Visual Studio-t.
4. Dokumentumfolyam: Készítsen elő egy dokumentumfolyamot a betöltéshez. Ez lehet egy fájladatfolyam vagy bármilyen más kompatibilis adatfolyam-forrás.

## Névterek importálása
Mielőtt implementálja a kódot a dokumentumok adatfolyamból való betöltéséhez, importálja a szükséges névtereket:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
Állítsa be a könyvtár elérési útját, ahová a renderelt dokumentum mentésre kerül.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Határozza meg az egyes oldalak fájlútvonalának formátumát. Itt a „{0}” helyére az oldalszám lép.
## 3. lépés: Töltse le a dokumentumfolyamot
```csharp
Stream stream = GetFileStream();
```
Szerezze be a dokumentumfolyamot a kívánt forrásból. Ez lehet fájladatfolyam, memóriafolyam vagy bármilyen más kompatibilis adatfolyam.
## 4. lépés: Töltse be a dokumentumot a Viewer segítségével
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Inicializálja a Viewer osztály új példányát a dokumentumfolyammal. Ezután adja meg a HTML nézet beállításait, és jelenítse meg a dokumentumot.
## 5. lépés: Jelenítse meg a kimeneti könyvtárat
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tájékoztassa a felhasználót a dokumentum sikeres megjelenítéséről, és adja meg a kimenet mentésének helyét.

## Következtetés
Összefoglalva, a GroupDocs.Viewer for .NET robusztus megoldást kínál a dokumentumok egyszerű betöltésére és megtekintésére adatfolyamokból. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen integrálhatja a dokumentummegtekintési képességeket .NET-alkalmazásaiba, javítva a felhasználói élményt és a termelékenységet.
## GYIK
### A GroupDocs.Viewer for .NET kezelheti a különböző dokumentumformátumokat?
Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF, DOCX, XLSX, PPTX és egyebeket.
### A GroupDocs.Viewer for .NET alkalmas webes és asztali alkalmazásokhoz is?
Teljesen! A GroupDocs.Viewer zökkenőmentesen integrálható a .NET segítségével fejlesztett webes és asztali alkalmazásokba.
### A GroupDocs.Viewer testreszabási lehetőségeket kínál a dokumentum-megjelenítéshez?
Igen, igényei szerint testreszabhatja a dokumentum-megjelenítés különböző szempontjait, például a vízjelezést, az oldalelforgatást és a nagyítási szintet.
### Használhatom a GroupDocs.Viewer for .NET programot kereskedelmi projektekben?
Igen, a GroupDocs.Viewer a kereskedelmi projektekhez megfelelő licencelési lehetőségeket kínál. Licenceket vásárolhat a hivatalostól[weboldal](https://purchase.groupdocs.com/temporary-license/).
### Elérhető technikai támogatás a GroupDocs.Viewer for .NET számára?
 Igen, kérhet technikai segítséget és útmutatást a által biztosított támogatási fórumon[GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).