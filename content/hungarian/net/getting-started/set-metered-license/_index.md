---
title: Állítsa be a mért licencet
linktitle: Állítsa be a mért licencet
second_title: GroupDocs.Viewer .NET API
description: Bővítse .NET-alkalmazásait a GroupDocs.Viewer segítségével a zökkenőmentes dokumentummegtekintés érdekében. Könnyen integrálhatja a dokumentum-renderelő funkciókat projektjeibe.
type: docs
weight: 12
url: /hu/net/getting-started/set-metered-license/
---
## Bevezetés
.NET-fejlesztés világában a hatékony dokumentummegtekintési képességek alkalmazása az alkalmazásokba elengedhetetlen a felhasználói élmény és a funkcionalitás javításához. A GroupDocs.Viewer for .NET robusztus megoldást kínál a dokumentummegtekintési funkciók zökkenőmentes integrálására a .NET-projektekbe. Függetlenül attól, hogy PDF-ekkel, Microsoft Office-dokumentumokkal vagy különféle képformátumokkal dolgozik, a GroupDocs.Viewer leegyszerűsíti ezeknek a dokumentumoknak az alkalmazásaiban való megjelenítését és megjelenítését.
## Előfeltételek
Mielőtt belevágna a GroupDocs.Viewer for .NET megvalósításába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
### 1. Telepítse a GroupDocs.Viewer for .NET programot
 A kezdéshez le kell töltenie és telepítenie kell a GroupDocs.Viewer for .NET programot. A letöltési linket megtalálod[itt](https://releases.groupdocs.com/viewer/net/). Kövesse a kapott telepítési utasításokat a könyvtár beállításához a fejlesztői környezetben.
### 2. Szerezzen mért engedélyt
GroupDocs.Viewer for .NET használatához mérős licencet kell beszereznie. Ez a licenc lehetővé teszi az API használatának szabályozását és figyelemmel kísérését előre meghatározott kvóták alapján. Kövesse az alábbi lépéseket a fizetős licenc beállításához:

## Névterek importálása
Először győződjön meg arról, hogy importálja a szükséges névtereket, hogy elérje a GroupDocs.Viewer for .NET funkcióit:
```csharp
using System;
```

Most bontsuk fel a példakódot több lépésre:
## 1. lépés: Nyilvános és privát kulcsok deklarálása
Deklaráljon változókat a nyilvános és privát kulcsok tárolására:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Biztosítsa a cserét`"YOUR_PUBLIC_KEY"` és`"YOUR_PRIVATE_KEY"` a valódi kulcsaiddal.
## 2. lépés: Állítsa be a mért licencet
Ellenőrizze, hogy rendelkezésre áll-e a nyilvános kulcs. Ha nem, kérje meg a felhasználót, hogy állítsa be a kulcsokat:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://buy.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## 3. lépés: Inicializálja a mért objektumot és állítsa be a licencet
Inicializálja a Mért objektumot, és állítsa be a mért licencet a nyilvános és privát kulcsaival:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## 4. lépés: Megerősítő üzenet
Megerősítő üzenet megjelenítése, amely jelzi, hogy a licencet sikeresen beállította:
```csharp
Console.WriteLine("License set successfully.");
```

## Következtetés
Összefoglalva, a GroupDocs.Viewer for .NET átfogó megoldást kínál a dokumentummegtekintési funkciók beépítésére a .NET-alkalmazásokba. A vázolt lépések követésével könnyedén beállíthat egy mért licencet, és elkezdheti kiaknázni a GroupDocs.Viewer képességeit projektjein belül.
## GYIK
### K: Hol találom a GroupDocs.Viewer for .NET dokumentációját?
 A dokumentációt megtalálod[itt](https://reference.groupdocs.com/viewer/net/).
### K: Elérhető ingyenes próbaverzió a GroupDocs.Viewer for .NET számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.groupdocs.com/).
### K: Hogyan szerezhetek ideiglenes licenceket tesztelési célokra?
 Ideiglenes jogosítványok szerezhetők be[itt](https://purchase.groupdocs.com/temporary-license/).
### K: Hol kérhetek támogatást, vagy hol tehetek fel kérdéseket a GroupDocs.Viewer for .NET-hez kapcsolódóan?
 A GroupDocs.Viewer fórumon kérhet támogatást és kérdéseket tehet fel[itt](https://forum.groupdocs.com/c/viewer/9).
### K: Hol vásárolhatok licencet a GroupDocs.Viewer for .NET számára?
 Vásárolhat licencet[itt](https://purchase.groupdocs.com/buy).