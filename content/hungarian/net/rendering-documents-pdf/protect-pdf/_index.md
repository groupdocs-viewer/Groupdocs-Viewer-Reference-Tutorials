---
title: A renderelt PDF védelme jelszóval
linktitle: A renderelt PDF védelme jelszóval
second_title: GroupDocs.Viewer .NET API
description: A Groupdocs.Viewer for .NET segítségével egyszerűen jelszavakkal védheti renderelt PDF-fájljait. Tartsa biztonságban és bizalmasan dokumentumait.
weight: 12
url: /hu/net/rendering-documents-pdf/protect-pdf/
---
## Bevezetés
Ebből az oktatóanyagból megtudhatja, hogyan használhatja a Groupdocs.Viewer for .NET alkalmazást a renderelt PDF jelszóval történő védelmére. Biztonsági intézkedések hozzáadásával szabályozhatja a PDF-dokumentumokhoz való hozzáférést, biztosítva a bizalmasságot és az integritást.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Groupdocs.Viewer for .NET Library: Töltse le és telepítse a könyvtárat a[weboldal](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztési környezet: Győződjön meg arról, hogy működő fejlesztői környezet van beállítva a .NET fejlesztéshez.

## Névterek importálása
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Határozza meg a kimeneti könyvtárat és a fájl elérési útját
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 2. lépés: Inicializálja a Viewer Object-et és állítsa be a biztonsági beállításokat
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## 3. lépés: Állítsa be a PDF nézet beállításait
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## 4. lépés: Dokumentum renderelése biztonsági beállításokkal
```csharp
    viewer.View(options);
}
```
## 5. lépés: Ellenőrizze a renderelt dokumentumot
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ha követi ezeket a lépéseket, jelszóval védheti meg a renderelt PDF fájlt a Groupdocs.Viewer for .NET segítségével. Ez biztosítja, hogy dokumentumai biztonságban maradjanak, és csak az arra jogosult felhasználók számára férhessenek hozzá.

## Következtetés
A PDF-dokumentumok biztonságossá tétele elengedhetetlen a titkosság és az integritás megőrzéséhez. A Groupdocs.Viewer for .NET segítségével könnyedén megvédheti a renderelt PDF-fájlokat jelszavakkal, így szabályozva a bizalmas információkhoz való hozzáférést.

## GYIK
### Megvédhetem a PDF-fájlokat különböző szintű engedélyekkel?
Igen, megadhat különböző engedélyeket a megtekintéshez, nyomtatáshoz, másoláshoz és egyebekhez, miközben jelszóval védi a PDF-fájlokat.
### A Groupdocs.Viewer kompatibilis a különböző fájlformátumokkal?
Teljesen! A Groupdocs.Viewer a fájlformátumok széles skálájának megjelenítését támogatja, beleértve a DOCX, XLSX, PPTX, PDF stb.
### Integrálhatom a Groupdocs.Viewert a meglévő .NET-alkalmazásomba?
Biztosan! A Groupdocs.Viewer API-kat biztosít a .NET-alkalmazásokba való zökkenőmentes integrációhoz, robusztus dokumentummegtekintési lehetőségeket kínálva.
### A Groupdocs.Viewer támogatja a felhőalapú tárolási szolgáltatásokat?
Igen, a Groupdocs.Viewer támogatja az olyan népszerű felhőalapú tárolási szolgáltatásokkal való integrációt, mint a Dropbox, a Google Drive és az Amazon S3, lehetővé téve a felhőben tárolt dokumentumok megjelenítését.
### Elérhető a Groupdocs.Viewer próbaverziója?
 Igen, elkezdheti a Groupdocs.Viewer alkalmazást, ha eléri az ingyenes próbaverziót a webhelyről[weboldal](https://releases.groupdocs.com/).