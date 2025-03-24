---
title: Sorok és oszlopok fejléceinek megjelenítése
linktitle: Sorok és oszlopok fejléceinek megjelenítése
second_title: GroupDocs.Viewer .NET API
description: Javítsa a dokumentumok megtekintését .NET-ben! Ismerje meg a sorok és oszlopok fejléceinek megjelenítését a GroupDocs.Viewer for .NET segítségével. Fedezze fel a HTML, JPG, PNG és PDF kimeneteket.
weight: 18
url: /hu/net/spreadsheet-rendering-options/render-row-column-headings/
---

# Sorok és oszlopok fejléceinek megjelenítése

## Bevezetés
Szeretné javítani a dokumentummegtekintési élményt .NET-alkalmazásokban? A GroupDocs.Viewer for .NET segítségével zökkenőmentesen jelenítheti meg a sorok és oszlopok fejléceit a táblázatfájljaiból. Ebben az oktatóanyagban végigvezetjük a sor- és oszlopfejlécek különböző kimeneti formátumok (például HTML, JPG, PNG és PDF) használatával történő megjelenítésének folyamatán.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Telepített GroupDocs.Viewer for .NET könyvtár.
- Egy minta XLSX fájl tesztelési célokra.
- C# és .NET fejlesztési ismeretek.
## Névterek importálása
Győződjön meg arról, hogy a C#-kódban importálja a GroupDocs.Viewer használatához szükséges névtereket:
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
## 2. Renderelés HTML-be
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. Renderelje le JPG formátumban
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. Renderelés PNG formátumban
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
Gratulálunk! Sikeresen megjelenítette a sorok és oszlopok fejléceit a táblázatból a GroupDocs.Viewer for .NET segítségével. Kísérletezzen különböző kimeneti formátumokkal, hogy megfeleljen az alkalmazás igényeinek.
## Gyakran Ismételt Kérdések
### K: Testreszabhatom a megjelenített dokumentumok kimeneti könyvtárát?
 V: Igen, beállíthatja a kívánt kimeneti könyvtárat abban a kódban, ahol a`outputDirectory` változó van definiálva.
### K: A GroupDocs.Viewer kompatibilis más táblázatformátumokkal?
V: Igen, a GroupDocs.Viewer különféle táblázatformátumokat támogat, beleértve az XLS-t, XLSX-et, CSV-t és még sok mást.
### K: Hogyan kezelhetem a kivételeket a renderelési folyamat során?
V: Megvalósíthat try-catch blokkokat a kivételek kezelésére és a megfelelő üzenetek naplózására vagy megjelenítésére a felhasználó számára.
### K: Vannak-e licenckövetelmények a GroupDocs.Viewer alkalmazásban való használatához?
V: Igen, érvényes engedély szükséges. Kaphat ideiglenes licencet tesztelési célokra, vagy vásárolhat teljes licencet a gyártáshoz.
### K: Hol találhatok további támogatást vagy közösségi megbeszéléseket?
 V: Látogassa meg a[GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) támogatásért és megbeszélésekért.