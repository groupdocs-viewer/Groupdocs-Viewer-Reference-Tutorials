---
title: Kijelölt oldalak renderelése
linktitle: Kijelölt oldalak renderelése
second_title: GroupDocs.Viewer .NET API
description: Ismerje meg, hogyan lehet dokumentumokból kiválasztott oldalakat renderelni a Groupdocs.Viewer for .NET segítségével. Lépésről lépésre bemutató oktatóprogram kódpéldákkal.
weight: 17
url: /hu/net/rendering-options/render-selected-pages/
---

# Kijelölt oldalak renderelése

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan használható a Groupdocs.Viewer for .NET a dokumentum kiválasztott oldalainak megjelenítésére. Akár tapasztalt fejlesztő, akár csak most kezdi, ez a lépésről lépésre bemutató útmutató könnyedén végigvezeti a folyamaton.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

### 1. Telepítés

 Győződjön meg arról, hogy a Groupdocs.Viewer for .NET telepítve van a fejlesztői környezetében. Ha nem, akkor letöltheti a[Letöltési link](https://releases.groupdocs.com/viewer/net/).

## Névterek importálása

 C# kódfájlba importálja a szükséges névtereket a szükséges osztályok és metódusok eléréséhez. Ezt megteheti a`using` irányelv:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most bontsuk fel a példakódot több lépésre:

## 1. lépés: Állítsa be a kimeneti könyvtárat

 Határozza meg azt a könyvtárat, ahová a megjelenített oldalakat menteni szeretné. Cserélje ki`"Your Document Directory"` a kívánt könyvtár elérési úttal.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2. lépés: Határozza meg az oldalfájl elérési út formátumát

Adja meg a megjelenített oldalak fájlútvonalának formátumát. Ezzel minden oldalt HTML-fájlként mentünk a kimeneti könyvtárba.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 3. lépés: Példányosítsa a Viewer objektumot

Hozzon létre egy példányt a Viewer osztályból, és adja át a megjeleníteni kívánt dokumentum elérési útját argumentumként.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## 4. lépés: Konfigurálja a HTML nézet beállításait

Állítsa be a HTML nézet beállításait a megjelenítéshez. Ebben a példában az erőforrások HTML-kimenetbe való beágyazására vonatkozó beállításokat állítunk be.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## 5. lépés: Jelenítse meg a kiválasztott oldalakat

Adja meg a megjeleníteni kívánt oldalszámokat. Ebben az esetben az 1–3. oldalakat jelenítjük meg. Ezután hívja meg a Viewer objektum View metódust, argumentumként átadva a beállításokat és az oldalszámokat.

```csharp
viewer.View(options, 1, 3);
```

## 6. lépés: Kimeneti eredmény

Végül jelenítsen meg egy üzenetet, amely jelzi a dokumentum sikeres megjelenítését és a kimeneti fájlok mentési helyét.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan lehet egy dokumentumból kiválasztott oldalakat renderelni a Groupdocs.Viewer for .NET segítségével. Ennek a tudásnak a birtokában most már könnyedén integrálhatja a dokumentum-renderelő képességeket .NET-alkalmazásaiba.

## GYIK

### K: Renderelhetek oldalakat különböző típusú dokumentumokból, például PDF-ekből vagy képekből?

V: Igen, a Groupdocs.Viewer for .NET támogatja az oldalak megjelenítését különféle dokumentumformátumokból, beleértve a PDF-eket, Microsoft Office dokumentumokat és képfájlokat.

### K: Rendelkezésre áll egy próbaverzió a vásárlás előtti tesztelésre?

 V: Igen, elérheti a Groupdocs.Viewer for .NET ingyenes próbaverzióját a webhelyről[weboldal](https://releases.groupdocs.com/).

### K: Testreszabhatom a kimeneti formátumot a HTML-től eltérően?

V: Természetesen a Groupdocs.Viewer for .NET lehetőséget biztosít az oldalak képként, PDF-ként és egyebekként való megjelenítésére a HTML mellett.

### K: Hogyan szerezhetek ideiglenes licenceket tesztelési célokra?

V: Ideiglenes engedélyek szerezhetők be a[ideiglenes licenc oldal](https://purchase.groupdocs.com/temporary-license/) a Groupdocs honlapján.

### K: Hol kérhetek segítséget vagy kaphatok segítséget bármilyen felmerülő problémával kapcsolatban?

 V: Meglátogathatja a[Groupdocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) támogatásért és útmutatásért a közösségtől és a fejlesztőktől.