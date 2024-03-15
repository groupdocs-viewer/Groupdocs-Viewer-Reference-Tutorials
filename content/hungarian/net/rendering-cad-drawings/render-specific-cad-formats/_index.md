---
title: Renderelésspecifikus CAD-formátumok (CF2)
linktitle: Renderelésspecifikus CAD-formátumok (CF2)
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet meghatározott CAD-formátumokat, például CF2-t HTML-, JPG-, PNG- és PDF-formátumba renderelni a Groupdocs.Viewer for .NET segítségével.
type: docs
weight: 12
url: /hu/net/rendering-cad-drawings/render-specific-cad-formats/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet adott CAD-formátumokat előállítani a Groupdocs.Viewer for .NET segítségével. A Groupdocs.Viewer egy hatékony dokumentumnézegető API, amely lehetővé teszi a fejlesztők számára, hogy több mint 170 dokumentumtípust jelenítsenek meg alkalmazásaikban külső szoftver telepítése nélkül. Konkrétan a CAD formátumok, például a CF2 megjelenítésére fogunk összpontosítani különféle kimeneti formátumokká, például HTML, JPG, PNG és PDF.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- A Visual Studio telepítve van a rendszerére.
-  Groupdocs.Viewer .NET SDK-hoz. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
- C# programozási nyelv alapismerete.
## Névterek importálása
Először is importáljuk a CAD formátumok rendereléséhez szükséges névtereket.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Most bontsuk le az egyes példákat több lépésre:
## Renderelje le a CF2-t HTML-be
### 1. lépés: Határozza meg a kimeneti könyvtárat, ahová a renderelt HTML mentésre kerül.
```csharp
string outputDirectory = "Your Document Directory";
```
### 2. lépés: Határozza meg a HTML-kimenet fájlútvonal-formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### 3. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Adjon meg további renderelési beállításokat, ha szükséges
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderje le a CF2-t JPG formátumba
### 1. lépés: Határozza meg a fájl elérési út formátumát a JPG kimenethez.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### 2. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Adjon meg további renderelési beállításokat, ha szükséges
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderje le a CF2-t PNG-re

### 1. lépés: Határozza meg a PNG-kimenet fájlútvonal-formátumát.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### 2. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Adjon meg további renderelési beállításokat, ha szükséges
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderje le a CF2-t PDF-be
### 1. lépés: Határozza meg a PDF kimenet fájlútvonal-formátumát.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### 2. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Adjon meg további renderelési beállításokat, ha szükséges
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet meghatározott CAD-formátumokat, például CF2-t előállítani a Groupdocs.Viewer for .NET használatával. A lépésenkénti útmutató követésével könnyedén integrálhatja a dokumentum-megjelenítési képességeket .NET-alkalmazásaiba.
## GYIK
### A Groupdocs.Viewer képes a CF2-n kívül más CAD-formátumokat is megjeleníteni?
Igen, a Groupdocs.Viewer a CAD formátumok széles skáláját támogatja, beleértve a DWG-t, DXF-et, DGN-t stb.
### A Groupdocs.Viewer alkalmas dokumentumok webes alkalmazásokban történő megjelenítésére?
Természetesen a Groupdocs.Viewer zökkenőmentesen integrálható webalkalmazásokba a dokumentumok közvetlen böngészőben történő megjelenítéséhez.
### A Groupdocs.Viewernek szüksége van külső függőségekre a megjelenítéshez?
Nem, a Groupdocs.Viewer egy önálló API, és nem igényel semmilyen külső függőséget vagy szoftvertelepítést.
### Testreszabhatom a renderelési beállításokat igényeim szerint?
Igen, a Groupdocs.Viewer különféle megjelenítési lehetőségeket kínál, amelyek testreszabhatók az Ön egyedi igényei szerint.
### Elérhető a Groupdocs.Viewer próbaverziója?
 Igen, beszerezheti a Groupdocs.Viewer ingyenes próbaverzióját a webhelyről[itt](https://releases.groupdocs.com/).