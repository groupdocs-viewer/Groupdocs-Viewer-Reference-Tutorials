---
"description": "Ismerje meg, hogyan zárhatja ki a betűtípusokat a renderelt HTML-ből a GroupDocs.Viewer for .NET használatával. Kövesse ezt a lépésenkénti útmutatót a zökkenőmentes dokumentummegjelenítéshez."
"linktitle": "Betűtípusok kizárása a renderelt HTML-ből"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Betűtípusok kizárása a renderelt HTML-ből"
"url": "/hu/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# Betűtípusok kizárása a renderelt HTML-ből

## Bevezetés
A GroupDocs.Viewer for .NET egy hatékony dokumentumrenderelő könyvtár, amely lehetővé teszi a fejlesztők számára, hogy több mint 50 dokumentumformátumot jelenítsenek meg .NET alkalmazásaikban külső függőségek nélkül. Ebben az oktatóanyagban a GroupDocs.Viewer egy adott funkciójára fogunk összpontosítani: a betűtípusok kizárására a renderelt HTML-kimenetből. 
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:
1. C# és .NET fejlesztés alapjainak ismerete.
2. GroupDocs.Viewer for .NET telepítve. Letöltheti innen: [itt](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio vagy bármilyen más C# fejlesztéshez használt IDE.

## Névterek importálása
A C# kódodban mindenképpen szerepeltesd a szükséges névtereket:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1. lépés: Kimeneti könyvtár definiálása
Állítsa be azt a könyvtárat, ahová a renderelt HTML fájlokat menteni szeretné.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása
Adja meg a renderelt dokumentum egyes oldalainak fájlelérési útjának formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Viewer objektum inicializálása
Hozza létre a Viewer objektum példányát a megjeleníteni kívánt dokumentummal.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // A kódod ide kerül
}
```
## 4. lépés: HTML nézetbeállítások megadása
Adja meg a HTML-megjelenítés beállításait, beleértve a beágyazott erőforrások formátumát és a kizárandó betűtípusokat.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## 5. lépés: Dokumentum renderelése
Add át a HTML nézetbeállításokat a Viewer objektumnak a dokumentum megjelenítéséhez.
```csharp
viewer.View(options);
```
## 6. lépés: A renderelt dokumentum helyének megjelenítése
Tájékoztassa a felhasználót a megjelenített HTML-fájlok mentési helyéről.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan használhatjuk a GroupDocs.Viewer for .NET programot betűtípusok kizárására a renderelt HTML-kimenetből. A fent vázolt lépéseket követve testreszabhatja a renderelési folyamatot az Ön igényeinek megfelelően, biztosítva a dokumentumok optimális megjelenítését az alkalmazásaiban.
## GYIK
### Kizárhatok több betűtípust a megjelenített HTML-ből?
Igen, több betűtípusnevet is hozzáadhat a `FontsToExclude` listában a HTML nézet beállításai között.
### A GroupDocs.Viewer kompatibilis az összes .NET keretrendszerrel?
Igen, a GroupDocs.Viewer támogatja a .NET Framework 4.6.1-es és újabb verzióit.
### Renderelhetek dokumentumokat távoli tárolóhelyekről?
Igen, a GroupDocs.Viewer támogatja a dokumentumok renderelését a helyi tárolóból, valamint a távoli tárolóhelyekről és adatfolyamokból is.
### A GroupDocs.Viewer támogatja a reszponzív HTML-kimenetet?
Igen, a HTML nézet beállításainak megfelelő módosításával engedélyezheti a reszponzív megjelenítést.
### Elérhető technikai támogatás a GroupDocs.Viewerhez?
Igen, kérhet segítséget és részt vehet a beszélgetésekben a következő oldalon: [GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9).