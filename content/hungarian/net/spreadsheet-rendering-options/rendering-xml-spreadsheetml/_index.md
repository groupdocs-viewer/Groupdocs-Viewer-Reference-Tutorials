---
title: XML SpreadSheetML megjelenítése
linktitle: XML SpreadSheetML megjelenítése
second_title: GroupDocs.Viewer .NET API
description: Fedezze fel az XML SpreadSheetML fájlok zökkenőmentes megjelenítését különféle formátumokban a GroupDocs.Viewer for .NET segítségével. Könnyedén integrálható az alkalmazásaiba.
weight: 16
url: /hu/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## Bevezetés
Üdvözöljük a GroupDocs.Viewer for .NET világában! Ebben az oktatóanyagban végigvezetjük az XML SpreadSheetML-fájlok egyszerű megjelenítésén a GroupDocs.Viewer, egy hatékony .NET-könyvtár segítségével. Akár tapasztalt fejlesztő, akár csak most kezdi, ez a lépésről-lépésre útmutató segít az XML SpreadSheetML-megjelenítésnek az alkalmazásaiba való erőfeszítés nélküli integrálásában.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy beállította a következő előfeltételeket:
- Fejlesztői környezet .NET támogatással.
-  A GroupDocs.Viewer for .NET könyvtár telepítve. Letöltheti[itt](https://releases.groupdocs.com/viewer/net/).
- A C# programozás alapvető ismerete.
## Névterek importálása
Kezdje a szükséges névterek importálásával a C# projektbe. Ez biztosítja, hogy hozzáférjen a GroupDocs.Viewer által biztosított funkciókhoz.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. lépés: Állítsa be a dokumentumkönyvtárat
Határozza meg a dokumentumkönyvtár elérési útját, ahová a kimenet mentésre kerül.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Adja meg a kimeneti fájl elérési útját
Állítsa be a HTML, JPG, PNG és PDF kimeneti fájlok teljes elérési útját.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## 3. lépés: Adja meg a Betöltési beállításokat
A pontos megjelenítés érdekében kifejezetten adja meg a fájltípust: Excel 2003 XML SpreadSheetML.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## 4. lépés: Rendereljen többoldalas HTML-ként
Használja a HTML nézet beállításait, hogy az XML SpreadSheetML fájlt többoldalas HTML-dokumentummá jelenítse meg.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 5. lépés: Renderelje le JPG formátumban
Rendelje meg az XML SpreadSheetML fájlt JPG képpé a megadott beállításokkal.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 6. lépés: Renderelés PNG formátumban
Hasonlóképpen jelenítse meg a fájlt PNG képpé a megadott beállításokkal.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 7. lépés: Renderje le PDF-be
Végül az XML SpreadSheetML fájlt PDF-dokumentummá jelenítse meg a megadott beállításokkal.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan lehet XML SpreadSheetML fájlokat előállítani a GroupDocs.Viewer for .NET segítségével. Fokozza dokumentummegtekintési képességeit a sokoldalú könyvtár által biztosított további funkciók és lehetőségek felfedezésével.
## GYIK
### A GroupDocs.Viewer kompatibilis más fájlformátumokkal?
Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF, Word, Excel és egyebeket.
### Testreszabhatom a renderelt dokumentumok megjelenését?
Teljesen! A GroupDocs.Viewer különféle testreszabási lehetőségeket kínál, amelyek lehetővé teszik, hogy a kimenetet az Ön egyedi igényeihez igazítsa.
### Hol találhatok további támogatást és forrásokat?
 Meglátogatni a[GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) közösségi támogatásért és fedezze fel a[dokumentáció](https://tutorials.groupdocs.com/viewer/net/)részletes információkért.
### Van ingyenes próbaverzió?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.groupdocs.com/).
### Hogyan szerezhetek ideiglenes engedélyt?
 Kaphat ideiglenes engedélyt[itt](https://purchase.groupdocs.com/temporary-license/).