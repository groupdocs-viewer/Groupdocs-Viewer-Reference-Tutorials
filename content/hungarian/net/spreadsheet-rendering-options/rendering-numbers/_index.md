---
title: Számok renderelése
linktitle: Számok renderelése
second_title: GroupDocs.Viewer .NET API
description: Fedezze fel a Groupdocs.Viewer for .NET erejét a Numbers-fájlok zökkenőmentes megjelenítésében. Könnyedén konvertálhat HTML, JPG, PNG és PDF formátumba.
weight: 15
url: /hu/net/spreadsheet-rendering-options/rendering-numbers/
---

# Számok renderelése

## Bevezetés
Üdvözöljük ebben a lépésenkénti oktatóanyagban a Numbers-fájlok Groupdocs.Viewer for .NET használatával történő megjelenítéséről. Akár tapasztalt fejlesztő, akár kezdő, ez az útmutató végigvezeti a Numbers-dokumentumok különböző formátumokba konvertálásának folyamatán. A Groupdocs.Viewer for .NET egy hatékony eszköz, amely lehetővé teszi a dokumentummegtekintési képességek zökkenőmentes integrálását .NET-alkalmazásaiba.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- C# és .NET fejlesztési ismeretek.
-  A Groupdocs.Viewer for .NET könyvtár telepítve. Letöltheti[itt](https://releases.groupdocs.com/viewer/net/).
- A dokumentumkönyvtár elérési útja, ahová a kimeneti fájlok mentésre kerülnek.
## Névterek importálása
C# projektben győződjön meg arról, hogy importálja a szükséges névtereket a Groupdocs.Viewer könyvtár használatához:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Állítsa be a kimeneti könyvtárat
Mielőtt elkezdené a renderelést, határozza meg a kimeneti könyvtárat, ahová a konvertált fájlok mentésre kerülnek. Cserélje ki a "Saját dokumentumkönyvtárat" a tényleges elérési úttal:
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Rendereljen többoldalas HTML-ként
Használja a következő kódot a Numbers fájl többoldalas HTML-formátumba konvertálásához:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 3. lépés: Renderelje le JPG formátumban
Alakítsa át a Numbers fájlt JPG formátumba a következő kóddal:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 4. lépés: Renderelje le PNG formátumban
Alakítsa át a Numbers fájlt PNG formátumba a következő kóddal:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 5. lépés: Rendelje le PDF-be
Végül konvertálja a Numbers fájlt PDF formátumba a következő kóddal:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Gratulálunk! Sikeresen renderelte a Numbers fájlokat különböző formátumokba a Groupdocs.Viewer for .NET segítségével.
## Következtetés
Ebben az oktatóanyagban a Numbers-fájlok Groupdocs.Viewer for .NET használatával történő előállításának alapjait ismertettük. Ez a hatékony könyvtár zökkenőmentes integrációt biztosít a dokumentumok megtekintéséhez és konvertálásához a .NET-alkalmazásokban.
## GYIK
### Használhatom a Groupdocs.Viewer for .NET programot más dokumentumtípusokkal?
Igen, a Groupdocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a Word, Excel, PDF és egyebeket.
### Kapható-e ideiglenes licenc tesztelési célokra?
 Igen, kaphat ideiglenes engedélyt[itt](https://purchase.groupdocs.com/temporary-license/) tesztelésre.
### Hol találok támogatást a Groupdocs.Viewer for .NET számára?
 Meglátogatni a[Groupdocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) segítségért és megbeszélésekért.
### Hogyan vásárolhatom meg a Groupdocs.Viewer for .NET teljes verzióját?
 Megvásárolhatja a teljes verziót[itt](https://purchase.groupdocs.com/buy).
### Létezik ingyenes próbaverzió?
 Igen, felfedezheti az ingyenes próbaverziót[itt](https://releases.groupdocs.com/).