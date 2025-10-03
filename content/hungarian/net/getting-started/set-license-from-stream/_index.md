---
"description": "Fejleszd .NET alkalmazásaidat a GroupDocs.Viewer segítségével a zökkenőmentes dokumentummegtekintés érdekében. Kövesd lépésről lépésre szóló útmutatónkat, és integráld a hatékony dokumentummegtekintési funkciókat könnyedén."
"linktitle": "Licenc beállítása adatfolyamból"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Licenc beállítása adatfolyamból"
"url": "/hu/net/getting-started/set-license-from-stream/"
"weight": 11
type: docs
---
# Licenc beállítása adatfolyamból

## Bevezetés
Szeretné .NET-alkalmazásait fejlett dokumentummegtekintési lehetőségekkel felruházni? A GroupDocs.Viewer for .NET átfogó megoldást kínál a dokumentummegtekintési funkciók zökkenőmentes integrálására projektjeibe. Ebben az oktatóanyagban részletesen bemutatjuk, hogyan használhatja a GroupDocs.Viewer for .NET alkalmazást alkalmazásai hatékony dokumentummegtekintési lehetőségekkel való gazdagításához. 

![Licenc beállítása a Streamből a GroupDocs.Viewer for .NET segítségével](/viewer/getting-started/set-license-from-stream.png)

## Előfeltételek
Mielőtt belevágnánk az integrációs folyamatba, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:
1. .NET fejlesztési alapismeretek: A C# és a .NET keretrendszer ismerete elengedhetetlen a tutoriál követéséhez.
   
2. GroupDocs.Viewer for .NET csomag: Győződjön meg róla, hogy letöltötte és telepítette a GroupDocs.Viewer for .NET csomagot. A csomagot a következő helyről szerezheti be: [letöltési link](https://releases.groupdocs.com/viewer/net/).
3. Hozzáférés a GroupDocs dokumentációjához: Tartsa meg a [dokumentáció](https://tutorials.groupdocs.com/viewer/net/) hasznos oktatóanyagokhoz az integrációs folyamat során.

## Névterek importálása
Először importálja a szükséges névtereket a .NET alkalmazásába. Kövesse az alábbi lépéseket:
### 1. lépés: Nyissa meg a .NET-projektjét.
Győződjön meg arról, hogy a .NET-projektje a kívánt fejlesztői környezetben van megnyitva.
### 2. lépés: GroupDocs.Viewer névtér hozzáadása.
A kódfájlban add hozzá a következő névteret a GroupDocs.Viewer funkcióinak eléréséhez:
```csharp
using System;
using System.IO;
```
## Licenc beállítása adatfolyamból
A következő lépés a licenc beállítása egy adatfolyamból. Kövesse az alábbi részletes lépéseket:
### 1. lépés: Kimeneti könyvtár meghatározása.
Állítsa be a dokumentumok tárolására szolgáló könyvtárat a kimeneti könyvtár definiálásával:
```csharp
string outputDirectory = "Your Document Directory";
```
### 2. lépés: Ellenőrizze a licencfájl meglétét.
Ellenőrizd, hogy a licencfájl létezik-e a projektkönyvtáradban:
```csharp
if (File.Exists(Utils.LicensePath))
```
### 3. lépés: Licenc beállítása.
Ha a licencfájl létezik, állítsa be a licencet a megadott adatfolyam használatával:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 4. lépés: Jogosítvány hiányának kezelése.
Ha a licencfájl nem található, adja meg a licenc beszerzéséhez szükséges utasításokat:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/ideiglenes-license.");
}
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan integrálhatja a GroupDocs.Viewer for .NET-et az alkalmazásaiba. Ezzel a hatékony eszközzel mostantól könnyedén megtekintheti a .NET-projektjein belüli különféle dokumentumformátumokat, növelve a felhasználói élményt és a termelékenységet.
## GYIK
### Szükségem van licencre a GroupDocs.Viewer for .NET használatához?
Igen, licenc szükséges a GroupDocs.Viewer for .NET használatához. Ideiglenes vagy állandó licencet a GroupDocs weboldaláról szerezhet be.
### Integrálhatom a GroupDocs.Viewer-t az ASP.NET alkalmazásomba?
Abszolút! A GroupDocs.Viewer for .NET zökkenőmentesen integrálható mind az asztali, mind a webes alkalmazásokba, beleértve az ASP.NET-et is.
### Milyen dokumentumformátumokat támogat a GroupDocs.Viewer?
A GroupDocs.Viewer számos dokumentumformátumot támogat, beleértve a PDF-et, a Microsoft Office-t (Word, Excel, PowerPoint), a képeket és egyebeket.
### Kompatibilis a GroupDocs.Viewer a .NET Core-ral?
Igen, a GroupDocs.Viewer for .NET kompatibilis mind a .NET Framework, mind a .NET Core rendszerrel.
### Testreszabhatom a megjelenítő felületét az alkalmazásom témája szerint?
Igen, a GroupDocs.Viewer széleskörű testreszabási lehetőségeket kínál, lehetővé téve a megjelenítő felületének zökkenőmentes testreszabását az alkalmazás témájához.