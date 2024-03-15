---
title: Rendereljen CMX képeket
linktitle: Rendereljen CMX képeket
second_title: GroupDocs.Viewer .NET API
description: Tanulja meg, hogyan lehet könnyedén CMX képeket különböző formátumokba renderelni a GroupDocs.Viewer for .NET segítségével. Javítsa dokumentumkezelését.
type: docs
weight: 13
url: /hu/net/image-rendering/render-cmx-images/
---
## Bevezetés
A dokumentumkezelés és -manipuláció területén a különböző formátumú képek renderelése kulcsfontosságú feladat. A GroupDocs.Viewer for .NET leegyszerűsíti ezt a folyamatot azáltal, hogy átfogó funkciókat biztosít a CMX-képek különböző formátumokba, például HTML, JPG, PNG és PDF formátumokba történő megjelenítéséhez. Ez az oktatóanyag lépésről lépésre végigvezeti Önt a GroupDocs.Viewer for .NET használatával CMX-képek megjelenítésének folyamatán.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1.  GroupDocs.Viewer for .NET Library: Töltse le és telepítse a GroupDocs.Viewer for .NET könyvtárat innen:[itt](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztési környezet: .NET keretrendszerrel kell beállítania működő fejlesztői környezetet.
3. CMX képfájl: Szerezzen be egy CMX képfájlt, amelyet elő szeretne készíteni.

## Névterek importálása
Mielőtt folytatná, importálja a szükséges névtereket a GroupDocs.Viewer funkcióinak eléréséhez .NET-alkalmazásában:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Renderelés HTML-be
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Kimeneti könyvtár meghatározása: Állítsa be azt a könyvtárat, ahol a renderelt HTML fájlokat tárolni szeretné.
- Fájl elérési út formátumának megadása: Határozza meg a kimeneti HTML-fájlok formátumát.
- Viewer objektum példányosítása: Hozzon létre egy példányt a Viewer osztályból a CMX képfájllal.
- HTML-megjelenítési beállítások: Konfigurálja a HTML-megjelenítési beállításokat, például az erőforrások beágyazását.
- CMX renderelése HTML formátumban: Hívja meg a Viewer objektum View metódusát a CMX kép HTML formátumban történő megjelenítéséhez.
## Renderelés JPG formátumban
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Kimeneti könyvtár meghatározása: Állítsa be a renderelt JPG fájlok tárolási könyvtárát.
- Fájl elérési út formátumának megadása: Határozza meg a kimeneti JPG fájlok formátumát.
- Viewer objektum példányosítása: Hozzon létre egy példányt a Viewer osztályból a CMX képfájllal.
- JPG renderelési beállítások: Konfigurálja a JPG renderelési beállításokat.
- CMX renderelése JPG formátumban: A megjelenítő objektum View metódusának meghívása a CMX kép JPG formátumban történő megjelenítéséhez.
## Renderelés PNG-be
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Kimeneti könyvtár meghatározása: Állítsa be a renderelt PNG fájlok tárolási könyvtárát.
- Fájlútvonal-formátum megadása: Határozza meg a kimeneti PNG-fájlok formátumát.
- Viewer objektum példányosítása: Hozzon létre egy példányt a Viewer osztályból a CMX képfájllal.
- PNG renderelési beállítások: Konfigurálja a PNG renderelési beállításokat.
- CMX renderelése PNG formátumban: Hívja meg a Viewer objektum View metódusát a CMX kép PNG formátumban való megjelenítéséhez.
## Renderelés PDF-be
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Kimeneti könyvtár meghatározása: Állítsa be a renderelt PDF fájl tárolási könyvtárát.
- Fájl elérési út formátumának megadása: Határozza meg a kimeneti PDF-fájl formátumát.
- Viewer objektum példányosítása: Hozzon létre egy példányt a Viewer osztályból a CMX képfájllal.
- PDF-megjelenítési beállítások: Konfigurálja a PDF-megjelenítési beállításokat.
- CMX renderelése PDF formátumban: Hívja meg a Viewer objektum View metódusát a CMX kép PDF formátumban történő megjelenítéséhez.

## Következtetés
Összefoglalva, a GroupDocs.Viewer for .NET robusztus megoldást kínál a CMX képek különböző formátumokba való zökkenőmentes megjelenítéséhez. Az oktatóanyagban ismertetett lépések követésével könnyedén integrálhatja a CMX képmegjelenítési képességeket .NET-alkalmazásaiba, javítva ezzel a dokumentumkezelés hatékonyságát.
## GYIK
### Renderelhetek egy CMX-kép adott oldalait?
Igen, adott oldalakat renderelhet, ha megadja az oldalszámot a megjelenítési beállításoknál.
### GroupDocs.Viewer for .NET kompatibilis az összes .NET-keretrendszerrel?
Igen, a GroupDocs.Viewer for .NET több .NET-keretrendszerrel is kompatibilis, beleértve a .NET Core-t és a .NET-keretrendszert.
### A GroupDocs.Viewer támogatja a titkosított CMX-képek megjelenítését?
Igen, a GroupDocs.Viewer támogatja a titkosított CMX-képek megfelelő visszafejtési kulcsokkal történő megjelenítését.
### Testreszabhatom a renderelési beállításokat a különböző kimeneti formátumokhoz?
Természetesen a GroupDocs.Viewer kiterjedt lehetőségeket kínál a megjelenítési paraméterek igényeinek megfelelő testreszabásához.
### Létezik közösségi fórum a GroupDocs.Viewer támogatására?
 Igen, kérhet segítséget, és kapcsolatba léphet a GroupDocs.Viewer közösséggel a támogatási fórumon[itt](https://forum.groupdocs.com/c/viewer/9).