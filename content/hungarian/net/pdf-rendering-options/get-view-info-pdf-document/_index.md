---
"description": "Ebben az átfogó oktatóanyagban megtudhatja, hogyan kinyerheti a nézetadatokat PDF dokumentumokból a GroupDocs.Viewer for .NET segítségével."
"linktitle": "PDF dokumentum megtekintési adatainak lekérése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF dokumentum megtekintési adatainak lekérése"
"url": "/hu/net/pdf-rendering-options/get-view-info-pdf-document/"
"weight": 16
---

# PDF dokumentum megtekintési adatainak lekérése

## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony eszköz, amelyet a .NET alkalmazásokon belüli dokumentummegtekintés egyszerűsítésére terveztek. Akár PDF-ekkel, Word-dokumentumokkal, Excel-táblázatokkal vagy PowerPoint-bemutatókkal foglalkozik, ez a könyvtár leegyszerűsíti a különféle fájlformátumok renderelését és a velük való interakciót. Ebben az oktatóanyagban a GroupDocs.Viewer képességeinek kihasználására fogunk összpontosítani, kifejezetten a PDF-dokumentumokból származó nézetinformációk kinyerésére.

![PDF dokumentum megtekintési adatainak lekérése a GroupDocs.Viewer .NET segítségével](/viewer/pdf-rendering-options/get-view-iInfo-for-pdf-document.png)

## Előfeltételek
Mielőtt belemerülnél az oktatóanyagba, győződj meg róla, hogy a következő előfeltételekkel rendelkezel:
1. A GroupDocs.Viewer telepítése .NET-hez: Győződjön meg róla, hogy letöltötte és telepítette a GroupDocs.Viewer könyvtárat. A könyvtárat a következő helyről szerezheti be: [letöltési link](https://releases.groupdocs.com/viewer/net/).   
2. C# alapismeretek: A C# programozási nyelv ismerete elengedhetetlen a megadott kódpéldák megértéséhez és megvalósításához.
3. PDF-dokumentum elérése: Készítsen elő egy PDF-dokumentumot, amelyből kinyerheti a megtekintési információkat.

## Névterek importálása
A C# projektedben importáld a szükséges névtereket a GroupDocs.Viewer funkcióinak használatához.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Most pedig bontsuk le a nézetinformációk lekérésének folyamatát egy PDF dokumentumból a GroupDocs.Viewer for .NET használatával.
## 1. lépés: Viewer objektum inicializálása
Hozz létre egy Viewer objektumot, és paraméterként add meg a PDF dokumentum elérési útját.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## 2. lépés: ViewInfoOptions definiálása
Adja meg a nézetbeállításokat, például a HTML nézetet, a nézetinformációk lekéréséhez.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## 3. lépés: Nézetinformációk lekérése
A GetViewInfo metódus meghívásával kinyerhetjük a nézetinformációkat a PDF dokumentumból.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## 4. lépés: Kimeneti nézetinformációk
Jelenítse meg a kinyert nézetinformációkat, például a dokumentum típusát, az oldalszámot és a nyomtatási engedélyeket.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Következtetés
Ebben az oktatóanyagban azt vizsgáltuk meg, hogyan használható a GroupDocs.Viewer for .NET a PDF dokumentumokból való megtekintési információk kinyerésére. A megadott lépéseket követve zökkenőmentesen integrálhatja ezt a funkciót .NET alkalmazásaiba, javítva a dokumentumkezelési és megtekintési képességeket.
## GYIK
### A GroupDocs.Viewer kompatibilis a PDF-en kívül más fájlformátumokkal is?
Igen, a GroupDocs.Viewer számos dokumentumformátumot támogat, beleértve a Wordöt, az Excelt, a PowerPointot és egyebeket.
### Testreszabhatom a nézetbeállításokat az alkalmazásom igényei szerint?
Természetesen a GroupDocs.Viewer számos lehetőséget kínál a megtekintési élmény testreszabására az Ön egyedi igényei alapján.
### A GroupDocs.Viewer alkalmas asztali és webes alkalmazásokhoz is?
Igen, a GroupDocs.Viewer sokoldalú, és zökkenőmentesen integrálható mind asztali, mind webes .NET alkalmazásokba.
### A GroupDocs.Viewer nyújt-e támogatást és segítséget, ha bármilyen problémába ütközöm a megvalósítás során?
Természetesen kérhet segítséget a GroupDocs.Viewer közösségi fórumon, vagy igénybe veheti a professzionális támogatási szolgáltatásokat a problémák gyors megoldása érdekében.
### Kipróbálhatom a GroupDocs.Viewer alkalmazást vásárlás előtt?
Igen, a GroupDocs.Viewer funkcióit felfedezheti az ingyenes próbaverzió elérésével, amely elérhető a következő címen: [weboldal](https://purchase.groupdocs.com/buy).