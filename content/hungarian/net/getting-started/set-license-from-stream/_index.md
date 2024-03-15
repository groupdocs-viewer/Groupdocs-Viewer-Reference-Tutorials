---
title: Licenc beállítása a Streamből
linktitle: Licenc beállítása a Streamből
second_title: GroupDocs.Viewer .NET API
description: Bővítse .NET-alkalmazásait a GroupDocs.Viewer segítségével a zökkenőmentes dokumentummegtekintés érdekében. Kövesse lépésről lépésre útmutatónkat, és könnyedén integrálja a hatékony dokumentummegtekintési funkciókat.
type: docs
weight: 11
url: /hu/net/getting-started/set-license-from-stream/
---
## Bevezetés
Fejlett dokumentummegtekintési lehetőségekkel szeretné felruházni .NET-alkalmazásait? A GroupDocs.Viewer for .NET átfogó megoldást kínál a dokumentummegtekintési funkciók zökkenőmentes integrálására a projektekbe. Ebben az oktatóanyagban elmélyülünk a GroupDocs.Viewer for .NET használatának folyamatában, hogy alkalmazásait hatékony dokumentummegtekintési lehetőségekkel gazdagítsa. 
## Előfeltételek
Mielőtt belevágnánk az integrációs folyamatba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Alapvető ismeretek a .NET fejlesztésről: A C# és a .NET keretrendszer ismerete elengedhetetlen, hogy kövesse ezt az oktatóanyagot.
   
2.  GroupDocs.Viewer for .NET Package: Győződjön meg arról, hogy letöltötte és telepítette a GroupDocs.Viewer for .NET csomagot. Beszerezheti a[letöltési link](https://releases.groupdocs.com/viewer/net/).
3.  Hozzáférés a GroupDocs dokumentációjához: Tartsa meg a[dokumentáció](https://reference.groupdocs.com/viewer/net/) hasznos referenciaként szolgálhat az integrációs folyamat során.

## Névterek importálása
Először is importálja a szükséges névtereket .NET-alkalmazásába. Kovesd ezeket a lepeseket:
### 1. lépés: Nyissa meg a .NET-projektet.
Győződjön meg arról, hogy a .NET-projektje a kívánt fejlesztői környezetben van megnyitva.
### 2. lépés: Adja hozzá a GroupDocs.Viewer névteret.
A GroupDocs.Viewer funkcióinak eléréséhez adja hozzá a következő névteret a kódfájlhoz:
```csharp
using System;
using System.IO;
```
## Licenc beállítása a Streamből
A következő lépés a licenc adatfolyamból történő beállítása. Kövesse az alábbi részletes lépéseket:
### 1. lépés: Határozza meg a kimeneti könyvtárat.
Állítsa be a könyvtárat, ahol a dokumentumokat tárolni fogja a kimeneti könyvtár megadásával:
```csharp
string outputDirectory = "Your Document Directory";
```
### 2. lépés: Ellenőrizze a licencfájl meglétét.
Ellenőrizze, hogy a licencfájl létezik-e a projektkönyvtárban:
```csharp
if (File.Exists(Utils.LicensePath))
```
### 3. lépés: Állítsa be a licencet.
Ha a licencfájl létezik, állítsa be a licencet a biztosított adatfolyam segítségével:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 4. lépés: Kezelje a licenc hiányát.
Ha a licencfájl nem található, adjon meg utasításokat a licenc beszerzéséhez:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing. "+
                      "\nLearn how to request a temporary license at https://buy.groupdocs.com/temporary-license.");
}
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan integrálhatja a GroupDocs.Viewer for .NET programot alkalmazásaiba. Ezzel a hatékony eszközzel könnyedén megtekintheti a különböző dokumentumformátumokat .NET-projektjein belül, javítva a felhasználói élményt és a termelékenységet.
## GYIK
### Szükségem van licencre a GroupDocs.Viewer for .NET használatához?
Igen, licencre van szüksége a GroupDocs.Viewer for .NET használatához. Ideiglenes vagy állandó licencet szerezhet be a GroupDocs webhelyéről.
### Integrálhatom a GroupDocs.Viewert az ASP.NET-alkalmazásomba?
Teljesen! A GroupDocs.Viewer for .NET zökkenőmentesen integrálódik az asztali és webes alkalmazásokba, beleértve az ASP.NET-et is.
### Mely dokumentumformátumokat támogatja a GroupDocs.Viewer?
A GroupDocs.Viewer a dokumentumformátumok széles skáláját támogatja, beleértve a PDF-et, a Microsoft Office-t (Word, Excel, PowerPoint), a képeket stb.
### A GroupDocs.Viewer kompatibilis a .NET Core programmal?
Igen, a GroupDocs.Viewer for .NET kompatibilis a .NET-keretrendszerrel és a .NET Core-al is.
### Testreszabhatom a megtekintő felületet az alkalmazás témájának megfelelően?
Igen, a GroupDocs.Viewer kiterjedt testreszabási lehetőségeket kínál, amelyek lehetővé teszik a megjelenítő felületének zökkenőmentesen az alkalmazás témájához való igazítását.