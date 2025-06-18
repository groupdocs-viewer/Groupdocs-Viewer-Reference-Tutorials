---
"description": "Dowiedz się, jak renderować obrazy FODG i ODG do formatów HTML, JPG, PNG i PDF przy użyciu GroupDocs.Viewer dla platformy .NET. Ulepsz obsługę dokumentów."
"linktitle": "Renderuj obrazy FODG i ODG"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj obrazy FODG i ODG"
"url": "/pl/net/image-rendering/render-fodg-odg-images/"
"weight": 15
---

# Renderuj obrazy FODG i ODG

## Wstęp
W świecie rozwoju oprogramowania, wydajna obsługa formatów dokumentów jest najważniejsza. GroupDocs.Viewer dla .NET to potężne narzędzie zaprojektowane w celu uproszczenia procesu renderowania obrazów FODG i ODG w aplikacjach .NET. Ten samouczek przeprowadzi Cię przez kroki wymagane do renderowania tych obrazów do różnych formatów, takich jak HTML, JPG, PNG i PDF, przy użyciu GroupDocs.Viewer dla .NET.

![Renderuj obrazy FODG i ODG za pomocą GroupDocs.Viewer dla .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Upewnij się, że w systemie jest zainstalowany .NET Framework.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie pomocna.

## Importuj przestrzenie nazw
Przed rozpoczęciem implementacji należy zaimportować niezbędne przestrzenie nazw:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Ustaw katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Zastępować `"Your Document Directory"` ze ścieżką do katalogu, w którym chcesz zapisać wyrenderowane obrazy.
## Krok 2: Renderowanie do HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Ten krok renderuje obraz FODG do formatu HTML.
## Krok 3: Renderowanie do JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Tutaj obraz FODG został przekonwertowany do formatu JPG.
## Krok 4: Renderowanie do PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Ten krok konwertuje obraz FODG do formatu PNG.
## Krok 5: Renderowanie do PDF
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
tym samouczku sprawdziliśmy, jak renderować obrazy FODG i ODG do różnych formatów przy użyciu GroupDocs.Viewer dla .NET. Wykonując te kroki, możesz bezproblemowo zintegrować możliwości renderowania dokumentów z aplikacjami .NET.
## Najczęściej zadawane pytania
### Czy GroupDocs.Viewer dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?
GroupDocs.Viewer dla platformy .NET jest kompatybilny z szeroką gamą wersji platformy .NET Framework, w tym z najnowszymi.
### Czy mogę renderować dokumenty asynchronicznie za pomocą GroupDocs.Viewer dla .NET?
Tak, GroupDocs.Viewer dla .NET oferuje możliwości asynchronicznego renderowania, co poprawia wydajność.
### Czy GroupDocs.Viewer dla platformy .NET obsługuje renderowanie zaszyfrowanych dokumentów?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie zaszyfrowanych dokumentów przy użyciu odpowiednich kluczy deszyfrujących.
### Czy można dostosować wyjście renderowania za pomocą GroupDocs.Viewer dla .NET?
Oczywiście, GroupDocs.Viewer dla .NET oferuje różne opcje dostosowywania pozwalające dostosować wynik renderowania do Twoich wymagań.
### Czy mogę renderować dokumenty ze zdalnych lokalizacji przechowywania przy użyciu GroupDocs.Viewer dla .NET?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie dokumentów zarówno z lokalnych, jak i zdalnych lokalizacji przechowywania.