---
"description": "Ismerje meg, hogyan adhatja meg a fájltípust dokumentumok betöltésekor a GroupDocs.Viewer for .NET használatával. Különböző formátumok pontos megjelenítése .NET alkalmazásaiban."
"linktitle": "Fájltípus megadása dokumentumok betöltésekor"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Fájltípus megadása dokumentumok betöltésekor"
"url": "/hu/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Fájltípus megadása dokumentumok betöltésekor

## Bevezetés
A GroupDocs.Viewer for .NET egy sokoldalú dokumentumrenderelési API, amely számos fájlformátumot támogat, beleértve a DOCX, PDF, PPTX és egyebeket. A fájltípus megadásával a dokumentumok betöltésekor biztosíthatja a pontos renderelést és a zökkenőmentes megtekintési élményt a felhasználók számára.

![Fájltípus megadása dokumentumok betöltésekor a GroupDocs.Viewer for .NET programban](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- C# és .NET keretrendszer alapismeretek.
- Visual Studio telepítve a rendszeredre.
- A GroupDocs.Viewer for .NET telepítve van a projektedben. Letöltheted innen: [itt](https://releases.groupdocs.com/viewer/net/).
##
## Névterek importálása
Először is importálnod kell a szükséges névtereket a C# kódodba. Ezek a névterek hozzáférést biztosítanak a dokumentumok rendereléséhez szükséges osztályokhoz és metódusokhoz.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Kimeneti könyvtár beállítása
Adja meg azt a könyvtárat, ahová a renderelt dokumentumoldalakat menteni szeretné.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása
Adja meg a dokumentum minden oldalához tartozó kimeneti HTML-fájlok elnevezési formátumát.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Betöltési beállítások megadása
Hozz létre egy példányt a `LoadOptions` osztályt, és állítsa be a kívánt fájltípust.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## 4. lépés: Dokumentum betöltése és renderelés
Használd a `Viewer` osztály a dokumentum betöltéséhez és HTML formátumba rendereléséhez.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 5. lépés: Sikeres üzenet megjelenítése
Tájékoztassa a felhasználót a dokumentum sikeres megjelenítéséről, és adja meg a kimeneti fájlok helyét.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan használható a GroupDocs.Viewer for .NET a fájltípus megadására dokumentumok betöltésekor. Ezeket az egyszerű lépéseket követve biztosíthatja a különböző dokumentumformátumok pontos megjelenítését .NET alkalmazásaiban.
## GYIK
### Renderelhetek DOCX formátumtól eltérő dokumentumokat a GroupDocs.Viewer for .NET segítségével?
Igen, a GroupDocs.Viewer számos fájlformátumot támogat, beleértve a PDF, PPTX, XLSX és egyebeket.
### A GroupDocs.Viewer for .NET kompatibilis a .NET Core-ral?
Igen, a GroupDocs.Viewer for .NET kompatibilis mind a .NET Framework, mind a .NET Core rendszerrel.
### Testreszabhatom a GroupDocs.Viewer által generált kimeneti HTML fájlokat?
Igen, testreszabhatja a HTML-kimenetet az API által biztosított különféle beállításokkal.
### A GroupDocs.Viewer for .NET igényel külső függőségeket?
Nem, a GroupDocs.Viewer for .NET egy önálló függvénytár, és nem igényel semmilyen külső függőséget.
### Van elérhető próbaverzió a GroupDocs.Viewer for .NET-hez?
Igen, letölthet egy ingyenes próbaverziót innen [itt](https://releases.groupdocs.com/viewer/net/).