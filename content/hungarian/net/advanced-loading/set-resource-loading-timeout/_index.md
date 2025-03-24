---
title: Erőforrás betöltési időtúllépés beállítása (speciális)
linktitle: Erőforrás betöltési időtúllépés beállítása (speciális)
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan konfigurálhatja hatékonyan az erőforrás-betöltési időtúllépéseket a GroupDocs.Viewer for .NET alkalmazásban. Mesterdokumentum renderelés precízen és stabilan.
weight: 13
url: /hu/net/advanced-loading/set-resource-loading-timeout/
---
## Bevezetés
.NET fejlesztés területén a GroupDocs.Viewer hatékony eszközkészletet biztosít a dokumentumok és képek precíz és hatékony megjelenítéséhez. Képességeinek kiaknázásához meg kell érteni annak bonyolultságát, beleértve az erőforrás-betöltési időtúllépések beállítását. Ebben az oktatóanyagban az erőforrás-betöltési időtúllépések konfigurálásának folyamatát mutatjuk be a GroupDocs.Viewer for .NET-ben.
## Előfeltételek
Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Alapvető ismeretek a .NET fejlesztésről: A C# programozás és a .NET keretrendszer alapjainak ismerete elengedhetetlen.
2.  A GroupDocs.Viewer for .NET telepítése: Töltse le és telepítse a GroupDocs.Viewer for .NET könyvtárból[letöltési oldal](https://releases.groupdocs.com/viewer/net/).
3. Integrált fejlesztői környezet (IDE): A rendszeren telepítve legyen egy IDE, például a Visual Studio.

## Névterek importálása
Mielőtt belevágna a kódolási folyamatba, importálja a szükséges névtereket:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Határozza meg a kimeneti könyvtárat
Először is, határozza meg a könyvtárat, ahová a renderelt dokumentumok mentésre kerülnek:
```csharp
string outputDirectory = "Your Document Directory";
```
 Cserélje ki`"Your Document Directory"`azzal az elérési úttal, ahová a renderelt dokumentumokat menteni szeretné.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
Határozza meg az egyes oldalak fájlútvonalainak formátumát:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Ez a formátum olyan fájlneveket generál, mint a`page_1.html`, `page_2.html`stb., a megadott kimeneti könyvtárban.
## 3. lépés: Konfigurálja a betöltési beállításokat
Konfigurálja a betöltési beállításokat, beleértve az erőforrásbetöltési időtúllépést is:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Ebben a példában 5 másodperces időtúllépés van beállítva az erőforrások betöltéséhez.
## 4. lépés: Inicializálja a Viewer Object-et
 Inicializálja a`Viewer` objektum a megjelenítendő dokumentummal és a meghatározott betöltési beállításokkal:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Cserélje ki`TestFiles.WITH_EXTERNAL_IMAGE_DOC` a megjeleníteni kívánt dokumentum elérési útjával.
## 5. lépés: Konfigurálja a HTML nézet beállításait
A beágyazott erőforrások HTML-nézeti beállításainak konfigurálása:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Ez a konfiguráció biztosítja, hogy a beágyazott erőforrások, például a képek szerepeljenek a renderelt HTML-ben.
## 6. lépés: Renderelje le a dokumentumot
Renderelje le a dokumentumot a konfigurált beállításokkal:
```csharp
viewer.View(options);
```
Ez a lépés elindítja a renderelési folyamatot.
## 7. lépés: Jelenítse meg a kimeneti könyvtárat
Jelenítsen meg egy üzenetet, amely jelzi a sikeres megjelenítést és a kimeneti könyvtár helyét:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Az erőforrás-betöltési időtúllépések elsajátítása a GroupDocs.Viewer for .NET-ben kulcsfontosságú a zökkenőmentes dokumentum-megjelenítési folyamatok biztosításához. Ennek az oktatóanyagnak a követésével betekintést nyerhetett az időtúllépések hatékony konfigurálásába, és ezzel fejlesztheti jártasságát a .NET-fejlesztésben.
## GYIK
### Mi a jelentősége az erőforrás-betöltési időtúllépések beállításának?
Az erőforrás-betöltési időtúllépések beállítása biztosítja, hogy a renderelési folyamatok ne akadjanak le a végtelenségig, ami javítja az alkalmazás stabilitását.
### Testreszabhatók az erőforrás-betöltési időtúllépések a dokumentumtípusok alapján?
Igen, az erőforrás-betöltési időtúllépések beállíthatók a megjelenítendő dokumentumok összetettsége és mérete alapján.
### Van-e teljesítménykövetkezménye a rövidebb időkorlátok beállításának?
A rövidebb időkorlátok az összetett dokumentumok hiányos megjelenítéséhez vezethetnek, ha az erőforrások nem tölthetők be a megadott időtartamon belül.
### Alkalmas-e a GroupDocs.Viewer különféle dokumentumformátumok renderelésére?
Igen, a GroupDocs.Viewer támogatja a dokumentumformátumok széles skálájának renderelését, beleértve a PDF, DOCX, XLSX stb.
### Letilthatók az erőforrás-betöltési időtúllépések?
Bár nem ajánlott, az erőforrás-betöltési időtúllépések nagy értékre állíthatók, vagy teljesen letilthatók az adott követelményektől függően.