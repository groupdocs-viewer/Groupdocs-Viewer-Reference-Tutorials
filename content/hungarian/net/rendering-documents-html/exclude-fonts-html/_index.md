---
title: Betűtípusok kizárása a renderelt HTML-ből
linktitle: Betűtípusok kizárása a renderelt HTML-ből
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan zárhat ki betűtípusokat a megjelenített HTML-ből a GroupDocs.Viewer for .NET segítségével. Kövesse ezt a lépésről lépésre szóló útmutatót a zökkenőmentes dokumentummegjelenítéshez.
weight: 10
url: /hu/net/rendering-documents-html/exclude-fonts-html/
---
## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony dokumentum-megjelenítő könyvtár, amely lehetővé teszi a fejlesztők számára, hogy több mint 50 dokumentumformátumot jelenítsenek meg .NET-alkalmazásaikban anélkül, hogy külső függőségekre lenne szükségük. Ebben az oktatóanyagban a GroupDocs.Viewer egy speciális funkciójára összpontosítunk: a betűtípusok kizárására a renderelt HTML-kimenetből. 
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Alapvető ismeretek a C# és .NET fejlesztésről.
2.  A GroupDocs.Viewer for .NET telepítve. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio vagy bármely más IDE a C# fejlesztéshez.

## Névterek importálása
Győződjön meg arról, hogy a C# kódban szerepelteti a szükséges névtereket:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Határozza meg a kimeneti könyvtárat
Állítsa be azt a könyvtárat, ahová a renderelt HTML-fájlokat menteni szeretné.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
Adja meg a renderelt dokumentum egyes oldalai fájlútvonalainak formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Inicializálja a Viewer Object-et
Példányosítsa a Viewer objektumot a megjeleníteni kívánt dokumentummal.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // A kódod ide kerül
}
```
## 4. lépés: Állítsa be a HTML nézet beállításait
Határozza meg a HTML-megjelenítés beállításait, beleértve a beágyazott erőforrások formátumát és a kizárandó betűtípusokat.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## 5. lépés: Renderelje le a dokumentumot
A dokumentum megjelenítéséhez adja át a HTML nézet beállításait a Viewer objektumnak.
```csharp
viewer.View(options);
```
## 6. lépés: Kimeneti renderelt dokumentum helye
Tájékoztassa a felhasználót a renderelt HTML-fájlok mentési helyéről.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell használni a GroupDocs.Viewer for .NET-et a betűtípusok kizárására a renderelt HTML-kimenetből. A fent vázolt lépések követésével testreszabhatja a renderelési folyamatot, hogy megfeleljen az egyedi követelményeknek, biztosítva a dokumentumok optimális megjelenítését az alkalmazásokban.
## GYIK
### Kizárhatok több betűtípust a renderelt HTML-ből?
 Igen, több betűtípusnevet is hozzáadhat a`FontsToExclude` listát a HTML nézet opcióiban.
### A GroupDocs.Viewer kompatibilis az összes .NET keretrendszerrel?
Igen, a GroupDocs.Viewer támogatja a .NET Framework 4.6.1-es és újabb verzióit.
### Renderelhetek dokumentumokat távoli tárolóhelyekről?
Igen, a GroupDocs.Viewer támogatja a dokumentumok helyi tárhelyről, valamint távoli tárolóhelyekről és adatfolyamokból történő megjelenítését.
### Támogatja a GroupDocs.Viewer a reszponzív tervezést a HTML-kimenethez?
Igen, engedélyezheti a reszponzív megjelenítést a HTML nézetbeállítások megfelelő módosításával.
### Elérhető a GroupDocs.Viewer technikai támogatása?
 Igen, kérhet segítséget, és részt vehet az erről szóló megbeszéléseken[GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9).