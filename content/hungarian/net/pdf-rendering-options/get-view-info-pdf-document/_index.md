---
title: Információ megtekintése PDF-dokumentumhoz
linktitle: Információ megtekintése PDF-dokumentumhoz
second_title: GroupDocs.Viewer .NET API
description: Ebben az átfogó oktatóanyagban megtudhatja, hogyan nyerhet ki nézeti információkat PDF-dokumentumokból a GroupDocs.Viewer for .NET segítségével.
weight: 16
url: /hu/net/pdf-rendering-options/get-view-info-pdf-document/
---
## Bevezetés
GroupDocs.Viewer for .NET egy hatékony eszköz, amelyet a .NET-alkalmazásokon belüli dokumentumok megtekintésének egyszerűsítésére terveztek. Függetlenül attól, hogy PDF-ekkel, Word-dokumentumokkal, Excel-táblázatokkal vagy PowerPoint-prezentációkkal foglalkozik, ez a könyvtár leegyszerűsíti a különböző fájlformátumok megjelenítésének és interakciójának folyamatát. Ebben az oktatóanyagban a GroupDocs.Viewer képességeinek kiaknázására összpontosítunk, kifejezetten a nézeti információk PDF-dokumentumokból való kinyerésére.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  A GroupDocs.Viewer .NET-hez telepítése: Győződjön meg arról, hogy letöltötte és telepítette a GroupDocs.Viewer könyvtárat. Beszerezheti a[letöltési link](https://releases.groupdocs.com/viewer/net/).   
2. Alapvető C# ismerete: A C# programozási nyelv ismerete elengedhetetlen a mellékelt kódpéldák megértéséhez és megvalósításához.
3. Hozzáférés a PDF-dokumentumhoz: Készítsen egy PDF-dokumentumot, amelyet a megtekintési információk kinyerésére fog használni.

## Névterek importálása
A C# projektben importálja a szükséges névtereket a GroupDocs.Viewer funkcióinak használatához.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Most bontsuk le a nézetadatok PDF-dokumentumból történő lekérésének folyamatát a GroupDocs.Viewer for .NET használatával.
## 1. lépés: Inicializálja a Viewer Object-et
Hozzon létre egy Viewer objektumot, és adja meg a PDF-dokumentum elérési útját paraméterként.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## 2. lépés: Adja meg a ViewInfoOptions
Adja meg a nézetbeállításokat, például a HTML-nézetet a nézetadatok lekéréséhez.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## 3. lépés: Nézetinformációk lekérése
Hívja meg a GetViewInfo metódust a nézeti információk kinyeréséhez a PDF-dokumentumból.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## 4. lépés: Kimeneti információ
Megjeleníti a kivont nézetinformációkat, például a dokumentum típusát, az oldalak számát és a nyomtatási engedélyeket.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan használhatjuk a GroupDocs.Viewer for .NET-et a megtekintési információk PDF-dokumentumokból való kinyerésére. A megadott lépések követésével zökkenőmentesen integrálhatja ezt a funkciót .NET-alkalmazásaiba, javítva ezzel a dokumentumkezelési és -megtekintési képességeket.
## GYIK
### A GroupDocs.Viewer a PDF-en kívül más fájlformátumokkal is kompatibilis?
Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a Word, Excel, PowerPoint és egyebeket.
### Testreszabhatom a nézetbeállításokat az alkalmazásom követelményei szerint?
Természetesen a GroupDocs.Viewer különféle lehetőségeket kínál a megtekintési élmény személyre szabására az Ön egyedi igényei alapján.
### A GroupDocs.Viewer alkalmas asztali és webes alkalmazásokhoz is?
Igen, a GroupDocs.Viewer sokoldalú, és zökkenőmentesen integrálható asztali és webalapú .NET-alkalmazásokba is.
### A GroupDocs.Viewer nyújt támogatást és segítséget, ha bármilyen problémába ütközöm a megvalósítás során?
Természetesen kérhet segítséget a GroupDocs.Viewer közösségi fórumtól, vagy igénybe veheti a professzionális támogatási szolgáltatásokat a probléma gyors megoldása érdekében.
### Kipróbálhatom a GroupDocs.Viewer programot vásárlás előtt?
 Igen, felfedezheti a GroupDocs.Viewer szolgáltatásait, ha eléri a webhelyen elérhető ingyenes próbaverziót[weboldal](https://purchase.groupdocs.com/buy).