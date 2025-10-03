---
"description": "Dowiedz się, jak bez wysiłku renderować obrazy CMX do różnych formatów za pomocą GroupDocs.Viewer dla .NET. Ulepsz zarządzanie dokumentami."
"linktitle": "Renderuj obrazy CMX"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj obrazy CMX"
"url": "/pl/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# Renderuj obrazy CMX

## Wstęp
W dziedzinie zarządzania dokumentami i manipulacji renderowanie obrazów z różnych formatów jest kluczowym zadaniem. GroupDocs.Viewer dla .NET upraszcza ten proces, zapewniając kompleksowe funkcjonalności renderowania obrazów CMX do różnych formatów, takich jak HTML, JPG, PNG i PDF. Ten samouczek przeprowadzi Cię przez proces renderowania obrazów CMX krok po kroku przy użyciu GroupDocs.Viewer dla .NET.

![Renderowanie obrazów CMX za pomocą GroupDocs.Viewer dla .NET](/viewer/image-rendering/render-cmx-images.png)

## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
1. Biblioteka GroupDocs.Viewer dla platformy .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer dla platformy .NET z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Skonfiguruj działające środowisko programistyczne z wykorzystaniem platformy .NET.
3. Plik obrazu CMX: Uzyskaj plik obrazu CMX, który chcesz wyrenderować.

## Importowanie przestrzeni nazw
Przed kontynuowaniem należy zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności GroupDocs.Viewer w aplikacji .NET:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Renderowanie do HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Zdefiniuj katalog wyjściowy: Ustaw katalog, w którym chcesz przechowywać wyrenderowane pliki HTML.
- Określ format ścieżki pliku: Zdefiniuj format plików wyjściowych HTML.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer przy użyciu pliku obrazu CMX.
- Opcje renderowania HTML: Konfiguruj opcje renderowania HTML, takie jak osadzanie zasobów.
- Renderowanie CMX do HTML: Wywołaj metodę View obiektu przeglądarki, aby wyrenderować obraz CMX do HTML.
## Renderowanie do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Zdefiniuj katalog wyjściowy: Ustaw katalog, w którym będą przechowywane renderowane pliki JPG.
- Określ format ścieżki pliku: Zdefiniuj format plików wyjściowych JPG.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer przy użyciu pliku obrazu CMX.
- Opcje renderowania JPG: skonfiguruj opcje renderowania JPG.
- Renderowanie CMX do JPG: Wywołaj metodę View obiektu przeglądarki, aby renderować obraz CMX do JPG.
## Renderowanie do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Zdefiniuj katalog wyjściowy: Ustaw katalog, w którym będą przechowywane renderowane pliki PNG.
- Określ format ścieżki pliku: Zdefiniuj format plików wyjściowych PNG.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer przy użyciu pliku obrazu CMX.
- Opcje renderowania PNG: skonfiguruj opcje renderowania PNG.
- Renderowanie CMX do PNG: Wywołaj metodę View obiektu przeglądarki, aby renderować obraz CMX do PNG.
## Renderowanie do PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Zdefiniuj katalog wyjściowy: Ustaw katalog, w którym będzie przechowywany wyrenderowany plik PDF.
- Określ format ścieżki pliku: Zdefiniuj format wyjściowego pliku PDF.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer przy użyciu pliku obrazu CMX.
- Opcje renderowania PDF: skonfiguruj opcje renderowania PDF.
- Renderowanie CMX do PDF: Wywołaj metodę View obiektu przeglądarki, aby renderować obraz CMX do PDF.

## Wniosek
Podsumowując, GroupDocs.Viewer dla .NET oferuje solidne rozwiązanie do bezproblemowego renderowania obrazów CMX do różnych formatów. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz bez wysiłku zintegrować możliwości renderowania obrazów CMX z aplikacjami .NET, zwiększając wydajność zarządzania dokumentami.
## Najczęściej zadawane pytania
### Czy mogę renderować konkretne strony obrazu CMX?
Tak, możesz renderować konkretne strony, określając numer strony w opcjach renderowania.
### Czy GroupDocs.Viewer dla .NET jest kompatybilny ze wszystkimi platformami .NET?
Tak, GroupDocs.Viewer dla .NET jest kompatybilny z wieloma platformami .NET, w tym .NET Core i .NET Framework.
### Czy GroupDocs.Viewer obsługuje renderowanie zaszyfrowanych obrazów CMX?
Tak, GroupDocs.Viewer obsługuje renderowanie zaszyfrowanych obrazów CMX z odpowiednimi kluczami deszyfrującymi.
### Czy mogę dostosować opcje renderowania do różnych formatów wyjściowych?
Oczywiście, GroupDocs.Viewer oferuje rozbudowane opcje dostosowywania parametrów renderowania w zależności od wymagań.
### Czy istnieje forum społecznościowe poświęcone pomocy technicznej GroupDocs.Viewer?
Tak, możesz szukać pomocy i nawiązywać kontakt ze społecznością GroupDocs.Viewer na forum wsparcia [Tutaj](https://forum.groupdocs.com/c/viewer/9).