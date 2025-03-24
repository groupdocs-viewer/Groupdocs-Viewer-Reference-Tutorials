---
title: Betűtípus-licenc-ellenőrzés letiltása PDF-ben
linktitle: Betűtípus-licenc-ellenőrzés letiltása PDF-ben
second_title: GroupDocs.Viewer .NET API
description: A GroupDocs.Viewer for .NET segítségével zökkenőmentes dokumentummegtekintési lehetőségeket nyithat meg .NET-ben. Könnyen integrálhatja és testreszabhatja a dokumentumok megjelenítését minimális függőséggel.
weight: 12
url: /hu/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## Bevezetés
A .NET fejlesztés területén a dokumentumok kezelése és manipulálása gyakran számos alkalmazás kulcsfontosságú eleme. Legyen szó PDF-fájlok, Word-dokumentumok vagy más fájltípusok megtekintéséről, elengedhetetlen, hogy hatékony eszközökkel rendelkezzenek ezeknek a feladatoknak a hatékony kezeléséhez. Itt jön képbe a GroupDocs.Viewer for .NET. Ez a hatékony könyvtár lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen integrálják a dokumentummegtekintési funkciókat .NET-alkalmazásaikba.
## Előfeltételek
Mielőtt belevágna a GroupDocs.Viewer for .NET használatába, meg kell felelnie néhány előfeltételnek:
### 1. Telepítse a Visual Studio programot
Mindenekelőtt győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren. Letöltheti a Microsoft webhelyéről, ha még nem tette meg.
### 2. Töltse le a GroupDocs.Viewer programot .NET-hez
 Irány a[letöltési link](https://releases.groupdocs.com/viewer/net/) hogy megszerezze a GroupDocs.Viewer .NET legújabb verzióját. Kövesse a mellékelt telepítési utasításokat a fejlesztői környezetben történő beállításához.
### 3. Szerezzen ideiglenes engedélyt
 A GroupDocs.Viewer for .NET-ben rejlő teljes potenciál kiaknázásához a fejlesztés és a tesztelés során javasolt ideiglenes licenc beszerzése. Kérhetsz egyet innen[itt](https://purchase.groupdocs.com/temporary-license/).

## Névterek importálása
Miután teljesítette az előfeltételeket, készen áll a GroupDocs.Viewer for .NET használatára projektjeiben. Kezdje a szükséges névterek importálásával a kódbázisba.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bontsuk fel a megadott példát több lépésre a jobb megértés érdekében:
## 1. lépés: Határozza meg a kimeneti könyvtárat
Kezdje azzal, hogy meghatározza azt a könyvtárat, ahol a megjelenített dokumentumoldalakat tárolni szeretné.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
Állítsa be a dokumentum egyes oldalai fájlútvonalainak formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## 3. lépés: Inicializálja a Viewer Object-et
Hozzon létre egy példányt a Viewer osztályból, átadva a megtekinteni kívánt dokumentum elérési útját.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## 4. lépés: Konfigurálja a HTML nézet beállításait
Határozza meg a dokumentum HTML formátumban való megjelenítésének beállításait, és adja meg a beágyazott erőforrások (pl. képek) formátumát.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5. lépés: Tiltsa le a betűtípuslicenc-ellenőrzést
Engedélyezze a betűtípus-licenc-ellenőrzések letiltását a zökkenőmentes megjelenítés érdekében.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## 6. lépés: Dokumentum megtekintése
Hívja meg a Viewer objektum View metódusát, átadva a beállított opciókat.
```csharp
viewer.View(options);
```
## 7. lépés: Jelenítse meg a kimeneti könyvtárat
Tájékoztassa a felhasználót a megjelenített dokumentumoldalak tárolási helyéről.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
GroupDocs.Viewer for .NET átfogó megoldást kínál a fejlesztőknek a dokumentummegtekintési képességek .NET-alkalmazásaikba való erőfeszítés nélküli integrálására. Az oktatóanyagban ismertetett lépések követésével hatékonyan használhatja ezt a hatékony könyvtárat a dokumentumkezelési munkafolyamatok javítására.
## GYIK
### A GroupDocs.Viewer for .NET kezelhet több dokumentumformátumot?
Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF, Microsoft Word, Excel, PowerPoint és egyebeket.
### A GroupDocs.Viewer for .NET alkalmas webes alkalmazásokhoz?
Természetesen a GroupDocs.Viewer zökkenőmentesen integrálható mind az asztali, mind a webes alkalmazásokba, amelyeket .NET technológiákkal fejlesztettek ki.
### A GroupDocs.Viewernek szüksége van további függőségekre?
Nem, a GroupDocs.Viewer for .NET minimális függőséggel rendelkezik, és könnyen integrálható meglévő projektjeibe.
### Testreszabhatom a renderelt dokumentumok megjelenését?
Igen, a GroupDocs.Viewer különféle lehetőségeket kínál a renderelt dokumentumok megjelenésének és viselkedésének testreszabására, hogy megfeleljen az Ön egyedi igényeinek.
### Elérhető technikai támogatás a GroupDocs.Viewer for .NET számára?
 Igen, segítséget és útmutatást kérhet a dedikált ügyfélszolgálati csapattól a következőn keresztül[fórum](https://forum.groupdocs.com/c/viewer/9).