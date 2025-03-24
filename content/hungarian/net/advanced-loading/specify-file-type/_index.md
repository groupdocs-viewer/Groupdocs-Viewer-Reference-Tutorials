---
title: Adja meg a fájl típusát a dokumentumok betöltésekor
linktitle: Adja meg a fájl típusát a dokumentumok betöltésekor
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan adhat meg fájltípust dokumentumok betöltésekor a GroupDocs.Viewer for .NET használatával. A különböző formátumokat pontosan jelenítse meg .NET-alkalmazásaiban.
weight: 10
url: /hu/net/advanced-loading/specify-file-type/
---
## Bevezetés
A GroupDocs.Viewer for .NET egy sokoldalú dokumentum-megjelenítő API, amely a fájlformátumok széles skáláját támogatja, beleértve a DOCX, PDF, PPTX stb. Ha a dokumentumok betöltésekor megadja a fájltípust, pontos megjelenítést és zökkenőmentes megtekintési élményt biztosíthat a felhasználók számára.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- C# és .NET keretrendszer alapismeretei.
- A Visual Studio telepítve van a rendszerére.
-  GroupDocs.Viewer for .NET telepítve van a projektben. Letöltheti innen[itt](https://releases.groupdocs.com/viewer/net/).
##
## Névterek importálása
Először is importálnia kell a szükséges névtereket a C# kódjába. Ezek a névterek hozzáférést biztosítanak a dokumentum-megjelenítéshez szükséges osztályokhoz és metódusokhoz.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. lépés: Állítsa be a kimeneti könyvtárat
Határozza meg azt a könyvtárat, ahová menteni szeretné a megjelenített dokumentumoldalakat.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
Adja meg a kimeneti HTML-fájlok elnevezésének formátumát a dokumentum minden oldalához.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. lépés: Adja meg a Betöltési beállításokat
 Hozzon létre egy példányt a`LoadOptions` osztályt, és állítsa be a kívánt fájltípust.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## 4. lépés: Töltse be a dokumentumot és renderelje le
 Használja a`Viewer` osztályt a dokumentum betöltéséhez és HTML formátumba történő megjelenítéséhez.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 5. lépés: Jelenítse meg a sikeres üzenetet
Tájékoztassa a felhasználót a dokumentum sikeres megjelenítéséről, és adja meg a kimeneti fájlok helyét.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell használni a GroupDocs.Viewer for .NET alkalmazást a fájltípus megadására dokumentumok betöltésekor. Ezen egyszerű lépések követésével biztosíthatja a különböző dokumentumformátumok pontos megjelenítését .NET-alkalmazásaiban.
## GYIK
### Renderelhetek-e DOCX-től eltérő dokumentumokat a GroupDocs.Viewer for .NET használatával?
Igen, a GroupDocs.Viewer a fájlformátumok széles skáláját támogatja, beleértve a PDF, PPTX, XLSX és egyebeket.
### A GroupDocs.Viewer for .NET kompatibilis a .NET Core-al?
Igen, a GroupDocs.Viewer for .NET kompatibilis a .NET-keretrendszerrel és a .NET Core-al is.
### Testreszabhatom a GroupDocs.Viewer által generált kimeneti HTML-fájlokat?
Igen, testreszabhatja a HTML-kimenetet az API által biztosított különféle opciókkal.
### A GroupDocs.Viewer for .NET-nek szüksége van külső függőségekre?
Nem, a GroupDocs.Viewer for .NET egy önálló könyvtár, és nem igényel semmilyen külső függőséget.
### Elérhető a GroupDocs.Viewer for .NET próbaverziója?
Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.groupdocs.com/viewer/net/).