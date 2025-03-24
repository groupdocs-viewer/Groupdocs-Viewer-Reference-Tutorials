---
title: Rétegek renderelése CAD rajzokban
linktitle: Rétegek renderelése CAD rajzokban
second_title: GroupDocs.Viewer .NET API
description: CAD-rajzok zökkenőmentes megjelenítése .NET-alkalmazásokban a GroupDocs.Viewer for .NET segítségével. Fedezze fel a megjelenítési lehetőségeket, szabja testre a rétegeket és sok mást.
weight: 13
url: /hu/net/rendering-cad-drawings/render-layers-cad/
---
## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony eszköz, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen integrálják a dokumentum-megjelenítési képességeket .NET-alkalmazásaikba. Akár CAD-rajzokat, PDF-eket, Microsoft Office dokumentumokat vagy egyebeket kell renderelni, a GroupDocs.Viewer átfogó megoldást kínál.
## Előfeltételek
Mielőtt belevágna a GroupDocs.Viewer for .NET használatába, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- C# programozási nyelv alapvető ismerete.
- .NET fejlesztői környezet a gépén.
-  A GroupDocs.Viewer for .NET telepítve. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
-  Hozzáférés a GroupDocs.Viewer for .NET dokumentációjához referenciaként, amely megtalálható[itt](https://tutorials.groupdocs.com/viewer/net/).

## Névterek importálása
A GroupDocs.Viewer for .NET használatának megkezdéséhez importálnia kell a szükséges névtereket a projektbe. Kovesd ezeket a lepeseket:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Bontsuk fel a megadott példát több lépésre:
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Inicializálja a Viewer Object-et
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // A kódblokk folytatódik...
}
```
## 4. lépés: Állítsa be a HTML nézet beállításait
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5. lépés: Határozza meg a CAD rétegeket
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## 6. lépés: Renderelje le a dokumentumot
```csharp
viewer.View(options);
```
## 7. lépés: Kimeneti renderelt dokumentum helye
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
A GroupDocs.Viewer for .NET segítségével zökkenőmentes folyamattá válik a CAD-rajzok megjelenítése a .NET-alkalmazásokban. Az ebben az útmutatóban ismertetett lépések követésével könnyedén integrálhatja projektjeibe a dokumentum-megjelenítési képességeket.
## GYIK
### Kompatibilis a GroupDocs.Viewer minden típusú CAD-rajzzal?
Igen, a GroupDocs.Viewer támogatja a CAD rajzformátumok széles skálájának renderelését, beleértve a DWG-t és a DXF-et is.
### Testreszabhatom a CAD-rajzok renderelési beállításait?
Természetesen a GroupDocs.Viewer különféle testreszabási lehetőségeket kínál, mint például a megjelenítendő rétegek megadása vagy a kimeneti formátumok beállítása.
### A GroupDocs.Viewernek szüksége van internetkapcsolatra a dokumentumok megjelenítéséhez?
Nem, a GroupDocs.Viewer helyileg, internetkapcsolat nélkül hajtja végre a renderelést.
### Elérhető ingyenes próbaverzió a GroupDocs.Viewer for .NET számára?
 Igen, hozzáférhet a GroupDocs.Viewer for .NET ingyenes próbaverziójához[itt](https://releases.groupdocs.com/).
### Hol kaphatok támogatást a GroupDocs.Viewer for .NET-hez?
 Bármilyen technikai segítségért vagy kérdésért keresse fel a GroupDocs.Viewer fórumot[itt](https://forum.groupdocs.com/c/viewer/9).