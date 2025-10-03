---
"description": "Tanulja meg, hogyan jeleníthet meg SVG és SVGZ képeket a GroupDocs.Viewer for .NET segítségével. Könnyedén konvertálhat vektorgrafikákat HTML, JPG, PNG és PDF formátumba."
"linktitle": "SVG és SVGZ képek renderelése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "SVG és SVGZ képek renderelése"
"url": "/hu/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# SVG és SVGZ képek renderelése

## Bevezetés
Ebben az oktatóanyagban végigvezetjük az SVG és SVGZ képek renderelésének folyamatán a GroupDocs.Viewer for .NET segítségével. A GroupDocs.Viewer for .NET egy hatékony dokumentumrenderelési API, amely lehetővé teszi a fejlesztők számára, hogy különféle dokumentumformátumokat jelenítsenek meg .NET alkalmazásaikban. Az SVG és az SVGZ népszerű képformátumok, amelyeket vektorgrafikákhoz használnak, és a GroupDocs.Viewer for .NET segítségével könnyedén renderelheti őket különböző kimeneti formátumokba, például HTML, JPG, PNG és PDF formátumba.

![SVG és SVGZ képek renderelése a GroupDocs.Viewer for .NET segítségével](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételek telepítve és beállítva vannak:
1. GroupDocs.Viewer .NET-hez: Töltse le és telepítse a GroupDocs.Viewer .NET-hez alkalmazást innen: [itt](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztői környezet: Győződjön meg arról, hogy rendelkezik egy működő fejlesztői környezettel a .NET fejlesztéséhez, például a Visual Studio-val.
3. Minta SVGZ fájl: Készítsen elő egy minta SVGZ fájlt tesztelésre.

## Névterek importálása
Mielőtt belemerülnénk a kódba, importáljuk a szükséges névtereket:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. lépés: SVGZ renderelése HTML-lé
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## 2. lépés: SVGZ renderelése JPG-vé
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 3. lépés: SVGZ renderelése PNG-vé
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 4. lépés: SVGZ renderelése PDF-be
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet SVG és SVGZ képeket renderelni a GroupDocs.Viewer for .NET segítségével. Néhány egyszerű lépéssel konvertálhatja az SVGZ képeket különféle kimeneti formátumokba, például HTML, JPG, PNG és PDF formátumba, így azok különböző környezetekben is hozzáférhetővé és megtekinthetővé válnak.
## GYIK
### A GroupDocs.Viewer képes más képformátumokat is megjeleníteni?
Igen, a GroupDocs.Viewer különféle képformátumok megjelenítését támogatja, beleértve a PNG, JPEG, BMP, TIFF, GIF és egyebeket.
### Kompatibilis a GroupDocs.Viewer a .NET Core-ral?
Igen, a GroupDocs.Viewer kompatibilis mind a .NET Framework, mind a .NET Core rendszerrel.
### Testreszabhatom a renderelési beállításokat?
Igen, a GroupDocs.Viewer kiterjedt renderelési lehetőségeket kínál, amelyek lehetővé teszik a kimenet testreszabását az igényei szerint.
### GroupDocs.Viewer igényel-e harmadik féltől származó függőségeket?
Nem, a GroupDocs.Viewer egy önálló API, és nem igényel harmadik féltől származó függőségeket a dokumentumok rendereléséhez.
### Van elérhető próbaverzió tesztelésre?
Igen, letöltheti a GroupDocs.Viewer ingyenes próbaverzióját innen: [itt](https://releases.groupdocs.com/) hogy vásárlás előtt felmérje a tulajdonságait.