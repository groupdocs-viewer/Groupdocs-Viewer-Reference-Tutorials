---
title: Rendereljen Visio figurákat
linktitle: Rendereljen Visio figurákat
second_title: GroupDocs.Viewer .NET API
description: Tanulja meg, hogyan jeleníthet meg Visio-figurákat a GroupDocs.Viewer for .NET használatával ebben az átfogó cikkben. Fokozza a dokumentummegtekintési képességeket .NET-alkalmazásaiban.
weight: 10
url: /hu/net/rendering-visio-documents/render-visio-figures/
---
## Bevezetés
A mai digitális korban a dokumentum-megjelenítés döntő szerepet játszik különböző alkalmazásokban. Legyen szó dokumentumok megjelenítéséről egy webhelyen, vagy különböző formátumokba konvertálásáról, a hatékony megjelenítés elengedhetetlen. A GroupDocs.Viewer for .NET robusztus megoldást kínál a .NET-alkalmazásokon belüli dokumentumok megtekintéséhez és kezeléséhez. Ebben az oktatóanyagban a Visio-figurák GroupDocs.Viewer for .NET használatával történő megjelenítésével foglalkozunk, egyszerű lépésekre bontva a folyamatot.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Környezetbeállítás: Győződjön meg arról, hogy van munkakörnyezete a .NET fejlesztéshez.
2.  GroupDocs.Viewer for .NET: Töltse le és telepítse a GroupDocs.Viewer for .NET programot a[letöltési link](https://releases.groupdocs.com/viewer/net/).
3. A C# alapjai: Ismerkedjen meg a C# programozási nyelv alapjaival.
4. Visio-dokumentum minta: Készítsen elő egy minta Visio-dokumentumot.

## Névterek importálása
A C# projektben kezdje a szükséges névterek importálásával:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Renderelés HTML-be
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Kimeneti könyvtár: Határozza meg azt a könyvtárat, ahová a renderelt HTML mentésre kerül.
- Oldalfájl elérési út formátuma: Adja meg a HTML oldal elérési út formátumát.
- Viewer inicializálása: Inicializálja a Viewer objektumot a Visio dokumentum elérési útjával.
- HTML nézet beállításai: konfigurálja a HTML megjelenítési beállításokat.
- Visio renderelési beállításai: Állítsa be a Visio renderelésre jellemző beállításokat, például csak a számok megjelenítését és az ábra szélességét.
## 2. Renderelés JPG formátumban
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- A HTML formátumban történő megjelenítéshez hasonlóan konfigurálja a JPG formátumú megjelenítési beállításokat.
## 3. Renderelés PNG formátumba
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- A PNG formátumú renderelés konfigurációja hasonló mintát követ, mint a JPG renderelés.
## 4. Renderelés PDF-be
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- A PDF formátumban való megjelenítéshez konfigurálja a PDF formátumra jellemző beállításokat.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan lehet Visio-figurákat előállítani a GroupDocs.Viewer for .NET használatával. A lépésenkénti útmutató követésével zökkenőmentesen integrálhatja a dokumentum-megjelenítési képességeket .NET-alkalmazásaiba, javítva a felhasználói élményt és a termelékenységet.
## GYIK
### Testreszabhatom a Visio-figurák megjelenítési beállításait?
Igen, a GroupDocs.Viewer for .NET kiterjedt lehetőségeket kínál a renderelés testreszabására, beleértve az ábrák szélességét, a csak ábrák megjelenítését stb.
### A GroupDocs.Viewer for .NET alkalmas nagyméretű dokumentumok megjelenítésére?
Természetesen a GroupDocs.Viewer for .NET a nagyméretű dokumentum-megjelenítés hatékony kezelésére van optimalizálva.
### A GroupDocs.Viewer a Visio-n kívül más dokumentumformátumokat is támogat?
Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF-et, a Microsoft Office-t, az AutoCAD-et és egyebeket.
### Integrálhatom a GroupDocs.Viewert webes alkalmazásokba?
Igen, a GroupDocs.Viewer zökkenőmentesen integrálható webes alkalmazásokba a dokumentumok megtekintésére és manipulálására.
### Vásárlás előtt kipróbálható-e próbaverzió?
Igen, igénybe veheti az ingyenes próbaverziót a[weboldal](https://releases.groupdocs.com/) hogy tesztelje a GroupDocs.Viewer for .NET képességeit.