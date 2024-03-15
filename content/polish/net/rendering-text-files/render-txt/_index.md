---
title: Renderuj pliki tekstowe (.txt)
linktitle: Renderuj pliki tekstowe (.txt)
second_title: GroupDocs.Viewer API .NET
description: Poznaj bezproblemową konwersję plików tekstowych na wiele formatów za pomocą GroupDocs.Viewer dla .NET. Bez wysiłku zwiększ swoje możliwości zarządzania dokumentami.
type: docs
weight: 10
url: /pl/net/rendering-text-files/render-txt/
---
## Wstęp
dziedzinie zarządzania dokumentami i manipulacji nimi GroupDocs.Viewer dla .NET okazuje się potężnym narzędziem, oferującym mnóstwo funkcji do wydajnego renderowania różnych formatów dokumentów. W tym artykule opisano zawiłości korzystania z programu GroupDocs.Viewer dla platformy .NET w celu renderowania plików tekstowych (.txt) do wielu formatów. Niezależnie od tego, czy chcesz konwertować pliki tekstowe do formatu HTML, JPG, PNG czy PDF, GroupDocs.Viewer zapewnia narzędzia niezbędne do bezproblemowej realizacji tych zadań.
## Warunki wstępne
Przed przystąpieniem do procesu konwersji upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Instalacja GroupDocs.Viewer dla .NET
 Upewnij się, że w środowisku programistycznym zainstalowano GroupDocs.Viewer for .NET. Niezbędne pliki można pobrać ze strony[strona internetowa](https://releases.groupdocs.com/viewer/net/).
### 2. Podstawowa znajomość .NET Framework
Zapoznaj się z podstawami platformy .NET, w tym z konfiguracją projektu i wykorzystaniem bibliotek w bazie kodu.
### 3. Przykładowe pliki tekstowe
Przygotuj przykładowe pliki tekstowe (.txt), które zamierzasz przekonwertować. Pliki te będą służyć jako dane wejściowe w procesie konwersji.

## Importuj przestrzenie nazw
Zanim przystąpisz do procesu konwersji, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw do swojego projektu. Umożliwia to bezproblemowy dostęp do funkcjonalności udostępnianych przez GroupDocs.Viewer dla platformy .NET.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Podzielmy każdy przykład na wiele kroków, aby skutecznie przeprowadzić Cię przez proces konwersji:

## Krok 1: Zdefiniuj ścieżkę wyjściową HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
Określ pełną ścieżkę pliku wyjściowego HTML.
## Krok 2: Renderuj pliki tekstowe do wielostronicowego kodu HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 Utwórz instancję a`Viewer` obiekt ze ścieżką do pliku tekstowego. Skonfiguruj`HtmlViewOptions` dla zasobów osadzonych i renderuje plik tekstowy do wielostronicowego kodu HTML.
## Krok 3: Zdefiniuj jednostronicową ścieżkę wyjściową HTML
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Określ pełną ścieżkę jednostronicowego pliku wyjściowego HTML.
## Krok 4: Renderuj pliki tekstowe do jednostronicowego kodu HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 Utwórz instancję a`Viewer` obiekt ze ścieżką do pliku tekstowego. Skonfiguruj`HtmlViewOptions` dla zasobów osadzonych i set`RenderToSinglePage` do prawdy. Renderuj plik tekstowy do jednostronicowego kodu HTML.
## Krok 5: Zdefiniuj ścieżkę wyjściową JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
Określ pełną ścieżkę pliku wyjściowego JPG.
## Krok 6: Renderuj pliki tekstowe do formatu JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Utwórz instancję a`Viewer` obiekt ze ścieżką do pliku tekstowego. Skonfiguruj`JpgViewOptions` dla ścieżki wyjściowej i wyrenderuj plik tekstowy do formatu JPG.
## Krok 7: Zdefiniuj ścieżkę wyjściową PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
Określ pełną ścieżkę pliku wyjściowego PNG.
## Krok 8: Renderuj pliki tekstowe do formatu PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Utwórz instancję a`Viewer` obiekt ze ścieżką do pliku tekstowego. Skonfiguruj`PngViewOptions` dla ścieżki wyjściowej i renderuj plik tekstowy do formatu PNG.
## Krok 9: Zdefiniuj ścieżkę wyjściową pliku PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Określ pełną ścieżkę pliku wyjściowego PDF.
## Krok 10: Renderuj pliki tekstowe do formatu PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Utwórz instancję a`Viewer` obiekt ze ścieżką do pliku tekstowego. Skonfiguruj`PdfViewOptions` dla ścieżki wyjściowej i renderuj plik tekstowy do formatu PDF.

## Wniosek
Podsumowując, GroupDocs.Viewer dla .NET umożliwia programistom bezproblemowe renderowanie plików tekstowych do różnych formatów, w tym HTML, JPG, PNG i PDF. Postępując zgodnie ze szczegółowym przewodnikiem opisanym w tym artykule, możesz bezproblemowo zintegrować GroupDocs.Viewer z aplikacjami .NET, zwiększając możliwości zarządzania dokumentami.
## Często zadawane pytania
### P: Czy GroupDocs.Viewer dla .NET jest kompatybilny ze wszystkimi wersjami platformy .NET?
Tak, GroupDocs.Viewer dla .NET został zaprojektowany tak, aby był kompatybilny z szeroką gamą wersji platformy .NET, zapewniając wszechstronność i elastyczność programowania.
### P: Czy mogę dostosować wygląd wyjściowy renderowanych dokumentów?
Absolutnie! GroupDocs.Viewer oferuje szerokie opcje dostosowywania, umożliwiając programistom dostosowanie wyglądu renderowanych dokumentów do ich preferencji i wymagań.
### P: Czy dostępna jest wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz poznać funkcje GroupDocs.Viewer dla .NET, korzystając z bezpłatnej wersji próbnej dostępnej na stronie[strona internetowa]( https://releases.groupdocs.com/).
### P: Jak mogę uzyskać pomoc lub poprosić o pomoc dotyczącą GroupDocs.Viewer dla .NET?
 W przypadku jakichkolwiek pytań, wsparcia lub pomocy dotyczącej programu GroupDocs.Viewer dla .NET można odwiedzić dedykowane forum pomocy dostępne[Tutaj](https://forum.groupdocs.com/c/viewer/9).
### P: Czy mogę kupić tymczasową licencję na GroupDocs.Viewer dla .NET?
Tak, można kupić licencje tymczasowe, zapewniające użytkownikom elastyczność i wygodę w korzystaniu z GroupDocs.Viewer dla .NET przez określony czas.