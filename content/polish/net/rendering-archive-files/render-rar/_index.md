---
title: Renderuj archiwa RAR
linktitle: Renderuj archiwa RAR
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować archiwa RAR do formatów HTML, JPG, PNG lub PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Z łatwością przeglądaj i udostępniaj zawartość archiwów RAR.
weight: 13
url: /pl/net/rendering-archive-files/render-rar/
---
## Wstęp
Archiwa RAR to popularny format kompresji i przechowywania wielu plików i folderów w jednym kontenerze. Renderowanie archiwów RAR do różnych formatów, takich jak HTML, JPG, PNG lub PDF, może być niezbędne do przeglądania lub udostępniania zawartości tych archiwów. W tym samouczku przyjrzymy się, jak renderować archiwa RAR za pomocą GroupDocs.Viewer dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Zainstaluj bibliotekę GroupDocs.Viewer dla .NET z pliku[link do pobrania](https://releases.groupdocs.com/viewer/net/).
2. Przykładowe archiwum RAR: przygotuj przykładowe archiwum RAR do renderowania.

## Importuj przestrzenie nazw
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Renderuj do HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Renderuj do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 4: Renderuj do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 5: Renderuj do formatu PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Wniosek
Renderowanie archiwów RAR do różnych formatów jest proste dzięki GroupDocs.Viewer dla .NET. Wykonując kroki opisane w tym samouczku, możesz bez wysiłku konwertować archiwa RAR do formatów HTML, JPG, PNG lub PDF, umożliwiając łatwe przeglądanie i udostępnianie ich zawartości.
## Często zadawane pytania
### Czy GroupDocs.Viewer dla .NET może obsługiwać zaszyfrowane archiwa RAR?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie zaszyfrowanych archiwów RAR, pod warunkiem, że podczas procesu renderowania zostaną podane niezbędne hasła.
### Czy można dostosować wygląd wyjściowy renderowanych dokumentów?
Absolutnie! GroupDocs.Viewer dla .NET oferuje rozbudowane opcje dostosowywania, umożliwiające użytkownikom dostosowanie wyglądu renderowanych dokumentów zgodnie z ich preferencjami.
### Czy GroupDocs.Viewer dla .NET obsługuje renderowanie innych formatów archiwów oprócz RAR?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie różnych formatów archiwów, w tym ZIP, TAR, 7z i innych.
### Czy mogę zintegrować GroupDocs.Viewer for .NET z moją aplikacją internetową?
Z pewnością! GroupDocs.Viewer dla .NET udostępnia interfejsy API, które nadają się do integracji zarówno z aplikacjami stacjonarnymi, jak i internetowymi.
### Czy dostępna jest wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz skorzystać z bezpłatnej wersji próbnej GroupDocs.Viewer dla .NET w witrynie[strona internetowa](https://releases.groupdocs.com/).