---
title: Törölje a megjelenítést a törlési tokennel
linktitle: Törölje a megjelenítést a törlési tokennel
second_title: GroupDocs.Viewer .NET API
description: Integrálja a Groupdocs.Viewer for .NET-et zökkenőmentesen .NET-projektjeibe a hatékony dokumentummegtekintés érdekében.
type: docs
weight: 11
url: /hu/net/rendering-options/cancel-render-cancellation-token/
---
## Bevezetés
Groupdocs.Viewer for .NET egy hatékony eszköz, amelyet a .NET-alkalmazásokon belüli dokumentumok megtekintésének és feldolgozásának egyszerűsítésére terveztek. Legyen szó PDF-ekről, Microsoft Office dokumentumokról vagy más gyakori formátumokról, ez a könyvtár robusztus funkcionalitást kínál a dokumentummegtekintési képességek zökkenőmentes integrálásához .NET-projektjeibe.
## Előfeltételek
Mielőtt belevágna a Groupdocs.Viewer for .NET integrációjába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1.  Telepítés: Töltse le és telepítse a Groupdocs.Viewer for .NET könyvtárat a mellékelt könyvtárból[letöltési link](https://releases.groupdocs.com/viewer/net/).
   
2.  Licenc: Szerezzen engedélyt a következőtől[Groupdocs](https://purchase.groupdocs.com/buy) hogy kibontakoztassa a könyvtárban rejlő lehetőségeket. Alternatív megoldásként ingyenes próbaverzióval kezdheti a[ideiglenes engedély](https://purchase.groupdocs.com/temporary-license/).
   
3. Fejlesztői környezet: Győződjön meg arról, hogy be van állítva egy kompatibilis fejlesztői környezet, beleértve a Visual Studio-t vagy bármely más választott .NET IDE-t.

## Névterek importálása
A Groupdocs.Viewer for .NET hatékony használatához importálnia kell a szükséges névtereket a projektbe. Kovesd ezeket a lepeseket:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Most bontsuk fel a példát több lépésre a jobb megértés és megvalósítás érdekében:
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
string outputDirectory = "Your Document Directory";
```
Ez a lépés beállítja azt a könyvtárat, ahol a renderelt dokumentumoldalak tárolásra kerülnek.
## 2. lépés: Határozza meg az oldalfájl elérési út formátumát
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Itt határozzuk meg az egyes dokumentumoldalak fájlútvonalainak formátumát.
## 3. lépés: A CancellationTokenSource inicializálása
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
A CancellationTokenSource a CancellationToken példányok generálására szolgál, amelyek az aszinkron műveletek törlésére használhatók.
## 4. lépés: Szerezze be a CancellationTokent
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Ez a lépés lekéri a tokent a CancellationTokenSource-ból, amelyet a renderelési művelet megszakításához használunk.
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
Itt kezdeményezzük a dokumentumoldalak aszinkron megjelenítését a Task.Run() segítségével. A Viewer példány a megadott dokumentumfájllal (SAMPLE_DOCX) jön létre, és a megjelenítési beállítások konfigurálva vannak. A renderelési folyamat ezután elindul a Viewer osztály View metódusával.
## 6. lépés: Állítsa be a renderelési időt
```csharp
cancellationTokenSource.CancelAfter(10);
```
Ez a lépés 10 ezredmásodperces időtúllépést állít be a renderelési művelethez. Ha a művelet túllépi ezt az időtúllépést, automatikusan törlődik.
## 7. lépés: Jelenítse meg a sikeres üzenetet
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Végül egy sikerüzenet jelenik meg, amely jelzi, hogy a dokumentumot sikeresen renderelték.

## Következtetés
Ebben az oktatóanyagban a Groupdocs.Viewer for .NET projektekbe való integrálásának alapjait ismertetjük. A fent vázolt lépések követésével zökkenőmentesen beépítheti a dokumentummegtekintési képességeket .NET-alkalmazásaiba, javítva a felhasználói élményt és a termelékenységet.
## GYIK
### A Groupdocs.Viewer for .NET kompatibilis az összes dokumentumformátummal?
A Groupdocs.Viewer for .NET a dokumentumformátumok széles skáláját támogatja, beleértve a PDF-et, a Microsoft Office dokumentumokat, a képeket és egyebeket.
### Testreszabhatom a megjelenített dokumentumoldalak megjelenését?
Igen, testreszabhatja a renderelési folyamat különböző aspektusait, beleértve az oldalméretet, a minőséget, a vízjelet és még sok mást.
### A Groupdocs.Viewer for .NET használatához internetkapcsolat szükséges?
Nem, a Groupdocs.Viewer for .NET helyileg működik a .NET-környezetben, és nem igényel internetkapcsolatot a dokumentumok megtekintéséhez.
### Elérhető technikai támogatás a Groupdocs.Viewer for .NET számára?
 Igen, a technikai támogatás a következőn keresztül érhető el[Groupdocs fórum](https://forum.groupdocs.com/c/viewer/9), ahol kérdéseket tehet fel, problémákat jelenthet, és kapcsolatba léphet a közösséggel.
### Kipróbálhatom a Groupdocs.Viewer for .NET alkalmazást vásárlás előtt?
 Igen, a rendelkezésre álló ingyenes próbaverzióval kezdheti[próbaverzió](https://releases.groupdocs.com/).