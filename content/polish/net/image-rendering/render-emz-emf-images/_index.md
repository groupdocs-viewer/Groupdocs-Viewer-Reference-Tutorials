---
"description": "Dowiedz się, jak renderować obrazy EMZ i EMF do różnych formatów za pomocą GroupDocs.Viewer dla .NET. Łatwy do naśladowania samouczek dla programistów."
"linktitle": "Renderuj obrazy EMZ i EMF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj obrazy EMZ i EMF"
"url": "/pl/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# Renderuj obrazy EMZ i EMF

## Wstęp

GroupDocs.Viewer dla .NET to potężny interfejs API renderowania dokumentów, który umożliwia deweloperom wyświetlanie różnych typów dokumentów, w tym obrazów EMZ (Enhanced Windows Metafile) i EMF (Enhanced Metafile), w ich aplikacjach .NET. W tym samouczku pokażemy, jak renderować obrazy EMZ i EMF do różnych formatów, takich jak HTML, JPG, PNG i PDF, przy użyciu GroupDocs.Viewer dla .NET.

![Renderuj obrazy EMZ i EMF za pomocą GroupDocs.Viewer dla .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:

1. GroupDocs.Viewer dla .NET: Bibliotekę można pobrać ze strony [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane zgodne środowisko programistyczne przeznaczone do programowania w środowisku .NET.
3. Przykładowe obrazy EMZ/EMF: Dostępne są przykładowe obrazy EMZ i EMF do renderowania.

## Importuj przestrzenie nazw

Zanim zagłębimy się w kod, zaimportujmy niezbędne przestrzenie nazw:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Teraz rozbijmy każdy przykład na kilka kroków w formacie przewodnika krok po kroku:

## Renderowanie obrazów EMZ/EMF do HTML

### Krok 1: Ustaw katalog wyjściowy:
```csharp
string outputDirectory = "Your Document Directory";
```
Zastępować `"Your Document Directory"` ze ścieżką, pod którą chcesz zapisać wyrenderowany plik HTML.

### Krok 2: Zdefiniuj format ścieżki pliku stronicowania:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Określi format ścieżki pliku dla renderowanego pliku HTML.

### Krok 3: Renderowanie do HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Ten kod inicjuje `Viewer` obiekt z przykładowym obrazem EMZ i renderuje go do formatu HTML przy użyciu określonych opcji.

## Renderowanie obrazów EMZ/EMF do formatów JPG, PNG i PDF

Powtórz poniższe kroki, aby renderować do formatów JPG, PNG i PDF:

### Krok 1: Zdefiniuj format ścieżki pliku stronicowania:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Dostosuj nazwę i rozszerzenie pliku zgodnie z pożądanym formatem wyjściowym (`jpg`, `png`, Lub `pdf`).

### Krok 2: Renderowanie do odpowiedniego formatu:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Dostosuj opcje zgodnie z formatem wyjściowym (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Zastępować `JpgViewOptions` z `PngViewOptions` Lub `PdfViewOptions` na podstawie pożądanego formatu wyjściowego.

## Wniosek

Podsumowując, GroupDocs.Viewer dla .NET zapewnia bezproblemowe rozwiązanie do renderowania obrazów EMZ i EMF do różnych formatów w aplikacjach .NET. Postępując zgodnie z krokami opisanymi w tym samouczku, deweloperzy mogą bez wysiłku zintegrować możliwości renderowania dokumentów ze swoimi aplikacjami.

## Najczęściej zadawane pytania

### P: Czy GroupDocs.Viewer może renderować inne formaty dokumentów niż obrazy EMZ i EMF?
O: Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, DOCX, PPTX, XLSX i inne.

### P: Czy jest dostępna bezpłatna wersja próbna programu GroupDocs.Viewer dla platformy .NET?
A: Tak, możesz skorzystać z bezpłatnej wersji próbnej [Tutaj](https://releases.groupdocs.com/).

### P: Czy GroupDocs.Viewer oferuje wsparcie dla deweloperów?
O: Tak, GroupDocs zapewnia wsparcie poprzez swoje [forum](https://forum.groupdocs.com/c/viewer/9) gdzie programiści mogą zadawać pytania i szukać pomocy.

### P: Czy mogę kupić tymczasową licencję na GroupDocs.Viewer dla platformy .NET?
A: Tak, licencje tymczasowe są dostępne do kupienia [Tutaj](https://purchase.groupdocs.com/temporary-license/).

### P: Gdzie mogę znaleźć szczegółową dokumentację dla GroupDocs.Viewer dla .NET?
A: Możesz zapoznać się z dokumentacją [Tutaj](https://tutorials.groupdocs.com/viewer/net/) aby uzyskać kompleksowe wskazówki dotyczące korzystania z API.