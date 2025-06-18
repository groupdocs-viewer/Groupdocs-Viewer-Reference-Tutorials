---
"description": "Tanuld meg, hogyan renderelhetsz CDR képeket HTML, JPG, PNG és PDF formátumba a GroupDocs.Viewer for .NET segítségével. Ezzel az oktatóanyaggal könnyedén konvertálhatsz CorelDRAW fájlokat."
"linktitle": "CDR képek renderelése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CDR képek renderelése"
"url": "/hu/net/image-rendering/render-cdr-images/"
"weight": 12
---

# CDR képek renderelése

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a CDR (CorelDRAW) képek renderelésének folyamatán a GroupDocs.Viewer for .NET segítségével. A CDR egy fájlformátum, amely elsősorban a CorelDRAW-hoz, egy vektorgrafikus szerkesztőhöz kapcsolódik. A GroupDocs.Viewer segítségével könnyedén konvertálhat CDR fájlokat különböző formátumokba, például HTML, JPG, PNG és PDF formátumba.

![CDR-képek renderelése a GroupDocs.Viewer for .NET segítségével](/viewer/image-rendering/render-cdr-images.png)

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. GroupDocs.Viewer .NET-hez: Győződjön meg róla, hogy telepítette a GroupDocs.Viewer .NET-hez készült alkalmazást. Letöltheti innen: [itt](https://releases.groupdocs.com/viewer/net/).
2. Dokumentumkönyvtár: Készítsen elő egy könyvtárat, ahová a renderelt képeket menteni szeretné.
3. C# alapismeretek: A C# programozási nyelv ismerete szükséges a kódpéldák megértéséhez.
## Névterek importálása
Mielőtt belemerülnénk a kódpéldákba, importáljuk a szükséges névtereket a C# fájlunkba:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Most bontsuk le az egyes példákat több lépésre:
## HTML-re renderelés
1. Adja meg a kimeneti könyvtárat, ahová a renderelt HTML fájlokat menteni szeretné:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Adja meg a HTML fájlok elérési útjának formátumát:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. A Viewer osztály használatával rendereld a CDR fájlt HTML formátumba:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## JPG formátumú renderelés
1. JPG fájlok fájlútvonal-formátumának meghatározása:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. A Viewer osztály használatával rendereld a CDR fájlt JPG formátumba:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PNG formátumú renderelés
1. A PNG fájlok elérési útjának formátumának meghatározása:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. A Viewer osztály használatával rendereld a CDR fájlt PNG formátumba:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PDF-be renderelés
1. Adja meg a PDF fájlelérési útvonal formátumát:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. A Viewer osztály használatával rendereld PDF formátumba a CDR fájlt:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Opcionálisan megadhatja a megjelenítési beállításokat, vagy további paraméterek átadásával megjeleníthet adott oldalakat a `viewer.View()` módszer.
## Következtetés
A CDR-képek különböző formátumokba, például HTML, JPG, PNG és PDF formátumba történő renderelése a GroupDocs.Viewer for .NET segítségével egy egyszerű folyamat. Az ebben az oktatóanyagban ismertetett lépéseket követve hatékonyan konvertálhatja a CDR-fájlokat különböző formátumokba az igényeinek megfelelően.
## GYIK
### GroupDocs.Viewer for .NET kompatibilis a CDR fájlok összes verziójával?
A GroupDocs.Viewer for .NET támogatja a CorelDRAW különböző verzióival létrehozott CDR-fájlok renderelését.
### Testreszabhatom a renderelt fájlok kimenetét?
Igen, a GroupDocs.Viewer for .NET számos lehetőséget kínál a kimenet testreszabására, például a képminőség módosítását, vízjel beállítását stb.
### A GroupDocs.Viewer for .NET igényel külső függőségeket?
Nem, a GroupDocs.Viewer for .NET egy önálló függvénytár, és nem igényel külső függőségeket a dokumentumok rendereléséhez.
### Van elérhető próbaverzió a GroupDocs.Viewer for .NET-hez?
Igen, letöltheti a GroupDocs.Viewer for .NET ingyenes próbaverzióját innen: [itt](https://releases.groupdocs.com/).
### Hol kaphatok támogatást a GroupDocs.Viewer for .NET-hez?
Támogatást kaphatsz a GroupDocs.Viewer közösségi fórumon. [itt](https://forum.groupdocs.com/c/viewer/9).