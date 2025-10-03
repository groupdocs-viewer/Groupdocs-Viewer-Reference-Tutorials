---
"description": "Fejleszd .NET alkalmazásaidat a GroupDocs.Viewer segítségével a zökkenőmentes dokumentummegtekintés érdekében. Könnyedén integráld a dokumentumrenderelési funkciókat projektjeidbe."
"linktitle": "Mért licenc beállítása"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Mért licenc beállítása"
"url": "/hu/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# Mért licenc beállítása

## Bevezetés
.NET fejlesztés világában a hatékony dokumentummegtekintési funkciók beépítése az alkalmazásokba elengedhetetlen a felhasználói élmény és a funkcionalitás javítása érdekében. A GroupDocs.Viewer for .NET robusztus megoldást kínál a dokumentummegtekintési funkciók zökkenőmentes integrálására a .NET projektekbe. Akár PDF-ekkel, Microsoft Office dokumentumokkal vagy különféle képformátumokkal dolgozik, a GroupDocs.Viewer leegyszerűsíti ezen dokumentumok renderelésének és megjelenítésének folyamatát az alkalmazásokban.

![Mért licenc beállítása a GroupDocs.Viewer for .NET segítségével](/viewer/getting-started/set-metered-license.png)

## Előfeltételek
Mielőtt belemerülne a GroupDocs.Viewer for .NET implementációjába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
### 1. Telepítse a GroupDocs.Viewer for .NET programot
Kezdéshez le kell töltened és telepítened kell a GroupDocs.Viewer for .NET programot. A letöltési linket itt találod: [itt](https://releases.groupdocs.com/viewer/net/)Kövesse a mellékelt telepítési utasításokat a könyvtár fejlesztői környezetében történő beállításához.
### 2. Szerezze be a mért licencet
A GroupDocs.Viewer for .NET használatához mért licencet kell beszereznie. Ez a licenc lehetővé teszi az API-használat szabályozását és monitorozását előre meghatározott kvóták alapján. A mért licenc beállításához kövesse az alábbi lépéseket:

## Névterek importálása
Először is győződjön meg arról, hogy importálja a szükséges névtereket a GroupDocs.Viewer for .NET által biztosított funkciók eléréséhez:
```csharp
using System;
```

Most bontsuk le a megadott példakódot több lépésre:
## 1. lépés: Nyilvános és privát kulcsok deklarálása
Deklarálj változókat a nyilvános és privát kulcsok tárolására:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Biztosítsa a cserét `"YOUR_PUBLIC_KEY"` és `"YOUR_PRIVATE_KEY"` a valódi kulcsaiddal.
## 2. lépés: Mért licenc beállítása
Ellenőrizd, hogy meg van-e adva a nyilvános kulcs. Ha nem, kérd meg a felhasználót a kulcsok beállítására:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## 3. lépés: Mért objektum inicializálása és licenc beállítása
Inicializálja a Metered objektumot, és állítsa be a mért licencet a nyilvános és privát kulcsaival:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## 4. lépés: Megerősítő üzenet
Megjelenít egy megerősítő üzenetet, amely jelzi, hogy a licenc beállítása sikeresen megtörtént:
```csharp
Console.WriteLine("License set successfully.");
```

## Következtetés
Összefoglalva, a GroupDocs.Viewer for .NET átfogó megoldást kínál a dokumentummegtekintési funkciók .NET-alkalmazásokba való beépítésére. A vázolt lépéseket követve könnyedén beállíthat egy mért licencet, és elkezdheti kihasználni a GroupDocs.Viewer képességeit a projektjeiben.
## GYIK
### K: Hol találok dokumentációt a GroupDocs.Viewer for .NET-hez?
A dokumentációt megtalálod [itt](https://tutorials.groupdocs.com/viewer/net/).
### K: Van elérhető ingyenes próbaverzió a GroupDocs.Viewer for .NET-hez?
Igen, hozzáférhetsz az ingyenes próbaverzióhoz [itt](https://releases.groupdocs.com/).
### K: Hogyan szerezhetek ideiglenes engedélyeket tesztelési célokra?
Ideiglenes engedélyek szerezhetők be [itt](https://purchase.groupdocs.com/temporary-license/).
### K: Hol kérhetek támogatást vagy tehetek fel kérdéseket a GroupDocs.Viewer for .NET programmal kapcsolatban?
Támogatást kérhetsz és kérdéseket tehetsz fel a GroupDocs.Viewer fórumon. [itt](https://forum.groupdocs.com/c/viewer/9).
### K: Hol vásárolhatok licencet a GroupDocs.Viewer for .NET-hez?
Licenc vásárlása lehetséges [itt](https://purchase.groupdocs.com/buy).