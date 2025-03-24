---
title: Rendereljen CHM fájlokat
linktitle: Rendereljen CHM fájlokat
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet CHM-fájlokat előállítani .NET-ben a GroupDocs.Viewer segítségével. Konvertálja a CHM-et HTML, JPG, PNG és PDF formátumokba könnyedén.
weight: 10
url: /hu/net/rendering-web-documents/render-chm/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet CHM (összeállított HTML-súgó) fájlokat előállítani a GroupDocs.Viewer for .NET segítségével. A GroupDocs.Viewer for .NET egy hatékony dokumentum-megjelenítő API, amely lehetővé teszi a fejlesztők számára, hogy több mint 170 dokumentumtípust jelenítsenek meg .NET-alkalmazásaikon belül külső szoftver telepítése nélkül.

## Előfeltételek

Mielőtt belevágnánk a CHM-fájlok megjelenítésébe, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

### A GroupDocs.Viewer for .NET telepítése

 A kezdéshez telepítenie kell a GroupDocs.Viewer for .NET programot. A könyvtár letölthető a[GroupDocs webhely](https://releases.groupdocs.com/viewer/net/) vagy telepítse a NuGet Package Manageren keresztül a következő parancs futtatásával a Package Manager konzolon:

```bash
Install-Package GroupDocs.Viewer
```

## Névterek importálása

Ügyeljen arra, hogy a szükséges névtereket importálja a projektbe:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most bontsuk le a megjelenítési folyamatot több lépésre:

## 1. lépés: Határozza meg a kimeneti könyvtárat

Határozza meg azt a könyvtárat, ahová a renderelt fájlokat menteni szeretné:

```csharp
string outputDirectory = "Your Document Directory";
```

## 2. lépés: Rendereljen HTML-be

A CHM fájlok HTML formátumban történő megjelenítéséhez használja a következő kódrészletet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Állítsa igazra az összes CHM-tartalom egyetlen oldallá konvertálásához

    viewer.View(options); //Konvertálja az összes oldalt
}
```

## 3. lépés: Renderelje le JPG formátumban

A CHM-fájlok JPG-képekké alakításához használja a következő kódrészletet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Csak az 1., 2., 3. oldalt konvertálja
}
```

## 4. lépés: Renderelje le PNG formátumban

A CHM-fájlok PNG-képekké alakításához használja a következő kódrészletet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Csak az 1., 2., 3. oldalt konvertálja
}
```

## 5. lépés: Rendelje le PDF-be

A CHM-fájlok PDF-dokumentummá alakításához használja a következő kódrészletet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Konvertálja az összes oldalt
}
```

## 6. lépés: Ellenőrizze a kimenetet

Ha a renderelési folyamat befejeződött, ellenőrizze a megjelenített fájlok megadott kimeneti könyvtárát:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés

A CHM-fájlok előállítása a GroupDocs.Viewer for .NET használatával egyszerű folyamat. Az oktatóanyagban ismertetett lépések követésével hatékonyan konvertálhatja a CHM-dokumentumokat különféle formátumokba, például HTML-be, képekbe (JPG, PNG) és PDF-be a .NET-alkalmazásokon belül.

## GYIK

### 1. kérdés: A GroupDocs.Viewer a CHM-en kívül más dokumentumformátumokat is megjeleníthet?

1. válasz: Igen, a GroupDocs.Viewer több mint 170 dokumentumformátum megjelenítését támogatja, beleértve a PDF, DOCX, XLSX, PPTX stb.

### 2. kérdés: A GroupDocs.Viewer kompatibilis a .NET Core programmal?

2. válasz: Igen, a GroupDocs.Viewer támogatja a .NET Core-t a hagyományos .NET-keretrendszer mellett.

### 3. kérdés: Testreszabhatom a renderelési beállításokat a különböző kimeneti formátumokhoz?

3. válasz: Igen, a GroupDocs.Viewer különféle lehetőségeket kínál a megjelenítési folyamat testreszabásához, például oldalszámok megadásához, képminőség beállításához és kimeneti útvonalak konfigurálásához.

### 4. kérdés: A GroupDocs.Viewernek szüksége van külső függőségekre a dokumentumok megjelenítéséhez?

4. válasz: Nem, a GroupDocs.Viewer egy önálló könyvtár, és nem igényel külső függőséget vagy harmadik féltől származó szoftverek telepítését.

### 5. kérdés: Van ingyenes próbaverzió a GroupDocs.Viewer számára?

 5. válasz: Igen, igénybe veheti a GroupDocs.Viewer ingyenes próbaverzióját, ha felkeresi a[weboldal](https://releases.groupdocs.com/).