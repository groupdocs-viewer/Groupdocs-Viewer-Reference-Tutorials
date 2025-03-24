---
title: Szövegfájlok renderelése (.txt)
linktitle: Szövegfájlok renderelése (.txt)
second_title: GroupDocs.Viewer .NET API
description: Fedezze fel a szövegfájlok zökkenőmentes konvertálását többféle formátumba a GroupDocs.Viewer for .NET segítségével. Fokozatmentesen fokozza dokumentumkezelési képességeit.
weight: 10
url: /hu/net/rendering-text-files/render-txt/
---
## Bevezetés
dokumentumkezelés és -manipuláció területén a GroupDocs.Viewer for .NET hatékony eszközként jelenik meg, amely számos funkciót kínál a különféle dokumentumformátumok hatékony megjelenítéséhez. Ez a cikk a GroupDocs.Viewer for .NET alkalmazásának bonyolultságával foglalkozik a szövegfájlok (.txt) többféle formátumban történő megjelenítéséhez. Függetlenül attól, hogy a szöveges fájlokat HTML, JPG, PNG vagy PDF formátumba szeretné konvertálni, a GroupDocs.Viewer felvértezi a szükséges eszközökkel, hogy zökkenőmentesen elvégezhesse ezeket a feladatokat.
## Előfeltételek
Mielőtt belevágna az átalakítási folyamatba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
### 1. A GroupDocs.Viewer telepítése .NET-hez
 Győződjön meg arról, hogy a GroupDocs.Viewer for .NET telepítve van a fejlesztői környezetében. A szükséges fájlokat letöltheti a[weboldal](https://releases.groupdocs.com/viewer/net/).
### 2. A .NET-keretrendszer alapszintű ismerete
Ismerkedjen meg a .NET-keretrendszer alapjaival, beleértve a projektek beállítását és a programkönyvtárak használatát a kódbázison belül.
### 3. Minta szöveges fájlok
Készítsen minta szöveges fájlokat (.txt), amelyeket konvertálni kíván. Ezek a fájlok szolgálnak majd bemenetként az átalakítási folyamathoz.

## Névterek importálása
Mielőtt belevágna az átalakítási folyamatba, feltétlenül importálja a szükséges névtereket a projektbe. Ez lehetővé teszi a GroupDocs.Viewer for .NET által biztosított funkciók zökkenőmentes elérését.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Bontsuk le az egyes példákat több lépésre, hogy hatékonyan végigvezethessük a konverziós folyamaton:

## 1. lépés: Határozza meg a HTML kimeneti útvonalat
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
Adja meg a HTML kimeneti fájl teljes elérési útját.
## 2. lépés: Szövegfájlok megjelenítése többoldalas HTML-formátumban
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 Példányosítás a`Viewer` objektum a szövegfájl elérési útjával. Beállítás`HtmlViewOptions` beágyazott erőforrásokhoz, és a szöveges fájlt többoldalas HTML-formátumban jelenítse meg.
## 3. lépés: Határozza meg az egyoldalas HTML kimeneti útvonalat
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Adja meg az egyoldalas HTML kimeneti fájl teljes elérési útját.
## 4. lépés: Rendelje meg a szöveges fájlokat egyoldalas HTML-formátumban
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 Példányosítás a`Viewer` objektum a szövegfájl elérési útjával. Beállítás`HtmlViewOptions` beágyazott erőforrásokhoz és készlethez`RenderToSinglePage` igaznak. Renderje le a szövegfájlt egyoldalas HTML-formátumban.
## 5. lépés: Határozza meg a JPG kimeneti útvonalat
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
Adja meg a JPG kimeneti fájl teljes elérési útját.
## 6. lépés: Rendelje meg a szöveges fájlokat JPG formátumban
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Példányosítás a`Viewer` objektum a szövegfájl elérési útjával. Beállítás`JpgViewOptions` a kimeneti útvonalhoz, és renderelje a szövegfájlt JPG formátumba.
## 7. lépés: Határozza meg a PNG kimeneti útvonalat
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
Adja meg a PNG kimeneti fájl teljes elérési útját.
## 8. lépés: Rendelje meg a szöveges fájlokat PNG formátumban
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Példányosítás a`Viewer` objektum a szövegfájl elérési útjával. Beállítás`PngViewOptions` a kimeneti elérési úthoz, és rendereli a szövegfájlt PNG formátumba.
## 9. lépés: Határozza meg a PDF kimeneti útvonalat
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Adja meg a PDF kimeneti fájl teljes elérési útját.
## 10. lépés: Rendelje meg a szöveges fájlokat PDF-be
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Példányosítás a`Viewer` objektum a szövegfájl elérési útjával. Beállítás`PdfViewOptions` a kimeneti útvonalhoz, és renderelje le a szöveges fájlt PDF formátumba.

## Következtetés
Összefoglalva, a GroupDocs.Viewer for .NET lehetővé teszi a fejlesztők számára, hogy könnyedén rendereljenek szöveges fájlokat különféle formátumokba, beleértve a HTML, JPG, PNG és PDF formátumokat. Az ebben a cikkben felvázolt útmutató lépésenkénti követésével zökkenőmentesen integrálhatja a GroupDocs.Viewert .NET-alkalmazásaiba, javítva ezzel a dokumentumkezelési képességeket.
## GYIK
### K: A GroupDocs.Viewer for .NET kompatibilis a .NET keretrendszer összes verziójával?
Igen, a GroupDocs.Viewer for .NET úgy lett kialakítva, hogy kompatibilis legyen a .NET-keretrendszer-verziók széles skálájával, biztosítva a fejlesztés sokoldalúságát és rugalmasságát.
### K: Testreszabhatom a renderelt dokumentumok kimeneti megjelenését?
Teljesen! A GroupDocs.Viewer kiterjedt testreszabási lehetőségeket kínál, lehetővé téve a fejlesztők számára, hogy preferenciáik és követelményeik szerint testreszabják a renderelt dokumentumok megjelenését.
### K: Elérhető a GroupDocs.Viewer for .NET próbaverziója?
 Igen, felfedezheti a GroupDocs.Viewer for .NET funkcióit, ha eléri a webhelyen elérhető ingyenes próbaverziót.[weboldal]( https://releases.groupdocs.com/).
### K: Hogyan szerezhetek támogatást vagy kérhetek segítséget a GroupDocs.Viewer for .NET-hez?
 A GroupDocs.Viewer for .NET-hez kapcsolódó kérdéseivel, támogatásával vagy segítségével keresse fel a dedikált támogatási fórumot, amely elérhető.[itt](https://forum.groupdocs.com/c/viewer/9).
### K: Vásárolhatok ideiglenes licencet a GroupDocs.Viewer for .NET számára?
Igen, ideiglenes licencek megvásárolhatók, amelyek rugalmasságot és kényelmet biztosítanak a felhasználók számára a GroupDocs.Viewer for .NET használatában meghatározott időtartamra.