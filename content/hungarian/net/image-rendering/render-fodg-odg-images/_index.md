---
title: Rendereljen FODG és ODG képeket
linktitle: Rendereljen FODG és ODG képeket
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet FODG és ODG képeket HTML, JPG, PNG és PDF formátumba renderelni a GroupDocs.Viewer for .NET segítségével. Javítsa a dokumentumkezelést.
weight: 15
url: /hu/net/image-rendering/render-fodg-odg-images/
---
## Bevezetés
A szoftverfejlesztés világában a dokumentumformátumok hatékony kezelése a legfontosabb. A GroupDocs.Viewer for .NET egy hatékony eszköz, amelyet arra terveztek, hogy leegyszerűsítse a FODG- és ODG-képek .NET-alkalmazásokon belüli megjelenítési folyamatát. Ez az oktatóanyag végigvezeti azokon a lépéseken, amelyek szükségesek ahhoz, hogy ezeket a képeket különféle formátumokba, például HTML, JPG, PNG és PDF formátumba renderelje a GroupDocs.Viewer for .NET használatával.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  GroupDocs.Viewer for .NET: Töltse le és telepítse a GroupDocs.Viewer for .NET programot innen[itt](https://releases.groupdocs.com/viewer/net/).
2. .NET-keretrendszer: Győződjön meg arról, hogy a .NET-keretrendszer telepítve van a rendszeren.
3. C# alapismeretek: A C# programozási nyelv ismerete hasznos lesz.

## Névterek importálása
A megvalósítás megkezdése előtt importálja a szükséges névtereket:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. lépés: Állítsa be a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
 Cserélje ki`"Your Document Directory"` könyvtár elérési útjával, ahová a renderelt képeket menteni szeretné.
## 2. lépés: Rendereljen HTML-be
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Ez a lépés a FODG képet HTML formátumba teszi.
## 3. lépés: Renderelje le JPG formátumban
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Itt a FODG kép JPG formátumban jelenik meg.
## 4. lépés: Renderelje le PNG formátumban
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Ez a lépés a FODG képet PNG formátumba konvertálja.
## 5. lépés: Rendelje le PDF-be
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Végül a FODG kép PDF formátumba kerül.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan lehet FODG és ODG képeket különböző formátumokba renderelni a GroupDocs.Viewer for .NET segítségével. Az alábbi lépések követésével zökkenőmentesen integrálhatja a dokumentum-megjelenítési képességeket .NET-alkalmazásaiba.
## GYIK
### A GroupDocs.Viewer for .NET kompatibilis a .NET-keretrendszer összes verziójával?
A GroupDocs.Viewer for .NET kompatibilis a .NET-keretrendszer számos verziójával, beleértve a legújabbakat is.
### Renderelhetek dokumentumokat aszinkron módon a GroupDocs.Viewer for .NET segítségével?
Igen, a GroupDocs.Viewer for .NET aszinkron megjelenítési képességeket biztosít a jobb teljesítmény érdekében.
### A GroupDocs.Viewer for .NET támogatja a titkosított dokumentumok megjelenítését?
Igen, a GroupDocs.Viewer for .NET támogatja a titkosított dokumentumok megfelelő visszafejtési kulcsokkal történő megjelenítését.
### Testreszabható a renderelési kimenet a GroupDocs.Viewer for .NET segítségével?
Természetesen a GroupDocs.Viewer for .NET különféle testreszabási lehetőségeket kínál a megjelenítési kimenet igényeinek megfelelő személyre szabásához.
### Renderelhetek dokumentumokat távoli tárolóhelyekről a GroupDocs.Viewer for .NET segítségével?
Igen, a GroupDocs.Viewer for .NET támogatja a dokumentumok megjelenítését helyi és távoli tárolóhelyekről egyaránt.