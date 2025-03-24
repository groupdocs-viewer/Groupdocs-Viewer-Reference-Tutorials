---
title: Renderuj pojedynczy układ na rysunkach CAD
linktitle: Renderuj pojedynczy układ na rysunkach CAD
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować pojedynczy układ na rysunkach CAD przy użyciu GroupDocs.Viewer dla .NET. Proste kroki umożliwiające bezproblemową integrację z aplikacjami .NET.
weight: 14
url: /pl/net/rendering-cad-drawings/render-single-layout-cad/
---

# Renderuj pojedynczy układ na rysunkach CAD

## Wstęp
dziedzinie programowania .NET obsługa i przeglądanie rysunków CAD jest powszechnym wymaganiem. GroupDocs.Viewer dla .NET upraszcza to zadanie, zapewniając kompleksowe rozwiązanie do renderowania rysunków CAD w aplikacjach .NET. W tym samouczku zajmiemy się renderowaniem pojedynczego układu na rysunkach CAD przy użyciu GroupDocs.Viewer dla .NET.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania C# i frameworku .NET.
- Program Visual Studio zainstalowany w systemie.
-  Biblioteka GroupDocs.Viewer dla .NET pobrana i do której odwołuje się Twój projekt. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).
- Znajomość formatów plików CAD i ich struktur.

## Importuj przestrzenie nazw
Najpierw zaimportuj niezbędne przestrzenie nazw do kodu C#, aby uzyskać dostęp do funkcjonalności GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Zdefiniuj katalog wyjściowy
Określ katalog, w którym chcesz zapisać renderowane dane wyjściowe.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj format ścieżki pliku strony
Zdefiniuj format ścieżki pliku każdej renderowanej strony.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Utwórz instancję obiektu przeglądarki
Utwórz instancję klasy Viewer udostępnioną przez GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Krok 4: Skonfiguruj opcje widoku HTML
Skonfiguruj opcje renderowania danych wyjściowych HTML z osadzonymi zasobami.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Krok 5: Określ nazwę układu CAD
Określ nazwę układu CAD, który chcesz renderować.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Krok 6: Renderuj rysunek CAD
Wywołaj metodę View obiektu Viewer z określonymi opcjami.
```csharp
viewer.View(options);
```
## Krok 7: Wyświetl komunikat o powodzeniu
Poinformuj użytkownika o pomyślnym wygenerowaniu dokumentu źródłowego.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Renderowanie rysunków CAD, szczególnie w przypadku układów, może być trudnym zadaniem. Jednak dzięki GroupDocs.Viewer dla .NET proces ten staje się płynny i wydajny. Wykonując kroki opisane w tym samouczku, możesz bez wysiłku renderować pojedynczy układ na rysunkach CAD w aplikacjach .NET.
## Często zadawane pytania
### Czy mogę renderować wiele układów jednocześnie za pomocą GroupDocs.Viewer dla .NET?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie wielu układów z rysunków CAD.
### Czy GroupDocs.Viewer jest kompatybilny z różnymi formatami plików CAD?
Oczywiście GroupDocs.Viewer obsługuje szeroką gamę formatów plików CAD, w tym DWG, DXF, DGN i inne.
### Czy mogę dostosować opcje renderowania rysunków CAD?
Tak, GroupDocs.Viewer udostępnia rozbudowane opcje dostosowywania ustawień renderowania zgodnie z własnymi wymaganiami.
### Czy dostępna jest bezpłatna wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz poznać funkcje GroupDocs.Viewer w ramach bezpłatnej wersji próbnej[Tutaj](https://releases.groupdocs.com/).
### Gdzie mogę uzyskać pomoc dotyczącą GroupDocs.Viewer dla platformy .NET?
 W razie jakichkolwiek pytań lub pomocy możesz odwiedzić forum GroupDocs.Viewer[Tutaj](https://forum.groupdocs.com/c/viewer/9).