---
"description": "Dowiedz się, jak renderować obrazy SVG i SVGZ za pomocą GroupDocs.Viewer dla platformy .NET. Bezproblemowo konwertuj grafikę wektorową do formatów HTML, JPG, PNG i PDF."
"linktitle": "Renderuj obrazy SVG i SVGZ"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj obrazy SVG i SVGZ"
"url": "/pl/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# Renderuj obrazy SVG i SVGZ

## Wstęp
tym samouczku przeprowadzimy Cię przez proces renderowania obrazów SVG i SVGZ przy użyciu GroupDocs.Viewer dla .NET. GroupDocs.Viewer dla .NET to potężny interfejs API renderowania dokumentów, który umożliwia deweloperom renderowanie różnych formatów dokumentów w ich aplikacjach .NET. SVG i SVGZ to popularne formaty obrazów używane w grafice wektorowej, a dzięki GroupDocs.Viewer dla .NET możesz łatwo renderować je do różnych formatów wyjściowych, takich jak HTML, JPG, PNG i PDF.

![Renderuj obrazy SVG i SVGZ za pomocą GroupDocs.Viewer dla .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz zainstalowane i skonfigurowane następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Upewnij się, że dysponujesz działającym środowiskiem programistycznym do tworzenia oprogramowania .NET, np. Visual Studio.
3. Przykładowy plik SVGZ: Przygotuj przykładowy plik SVGZ w celu przetestowania.

## Importuj przestrzenie nazw
Zanim zagłębimy się w kod, zaimportujmy niezbędne przestrzenie nazw:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Renderowanie SVGZ do HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Krok 2: Renderowanie SVGZ do JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Krok 3: Renderowanie SVGZ do PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Krok 4: Renderowanie SVGZ do PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Wniosek
W tym samouczku nauczyliśmy się, jak renderować obrazy SVG i SVGZ za pomocą GroupDocs.Viewer dla .NET. Za pomocą kilku prostych kroków możesz przekonwertować obrazy SVGZ do różnych formatów wyjściowych, takich jak HTML, JPG, PNG i PDF, dzięki czemu będą dostępne i możliwe do przeglądania w różnych środowiskach.
## Najczęściej zadawane pytania
### Czy GroupDocs.Viewer może renderować inne formaty obrazów?
Tak, GroupDocs.Viewer obsługuje renderowanie różnych formatów obrazów, w tym PNG, JPEG, BMP, TIFF, GIF i innych.
### Czy GroupDocs.Viewer jest kompatybilny z .NET Core?
Tak, GroupDocs.Viewer jest kompatybilny zarówno z .NET Framework, jak i .NET Core.
### Czy mogę dostosować opcje renderowania?
Tak, GroupDocs.Viewer oferuje rozbudowane opcje renderowania, pozwalające dostosować dane wyjściowe do własnych wymagań.
### Czy GroupDocs.Viewer wymaga jakichkolwiek zależności od systemów innych firm?
Nie, GroupDocs.Viewer jest samodzielnym interfejsem API i nie wymaga żadnych zależności od rozwiązań innych firm w celu renderowania dokumentów.
### Czy jest dostępna wersja próbna do przetestowania?
Tak, możesz pobrać bezpłatną wersję próbną GroupDocs.Viewer ze strony [Tutaj](https://releases.groupdocs.com/) aby ocenić jego cechy przed dokonaniem zakupu.