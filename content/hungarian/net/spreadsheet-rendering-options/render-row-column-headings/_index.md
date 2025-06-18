---
"description": "Javítsa a dokumentumok megtekintését .NET-ben! Tanulja meg, hogyan jelenítheti meg a sor- és oszlopfejléceket a GroupDocs.Viewer for .NET segítségével. Fedezze fel a HTML, JPG, PNG és PDF kimeneteket."
"linktitle": "Sor- és oszlopfejlécek megjelenítése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Sor- és oszlopfejlécek megjelenítése"
"url": "/hu/net/spreadsheet-rendering-options/render-row-column-headings/"
"weight": 18
---

# Sor- és oszlopfejlécek megjelenítése

## Bevezetés
Szeretnéd javítani a dokumentummegtekintési élményedet .NET alkalmazásokban? A GroupDocs.Viewer for .NET segítségével zökkenőmentesen megjelenítheted a sor- és oszlopfejléceket a táblázatfájljaidból. Ebben az oktatóanyagban végigvezetünk a sor- és oszlopfejlécek megjelenítésének folyamatán különböző kimeneti formátumok, például HTML, JPG, PNG és PDF használatával.
## Előfeltételek
Mielőtt belemerülnénk az oktatóanyagba, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:
- Telepítettem a GroupDocs.Viewer for .NET könyvtárat.
- Egy minta XLSX fájl tesztelési célokra.
- C# és .NET fejlesztési ismeretek.
## Névterek importálása
C# kódban ügyeljen arra, hogy importálja a GroupDocs.Viewer használatához szükséges névtereket:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Állítsa be a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. HTML-re renderelés
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. JPG formátumba renderelés
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. Renderelés PNG formátumba
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. Renderelés PDF-be
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## Következtetés
Gratulálunk! Sikeresen megjelenítette a táblázat sor- és oszlopfejléceit a GroupDocs.Viewer for .NET segítségével. Kísérletezzen különböző kimeneti formátumokkal az alkalmazása igényeinek megfelelően.
## Gyakran Ismételt Kérdések
### K: Testreszabhatom a renderelt dokumentumok kimeneti könyvtárát?
V: Igen, beállíthatja a kívánt kimeneti könyvtárat a kódban, ahol a `outputDirectory` változó definiálva van.
### K: A GroupDocs.Viewer kompatibilis más táblázatkezelő formátumokkal?
V: Igen, a GroupDocs.Viewer különféle táblázatformátumokat támogat, beleértve az XLS, XLSX, CSV és egyebeket.
### K: Hogyan kezelhetem a kivételeket a renderelési folyamat során?
V: A try-catch blokkokat implementálhatja a kivételek kezelésére, valamint a felhasználónak küldött megfelelő üzenetek naplózására vagy megjelenítésére.
### K: Vannak-e licencelési követelmények a GroupDocs.Viewer használatához az alkalmazásomban?
V: Igen, érvényes licencre van szüksége. Tesztelési célokra ideiglenes licencet szerezhet, vagy teljes licencet vásárolhat éles környezetbe.
### K: Hol találok további támogatást vagy közösségi beszélgetéseket?
V: Látogassa meg a [GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) támogatásért és megbeszélésekért.