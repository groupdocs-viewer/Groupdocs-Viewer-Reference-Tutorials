---
"description": "Fedezze fel a Groupdocs.Viewer for .NET erejét a Numbers fájlok zökkenőmentes renderelésében. Könnyedén konvertálhat HTML, JPG, PNG és PDF formátumba."
"linktitle": "Számok megjelenítése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Számok megjelenítése"
"url": "/hu/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# Számok megjelenítése

## Bevezetés
Üdvözlünk ebben a lépésről lépésre bemutató oktatóanyagban, amely a Groupdocs.Viewer for .NET segítségével renderel Numbers fájlokat. Akár tapasztalt fejlesztő, akár kezdő, ez az útmutató végigvezeti Önt a Numbers dokumentumok különböző formátumokba konvertálásának folyamatán. A Groupdocs.Viewer for .NET egy hatékony eszköz, amely lehetővé teszi a dokumentummegtekintési funkciók zökkenőmentes integrálását a .NET alkalmazásaiba.
## Előfeltételek
Mielőtt belevágnál az oktatóanyagba, győződj meg róla, hogy a következő előfeltételek teljesülnek:
- C# és .NET fejlesztési ismeretek.
- Groupdocs.Viewer for .NET könyvtár telepítve. Letöltheti. [itt](https://releases.groupdocs.com/viewer/net/).
- dokumentum könyvtárának elérési útja, ahová a kimeneti fájlok mentésre kerülnek.
## Névterek importálása
A C# projektedben ügyelj arra, hogy importáld a Groupdocs.Viewer könyvtár használatához szükséges névtereket:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Kimeneti könyvtár beállítása
A renderelés megkezdése előtt adja meg a kimeneti könyvtárat, ahová a konvertált fájlok mentésre kerülnek. Cserélje ki a „Saját dokumentumkönyvtár” részt a tényleges elérési útra:
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Többoldalas HTML-ként való renderelés
A következő kóddal konvertálhatod a Numbers fájlt többoldalas HTML-fájllá:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 3. lépés: Renderelés JPG formátumba
Konvertálja a Numbers fájlt JPG formátumba a következő kóddal:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 4. lépés: Renderelés PNG formátumba
Alakítsd át a Numbers fájlt PNG formátumba a következő kóddal:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 5. lépés: Renderelés PDF-be
Végül konvertáld a Numbers fájlt PDF formátumba a következő kóddal:
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
Ebben az oktatóanyagban a Numbers fájlok Groupdocs.Viewer for .NET használatával történő renderelésének alapjait ismertettük. Ez a hatékony könyvtár zökkenőmentes integrációt biztosít a dokumentumok megtekintéséhez és konvertálásához a .NET alkalmazásokban.
## GYIK
### Használhatom a Groupdocs.Viewer for .NET-et más dokumentumtípusokkal?
Igen, a Groupdocs.Viewer számos dokumentumformátumot támogat, beleértve a Wordöt, Excelt, PDF-et és egyebeket.
### Van ideiglenes jogosítvány tesztelési célokra?
Igen, igényelhet ideiglenes jogosítványt [itt](https://purchase.groupdocs.com/temporary-license/) teszteléshez.
### Hol találok támogatást a Groupdocs.Viewer for .NET-hez?
Látogassa meg a [Groupdocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) segítségért és megbeszélésekért.
### Hogyan vásárolhatom meg a Groupdocs.Viewer teljes verzióját .NET-hez?
Megvásárolhatod a teljes verziót [itt](https://purchase.groupdocs.com/buy).
### Van elérhető ingyenes próbaverzió?
Igen, kipróbálhatod az ingyenes próbaverziót [itt](https://releases.groupdocs.com/).