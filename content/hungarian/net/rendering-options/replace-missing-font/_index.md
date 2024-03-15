---
title: Cserélje ki a hiányzó betűtípust
linktitle: Cserélje ki a hiányzó betűtípust
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan pótolhatja könnyedén a hiányzó betűtípusokat a .NET-dokumentumokban a GroupDocs.Viewer segítségével. Biztosítsa a pontos megjelenítést egyszerű lépésekkel.
type: docs
weight: 20
url: /hu/net/rendering-options/replace-missing-font/
---
## Bevezetés
A .NET fejlesztés világában a hatékony dokumentumkezelés kulcsfontosságú. A GroupDocs.Viewer for .NET hatékony megoldást kínál a különféle dokumentumformátumok megtekintésére a .NET-alkalmazásokon belül. Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatjuk a GroupDocs.Viewer for .NET alkalmazást a hiányzó betűtípusok pótlására a dokumentumokban. Függetlenül attól, hogy PDF-ekkel, PowerPoint-prezentációkkal vagy Word-dokumentumokkal foglalkozik, a GroupDocs.Viewer leegyszerűsíti a folyamatot, és biztosítja, hogy a dokumentumok pontosan jelenjenek meg, még akkor is, ha hiányoznak a betűtípusok.
## Előfeltételek
Mielőtt belevágna ebbe az oktatóanyagba, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. GroupDocs.Viewer for .NET: Töltse le és telepítse a GroupDocs.Viewer könyvtárat a webhelyről](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztői környezet: .NET fejlesztői környezet beállítása, például a Visual Studio.
3. Alapszintű C# ismeretek: C# programozási nyelv és .NET keretrendszer ismerete.

## Névterek importálása
A C# kódban importálja a szükséges névtereket a GroupDocs.Viewer funkcióinak eléréséhez.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most pedig nézzük meg a hiányzó betűtípusok pótlásának folyamatát a dokumentumokban a GroupDocs.Viewer for .NET használatával.
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
Állítsa be azt a könyvtárat, ahová a renderelt dokumentumoldalak mentésre kerülnek.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Adja meg a kimeneti HTML-fájlok elnevezésének formátumát. Ebben a példában minden oldal HTML-fájlként lesz elmentve a következő elnevezési konvencióval: "page_{page_number}.html".
## 3. lépés: Inicializálja a Viewer Object-et
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inicializálja a Viewer osztály új példányát, paraméterként átadva a dokumentumfájl elérési útját (jelen esetben egy PowerPoint bemutatót hiányzó betűtípusokkal).
## 4. lépés: Állítsa be a HTML nézet beállításait
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Hozzon létre egy HtmlViewOptions példányt, és konfigurálja úgy, hogy erőforrásokat ágyazzon be a HTML-kimenetbe. Adjon meg egy alapértelmezett betűtípusnevet a hiányzó betűtípusok helyettesítésére.
## 5. lépés: Renderelje le a dokumentumot
```csharp
viewer.View(options);
```
Hívja meg a Viewer objektum View metódusát, átadva a HTML nézet opciókat. Ez a dokumentum oldalait a megadott beállításokkal jeleníti meg.
## 6. lépés: Kimeneti útvonal megjelenítése
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nyomtasson ki egy üzenetet, amely jelzi a dokumentum sikeres megjelenítését, és adja meg a kimeneti HTML-fájlok mentési útvonalát.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell használni a GroupDocs.Viewer for .NET-et a dokumentumokban hiányzó betűtípusok pótlására. Az alábbi lépések követésével biztosíthatja, hogy a dokumentumok pontosan megjelenjenek, még akkor is, ha bizonyos betűtípusok nem állnak rendelkezésre. A GroupDocs.Viewer leegyszerűsíti a folyamatot, lehetővé téve, hogy a robusztus .NET-alkalmazások létrehozására összpontosítson anélkül, hogy a betűtípus-kompatibilitási problémák miatt aggódna.
## GYIK
### A GroupDocs.Viewer kezelhet más típusú betűtípusokkal kapcsolatos problémákat?
Igen, a GroupDocs.Viewer különféle betűtípusokkal kapcsolatos funkciókat kínál, beleértve a betűtípus helyettesítését és a betűtípus észlelését.
### A GroupDocs.Viewer kompatibilis az összes .NET keretrendszerrel?
A GroupDocs.Viewer a .NET-keretrendszerek széles skáláját támogatja, beleértve a .NET Core-t és a .NET Standard-t.
### Testreszabhatom az alapértelmezett betűtípus-cserét a GroupDocs.Viewerben?
Természetesen bármilyen betűtípust megadhat a hiányzó betűtípusok alapértelmezett helyettesítőjeként.
### A GroupDocs.Viewer támogatja a dokumentumok kötegelt feldolgozását?
Igen, a GroupDocs.Viewer lehetővé teszi több dokumentum egyidejű feldolgozását, így ideális kötegelt feldolgozási forgatókönyvekhez.
### Hol találhatok további segítséget vagy támogatást a GroupDocs.Viewerhez?
 Látogassa meg a GroupDocs.Viewer fórumot[itt](https://forum.groupdocs.com/c/viewer/9) bármilyen segítségre vagy támogatási kérdésre.