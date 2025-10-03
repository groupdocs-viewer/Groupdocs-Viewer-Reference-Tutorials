---
"description": "Poznaj moc Groupdocs.Viewer dla .NET w bezproblemowym renderowaniu plików Numbers. Konwertuj do HTML, JPG, PNG i PDF bez wysiłku."
"linktitle": "Renderowanie liczb"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderowanie liczb"
"url": "/pl/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
type: docs
---
# Renderowanie liczb

## Wstęp
Witamy w tym samouczku krok po kroku dotyczącym renderowania plików Numbers przy użyciu Groupdocs.Viewer dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy początkującym, ten przewodnik przeprowadzi Cię przez proces konwersji dokumentów Numbers do różnych formatów. Groupdocs.Viewer dla .NET to potężne narzędzie, które umożliwia bezproblemową integrację możliwości przeglądania dokumentów z aplikacjami .NET.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
- Praktyczna znajomość programowania w językach C# i .NET.
- Zainstalowano bibliotekę Groupdocs.Viewer dla .NET. Można ją pobrać [Tutaj](https://releases.groupdocs.com/viewer/net/).
- Ścieżka katalogu dokumentów, w którym zostaną zapisane pliki wyjściowe.
## Importuj przestrzenie nazw
W swoim projekcie C# upewnij się, że zaimportowałeś niezbędne przestrzenie nazw, aby móc korzystać z biblioteki Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Skonfiguruj katalog wyjściowy
Przed rozpoczęciem renderowania zdefiniuj katalog wyjściowy, w którym zostaną zapisane przekonwertowane pliki. Zastąp „Twój katalog dokumentów” rzeczywistą ścieżką:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Renderowanie do wielostronicowego kodu HTML
Użyj poniższego kodu, aby przekonwertować plik Numbers na wielostronicowy kod HTML:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 3: Renderowanie do JPG
Przekonwertuj plik Numbers do formatu JPG za pomocą następującego kodu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 4: Renderowanie do PNG
Przekształć plik Numbers do formatu PNG, korzystając z następującego kodu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 5: Renderowanie do PDF
Na koniec przekonwertuj plik Numbers do formatu PDF, korzystając z następującego kodu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Gratulacje! Udało Ci się pomyślnie renderować pliki Numbers do różnych formatów przy użyciu Groupdocs.Viewer dla .NET.
## Wniosek
tym samouczku omówiliśmy podstawy renderowania plików Numbers przy użyciu Groupdocs.Viewer dla .NET. Ta potężna biblioteka zapewnia bezproblemową integrację w celu przeglądania i konwertowania dokumentów w aplikacjach .NET.
## Często zadawane pytania
### Czy mogę używać Groupdocs.Viewer dla .NET z innymi typami dokumentów?
Tak, Groupdocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym Word, Excel, PDF i inne.
### Czy dostępna jest tymczasowa licencja do celów testowych?
Tak, możesz uzyskać tymczasową licencję [Tutaj](https://purchase.groupdocs.com/temporary-license/) do testowania.
### Gdzie mogę znaleźć pomoc techniczną dotyczącą Groupdocs.Viewer dla platformy .NET?
Odwiedź [Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) w celu uzyskania pomocy i dyskusji.
### Jak mogę zakupić pełną wersję Groupdocs.Viewer dla platformy .NET?
Możesz kupić pełną wersję [Tutaj](https://purchase.groupdocs.com/buy).
### Czy jest dostępna bezpłatna wersja próbna?
Tak, możesz zapoznać się z bezpłatną wersją próbną [Tutaj](https://releases.groupdocs.com/).