---
title: Renderuj figury programu Visio
linktitle: Renderuj figury programu Visio
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować figury programu Visio przy użyciu programu GroupDocs.Viewer dla platformy .NET, korzystając z tego wszechstronnego narzędzia. Zwiększ możliwości przeglądania dokumentów w aplikacjach .NET.
weight: 10
url: /pl/net/rendering-visio-documents/render-visio-figures/
---
## Wstęp
W dzisiejszej erze cyfrowej renderowanie dokumentów odgrywa kluczową rolę w różnych zastosowaniach. Niezależnie od tego, czy chodzi o wyświetlanie dokumentów w witrynie internetowej, czy konwertowanie ich do różnych formatów, wydajne renderowanie jest niezbędne. GroupDocs.Viewer dla .NET zapewnia solidne rozwiązanie do przeglądania i manipulowania dokumentami w aplikacjach .NET. W tym samouczku zajmiemy się renderowaniem figur programu Visio przy użyciu programu GroupDocs.Viewer dla platformy .NET, dzieląc proces na proste kroki.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1. Konfiguracja środowiska: Upewnij się, że masz środowisko robocze do programowania .NET.
2.  GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z[link do pobrania](https://releases.groupdocs.com/viewer/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.
4. Przykładowy dokument Visio: Przygotuj przykładowy dokument Visio do renderowania.

## Importuj przestrzenie nazw
W projekcie C# zacznij od zaimportowania niezbędnych przestrzeni nazw:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Renderowanie do HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Katalog wyjściowy: Zdefiniuj katalog, w którym zostanie zapisany wyrenderowany kod HTML.
- Format ścieżki pliku strony: Określ format ścieżki dla strony HTML.
- Inicjalizacja przeglądarki: Zainicjuj obiekt przeglądarki ścieżką do dokumentu Visio.
- Opcje widoku HTML: skonfiguruj opcje renderowania HTML.
- Opcje renderowania programu Visio: Ustaw opcje specyficzne dla renderowania programu Visio, takie jak renderowanie tylko figur i szerokość figur.
## 2. Renderowanie do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Podobnie jak w przypadku renderowania do formatu HTML, skonfiguruj opcje renderowania do formatu JPG.
## 3. Renderowanie do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Konfiguracja renderowania do formatu PNG przebiega według podobnego wzorca jak renderowanie JPG.
## 4. Renderowanie do formatu PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Aby renderować do formatu PDF, skonfiguruj opcje specyficzne dla formatu PDF.

## Wniosek
W tym samouczku omówiliśmy sposób renderowania figur programu Visio przy użyciu narzędzia GroupDocs.Viewer dla platformy .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz bezproblemowo zintegrować możliwości renderowania dokumentów z aplikacjami .NET, zwiększając komfort użytkownika i produktywność.
## Często zadawane pytania
### Czy mogę dostosować opcje renderowania figurek programu Visio?
Tak, GroupDocs.Viewer dla .NET udostępnia rozbudowane opcje dostosowywania renderowania, w tym szerokość figury, renderowanie samych figur i nie tylko.
### Czy GroupDocs.Viewer dla .NET nadaje się do renderowania dokumentów na dużą skalę?
Oczywiście GroupDocs.Viewer dla .NET jest zoptymalizowany pod kątem wydajnej obsługi renderowania dokumentów na dużą skalę.
### Czy GroupDocs.Viewer obsługuje inne formaty dokumentów oprócz Visio?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, Microsoft Office, AutoCAD i inne.
### Czy mogę zintegrować GroupDocs.Viewer z aplikacjami internetowymi?
Tak, GroupDocs.Viewer można bezproblemowo zintegrować z aplikacjami internetowymi w celu przeglądania i manipulowania dokumentami.
### Czy dostępna jest wersja próbna do przetestowania przed zakupem?
Tak, możesz skorzystać z bezpłatnego okresu próbnego w witrynie[strona internetowa](https://releases.groupdocs.com/) aby przetestować możliwości GroupDocs.Viewer dla .NET.