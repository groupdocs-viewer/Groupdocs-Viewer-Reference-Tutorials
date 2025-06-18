---
"description": "Integrálja zökkenőmentesen a Groupdocs.Viewer for .NET programot .NET projektjeibe a hatékony dokumentummegtekintés érdekében."
"linktitle": "Renderelés visszavonása visszavonási tokennel"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderelés visszavonása visszavonási tokennel"
"url": "/hu/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# Renderelés visszavonása visszavonási tokennel

## Bevezetés
A Groupdocs.Viewer for .NET egy hatékony eszköz, amelyet a dokumentumok megtekintésének és feldolgozásának egyszerűsítésére terveztek a .NET alkalmazásokon belül. Akár PDF-ekkel, Microsoft Office dokumentumokkal vagy más elterjedt formátumokkal foglalkozik, ez a könyvtár robusztus funkciókat kínál a dokumentummegtekintési képességek zökkenőmentes integrálásához a .NET projektekbe.
## Előfeltételek
Mielőtt belemerülne a Groupdocs.Viewer for .NET integrációjába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Telepítés: Töltse le és telepítse a Groupdocs.Viewer for .NET könyvtárat a mellékelt [letöltési link](https://releases.groupdocs.com/viewer/net/).
   
2. Engedély: Szerezzen be engedélyt a következő helyről: [Csoportdokumentációk](https://purchase.groupdocs.com/buy) hogy kiaknázza a könyvtár teljes potenciálját. Alternatív megoldásként ingyenes próbaverzióval is elkezdheti a következő használatával: [ideiglenes engedély](https://purchase.groupdocs.com/temporary-license/).
   
3. Fejlesztői környezet: Győződjön meg arról, hogy kompatibilis fejlesztői környezettel rendelkezik, beleértve a Visual Studio-t vagy bármely más, Ön által választott .NET IDE-t.

## Névterek importálása
A Groupdocs.Viewer for .NET hatékony használatához importálnia kell a szükséges névtereket a projektjébe. Kövesse az alábbi lépéseket:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Most bontsuk a bemutatott példát több lépésre a jobb megértés és megvalósítás érdekében:
## 1. lépés: Kimeneti könyvtár definiálása
```csharp
string outputDirectory = "Your Document Directory";
```
Ez a lépés beállítja azt a könyvtárat, ahová a renderelt dokumentumoldalak tárolásra kerülnek.
## 2. lépés: Oldalfájl elérési útjának formátumának meghatározása
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Itt definiáljuk az egyes dokumentumoldalak fájlelérési útvonalainak formátumát.
## 3. lépés: CancellationTokenSource inicializálása
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource olyan CancellationToken példányok létrehozására szolgál, amelyek aszinkron műveletek megszakítására használhatók.
## 4. lépés: CancellationToken beszerzése
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Ez a lépés lekéri a tokent a CancellationTokenSource-ból, amelyet a renderelési művelet megszakításához fogunk használni.
## 5. lépés: Dokumentumoldalak renderelése
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Itt a dokumentumoldalak aszinkron renderelését kezdeményezzük a Task.Run() használatával. Létrejön a Viewer példány a megadott dokumentumfájllal (SAMPLE_DOCX), és konfiguráljuk a renderelési beállításokat. A renderelési folyamat ezután a Viewer osztály View metódusával indul el.
## 6. lépés: Renderelési időtúllépés beállítása
```csharp
cancellationTokenSource.CancelAfter(10);
```
Ez a lépés 10 milliszekundumos időkorlátot állít be a renderelési művelethez. Ha a művelet túllépi ezt az időkorlátot, automatikusan megszakításra kerül.
## 7. lépés: Sikeres üzenet megjelenítése
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Végül egy sikeres üzenet jelenik meg, amely jelzi, hogy a dokumentum sikeresen megjelenítve lett.

## Következtetés
Ebben az oktatóanyagban áttekintettük a Groupdocs.Viewer for .NET integrálásának alapjait a projektjeibe. A fent vázolt lépéseket követve zökkenőmentesen beépítheti a dokumentummegtekintési funkciókat a .NET alkalmazásaiba, javítva a felhasználói élményt és a termelékenységet.
## GYIK
### A Groupdocs.Viewer for .NET kompatibilis az összes dokumentumformátummal?
A Groupdocs.Viewer for .NET számos dokumentumformátumot támogat, beleértve a PDF-et, a Microsoft Office dokumentumokat, a képeket és egyebeket.
### Testreszabhatom a renderelt dokumentumoldalak megjelenését?
Igen, testreszabhatja a renderelési folyamat különböző aspektusait, beleértve az oldalméretet, a minőséget, a vízjelet és egyebeket.
### A Groupdocs.Viewer for .NET használatához internetkapcsolat szükséges?
Nem, a Groupdocs.Viewer for .NET lokálisan működik a .NET környezetedben, és nem igényel internetkapcsolatot a dokumentumok megtekintéséhez.
### Elérhető technikai támogatás a Groupdocs.Viewer for .NET-hez?
Igen, a technikai támogatás elérhető a következő címen: [Groupdocs fórum](https://forum.groupdocs.com/c/viewer/9), ahol kérdéseket tehet fel, problémákat jelenthet és kapcsolatba léphet a közösséggel.
### Kipróbálhatom a Groupdocs.Viewer for .NET-et vásárlás előtt?
Igen, kipróbálhatja ingyenesen a mellékelt alkalmazást. [próbaverzió](https://releases.groupdocs.com/).