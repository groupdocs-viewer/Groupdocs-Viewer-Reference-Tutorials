---
"description": "Dowiedz się, jak renderować pojedynczy układ w rysunkach CAD za pomocą GroupDocs.Viewer dla .NET. Proste kroki dla bezproblemowej integracji w aplikacjach .NET."
"linktitle": "Renderuj pojedynczy układ na rysunkach CAD"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj pojedynczy układ na rysunkach CAD"
"url": "/pl/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# Renderuj pojedynczy układ na rysunkach CAD

## Wstęp
W obszarze rozwoju .NET obsługa i przeglądanie rysunków CAD jest powszechnym wymogiem. GroupDocs.Viewer dla .NET upraszcza to zadanie, zapewniając kompleksowe rozwiązanie do renderowania rysunków CAD w aplikacjach .NET. W tym samouczku zagłębimy się w renderowanie pojedynczego układu w rysunkach CAD przy użyciu GroupDocs.Viewer dla .NET.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania C# i platformy .NET.
- Program Visual Studio zainstalowany w systemie.
- Biblioteka GroupDocs.Viewer dla .NET pobrana i tutorialsd w Twoim projekcie. Możesz ją pobrać z [Tutaj](https://releases.groupdocs.com/viewer/net/).
- Znajomość formatów plików CAD i ich struktury.

## Importuj przestrzenie nazw
Najpierw zaimportuj niezbędne przestrzenie nazw do kodu C#, aby uzyskać dostęp do funkcjonalności GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Zdefiniuj katalog wyjściowy
Określ katalog, w którym chcesz zapisać wyrenderowane dane wyjściowe.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
Zdefiniuj format ścieżki pliku każdej renderowanej strony.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Utwórz obiekt Viewer
Utwórz instancję klasy Viewer dostarczonej przez GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Krok 4: Skonfiguruj opcje widoku HTML
Konfiguruj opcje renderowania wyników HTML z osadzonymi zasobami.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Określ nazwę układu CAD
Podaj nazwę układu CAD, który chcesz wyrenderować.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Krok 6: Renderowanie rysunku CAD
Wywołaj metodę View obiektu Viewer z określonymi opcjami.
```csharp
viewer.View(options);
```
## Krok 7: Wyświetl komunikat o powodzeniu
Poinformuj użytkownika o pomyślnym wyrenderowaniu dokumentu źródłowego.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Renderowanie rysunków CAD, zwłaszcza w przypadku układów, może być trudnym zadaniem. Jednak dzięki GroupDocs.Viewer dla .NET proces ten staje się płynny i wydajny. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz bez wysiłku renderować pojedynczy układ w rysunkach CAD w swoich aplikacjach .NET.
## Najczęściej zadawane pytania
### Czy mogę renderować wiele układów jednocześnie, używając GroupDocs.Viewer dla .NET?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie wielu układów na podstawie rysunków CAD.
### Czy GroupDocs.Viewer jest kompatybilny z różnymi formatami plików CAD?
Oczywiście, GroupDocs.Viewer obsługuje szeroką gamę formatów plików CAD, w tym DWG, DXF, DGN i inne.
### Czy mogę dostosować opcje renderowania rysunków CAD?
Tak, GroupDocs.Viewer oferuje rozbudowane opcje dostosowywania ustawień renderowania zgodnie z Twoimi wymaganiami.
### Czy jest dostępna bezpłatna wersja próbna GroupDocs.Viewer dla .NET?
Tak, możesz zapoznać się z funkcjami GroupDocs.Viewer dzięki dostępnej bezpłatnej wersji próbnej [Tutaj](https://releases.groupdocs.com/).
### Gdzie mogę uzyskać pomoc techniczną dotyczącą GroupDocs.Viewer dla .NET?
W przypadku pytań lub potrzeby pomocy możesz odwiedzić forum GroupDocs.Viewer [Tutaj](https://forum.groupdocs.com/c/viewer/9).