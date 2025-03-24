---
title: Jegyzetek renderelése és időegységek beállítása (MS Project)
linktitle: Jegyzetek renderelése és időegységek beállítása (MS Project)
second_title: GroupDocs.Viewer .NET API
description: Az MS Project dokumentumok elsajátítása a GroupDocs.Viewer for .NET segítségével. Rendereljen jegyzeteket, állítsa be az időegységeket és fedezze fel a különféle kimeneti formátumokat könnyedén.
weight: 11
url: /hu/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony dokumentum-megjelenítő API, amely lehetővé teszi a fejlesztők számára, hogy megtekintsenek és kezeljenek különféle dokumentumformátumokat .NET-alkalmazásaikon belül. Ebben az oktatóanyagban a megjegyzések renderelésére és az időegységek beállítására összpontosítunk kifejezetten az MS Project dokumentumokhoz.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. GroupDocs.Viewer for .NET: Győződjön meg arról, hogy letöltötte és telepítette a GroupDocs.Viewer for .NET könyvtárat. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztési környezet: Állítsa be kedvenc fejlesztői környezetét .NET támogatással.
3. MS Project Document: Készítsen egy minta MS Project dokumentumot tesztelésre.
## Névterek importálása
Először is importáljuk a szükséges névtereket az MS Project dokumentumok renderelésének megkezdéséhez:
## 1. lépés: Névterek importálása
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Most, hogy importáltuk a szükséges névtereket, bontsuk le az egyes példákat több lépésre az átfogó megértés érdekében.
## Az MS Project Document renderelése HTML-be
Ha egy MS Project dokumentumot megjegyzésekkel együtt szeretne HTML formátumba renderelni, kövesse az alábbi lépéseket:
### 2. lépés: Állítsa be a kimeneti könyvtárat és a fájlformátumot
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 3. lépés: Inicializálja a Viewer Object-et és állítsa be az opciókat
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### 4. lépés: Rendelje meg a dokumentumot HTML formátumban
```csharp
viewer.View(options);
```
## MS Project Document renderelése képformátumokba
Az MS Project dokumentumokat JPG és PNG képformátumokba is renderelheti. Itt van, hogyan:
### 5. lépés: Állítsa be a kimeneti könyvtárat és a fájlformátumot a JPG számára
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### 6. lépés: Inicializálja a Viewer Object-et és állítsa be a JPG-beállításokat
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 7. lépés: Rendelje meg a dokumentumot JPG formátumban
```csharp
viewer.View(options);
```
Ismételje meg a hasonló lépéseket a PNG és más képformátumok megjelenítéséhez.
## MS Project Document renderelése PDF-be
Ha egy MS Project dokumentumot PDF formátumba szeretne renderelni, kövesse az alábbi lépéseket:
### 8. lépés: Állítsa be a PDF kimeneti könyvtárát és fájlformátumát
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 9. lépés: Inicializálja a Viewer Object-et és állítsa be a PDF-beállításokat
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 10. lépés: Rendelje le a dokumentumot PDF formátumban
```csharp
viewer.View(options);
```

## Következtetés
Gratulálunk! Sikeresen megtanulta az MS Project dokumentumok renderelését és az időegységek beállítását a GroupDocs.Viewer for .NET segítségével. Építse be ezt a tudást projektjeibe a dokumentummegtekintési képességek javítása érdekében.
## GYIK
### Renderelhetem az MS Project dokumentumokat a HTML-en, a képeken és a PDF-en kívül más formátumban is?
Igen, a GroupDocs.Viewer for .NET támogatja a renderelést különböző formátumokba, például DOCX, XLSX, PPTX stb.
### Elérhető a GroupDocs.Viewer for .NET próbaverziója?
 Igen, ingyenes próbaverziót kaphat a webhelyen[itt](https://releases.groupdocs.com/).
### Hogyan szerezhetek ideiglenes licencet a GroupDocs.Viewer for .NET számára?
 Látogatás[ez a link](https://purchase.groupdocs.com/temporary-license/) ideiglenes engedély megszerzéséhez.
### Hol találom a GroupDocs.Viewer for .NET dokumentációját?
 Lásd a dokumentációt[itt](https://tutorials.groupdocs.com/viewer/net/).
### Hol kérhetek támogatást, vagy hol tehetek fel kérdéseket a GroupDocs.Viewer for .NET-hez kapcsolódóan?
 Látogassa meg a támogatási fórumot[itt](https://forum.groupdocs.com/c/viewer/9).