---
title: Renderuj obrazy CMX
linktitle: Renderuj obrazy CMX
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak bez wysiłku renderować obrazy CMX do różnych formatów za pomocą GroupDocs.Viewer dla .NET. Usprawnij zarządzanie dokumentami.
weight: 13
url: /pl/net/image-rendering/render-cmx-images/
---
## Wstęp
W dziedzinie zarządzania dokumentami i manipulacji, renderowanie obrazów w różnych formatach jest kluczowym zadaniem. GroupDocs.Viewer dla .NET upraszcza ten proces, udostępniając kompleksowe funkcje renderowania obrazów CMX do różnych formatów, takich jak HTML, JPG, PNG i PDF. Ten samouczek poprowadzi Cię krok po kroku przez proces renderowania obrazów CMX przy użyciu GroupDocs.Viewer dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Biblioteka GroupDocs.Viewer dla .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer dla .NET ze strony[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Skonfiguruj działające środowisko programistyczne z platformą .NET.
3. Plik obrazu CMX: Uzyskaj plik obrazu CMX, który chcesz wyrenderować.

## Importowanie przestrzeni nazw
Przed kontynuowaniem pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcji GroupDocs.Viewer w aplikacji .NET:
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
- Zdefiniuj katalog wyjściowy: Ustaw katalog, w którym chcesz przechowywać renderowane pliki HTML.
- Określ format ścieżki pliku: Zdefiniuj format wyjściowych plików HTML.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer z plikiem obrazu CMX.
- Opcje renderowania HTML: skonfiguruj opcje renderowania HTML, takie jak osadzanie zasobów.
- Renderuj CMX do HTML: Wywołaj metodę View obiektu przeglądarki, aby wyrenderować obraz CMX do formatu HTML.
## Renderowanie do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Zdefiniuj katalog wyjściowy: Ustaw katalog do przechowywania renderowanych plików JPG.
- Określ format ścieżki pliku: Określ format wyjściowych plików JPG.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer z plikiem obrazu CMX.
- Opcje renderowania JPG: skonfiguruj opcje renderowania JPG.
- Renderuj CMX do JPG: Wywołaj metodę View obiektu przeglądarki, aby wyrenderować obraz CMX do JPG.
## Renderowanie do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Zdefiniuj katalog wyjściowy: Ustaw katalog do przechowywania renderowanych plików PNG.
- Określ format ścieżki pliku: Zdefiniuj format wyjściowych plików PNG.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer z plikiem obrazu CMX.
- Opcje renderowania PNG: skonfiguruj opcje renderowania PNG.
- Renderuj CMX do PNG: Wywołaj metodę View obiektu przeglądarki, aby wyrenderować obraz CMX do formatu PNG.
## Renderowanie do pliku PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Zdefiniuj katalog wyjściowy: Ustaw katalog do przechowywania renderowanego pliku PDF.
- Określ format ścieżki pliku: Zdefiniuj format wyjściowego pliku PDF.
- Utwórz instancję obiektu Viewer: Utwórz instancję klasy Viewer z plikiem obrazu CMX.
- Opcje renderowania PDF: skonfiguruj opcje renderowania PDF.
- Renderuj CMX do formatu PDF: Wywołaj metodę View obiektu przeglądarki, aby wyrenderować obraz CMX do formatu PDF.

## Wniosek
Podsumowując, GroupDocs.Viewer dla .NET oferuje solidne rozwiązanie do płynnego renderowania obrazów CMX do różnych formatów. Wykonując kroki opisane w tym samouczku, możesz bez wysiłku zintegrować możliwości renderowania obrazów CMX z aplikacjami .NET, zwiększając efektywność zarządzania dokumentami.
## Często zadawane pytania
### Czy mogę renderować określone strony obrazu CMX?
Tak, możesz renderować określone strony, podając numer strony w opcjach renderowania.
### Czy GroupDocs.Viewer dla .NET jest kompatybilny ze wszystkimi frameworkami .NET?
Tak, GroupDocs.Viewer dla .NET jest kompatybilny z wieloma platformami .NET, w tym .NET Core i .NET Framework.
### Czy GroupDocs.Viewer obsługuje renderowanie zaszyfrowanych obrazów CMX?
Tak, GroupDocs.Viewer obsługuje renderowanie zaszyfrowanych obrazów CMX za pomocą odpowiednich kluczy deszyfrujących.
### Czy mogę dostosować opcje renderowania dla różnych formatów wyjściowych?
Absolutnie GroupDocs.Viewer zapewnia szerokie możliwości dostosowywania parametrów renderowania w oparciu o Twoje wymagania.
### Czy istnieje forum społecznościowe umożliwiające obsługę programu GroupDocs.Viewer?
 Tak, możesz szukać pomocy i nawiązać kontakt ze społecznością GroupDocs.Viewer na forum pomocy technicznej[Tutaj](https://forum.groupdocs.com/c/viewer/9).