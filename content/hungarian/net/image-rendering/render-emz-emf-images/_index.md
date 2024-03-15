---
title: Rendereljen EMZ és EMF képeket
linktitle: Rendereljen EMZ és EMF képeket
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet EMZ- és EMF-képeket különböző formátumokba renderelni a GroupDocs.Viewer for .NET segítségével. Könnyen követhető oktatóanyag fejlesztőknek.
type: docs
weight: 14
url: /hu/net/image-rendering/render-emz-emf-images/
---
## Bevezetés

GroupDocs.Viewer for .NET egy hatékony dokumentum-megjelenítő API, amely lehetővé teszi a fejlesztők számára, hogy különféle dokumentumtípusokat jelenítsenek meg, beleértve az EMZ (Enhanced Windows Metafile) és az EMF (Enhanced Metafile) képeket .NET-alkalmazásaikban. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet EMZ- és EMF-képeket különböző formátumokba, például HTML-, JPG-, PNG- és PDF-formátumba renderelni a GroupDocs.Viewer for .NET segítségével.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1.  GroupDocs.Viewer for .NET: Letöltheti a könyvtárat innen[itt](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztői környezet: Győződjön meg arról, hogy kompatibilis fejlesztői környezettel rendelkezik a .NET fejlesztéshez.
3. Minta EMZ/EMF képek: Legyen elérhető minta EMZ és EMF képek a megjelenítéshez.

## Névterek importálása

Mielőtt belemerülnénk a kódba, importáljuk a szükséges névtereket:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Most bontsuk le az egyes példákat több lépésre, lépésről lépésre útmutató formátumban:

## EMZ/EMF képek renderelése HTML-be

### 1. lépés: Állítsa be a kimeneti könyvtárat:
```csharp
string outputDirectory = "Your Document Directory";
```
 Cserélje ki`"Your Document Directory"`azzal az elérési úttal, ahová a renderelt HTML-fájlt menteni szeretné.

### 2. lépés: Az oldalfájl elérési út formátumának meghatározása:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Ez meghatározza a megjelenített HTML-fájl elérési útját.

### 3. lépés: Renderelés HTML formátumban:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Ez a kód inicializálja a`Viewer` objektumot a minta EMZ képpel, és a megadott beállításokkal HTML formátumba rendereli.

## EMZ/EMF képek renderelése JPG, PNG és PDF formátumban

Ismételje meg a következő lépéseket a JPG, PNG és PDF formátumú megjelenítéshez:

### 1. lépés: Az oldalfájl elérési út formátumának meghatározása:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Állítsa be a fájl nevét és kiterjesztését a kívánt kimeneti formátumnak megfelelően (`jpg`, `png` , vagy`pdf`).

### 2. lépés: Renderelés megfelelő formátumba:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Állítsa be a beállításokat a kimeneti formátumnak megfelelően (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Cserélje ki`JpgViewOptions` val vel`PngViewOptions` vagy`PdfViewOptions` a kívánt kimeneti formátum alapján.

## Következtetés

Összefoglalva, a GroupDocs.Viewer for .NET zökkenőmentes megoldást kínál az EMZ- és EMF-képek különféle formátumokba való renderelésére .NET-alkalmazásokban. Az oktatóanyagban ismertetett lépések követésével a fejlesztők könnyedén integrálhatják alkalmazásaikba a dokumentum-megjelenítési képességeket.

## GYIK

### K: A GroupDocs.Viewer az EMZ és az EMF képeken kívül más dokumentumformátumokat is megjeleníthet?
V: Igen, a GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF, DOCX, PPTX, XLSX és egyebeket.

### K: Elérhető ingyenes próbaverzió a GroupDocs.Viewer for .NET számára?
 V: Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.groupdocs.com/).

### K: A GroupDocs.Viewer kínál támogatást a fejlesztőknek?
 V: Igen, a GroupDocs támogatást nyújt rajta keresztül[fórum](https://forum.groupdocs.com/c/viewer/9) ahol a fejlesztők kérdéseket tehetnek fel és segítséget kérhetnek.

### K: Vásárolhatok ideiglenes licencet a GroupDocs.Viewer for .NET számára?
 V: Igen, ideiglenes licencek megvásárolhatók[itt](https://purchase.groupdocs.com/temporary-license/).

### K: Hol találom a GroupDocs.Viewer for .NET részletes dokumentációját?
 V: Tekintse meg a dokumentációt[itt](https://reference.groupdocs.com/viewer/net/)átfogó útmutatásért az API használatához.