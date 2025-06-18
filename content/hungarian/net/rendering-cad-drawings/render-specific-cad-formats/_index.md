---
"description": "Ismerje meg, hogyan renderelhet bizonyos CAD formátumokat, például CF2-t HTML, JPG, PNG és PDF formátumba a Groupdocs.Viewer for .NET segítségével."
"linktitle": "Renderelés-specifikus CAD formátumok (CF2)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderelés-specifikus CAD formátumok (CF2)"
"url": "/hu/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Renderelés-specifikus CAD formátumok (CF2)

## Bevezetés
Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan lehet bizonyos CAD formátumokat megjeleníteni a Groupdocs.Viewer for .NET segítségével. A Groupdocs.Viewer egy hatékony dokumentummegjelenítő API, amely lehetővé teszi a fejlesztők számára, hogy több mint 170 dokumentumtípust jelenítsenek meg alkalmazásaikban külső szoftvertelepítés nélkül. Konkrétan a CAD formátumok, például a CF2, különböző kimeneti formátumokba, például HTML, JPG, PNG és PDF formátumba történő renderelésére fogunk összpontosítani.
## Előfeltételek
Mielőtt belemerülnénk az oktatóanyagba, győződjünk meg arról, hogy a következő előfeltételekkel rendelkezünk:
- Visual Studio telepítve a rendszeredre.
- Groupdocs.Viewer .NET SDK-hoz. Letöltheti innen: [itt](https://releases.groupdocs.com/viewer/net/).
- C# programozási nyelv alapismerete.
## Névterek importálása
Először importáljuk a CAD formátumok rendereléséhez szükséges névtereket.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Most bontsuk le az egyes példákat több lépésre:
## CF2 renderelése HTML-ként
### 1. lépés: Adja meg a kimeneti könyvtárat, ahová a renderelt HTML-t menteni fogja.
```csharp
string outputDirectory = "Your Document Directory";
```
### 2. lépés: Adja meg a HTML-kimenet fájlelérési útvonalának formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### 3. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Szükség esetén további renderelési beállítások megadása
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 renderelése JPG-vé
### 1. lépés: Adja meg a JPG kimenet fájlelérési formátumát.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### 2. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Szükség esetén további renderelési beállítások megadása
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 renderelése PNG-vé

### 1. lépés: Adja meg a PNG kimenet fájlelérési formátumát.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### 2. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Szükség esetén további renderelési beállítások megadása
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 renderelése PDF-be
### 1. lépés: Adja meg a PDF kimenet fájlelérési útvonalának formátumát.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### 2. lépés: Inicializálja a Viewer objektumot, és adja meg a bemeneti CF2 fájlt.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Szükség esetén további renderelési beállítások megadása
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet bizonyos CAD formátumokat, például a CF2-t renderelni a Groupdocs.Viewer for .NET segítségével. A lépésről lépésre haladó útmutató követésével könnyedén integrálhatja a dokumentumrenderelési képességeket .NET alkalmazásaiba.
## GYIK
### A Groupdocs.Viewer képes a CF2-n kívül más CAD formátumokat is megjeleníteni?
Igen, a Groupdocs.Viewer számos CAD formátumot támogat, beleértve a DWG, DXF, DGN és egyebeket.
### Alkalmas a Groupdocs.Viewer dokumentumok webes alkalmazásokban történő megjelenítésére?
A Groupdocs.Viewer abszolút zökkenőmentesen integrálható webes alkalmazásokba, így dokumentumokat jeleníthet meg közvetlenül a böngészőben.
### A Groupdocs.Viewer igényel külső függőségeket a rendereléshez?
Nem, a Groupdocs.Viewer egy önálló API, és nem igényel semmilyen külső függőséget vagy szoftvertelepítést.
### Testreszabhatom a renderelési beállításokat az igényeim szerint?
Igen, a Groupdocs.Viewer különféle renderelési beállításokat kínál, amelyek testreszabhatók az Ön igényeinek megfelelően.
### Van elérhető próbaverzió a Groupdocs.Viewerhez?
Igen, letöltheti a Groupdocs.Viewer ingyenes próbaverzióját innen: [itt](https://releases.groupdocs.com/).