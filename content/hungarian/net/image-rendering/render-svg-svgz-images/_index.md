---
title: Rendereljen SVG és SVGZ képeket
linktitle: Rendereljen SVG és SVGZ képeket
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet SVG- és SVGZ-képeket renderelni a GroupDocs.Viewer for .NET használatával. Könnyedén konvertálja a vektorgrafikát HTML, JPG, PNG és PDF formátumba.
type: docs
weight: 16
url: /hu/net/image-rendering/render-svg-svgz-images/
---
## Bevezetés
Ebben az oktatóanyagban végigvezetjük az SVG- és SVGZ-képek megjelenítésének folyamatán a GroupDocs.Viewer for .NET használatával. A GroupDocs.Viewer for .NET egy hatékony dokumentum-megjelenítő API, amely lehetővé teszi a fejlesztők számára, hogy különféle dokumentumformátumokat jelenítsenek meg .NET-alkalmazásaikban. Az SVG és az SVGZ népszerű képformátumok, amelyeket vektorgrafikákhoz használnak, és a GroupDocs.Viewer for .NET segítségével egyszerűen renderelheti őket különböző kimeneti formátumokba, például HTML, JPG, PNG és PDF formátumba.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy telepítette és beállította a következő előfeltételeket:
1.  GroupDocs.Viewer for .NET: Töltse le és telepítse a GroupDocs.Viewer for .NET programot innen[itt](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztői környezet: Győződjön meg arról, hogy rendelkezik működő fejlesztői környezettel a .NET-fejlesztéshez, például a Visual Studio-hoz.
3. Minta SVGZ-fájl: Készítsen egy SVGZ-mintafájlt tesztelésre.

## Névterek importálása
Mielőtt belemerülnénk a kódba, importáljuk a szükséges névtereket:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. lépés: Rendelje meg az SVGZ-t HTML-be
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## 2. lépés: Rendelje le az SVGZ-t JPG-be
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 3. lépés: Az SVGZ renderelése PNG formátumban
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 4. lépés: Rendelje le az SVGZ-t PDF-be
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet SVG- és SVGZ-képeket renderelni a GroupDocs.Viewer for .NET használatával. Csupán néhány egyszerű lépéssel konvertálhatja az SVGZ-képeket különféle kimeneti formátumokká, például HTML-, JPG-, PNG- és PDF-formátumokká, így elérhetővé és megtekinthetővé teszi őket különböző környezetekben.
## GYIK
### A GroupDocs.Viewer képes más képformátumokat is megjeleníteni?
Igen, a GroupDocs.Viewer támogatja a különféle képformátumok megjelenítését, beleértve a PNG, JPEG, BMP, TIFF, GIF stb.
### A GroupDocs.Viewer kompatibilis a .NET Core programmal?
Igen, a GroupDocs.Viewer a .NET-keretrendszerrel és a .NET Core-val is kompatibilis.
### Testreszabhatom a renderelési beállításokat?
Igen, a GroupDocs.Viewer kiterjedt megjelenítési lehetőségeket kínál, amelyek lehetővé teszik a kimenet igényeinek megfelelő testreszabását.
### A GroupDocs.Viewernek szüksége van harmadik féltől származó függőségekre?
Nem, a GroupDocs.Viewer egy önálló API, és nem igényel harmadik féltől származó függőséget a dokumentumok megjelenítéséhez.
### Létezik próbaverzió tesztelésre?
Igen, letöltheti a GroupDocs.Viewer ingyenes próbaverzióját a webhelyről[itt](https://releases.groupdocs.com/) hogy vásárlás előtt értékelje tulajdonságait.