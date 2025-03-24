---
title: Renderuj obrazy FODG i ODG
linktitle: Renderuj obrazy FODG i ODG
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować obrazy FODG i ODG do formatu HTML, JPG, PNG i PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Usprawnij obsługę dokumentów.
weight: 15
url: /pl/net/image-rendering/render-fodg-odg-images/
---
## Wstęp
W świecie tworzenia oprogramowania sprawna obsługa formatów dokumentów jest najważniejsza. GroupDocs.Viewer dla .NET to potężne narzędzie zaprojektowane w celu uproszczenia procesu renderowania obrazów FODG i ODG w aplikacjach .NET. Ten samouczek przeprowadzi Cię przez kroki wymagane do renderowania tych obrazów do różnych formatów, takich jak HTML, JPG, PNG i PDF, przy użyciu programu GroupDocs.Viewer dla platformy .NET.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1.  GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Upewnij się, że masz zainstalowaną platformę .NET Framework w swoim systemie.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie pomocna.

## Importuj przestrzenie nazw
Przed rozpoczęciem wdrożenia zaimportuj niezbędne przestrzenie nazw:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Ustaw katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
 Zastępować`"Your Document Directory"`ze ścieżką katalogu, w którym chcesz zapisać wyrenderowane obrazy.
## Krok 2: Renderuj do HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Ten krok renderuje obraz FODG do formatu HTML.
## Krok 3: Renderuj do JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Tutaj obraz FODG jest renderowany do formatu JPG.
## Krok 4: Renderuj do PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Ten krok konwertuje obraz FODG do formatu PNG.
## Krok 5: Renderuj do formatu PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Na koniec obraz FODG jest renderowany do formatu PDF.

## Wniosek
W tym samouczku omówiliśmy, jak renderować obrazy FODG i ODG do różnych formatów przy użyciu programu GroupDocs.Viewer dla platformy .NET. Wykonując poniższe kroki, możesz bezproblemowo zintegrować możliwości renderowania dokumentów z aplikacjami .NET.
## Często zadawane pytania
### Czy GroupDocs.Viewer dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?
GroupDocs.Viewer dla .NET jest kompatybilny z szeroką gamą wersji .NET Framework, w tym z najnowszymi.
### Czy mogę renderować dokumenty asynchronicznie za pomocą GroupDocs.Viewer dla .NET?
Tak, GroupDocs.Viewer dla .NET zapewnia możliwości renderowania asynchronicznego w celu zwiększenia wydajności.
### Czy GroupDocs.Viewer dla .NET obsługuje renderowanie zaszyfrowanych dokumentów?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie zaszyfrowanych dokumentów za pomocą odpowiednich kluczy deszyfrujących.
### Czy można dostosować wynik renderowania za pomocą GroupDocs.Viewer dla .NET?
Oczywiście GroupDocs.Viewer dla .NET oferuje różne opcje dostosowywania, aby dostosować wynik renderowania do Twoich wymagań.
### Czy mogę renderować dokumenty ze zdalnych lokalizacji za pomocą GroupDocs.Viewer dla .NET?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie dokumentów zarówno z lokalnych, jak i zdalnych lokalizacji.