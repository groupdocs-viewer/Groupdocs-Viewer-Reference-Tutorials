---
"description": "Sajátítsa el az MS Project dokumentumok renderelését a GroupDocs.Viewer for .NET segítségével. Rendereljen jegyzeteket, állítsa be az időegységeket, és fedezze fel a különféle kimeneti formátumokat könnyedén."
"linktitle": "Jegyzetek renderelése és időegységek beállítása (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Jegyzetek renderelése és időegységek beállítása (MS Project)"
"url": "/hu/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Jegyzetek renderelése és időegységek beállítása (MS Project)

## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony dokumentumrenderelési API, amely lehetővé teszi a fejlesztők számára, hogy különféle dokumentumformátumokat tekintsenek meg és kezeljenek a .NET alkalmazásaikon belül. Ebben az oktatóanyagban a jegyzetek renderelésére és az időegységek beállítására fogunk összpontosítani kifejezetten az MS Project dokumentumokhoz.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:
1. GroupDocs.Viewer for .NET: Győződjön meg róla, hogy letöltötte és telepítette a GroupDocs.Viewer for .NET könyvtárat. Letöltheti innen: [itt](https://releases.groupdocs.com/viewer/net/).
2. Fejlesztői környezet: Állítsa be a kívánt fejlesztői környezetet .NET támogatással.
3. MS Project dokumentum: Készítsen elő egy minta MS Project dokumentumot tesztelésre.
## Névterek importálása
Először importáljuk a szükséges névtereket az MS Project dokumentumok renderelésének megkezdéséhez:
## 1. lépés: Névterek importálása
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Most, hogy importáltuk a szükséges névtereket, bontsuk le az egyes példákat több lépésre az átfogóbb megértés érdekében.
## MS Project dokumentum HTML-lé renderelése
Egy MS Project dokumentum HTML formátumba, jegyzetekkel együtt történő rendereléséhez kövesse az alábbi lépéseket:
### 2. lépés: Kimeneti könyvtár és fájlformátum beállítása
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 3. lépés: Viewer objektum inicializálása és beállítások megadása
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### 4. lépés: Dokumentum renderelése HTML-be
```csharp
viewer.View(options);
```
## MS Project dokumentum renderelése képformátumokba
Az MS Project dokumentumokat JPG és PNG képformátumokba is renderelheti. Így teheti meg:
### 5. lépés: Állítsa be a JPG kimeneti könyvtárát és fájlformátumát
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### 6. lépés: A Viewer objektum inicializálása és a JPG beállítások megadása
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 7. lépés: Dokumentum renderelése JPG formátumba
```csharp
viewer.View(options);
```
Ismételje meg a hasonló lépéseket PNG és más képformátumok rendereléséhez.
## MS Project dokumentum PDF formátumba renderelése
Egy MS Project dokumentum PDF formátumba konvertálásához tegye a következőket:
### 8. lépés: A PDF kimeneti könyvtárának és fájlformátumának beállítása
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 9. lépés: A megjelenítő objektum inicializálása és a PDF-beállítások megadása
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 10. lépés: Dokumentum renderelése PDF-be
```csharp
viewer.View(options);
```

## Következtetés
Gratulálunk! Sikeresen megtanultad, hogyan kell MS Project dokumentumokat megjeleníteni és időegységeket beállítani a GroupDocs.Viewer for .NET segítségével. Építsd be ezt a tudást a projektjeidbe a dokumentumok megtekintési képességeinek javítása érdekében.
## GYIK
### Meg tudom renderelni az MS Project dokumentumokat HTML, képek és PDF formátumon kívül más formátumba is?
Igen, a GroupDocs.Viewer for .NET támogatja a renderelést különféle formátumokban, például DOCX, XLSX, PPTX és egyebekben.
### Van elérhető próbaverzió a GroupDocs.Viewer for .NET-hez?
Igen, ingyenes próbaverziót kaphatsz a következőtől: [itt](https://releases.groupdocs.com/).
### Hogyan szerezhetek ideiglenes licencet a GroupDocs.Viewer for .NET-hez?
Látogatás [ezt a linket](https://purchase.groupdocs.com/temporary-license/) ideiglenes jogosítvány megszerzéséhez.
### Hol találok dokumentációt a GroupDocs.Viewer for .NET-hez?
Lásd a dokumentációt [itt](https://tutorials.groupdocs.com/viewer/net/).
### Hol kérhetek támogatást vagy tehetek fel kérdéseket a GroupDocs.Viewer for .NET programmal kapcsolatban?
Meglátogathatod a támogatási fórumot [itt](https://forum.groupdocs.com/c/viewer/9).