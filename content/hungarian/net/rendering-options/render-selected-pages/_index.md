---
"description": "Tanulja meg, hogyan jeleníthet meg kijelölt oldalakat dokumentumokból a Groupdocs.Viewer for .NET használatával. Lépésről lépésre bemutató kódpéldákkal."
"linktitle": "Kijelölt oldalak renderelése"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Kijelölt oldalak renderelése"
"url": "/hu/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# Kijelölt oldalak renderelése

## Bevezetés

Ebben az oktatóanyagban részletesen bemutatjuk, hogyan használható a Groupdocs.Viewer for .NET egy dokumentum kiválasztott oldalainak megjelenítéséhez. Akár tapasztalt fejlesztő vagy, akár most kezded, ez a lépésről lépésre szóló útmutató könnyedén végigvezet a folyamaton.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

### 1. Telepítés

Győződjön meg arról, hogy a Groupdocs.Viewer for .NET telepítve van a fejlesztői környezetében. Ha nem, akkor letöltheti innen: [Letöltési link](https://releases.groupdocs.com/viewer/net/).

## Névterek importálása

A C# kódfájlodban importáld a szükséges névtereket a szükséges osztályok és metódusok eléréséhez. Ezt a következővel teheted meg: `using` irányelv:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most bontsuk le a megadott példakódot több lépésre:

## 1. lépés: Kimeneti könyvtár beállítása

Adja meg azt a könyvtárat, ahová a renderelt oldalakat menteni szeretné. `"Your Document Directory"` a kívánt könyvtárútvonallal.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása

Adja meg a megjelenített oldalak fájlelérési útvonalainak formátumát. Ezt fogja használni a rendszer az egyes oldalak HTML-fájlként történő mentéséhez a kimeneti könyvtárba.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 3. lépés: Viewer objektum példányosítása

Hozz létre egy példányt a Viewer osztályból, argumentumként átadva a megjeleníteni kívánt dokumentum elérési útját.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## 4. lépés: HTML nézet beállításainak konfigurálása

Állítsa be a HTML nézet beállításait a rendereléshez. Ebben a példában a HTML kimenetbe beágyazott erőforrások beállításait konfiguráljuk.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## 5. lépés: Kijelölt oldalak renderelése

Adja meg a megjeleníteni kívánt oldalszámokat. Ebben az esetben az 1–3. oldalakat jelenítjük meg. Ezután hívja meg a View metódust a Viewer objektumon, és adja át az opciókat és az oldalszámokat argumentumként.

```csharp
viewer.View(options, 1, 3);
```

## 6. lépés: Eredmény kiírása

Végül jelenítsen meg egy üzenetet, amely jelzi a dokumentum sikeres renderelését és a kimeneti fájlok mentési helyét.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan jeleníthet meg kijelölt oldalakat egy dokumentumból a Groupdocs.Viewer for .NET segítségével. Ezzel a tudással most könnyedén integrálhatja a dokumentumrenderelési képességeket a .NET alkalmazásaiba.

## GYIK

### K: Meg tudom jeleníteni az oldalakat különböző típusú dokumentumokból, például PDF-ekből vagy képekből?

V: Igen, a Groupdocs.Viewer for .NET támogatja az oldalak renderelését különféle dokumentumformátumokból, beleértve a PDF-eket, a Microsoft Office dokumentumokat és a képfájlokat.

### K: Van elérhető próbaverzió a vásárlás előtti teszteléshez?

V: Igen, a Groupdocs.Viewer for .NET ingyenes próbaverzióját itt érheti el: [weboldal](https://releases.groupdocs.com/).

### K: Testreszabhatom a HTML-től eltérő kimeneti formátumot?

V: Természetesen, a Groupdocs.Viewer for .NET lehetőséget kínál oldalak képként, PDF-ként és egyebekként történő megjelenítésére a HTML mellett.

### K: Hogyan szerezhetek ideiglenes engedélyeket tesztelési célokra?

A: Ideiglenes engedélyek beszerezhetők a következő helyről: [ideiglenes licencoldal](https://purchase.groupdocs.com/temporary-license/) Groupdocs weboldalán.

### K: Hol kérhetek segítséget, vagy hol kaphatok segítséget a felmerülő problémákkal kapcsolatban?

V: Meglátogathatja a [Groupdocs.Viewer fórum](https://forum.groupdocs.com/c/viewer/9) támogatásért és útmutatásért a közösségtől és a fejlesztőktől.