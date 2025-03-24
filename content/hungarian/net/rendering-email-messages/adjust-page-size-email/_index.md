---
title: Állítsa be az oldalméretet e-mail üzenetek megjelenítésekor
linktitle: Állítsa be az oldalméretet e-mail üzenetek megjelenítésekor
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan állíthatja be az oldalméretet, amikor az e-mail üzeneteket PDF-formátumba rendereli a GroupDocs.Viewer for .NET segítségével. Növelje a dokumentumok megtekintésének hatékonyságát.
weight: 10
url: /hu/net/rendering-email-messages/adjust-page-size-email/
---
## Bevezetés
A .NET fejlesztés területén a GroupDocs.Viewer átfogó megoldást kínál különféle dokumentumformátumok, köztük e-mail üzenetek megjelenítésére. Ez az oktatóanyag az oldalméret beállítására összpontosít, amikor az e-mail üzeneteket PDF formátumba rendereli a GroupDocs.Viewer for .NET segítségével. Az ebben az útmutatóban vázolt lépések követésével megtanulhatja, hogyan lehet zökkenőmentesen módosítani az oldalméretet, hogy megfeleljen az Ön sajátos követelményeinek.
## Előfeltételek
Mielőtt belevágna ebbe az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. A GroupDocs.Viewer for .NET telepítve
 Győződjön meg arról, hogy a GroupDocs.Viewer for .NET telepítve van a fejlesztői környezetében. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
### 2. A .NET fejlesztés alapjai
Ismerkedjen meg a .NET fejlesztési alapjaival, beleértve a C# programozást és fájlkezelést.
### 3. IDE (integrált fejlesztői környezet)
Telepítsen egy IDE-t, például a Visual Studio-t a .NET-kód írásához és végrehajtásához.

## Névterek importálása
A C# projektben importálja a szükséges névtereket a GroupDocs.Viewer funkcióinak használatához.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Állítsa be a kimeneti könyvtárat
Határozza meg azt a könyvtárat, ahová a kimeneti PDF fájl mentésre kerül.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Adja meg a fájl elérési útját
Kombinálja a kimeneti könyvtárat a kimeneti fájl nevével.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 3. lépés: Inicializálja a Viewer Object-et
Hozzon létre egy példányt a Viewer osztályból, és adja meg az e-mail üzenet fájl elérési útját.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## 4. lépés: Konfigurálja a PDF nézet beállításait
Példányosítsa a PdfViewOptions-t, és állítsa be a kimeneti fájl elérési útját.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## 5. lépés: Állítsa be az oldalméretet
Módosítsa az oldalméret tulajdonságot a PdfViewOptions EmailOptions részében.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## 6. lépés: Renderelje le a dokumentumot
Hívja meg a Viewer objektum View metódusát a konfigurált PdfViewOptions átadásával.
```csharp
viewer.View(options);
```
## 7. lépés: Jelenítse meg a sikeres üzenetet
Tájékoztassa a felhasználót a sikeres leképezésről és a kimeneti könyvtárról.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Összefoglalva, ez az oktatóanyag bemutatja, hogyan állíthatja be az oldalméretet, amikor az e-mail üzeneteket PDF formátumba rendereli a GroupDocs.Viewer for .NET segítségével. Az alábbi lépésenkénti utasítások követésével hatékonyan módosíthatja az oldalméreteket, hogy megfeleljen az Ön sajátos követelményeinek, javítva a dokumentummegtekintési és -kezelési képességeket .NET-alkalmazásaiban.
## GYIK
### GroupDocs.Viewer kompatibilis a különböző e-mail-formátumokkal?
A GroupDocs.Viewer támogatja a különféle e-mail-formátumok megjelenítését, beleértve az MSG-t és az EML-t.
### Testreszabhatom az oldal méretét a preferenciáim szerint?
Igen, beállíthatja az oldal méretét a GroupDocs.Viewer PdfViewOptions segítségével, amely rugalmasságot biztosít a dokumentum-megjelenítésben.
### A GroupDocs.Viewer támogat más dokumentumformátumokat?
Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF-et, a Microsoft Office-t, a képeket és egyebeket.
### A GroupDocs.Viewer alkalmas vállalati szintű alkalmazásokhoz?
Természetesen a GroupDocs.Viewer robusztus funkcionalitásokat kínál kisméretű és vállalati szintű alkalmazásokhoz egyaránt, biztosítva a hatékony dokumentum-megjelenítést és -kezelést.
### Hol kérhetek segítséget vagy további támogatást a GroupDocs.Viewerhez?
 Látogassa meg a GroupDocs.Viewer fórumot[itt](https://forum.groupdocs.com/c/viewer/9) segítséget kérni, kérdéseket feltenni, és kapcsolatba lépni a közösséggel.