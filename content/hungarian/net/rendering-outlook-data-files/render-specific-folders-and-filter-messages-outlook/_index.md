---
title: Adott mappák és szűrőüzenetek renderelése (Outlook)
linktitle: Adott mappák és szűrőüzenetek renderelése (Outlook)
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan jeleníthet meg bizonyos mappákat és szűrhet üzeneteket az Outlook programban a GroupDocs.Viewer for .NET segítségével. Egyszerűsítse a dokumentumkezelést .NET-alkalmazásokban.
type: docs
weight: 11
url: /hu/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---
## Bevezetés
A .NET fejlesztés világában a dokumentumok hatékony kezelése és megjelenítése kulcsfontosságú. A GroupDocs.Viewer for .NET leegyszerűsíti ezt a feladatot, mivel hatékony funkciókat biztosít a különböző dokumentumformátumok zökkenőmentes megjelenítéséhez. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet adott mappákat megjeleníteni és üzeneteket szűrni az Outlookban a GroupDocs.Viewer for .NET segítségével.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  GroupDocs.Viewer for .NET: Győződjön meg arról, hogy telepítette a GroupDocs.Viewer for .NET programot. Letöltheti a[weboldal](https://releases.groupdocs.com/viewer/net/).
2. .NET-keretrendszer: telepítenie kell a .NET-keretrendszert a gépére.
3. A C# alapvető ismerete: A C# programozási nyelv ismerete hasznos lesz az oktatóanyag mellett.

## Névterek importálása
Először is importáljuk a szükséges névtereket a C# kódunkba:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
 Cserélje ki`"Your Document Directory"` azzal a könyvtárúttal, ahová a renderelt dokumentumokat menteni szeretné.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Ez a sor határozza meg az egyes megjelenített oldalak fájlútvonalainak formátumát. Ebben a példában a következő nevű HTML-fájlokat fogja generálni`page_1.html`, `page_2.html`, stb.
## 3. lépés: Inicializálja a Viewer Object-et
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
 Itt inicializáljuk a`Viewer` objektum a minta Outlook mappa elérési útjával.
## 4. lépés: Adja meg a HTML nézet beállításait
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
 Létrehozunk egy példányt`HtmlViewOptions` és adja meg a beágyazott erőforrások formátumát. Ezenkívül beállítottuk az Outlook mappát, hogy a következőként jelenjen meg`"Входящие"` (Beérkező).
## 5. lépés: Rendelje le a dokumentumot
```csharp
viewer.View(options);
```
Ez a sor elindítja a megjelenítési folyamatot a megadott beállításokkal.
## 6. lépés: Jelenítse meg a sikeres üzenetet
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
A renderelés után ez az üzenet jelenik meg, jelezve a renderelési folyamat sikeres befejezését, és a felhasználót a kimeneti könyvtárba irányítja.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan lehet adott mappákat megjeleníteni és üzeneteket szűrni az Outlookban a GroupDocs.Viewer for .NET segítségével. A fent vázolt lépések követésével hatékonyan kezelheti és jelenítheti meg a dokumentumokat .NET-alkalmazásaiban.
## GYIK
### Renderelhetek-e az Outlook-üzenetektől eltérő dokumentumokat a GroupDocs.Viewer for .NET segítségével?
Igen, a GroupDocs.Viewer for .NET a dokumentumformátumok széles skáláját támogatja, beleértve a PDF, DOCX, XLSX és egyebeket.
### A GroupDocs.Viewer for .NET kompatibilis a .NET Core-al?
Igen, a GroupDocs.Viewer for .NET kompatibilis a .NET-keretrendszerrel és a .NET Core-al is.
### Testreszabhatom a renderelés kimeneti formátumát?
Természetesen a GroupDocs.Viewer for .NET különféle lehetőségeket kínál a megjelenítési kimenet testreszabásához, beleértve a HTML-, kép- és PDF-formátumokat.
### Elérhető a GroupDocs.Viewer for .NET próbaverziója?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[weboldal](https://releases.groupdocs.com/).
### Hol kérhetek segítséget vagy támogatást a GroupDocs.Viewer for .NET-hez?
 Meglátogathatja a[GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) bármilyen segítségért vagy kérdésért.