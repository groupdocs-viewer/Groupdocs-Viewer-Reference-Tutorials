---
"description": "Fedezze fel az XML SpreadSheetML fájlok zökkenőmentes renderelését különböző formátumokban a GroupDocs.Viewer for .NET segítségével. Könnyedén integrálható az alkalmazásaiba."
"linktitle": "XML SpreadSheetML renderelése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "XML SpreadSheetML renderelése"
"url": "/hu/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
---

# XML SpreadSheetML renderelése

## Bevezetés
Üdvözlünk a GroupDocs.Viewer for .NET világában! Ebben az oktatóanyagban végigvezetünk az XML SpreadSheetML fájlok egyszerű renderelésében a GroupDocs.Viewer, egy hatékony .NET könyvtár segítségével. Akár tapasztalt fejlesztő vagy, akár most kezded, ez a lépésről lépésre szóló útmutató segít könnyedén integrálni az XML SpreadSheetML renderelését az alkalmazásaidba.
## Előfeltételek
Mielőtt belemerülnél az oktatóanyagba, győződj meg róla, hogy a következő előfeltételek teljesülnek:
- Fejlesztői környezet .NET támogatással.
- GroupDocs.Viewer for .NET könyvtár telepítve. Letöltheti. [itt](https://releases.groupdocs.com/viewer/net/).
- A C# programozás alapjainak ismerete.
## Névterek importálása
Kezd azzal, hogy importálod a szükséges névtereket a C# projektedbe. Ez biztosítja, hogy hozzáférj a GroupDocs.Viewer által biztosított funkciókhoz.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. lépés: Dokumentumkönyvtár beállítása
Adja meg a dokumentumok könyvtárának elérési útját, ahová a kimenet mentésre kerül.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Kimeneti fájlútvonalak megadása
Állítsa be a HTML, JPG, PNG és PDF kimeneti fájlok teljes elérési útját.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## 3. lépés: Betöltési beállítások megadása
A pontos megjelenítés érdekében explicit módon adja meg a fájltípust Excel 2003 XML SpreadSheetML-ként.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## 4. lépés: Többoldalas HTML-ként való renderelés
A HTML nézet beállításaival jelenítse meg az XML SpreadSheetML fájlt egy többoldalas HTML dokumentumban.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 5. lépés: Renderelés JPG formátumba
Rendereld az XML SpreadSheetML fájlt JPG képpé a megadott beállításokkal.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 6. lépés: Renderelés PNG formátumba
Hasonlóképpen, rendereld a fájlt PNG képpé a megadott beállításokkal.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 7. lépés: Renderelés PDF-be
Végül rendereld az XML SpreadSheetML fájlt PDF dokumentummá a megadott beállításokkal.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Következtetés
Gratulálunk! Sikeresen megtanultad, hogyan kell XML SpreadSheetML fájlokat megjeleníteni a GroupDocs.Viewer for .NET segítségével. Bővítsd dokumentummegtekintési képességeidet a sokoldalú könyvtár által kínált további funkciók és lehetőségek felfedezésével.
## GYIK
### A GroupDocs.Viewer kompatibilis más fájlformátumokkal?
Igen, a GroupDocs.Viewer számos dokumentumformátumot támogat, beleértve a PDF, Word, Excel és egyebeket.
### Testreszabhatom a megjelenített dokumentumok megjelenését?
Abszolút! A GroupDocs.Viewer számos testreszabási lehetőséget kínál, így a kimenetet az Ön igényeihez igazíthatja.
### Hol találok további támogatást és forrásokat?
Látogassa meg a [GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) közösségi támogatásért és a [dokumentáció](https://tutorials.groupdocs.com/viewer/net/) részletes információkért.
### Van ingyenes próbaverzió?
Igen, hozzáférhetsz az ingyenes próbaverzióhoz [itt](https://releases.groupdocs.com/).
### Hogyan szerezhetek ideiglenes jogosítványt?
Ideiglenes jogosítványt szerezhetsz [itt](https://purchase.groupdocs.com/temporary-license/).