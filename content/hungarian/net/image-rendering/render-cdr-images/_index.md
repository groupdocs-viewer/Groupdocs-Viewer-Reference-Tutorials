---
title: Rendereljen CDR képeket
linktitle: Rendereljen CDR képeket
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet CDR-képeket renderelni HTML, JPG, PNG és PDF formátumba a GroupDocs.Viewer for .NET segítségével. Könnyen konvertálhat CorelDRAW fájlokat ezzel az oktatóanyaggal.
weight: 12
url: /hu/net/image-rendering/render-cdr-images/
---
## Bevezetés
Ebben az oktatóanyagban végigvezetjük a CDR (CorelDRAW) képek GroupDocs.Viewer for .NET segítségével történő előállítási folyamatán. A CDR egy fájlformátum, amely elsősorban a CorelDRAW vektorgrafikus szerkesztőhöz kapcsolódik. A GroupDocs.Viewer segítségével könnyedén konvertálhat CDR fájlokat különféle formátumokba, például HTML, JPG, PNG és PDF formátumokba.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  GroupDocs.Viewer for .NET: Győződjön meg arról, hogy telepítette a GroupDocs.Viewer for .NET programot. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
2. Dokumentumkönyvtár: Készítsen egy könyvtárat, ahová a renderelt képeket menteni szeretné.
3. Alapvető C# ismerete: A kódpéldák megértéséhez a C# programozási nyelv ismerete szükséges.
## Névterek importálása
Mielőtt belevágna a kódpéldákba, importálja a szükséges névtereket a C# fájlba:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Most bontsuk le az egyes példákat több lépésre:
## Renderelés HTML-be
1. Határozza meg a kimeneti könyvtárat, ahová menteni szeretné a renderelt HTML fájlokat:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Adja meg a HTML-fájlok elérési útját:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Használja a Viewer osztályt a CDR-fájl HTML formátumba történő megjelenítéséhez:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderelés JPG formátumban
1. Határozza meg a JPG fájlok fájlútvonal-formátumát:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Használja a Viewer osztályt a CDR fájl JPG formátumban való megjelenítéséhez:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderelés PNG-be
1. Határozza meg a PNG fájlok fájlútvonal-formátumát:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Használja a Viewer osztályt a CDR fájl PNG formátumban való megjelenítéséhez:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderelés PDF-be
1. Határozza meg a PDF fájl elérési út formátumát:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Használja a Viewer osztályt a CDR-fájl PDF-formátumba történő megjelenítéséhez:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Opcionálisan megadhat megjelenítési beállításokat, vagy adott oldalakat renderelhet további paraméterek átadásával`viewer.View()` módszer.
## Következtetés
CDR-képek különféle formátumokba, például HTML-, JPG-, PNG- és PDF-formátumokba való renderelése a GroupDocs.Viewer for .NET használatával egyszerű folyamat. Az ebben az oktatóanyagban ismertetett lépések követésével hatékonyan konvertálhatja a CDR fájlokat különböző formátumokba az igényeinek megfelelően.
## GYIK
### A GroupDocs.Viewer for .NET kompatibilis a CDR-fájlok összes verziójával?
A GroupDocs.Viewer for .NET támogatja a CorelDRAW különböző verziói által létrehozott CDR-fájlok megjelenítését.
### Testreszabhatom a renderelt fájlok kimenetét?
Igen, a GroupDocs.Viewer for .NET különféle lehetőségeket kínál a kimenet testreszabásához, például a képminőség módosítását, a vízjel beállítását stb.
### A GroupDocs.Viewer for .NET-nek szüksége van külső függőségekre?
Nem, a GroupDocs.Viewer for .NET egy önálló könyvtár, és nem igényel semmilyen külső függőséget a dokumentumok megjelenítéséhez.
### Elérhető a GroupDocs.Viewer for .NET próbaverziója?
 Igen, letöltheti a GroupDocs.Viewer .NET-hez ingyenes próbaverzióját a webhelyről[itt](https://releases.groupdocs.com/).
### Hol kaphatok támogatást a GroupDocs.Viewer for .NET-hez?
 Támogatást a GroupDocs.Viewer közösségi fórumtól kaphat[itt](https://forum.groupdocs.com/c/viewer/9).