---
title: E-mail mezők átnevezése a renderelés során
linktitle: E-mail mezők átnevezése a renderelés során
second_title: GroupDocs.Viewer .NET API
description: Növelje a dokumentummegtekintési élményt a GroupDocs.Viewer for .NET segítségével. Az e-mailek zökkenőmentes megjelenítése és testreszabása.
weight: 12
url: /hu/net/rendering-email-messages/rename-email-fields/
---

# E-mail mezők átnevezése a renderelés során

## Bevezetés

Napjaink digitális korában a dokumentumok hatékony kezelése és megtekintése kiemelten fontos a vállalkozások és a magánszemélyek számára egyaránt. Legyen szó szerződésekről, jelentésekről vagy e-mailekről, a dokumentumok zökkenőmentes navigálása nagymértékben növelheti a termelékenységet. Itt jön képbe a GroupDocs.Viewer for .NET. Ez a nagy teljesítményű könyvtár lehetővé teszi a fejlesztők számára, hogy dokumentummegtekintési képességeiket közvetlenül .NET-alkalmazásaikba integrálják, és a funkciók széles skáláját kínálja a különböző dokumentumformátumok megjelenítéséhez.

## Előfeltételek

Mielőtt belevágna az e-mail mezők átnevezésével kapcsolatos oktatóanyagba a GroupDocs.Viewer for .NET használatával történő renderelés során, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1.  GroupDocs.Viewer for .NET Library: Töltse le és telepítse a GroupDocs.Viewer for .NET könyvtárat innen:[itt](https://releases.groupdocs.com/viewer/net/).

2. Fejlesztői környezet: Győződjön meg arról, hogy megfelelő fejlesztői környezetet állít be a .NET-fejlesztéshez, például a Visual Studio-t.

3. A C# alapvető ismerete: Ismerkedjen meg a C# programozási nyelv alapjaival, mivel az oktatóanyag C# kódrészleteket tartalmaz.

4. Dokumentumkönyvtár: Készítsen egy könyvtárat, ahol a renderelni kívánt dokumentumokat tárolják.

## Névterek importálása

A GroupDocs.Viewer funkcióinak .NET-alkalmazásában való használatához importálnia kell a szükséges névtereket.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Most bontsuk le több lépésre az e-mail mezők átnevezésének folyamatát a GroupDocs.Viewer for .NET használatával történő megjelenítés során:

## 1. lépés: Határozza meg a kimeneti könyvtárat

Először is adja meg azt a könyvtárat, ahová a renderelt HTML-oldalak mentésre kerülnek.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2. lépés: Határozza meg az oldalfájl elérési út formátumát

Határozza meg a megjelenített HTML-oldalak fájlútvonalának formátumát. Minden oldal külön HTML-fájlként kerül mentésre.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 3. lépés: Inicializálja a Viewer Object-et

Hozzon létre egy példányt a Viewer osztályból, és adja meg a megtekintendő dokumentum elérési útját paraméterként.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## 4. lépés: Konfigurálja a HTML nézet beállításait

Konfigurálja a HTML nézet beállításait, beleértve a kimeneti fájl formátumának megadását és az e-mail mezőleképezések beállítását.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## 5. lépés: Renderelje le a dokumentumot

Hívja meg a Viewer objektum View metódusát, átadva a konfigurált HTML nézetbeállításokat.

```csharp
viewer.View(options);
```

## 6. lépés: Jelenítse meg a sikeres üzenetet

Tájékoztassa a felhasználót a dokumentum sikeres megjelenítéséről.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Következtetés

Összefoglalva, a GroupDocs.Viewer for .NET zökkenőmentes megoldást kínál a dokumentumok .NET-alkalmazásokon belüli megjelenítésére. Az oktatóanyagban ismertetett lépések követésével egyszerűen átnevezheti az e-mail mezőket a renderelés során, javítva ezzel az e-mail dokumentumok olvashatóságát és használhatóságát. Intuitív API-jával és átfogó szolgáltatásaival a GroupDocs.Viewer képessé teszi a fejlesztőket a dokumentummegtekintési folyamatok hatékony egyszerűsítésére.

## GYIK

### K: Renderelhetek-e az e-maileken kívül más dokumentumokat is a GroupDocs.Viewer for .NET segítségével?

V: Igen, a GroupDocs.Viewer támogatja a különféle dokumentumformátumok renderelését, beleértve a PDF, Microsoft Office dokumentumok, képek és egyebek megjelenítését.

### K: A GroupDocs.Viewer kompatibilis a .NET Core programmal?

V: Igen, a GroupDocs.Viewer támogatja a .NET Core-t a hagyományos .NET-keretrendszer mellett.

### K: Testreszabhatom a renderelt dokumentumok megjelenését?

V: Természetesen a GroupDocs.Viewer kiterjedt testreszabási lehetőségeket kínál a renderelt dokumentumok megjelenésének és viselkedésének szabályozására.

### K: Támogatja a GroupDocs.Viewer a dokumentumok streamingjét?

V: Igen, a GroupDocs.Viewer lehetővé teszi a dokumentumok közvetlen streamelését a kliens böngészőjébe anélkül, hogy azokat a szerveren kellene tárolni.

### K: A GroupDocs.Viewer alkalmas vállalati szintű alkalmazásokhoz?

V: Természetesen a GroupDocs.Viewer-t úgy tervezték, hogy megfeleljen a vállalati szintű alkalmazások igényeinek méretezhetőségével, megbízhatóságával és robusztus szolgáltatáskészletével.
