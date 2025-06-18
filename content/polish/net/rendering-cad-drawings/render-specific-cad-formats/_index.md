---
"description": "Dowiedz się, jak renderować określone formaty CAD, takie jak CF2 do HTML, JPG, PNG i PDF przy użyciu Groupdocs.Viewer dla .NET."
"linktitle": "Renderuj określone formaty CAD (CF2)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj określone formaty CAD (CF2)"
"url": "/pl/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Renderuj określone formaty CAD (CF2)

## Wstęp
W tym samouczku pokażemy, jak renderować określone formaty CAD za pomocą Groupdocs.Viewer dla .NET. Groupdocs.Viewer to potężny interfejs API przeglądarki dokumentów, który umożliwia deweloperom wyświetlanie ponad 170 typów dokumentów w ich aplikacjach bez konieczności instalowania zewnętrznego oprogramowania. Skupimy się konkretnie na renderowaniu formatów CAD, takich jak CF2, do różnych formatów wyjściowych, takich jak HTML, JPG, PNG i PDF.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Program Visual Studio zainstalowany w systemie.
- Groupdocs.Viewer dla .NET SDK. Możesz pobrać go z [Tutaj](https://releases.groupdocs.com/viewer/net/).
- Podstawowa znajomość języka programowania C#.
## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw wymagane do renderowania formatów CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Teraz rozbijmy każdy przykład na kilka kroków:
## Renderuj CF2 do HTML
### Krok 1: Zdefiniuj katalog wyjściowy, w którym zostanie zapisany wyrenderowany kod HTML.
```csharp
string outputDirectory = "Your Document Directory";
```
### Krok 2: Zdefiniuj format ścieżki pliku dla wyniku HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Krok 3: Zainicjuj obiekt Viewer i określ plik wejściowy CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // W razie potrzeby ustaw dodatkowe opcje renderowania
    // opcje.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderuj CF2 do JPG
### Krok 1: Zdefiniuj format ścieżki pliku dla pliku wyjściowego JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Krok 2: Zainicjuj obiekt Viewer i określ plik wejściowy CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // W razie potrzeby ustaw dodatkowe opcje renderowania
    // opcje.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderuj CF2 do PNG

### Krok 1: Zdefiniuj format ścieżki pliku dla wyjściowego pliku PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Krok 2: Zainicjuj obiekt Viewer i określ plik wejściowy CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // W razie potrzeby ustaw dodatkowe opcje renderowania
    // opcje.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderuj CF2 do PDF
### Krok 1: Zdefiniuj format ścieżki pliku dla pliku wyjściowego PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Krok 2: Zainicjuj obiekt Viewer i określ plik wejściowy CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // W razie potrzeby ustaw dodatkowe opcje renderowania
    // opcje.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Wniosek
W tym samouczku nauczyliśmy się, jak renderować określone formaty CAD, takie jak CF2, przy użyciu Groupdocs.Viewer dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz łatwo zintegrować możliwości renderowania dokumentów z aplikacjami .NET.
## Najczęściej zadawane pytania
### Czy Groupdocs.Viewer może renderować inne formaty CAD niż CF2?
Tak, Groupdocs.Viewer obsługuje szeroką gamę formatów CAD, w tym DWG, DXF, DGN i inne.
### Czy Groupdocs.Viewer nadaje się do renderowania dokumentów w aplikacjach internetowych?
Oczywiście, Groupdocs.Viewer można bezproblemowo zintegrować z aplikacjami internetowymi w celu renderowania dokumentów bezpośrednio w przeglądarce.
### Czy Groupdocs.Viewer wymaga jakichkolwiek zewnętrznych zależności do renderowania?
Nie, Groupdocs.Viewer jest samodzielnym interfejsem API i nie wymaga żadnych zewnętrznych zależności ani instalacji oprogramowania.
### Czy mogę dostosować opcje renderowania do moich wymagań?
Tak, Groupdocs.Viewer oferuje różne opcje renderowania, które można dostosować do swoich konkretnych potrzeb.
### Czy jest dostępna wersja próbna Groupdocs.Viewer?
Tak, możesz uzyskać bezpłatną wersję próbną Groupdocs.Viewer na stronie: [Tutaj](https://releases.groupdocs.com/).