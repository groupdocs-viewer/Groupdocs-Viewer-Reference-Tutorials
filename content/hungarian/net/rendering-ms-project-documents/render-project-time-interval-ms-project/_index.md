---
title: Renderelés specifikus projektidőintervallum (MS Project)
linktitle: Renderelés specifikus projektidőintervallum (MS Project)
second_title: GroupDocs.Viewer .NET API
description: Integrálja a GroupDocs.Viewer for .NET-et zökkenőmentesen alkalmazásaiba a hatékony dokumentummegtekintés érdekében. Növelje a termelékenységet a sokoldalú renderelési képességekkel.
weight: 12
url: /hu/net/rendering-ms-project-documents/render-project-time-interval-ms-project/
---

# Renderelés specifikus projektidőintervallum (MS Project)

## Bevezetés
A szoftverfejlesztés területén a különböző dokumentumformátumok hatékony kezelése és renderelése a legfontosabb. Legyen szó dokumentumok megtekintéséről vagy manipulálásáról, a megfelelő eszközök birtokában jelentősen növelheti a termelékenységet és ésszerűsítheti a folyamatokat. A GroupDocs.Viewer for .NET sokoldalú megoldásként tűnik ki, és lehetőséget kínál a fejlesztőknek, hogy zökkenőmentesen integrálják a dokumentummegtekintési képességeket .NET-alkalmazásaikba.
## Előfeltételek
Mielőtt belevágna a GroupDocs.Viewer for .NET integrációjába, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. A .NET-keretrendszer ismerete
Győződjön meg arról, hogy alapvető ismeretekkel rendelkezik a .NET keretrendszerről, beleértve a C# programozási nyelvet és a Visual Studio IDE-t.
### 2. A GroupDocs.Viewer telepítése .NET-hez
 Töltse le és telepítse a GroupDocs.Viewer for .NET programot a[letöltési link](https://releases.groupdocs.com/viewer/net/). Kövesse a kapott telepítési utasításokat a könyvtár beállításához a fejlesztői környezetben.
### 3. Érvényes licenc vagy ideiglenes licenc
 Szerezzen be érvényes engedélyt innen[GroupDocs](https://purchase.groupdocs.com/buy) vagy ideiglenes engedélyt szerezni tőle[itt](https://purchase.groupdocs.com/temporary-license/) a GroupDocs.Viewer for .NET teljes funkciójának kihasználásához.
### 4. Dokumentumminta
Készítsen egy mintadokumentumot, például egy MS Project fájlt a renderelési funkcionalitás tesztelésére.

## Névterek importálása
Építse be a szükséges névtereket a projektbe, hogy elérje a GroupDocs.Viewer for .NET funkcióit.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Bontsuk le a példát egy adott projekt időintervallumának egy MS Project fájlból történő megjelenítésére több lépésre:
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
Adja meg azt a könyvtárat, ahová a renderelt HTML-oldalak mentésre kerülnek.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Állítsa be az egyes megjelenített HTML-oldalak fájlútvonalának formátumát.
## 3. lépés: Példányosítsa a Viewer objektumot
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Hozzon létre egy példányt a Viewer osztályból, átadva az elérési utat a minta MS Project fájlhoz.
## 4. lépés: Konfigurálja a HTML nézet beállításait
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Konfigurálja a HTML-nézeti beállításokat a megjelenítéshez, megadva a beágyazott erőforrások formátumát.
## 5. lépés: A Project Management View információk lekérése
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
A projektmenedzsment nézet információinak lekérése a projekt kezdő és befejező dátumának meghatározásához.
## 6. lépés: Állítsa be a kezdési és befejezési dátumot
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
Állítsa be a megjelenítendő projektintervallum kezdő és befejező dátumát.
## 7. lépés: Renderelje le a dokumentumot
```csharp
viewer.View(options);
```
Indítsa el a renderelési folyamatot a megadott beállításokkal.
## 8. lépés: Jelenítse meg a kimeneti könyvtárat
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Értesítse a felhasználót a sikeres renderelésről, és jelenítse meg azt a könyvtárat, ahová a kimenetet menti.

## Következtetés
GroupDocs.Viewer for .NET projektjeibe való integrálása lehetővé teszi a dokumentummegtekintési feladatok hatékony kezelését, javítva a felhasználói élményt és a termelékenységet. A részletes útmutatót követve zökkenőmentesen beépítheti a dokumentum-megjelenítési funkciókat .NET-alkalmazásaiba.
## GYIK
### A GroupDocs.Viewer for .NET kompatibilis az összes dokumentumformátummal?
A GroupDocs.Viewer for .NET a dokumentumformátumok széles skáláját támogatja, beleértve a Microsoft Office-t, a PDF-et, a CAD-et és egyebeket.
### Testreszabhatom a renderelt dokumentumok megjelenését?
Igen, testreszabhatja a renderelési folyamat különböző aspektusait, például az oldalelrendezést, a vízjeleket és az oldalforgatást.
### A GroupDocs.Viewer for .NET alkalmas webes alkalmazásokhoz?
Természetesen a GroupDocs.Viewer for .NET zökkenőmentesen integrálható webes alkalmazásokba, hogy dokumentummegtekintési lehetőségeket biztosítson.
### A GroupDocs.Viewer for .NET támogatja a mobil platformokat?
Igen, a GroupDocs.Viewer for .NET támogatja a mobilplatformokat, lehetővé téve az érzékeny dokumentummegtekintési funkciókkal rendelkező alkalmazások létrehozását.
### Van olyan közösségi fórum, ahol segítséget kérhetek a GroupDocs.Viewer for .NET-hez?
 Igen, meglátogathatja a[GroupDocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) kérdéseket feltenni, ötleteket megosztani, és kapcsolatba lépni más felhasználókkal és fejlesztőkkel.